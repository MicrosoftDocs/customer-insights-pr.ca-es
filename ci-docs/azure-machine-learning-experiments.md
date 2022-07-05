---
title: Utilitzar models basats en l'aprenentatge automàtic de l'Azure
description: Utilitzeu els models basats en l'aprenentatge automàtic de l'Azure al Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a1efad2887a02a92ee2960b07b066edc331f3665
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082276"
---
# <a name="use-azure-machine-learning-based-models"></a>Utilitzar models basats en l'aprenentatge automàtic de l'Azure

Les dades unificades del Dynamics 365 Customer Insights constitueixen un origen per a la creació de models d'aprenentatge automàtic que puguin generar informació addicional de negoci. El Customer Insights s'integra amb l'Azure Machine Learning per utilitzar els vostres propis models personalitzats.

## <a name="prerequisites"></a>Requisits previs

- Accés al Customer Insights
- Subscripció a l'Azure Enterprise activa
- [Perfils de client unificats](data-unification.md)
- [Exportació d'entitats a l'emmagatzematge blob de l'Azure](export-azure-blob-storage.md) configurada

## <a name="set-up-azure-machine-learning-workspace"></a>Configurar l’àrea de treball de l'aprenentatge automàtic de l’Azure

1. Vegeu [crear una àrea de treball de l'aprenentatge automàtic de l'Azure](/azure/machine-learning/concept-workspace#-create-a-workspace) per conèixer les diferents opcions de creació de l'àrea de treball. Per obtenir el millor rendiment, creeu l'espai de treball en una regió de l'Azure que sigui geogràficament més propera a l'entorn del Customer Insights.

1. Accediu al vostre espai de treball a través de l'[Azure Machine Learning Studio](https://ml.azure.com/). Hi ha diverses [maneres d'interactuar](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) amb el vostre espai de treball.

## <a name="work-with-azure-machine-learning-designer"></a>Treballar amb el dissenyador de l'aprenentatge automàtic de l'Azure

El dissenyador de Aprenentatge automàtic De l'Azure proporciona un llenç visual on podeu arrossegar i deixar anar conjunts de dades i mòduls. És possible integrar un pipeline per lots creat des del dissenyador en el Customer Insights si es configuren de manera corresponent. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Treballar amb l'SDK de l'aprenentatge automàtic de l'Azure

Els científics de dades i els desenvolupadors d'IA utilitzen el [SDK de l'aprenentatge automàtic de l'Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) per crear fluxos de treball d'aprenentatge automàtic. Actualment, els models formats amb l'SDK no es poden integrar directament amb el Customer Insights. Per a la integració amb el Customer Insights, caldrà un pipeline d'inferència de lots que consumeixi aquest model.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Requisits del pipeline per lots per a la integració amb Customer Insights

### <a name="dataset-configuration"></a>Configuració dels conjunts de dades

Per poder utilitzar dades d'entitats del Customer Insights per al vostre pipeline d'inferència per lots, heu de crear conjunts de dades. Aquests conjunts de dades s'han de registrar a l'àrea de treball. Actualment, només s'admeten [conjunts de dades tabulars](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) en format .csv. Els conjunts de dades que corresponen a dades d'entitats s'han de configurar com a un paràmetre del pipeline.
   
* Paràmetres de conjunts de dades del dissenyador
   
     Al dissenyador, obriu **Selecciona les columnes del conjunt de dades** i seleccioneu **Defineix com a paràmetre del pipeline** per indicar un nom per al paràmetre.

     > [!div class="mx-imgBorder"]
     > ![Parametrització de conjunts de dades del dissenyador.](media/intelligence-designer-dataset-parameters.png "Parametrització de conjunts de dades del dissenyador")
   
* Paràmetre del conjunt de dades a l'SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Pipeline d'inferència per lots
  
* Al dissenyador, podeu utilitzar un pipeline d'entrenament per crear o actualitzar un pipeline d'inferència. Actualment, només s'admeten pipelines d'inferència per lots.

* Amb l'SDK, podeu publicar el pipeline en un extrem. Actualment, el Customer Insights s'integra amb el pipeline per defecte d'un extrem de pipeline per lots a l'àrea de treball de l'aprenentatge automàtic.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importar les dades del pipeline al Customer Insights

* El dissenyador proporciona el [mòdul de dades ](/azure/machine-learning/algorithm-module-reference/export-data)d'exportació que permet exportar la sortida d'un pipeline a l'Azure Storage. Actualment, el mòdul ha d'utilitzar el tipus de magatzem de dades **Emmagatzematge blob de l’Azure** i parametritzar el **Magatzem de dades** i el **Camí** relatiu. El Customer Insights substitueix aquests dos paràmetres durant l'execució del pipeline per un magatzem de dades i un camí accessible per al producte.
   > [!div class="mx-imgBorder"]
   > ![Exportar la configuració de mòduls de dades.](media/intelligence-designer-importdata.png "Exportar la configuració de mòduls de dades")
   
* Quan escriviu la sortida d'inferència mitjançant codi, podreu pujar la sortida a un camí dins d'un *magatzem de dades registrat* a l'àrea de treball. Si el camí i el magatzem de dades es parametritzen al pipeline, el Customer Insights podrà llegir i importar la sortida d'inferència. Actualment s'admet una única sortida tabular en format csv. El camí ha d'incloure el directori i el nom del fitxer.

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE [footer-include](includes/footer-banner.md)]