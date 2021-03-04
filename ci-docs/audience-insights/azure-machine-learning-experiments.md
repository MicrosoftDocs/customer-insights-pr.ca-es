---
title: Experiments de l'aprenentatge automàtic de l'Azure
description: Utilitzeu els models basats en l'aprenentatge automàtic de l'Azure al Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267894"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="801bc-103">Utilitzar models basats en l'aprenentatge automàtic de l'Azure</span><span class="sxs-lookup"><span data-stu-id="801bc-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="801bc-104">Les dades unificades del Dynamics 365 Customer Insights constitueixen un origen per a la creació de models d'aprenentatge automàtic que puguin generar informació addicional de negoci.</span><span class="sxs-lookup"><span data-stu-id="801bc-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="801bc-105">El Customer Insights s'integra amb el Machine Learning Studio (clàssic) i l'aprenentatge automàtic de l'Azure per utilitzar els vostres propis models personalitzats.</span><span class="sxs-lookup"><span data-stu-id="801bc-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="801bc-106">Consulteu [Experiments amb el Machine Learning Studio (clàssic)](machine-learning-studio-experiments.md) per obtenir exemples d'experiments generats al Machine Learning Studio (clàssic).</span><span class="sxs-lookup"><span data-stu-id="801bc-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="801bc-107">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="801bc-107">Prerequisites</span></span>

