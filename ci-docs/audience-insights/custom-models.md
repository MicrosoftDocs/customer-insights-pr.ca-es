---
title: Models d'aprenentatge automàtic personalitzats | Microsoft Docs
description: Treballeu amb models personalitzats de l'Aprenentatge automàtic de l'Azure al Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668891"
---
# <a name="custom-machine-learning-models"></a>Models d'aprenentatge automàtic personalitzats

**Intel·ligència** > **Models personalitzats** us permet administrar fluxos de treball basats en models de l'aprenentatge automàtic de l'Azure. Els fluxos de treball us ajuden a triar les dades a partir de les quals voleu generar conclusions i assignar els resultats a les dades unificades del client. Per obtenir més informació sobre la creació de models de ML personalitzats, vegeu [Utilitzar models basats en l'aprenentatge automàtic de l'Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsable

Les prediccions ofereixen capacitats per crear experiències dels clients més positives, i millorar les capacitats empresarials i les fonts d'ingressos. Us recomanem que feu un balanç del valor de la vostra predicció davant el seu impacte i les desviacions que es podrien introduir d'una manera ètica. Informeu-vos sobre com Microsoft està [responent a la qüestió d'una IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Informeu-vos també sobre [les tècniques i els processos per a un aprenentatge automàtic responsable](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) específics de l'aprenentatge automàtic de l'Azure.

## <a name="prerequisites"></a>Requisits previs

- Actualment, aquesta característica admet serveis web publicats mitjançant el [Machine Learning Studio (clàssic)](https://studio.azureml.net) i els [pipelines per lots de l'aprenentatge automàtic de l'Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Per poder utilitzar aquesta característica, heu de tenir un compte d'emmagatzematge Gen2 de l'Azure Data Lake associat amb la vostra instància de l'Azure Studio. Per obtenir més informació, vegeu [Crear un compte d'emmagatzematge de l'Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Afegir un flux de treball nou

1. Aneu a **Intel·ligència** > **Models personalitzats** i seleccioneu **Flux de treball nou**.

1. Doneu al model personalitzat un nom que pugueu reconèixer al camp **Nom**.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la subfinestra Flux de treball nou](media/new-workflowv2.png "Captura de pantalla de la subfinestra Flux de treball nou")

1. Seleccioneu l'organització que conté el servei web a **Inquilí que conté el servei web**.

1. Si la subscripció a l'Azure Machine Learning és en un inquilí diferent del Customer Insights, seleccioneu **Inicia la sessió** amb les credencials de l'organització seleccionada.

1. Seleccioneu els **Espais de treball** associats amb el servei web. Hi ha dues seccions, una per a l'Aprenentatge automàtic de l'Azure v1 (Machine Learning Studio [clàssic]) i una altra per a l'aprenentatge automàtic de l'Azure v2 (Aprenentatge automàtic de l'Azure). Si no esteu segur de quin àrea de treball és la correcta per al servei web del Machine Learning Studio (clàssic), seleccioneu **Qualsevol**.

1. Trieu el servei web del Machine Learning Studio (clàssic) o el pipeline de l'aprenentatge automàtic de l'Azure en el menú desplegable del **Servei web que conté el vostre model**. A continuació, seleccioneu **Següent**.
   - Més informació sobre la [publicació d'un servei web al Machine Learning Studio (clàssic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Més informació sobre [la publicació d'un pipeline a l'aprenentatge automàtic de l'Azure mitjançant el dissenyador](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) o l'[SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > El pipeline s'ha de publicar en un [extrem de pipeline](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Per a cada **Entrada del servei web**, seleccioneu l'**Entitat** coincident de les conclusions del públic i seleccioneu **Següent**.

   > [!div class="mx-imgBorder"]
   > ![Configurar un flux de treball](media/intelligence-screen2-updated.png "Configurar un flux de treball")

1. Al pas de **Paràmetres de sortida del model**, definiu les propietats següents:
   - Machine Learning Studio (clàssic)
      1. Introduïu el **Nom de l'entitat** de sortida a la qual voleu que vagin a parar els resultats de sortida del servei web.
   - Aprenentatge automàtic de l’Azure
      1. Introduïu el **Nom de l'entitat** de sortida a la qual voleu que vagin a parar els resultats de sortida del pipeline.
      1. Seleccioneu, al menú desplegable, el **Nom del paràmetre de magatzem de dades de sortida** del pipeline per lots.
      1. Seleccioneu, al menú desplegable, el **Nom del paràmetre de camí de sortida** del pipeline per lots.
      
      > [!div class="mx-imgBorder"]
      > ![Subfinestra Paràmetre de sortida del model](media/intelligence-screen3-outputparameters.png "Subfinestra Paràmetre de sortida del model")

1. Seleccioneu l'atribut coincident de la llista desplegable **Identificador del client als resultats** que identifiqui els clients i seleccioneu **Desa**.
   
   > [!div class="mx-imgBorder"]
   > ![Subfinestra Relacioneu els resultats amb les dades del client](media/intelligence-screen4-relatetocustomer.png "Subfinestra Relacioneu els resultats amb les dades del client")

1. Veureu la pantalla **Flux de treball desat** amb els detalls sobre el flux de treball.    
   Si heu configurat un flux de treball per a un pipeline de l'aprenentatge automàtic de l'Azure, les conclusions del públic s'adjuntaran a l'àrea de treball que conté el pipeline. Les conclusions del públic obtindran una funció de **Col·laborador** a l'àrea de treball de l'Azure.

1. Seleccioneu **Fet**.

1. Ara podeu executar el flux de treball des de la pàgina **Models personalitzats**.

## <a name="edit-a-workflow"></a>Editar un flux de treball

1. A la pàgina **Models personalitzats**, seleccioneu els punts suspensius verticals de la columna **Accions** al costat d'un flux de treball que heu creat anteriorment i seleccioneu **Edita**.

1. Podeu actualitzar el nom reconeixible del flux de treball al camp **Nom de visualització**, però no podreu canviar el servei web o el pipeline configurats. Seleccioneu **Següent**.

1. Per a cada **Entrada del servei web**, podeu actualitzar l'**Entitat** coincident des de les conclusions del públic. A continuació, seleccioneu **Següent**.

1. Al pas de **Paràmetres de sortida del model**, definiu les propietats següents:
   - Machine Learning Studio (clàssic)
      1. Introduïu el **Nom de l'entitat** de sortida a la qual voleu que vagin a parar els resultats de sortida del servei web.
   - Aprenentatge automàtic de l’Azure
      1. Introduïu el **Nom de l'entitat** de sortida a la qual voleu que vagin a parar els resultats de sortida del pipeline.
      1. Seleccioneu el **Nom del paràmetre de magatzem de dades de sortida** per al pipeline de prova.
      1. Seleccioneu el **Nom del paràmetre de camí de sortida** per al pipeline de prova.

1. Seleccioneu l'atribut coincident de la llista desplegable **Identificador del client als resultats** que identifiqui els clients i seleccioneu **Desa**.
   Heu de triar un atribut des de la sortida d'inferència que tingui valors similars a la columna ID de client de l'Entitat del client. Si no teniu una columna d'aquest tipus al vostre conjunt de dades, trieu un atribut que identifiqui de manera exclusiva la fila.

## <a name="run-a-workflow"></a>Executar un flux de treball

1. A la pàgina **Models personalitzats**, seleccioneu els punts suspensius verticals de la columna **Accions** al costat d'un flux de treball que heu creat anteriorment.

1. Seleccioneu **Executa**.

El flux de treball també s'executa automàticament amb cada actualització planificada. Més informació sobre la [configuració d'actualitzacions planificades](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Suprimir un flux de treball

1. A la pàgina **Models personalitzats**, seleccioneu els punts suspensius verticals de la columna **Accions** al costat d'un flux de treball que heu creat anteriorment.

1. Seleccioneu **Suprimeix** i confirmeu la supressió.

El flux de treball se suprimirà. L'[entitat](entities.md) que es va crear quan es va crear el flux de treball persisteix i es pot visualitzar des de la pàgina **Entitats**.