- <span data-ttu-id="801bc-108">Accés al Customer Insights</span><span class="sxs-lookup"><span data-stu-id="801bc-108">Access to Customer Insights</span></span>
- <span data-ttu-id="801bc-109">Subscripció a l'Azure Enterprise activa</span><span class="sxs-lookup"><span data-stu-id="801bc-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="801bc-110">Perfils de client unificats</span><span class="sxs-lookup"><span data-stu-id="801bc-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="801bc-111">[Exportació d'entitats a l'emmagatzematge blob de l'Azure](export-azure-blob-storage.md) configurada</span><span class="sxs-lookup"><span data-stu-id="801bc-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="801bc-112">Configurar l’àrea de treball de l'aprenentatge automàtic de l’Azure</span><span class="sxs-lookup"><span data-stu-id="801bc-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="801bc-113">Vegeu [crear una àrea de treball de l'aprenentatge automàtic de l'Azure](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) per conèixer les diferents opcions de creació de l'àrea de treball.</span><span class="sxs-lookup"><span data-stu-id="801bc-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="801bc-114">Per obtenir el millor rendiment, creeu l'espai de treball en una regió de l'Azure que sigui geogràficament més propera a l'entorn del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="801bc-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="801bc-115">Accediu al vostre espai de treball a través de l'[Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="801bc-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="801bc-116">Hi ha diverses [maneres d'interactuar](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) amb el vostre espai de treball.</span><span class="sxs-lookup"><span data-stu-id="801bc-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="801bc-117">Treballar amb el dissenyador de l'aprenentatge automàtic de l'Azure</span><span class="sxs-lookup"><span data-stu-id="801bc-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="801bc-118">El dissenyador de l'aprenentatge automàtic de l'Azure proporciona un llenç visual on podeu arrossegar i deixar anar conjunts de dades i mòduls, de manera semblant al Machine Learning Studio (clàssic).</span><span class="sxs-lookup"><span data-stu-id="801bc-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="801bc-119">És possible integrar un pipeline per lots creat des del dissenyador en el Customer Insights si es configuren de manera corresponent.</span><span class="sxs-lookup"><span data-stu-id="801bc-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="801bc-120">Treballar amb l'SDK de l'aprenentatge automàtic de l'Azure</span><span class="sxs-lookup"><span data-stu-id="801bc-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="801bc-121">Els científics de dades i els desenvolupadors d'IA utilitzen el [SDK de l'aprenentatge automàtic de l'Azure](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) per crear fluxos de treball d'aprenentatge automàtic.</span><span class="sxs-lookup"><span data-stu-id="801bc-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="801bc-122">Actualment, els models formats amb l'SDK no es poden integrar directament amb el Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="801bc-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="801bc-123">Per a la integració amb el Customer Insights, caldrà un pipeline d'inferència de lots que consumeixi aquest model.</span><span class="sxs-lookup"><span data-stu-id="801bc-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="801bc-124">Requisits del pipeline per lots per a la integració amb Customer Insights</span><span class="sxs-lookup"><span data-stu-id="801bc-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="801bc-125">Configuració dels conjunts de dades</span><span class="sxs-lookup"><span data-stu-id="801bc-125">Dataset Configuration</span></span>

<span data-ttu-id="801bc-126">Per poder utilitzar dades d'entitats del Customer Insights per al vostre pipeline d'inferència per lots, heu de crear conjunts de dades.</span><span class="sxs-lookup"><span data-stu-id="801bc-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="801bc-127">Aquests conjunts de dades s'han de registrar a l'àrea de treball.</span><span class="sxs-lookup"><span data-stu-id="801bc-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="801bc-128">Actualment, només s'admeten [conjunts de dades tabulars](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) en format .csv.</span><span class="sxs-lookup"><span data-stu-id="801bc-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="801bc-129">Els conjunts de dades que corresponen a dades d'entitats s'han de configurar com a un paràmetre del pipeline.</span><span class="sxs-lookup"><span data-stu-id="801bc-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="801bc-130">Paràmetres de conjunts de dades del dissenyador</span><span class="sxs-lookup"><span data-stu-id="801bc-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="801bc-131">Al dissenyador, obriu **Selecciona les columnes del conjunt de dades** i seleccioneu **Defineix com a paràmetre del pipeline** per indicar un nom per al paràmetre.</span><span class="sxs-lookup"><span data-stu-id="801bc-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="801bc-132">![Parametrització de conjunts de dades del dissenyador](media/intelligence-designer-dataset-parameters.png "Parametrització de conjunts de dades del dissenyador")</span><span class="sxs-lookup"><span data-stu-id="801bc-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="801bc-133">Paràmetre del conjunt de dades a l'SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="801bc-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="801bc-134">Pipeline d'inferència per lots</span><span class="sxs-lookup"><span data-stu-id="801bc-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="801bc-135">Al dissenyador, podeu utilitzar un pipeline d'entrenament per crear o actualitzar un pipeline d'inferència.</span><span class="sxs-lookup"><span data-stu-id="801bc-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="801bc-136">Actualment, només s'admeten pipelines d'inferència per lots.</span><span class="sxs-lookup"><span data-stu-id="801bc-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="801bc-137">Amb l'SDK, podeu publicar el pipeline en un extrem.</span><span class="sxs-lookup"><span data-stu-id="801bc-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="801bc-138">Actualment, el Customer Insights s'integra amb el pipeline per defecte d'un extrem de pipeline per lots a l'àrea de treball de l'aprenentatge automàtic.</span><span class="sxs-lookup"><span data-stu-id="801bc-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="801bc-139">Importar les dades del pipeline al Customer Insights</span><span class="sxs-lookup"><span data-stu-id="801bc-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="801bc-140">El dissenyador proporciona el [mòdul de dades ](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data)d'exportació que permet exportar la sortida d'un pipeline a l'Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="801bc-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="801bc-141">Actualment, el mòdul ha d'utilitzar el tipus de magatzem de dades **Emmagatzematge blob de l’Azure** i parametritzar el **Magatzem de dades** i el **Camí** relatiu.</span><span class="sxs-lookup"><span data-stu-id="801bc-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="801bc-142">El Customer Insights substitueix aquests dos paràmetres durant l'execució del pipeline per un magatzem de dades i un camí accessible per al producte.</span><span class="sxs-lookup"><span data-stu-id="801bc-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="801bc-143">![Exportar la configuració de mòduls de dades](media/intelligence-designer-importdata.png "Exportar la configuració de mòduls de dades")</span><span class="sxs-lookup"><span data-stu-id="801bc-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="801bc-144">Quan escriviu la sortida d'inferència mitjançant codi, podreu pujar la sortida a un camí dins d'un *magatzem de dades registrat* a l'àrea de treball.</span><span class="sxs-lookup"><span data-stu-id="801bc-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="801bc-145">Si el camí i el magatzem de dades es parametritzen al pipeline, el Customer Insights podrà llegir i importar la sortida d'inferència.</span><span class="sxs-lookup"><span data-stu-id="801bc-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="801bc-146">Actualment s'admet una única sortida tabular en format csv.</span><span class="sxs-lookup"><span data-stu-id="801bc-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="801bc-147">El camí ha d'incloure el directori i el nom del fitxer.</span><span class="sxs-lookup"><span data-stu-id="801bc-147">The path must include the directory and filename.</span></span>

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]