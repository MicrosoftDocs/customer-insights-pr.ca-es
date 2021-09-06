---
title: Models d'aprenentatge automàtic personalitzats | Microsoft Docs
description: Treballeu amb models personalitzats de l'Aprenentatge automàtic de l'Azure al Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 187995cdf4d92a0609f8abb4c792e698ad4342cdb1f578744136add1bfcf3a53
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032930"
---
# <a name="custom-machine-learning-models"></a>Models d'aprenentatge automàtic personalitzats

**Intel·ligència** > **Models personalitzats** us permet administrar fluxos de treball basats en models de l'aprenentatge automàtic de l'Azure. Els fluxos de treball us ajuden a triar les dades a partir de les quals voleu generar conclusions i assignar els resultats a les dades unificades del client. Per obtenir més informació sobre la creació de models de ML personalitzats, vegeu [Utilitzar models basats en l'aprenentatge automàtic de l'Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsable

Les prediccions ofereixen capacitats per crear experiències dels clients més positives, i millorar les capacitats empresarials i les fonts d'ingressos. Us recomanem que feu un balanç del valor de la vostra predicció davant el seu impacte i les desviacions que es podrien introduir d'una manera ètica. Informeu-vos sobre com Microsoft està [responent a la qüestió d'una IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Informeu-vos també sobre [les tècniques i els processos per a un aprenentatge automàtic responsable](/azure/machine-learning/concept-responsible-ml) específics de l'aprenentatge automàtic de l'Azure.

## <a name="prerequisites"></a>Requisits previs

- Actualment, aquesta característica admet serveis web publicats mitjançant el [Machine Learning Studio (clàssic)](https://studio.azureml.net) i els [pipelines per lots de l'aprenentatge automàtic de l'Azure](/azure/machine-learning/concept-ml-pipelines).

- Per poder utilitzar aquesta característica, heu de tenir un compte d'emmagatzematge Gen2 de l'Azure Data Lake associat amb la vostra instància de l'Azure Studio. Per obtenir més informació, vegeu [Crear un compte d'emmagatzematge de l'Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Per als espais de treball d'aprenentatge automàtic de l'Azure amb pipelines, necessiteu permisos de Propietari o d'Administrador d'accés d'usuari a l'espai de treball d'aprenentatge automàtic de l'Azure.

   > [!NOTE]
   > Les dades es transfereixen entre les vostres instàncies del Customer Insights i els pipelines o serveis web de l'Azure seleccionats al flux de treball. Quan transferiu dades a un servei de l'Azure, assegureu-vos que el servei estigui configurat per processar les dades de la manera i la ubicació necessàries per complir tots els requisits legals o normatius per a les dades en aquesta organització.

## <a name="add-a-new-workflow"></a>Afegir un flux de treball nou

1. Aneu a **Intel·ligència** > **Models personalitzats** i seleccioneu **Flux de treball nou**.

1. Doneu al model personalitzat un nom que pugueu reconèixer al camp **Nom**.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la subfinestra Flux de treball nou.](media/new-workflowv2.png "Captura de pantalla de la subfinestra Flux de treball nou")

1. Seleccioneu l'organització que conté el servei web a **Inquilí que conté el servei web**.

1. Si la subscripció a l'Azure Machine Learning és en un inquilí diferent del Customer Insights, seleccioneu **Inicia la sessió** amb les credencials de l'organització seleccionada.

1. Seleccioneu els **Espais de treball** associats amb el servei web. Hi ha dues seccions, una per a l'Aprenentatge automàtic de l'Azure v1 (Machine Learning Studio [clàssic]) i una altra per a l'aprenentatge automàtic de l'Azure v2 (Aprenentatge automàtic de l'Azure). Si no esteu segur de quin àrea de treball és la correcta per al servei web del Machine Learning Studio (clàssic), seleccioneu **Qualsevol**.

1. Trieu el servei web del Machine Learning Studio (clàssic) o el pipeline de l'aprenentatge automàtic de l'Azure en el menú desplegable del **Servei web que conté el vostre model**. A continuació, seleccioneu **Següent**.
   - Més informació sobre la [publicació d'un servei web al Machine Learning Studio (clàssic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Més informació sobre [la publicació d'un pipeline a l'aprenentatge automàtic de l'Azure mitjançant el dissenyador](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) o l'[SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). El pipeline s'ha de publicar en un [extrem de pipeline](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Per a cada **Entrada del servei web**, seleccioneu l'**Entitat** coincident de les conclusions del públic i seleccioneu **Següent**.
   > [!NOTE]
   > El flux de treball del model personalitzat aplicarà heurística per assignar els camps d'entrada del servei web als atributs de l'entitat segons el nom i el tipus de dades del camp. Veureu un error si un camp del servei web no es pot assignar a una entitat.

   > [!div class="mx-imgBorder"]
   > ![Configurar un flux de treball.](media/intelligence-screen2-updated.png "Configurar un flux de treball")

1. Al pas de **Paràmetres de sortida del model**, definiu les propietats següents:
   - Machine Learning Studio (clàssic)
      1. Introduïu el **Nom de l'entitat** de sortida a la qual voleu que vagin a parar els resultats de sortida del servei web.
   - Aprenentatge automàtic de l’Azure
      1. Introduïu el **Nom de l'entitat** de sortida a la qual voleu que vagin a parar els resultats de sortida del pipeline.
      1. Seleccioneu, al menú desplegable, el **Nom del paràmetre de magatzem de dades de sortida** del pipeline per lots.
      1. Seleccioneu, al menú desplegable, el **Nom del paràmetre de camí de sortida** del pipeline per lots.

      > [!div class="mx-imgBorder"]
      > ![Subfinestra Paràmetre de sortida del model.](media/intelligence-screen3-outputparameters.png "Subfinestra Paràmetre de sortida del model")

1. Seleccioneu l'atribut coincident de la llista desplegable **Identificador de client als resultats** que identifica els clients i seleccioneu **Desa**.

   > [!div class="mx-imgBorder"]
   > ![Subfinestra Relacioneu els resultats amb les dades del client.](media/intelligence-screen4-relatetocustomer.png "Subfinestra Relacioneu els resultats amb les dades del client")

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

1. Seleccioneu l'atribut coincident de la llista desplegable **Identificador de client als resultats** que identifica els clients i seleccioneu **Desa**.
   Trieu un atribut de la sortida d'inferència que tingui valors similars a la columna ID de client de l'Entitat del client. Si no teniu una columna d'aquest tipus al vostre conjunt de dades, trieu un atribut que identifiqui de manera exclusiva la fila.

## <a name="run-a-workflow"></a>Executar un flux de treball

1. A la pàgina **Models personalitzats**, seleccioneu els punts suspensius verticals de la columna **Accions** al costat d'un flux de treball que heu creat anteriorment.

1. Seleccioneu **Executa**.

El flux de treball també s'executa automàticament amb cada actualització planificada. Més informació sobre la [configuració d'actualitzacions planificades](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Suprimir un flux de treball

1. A la pàgina **Models personalitzats**, seleccioneu els punts suspensius verticals de la columna **Accions** al costat d'un flux de treball que heu creat anteriorment.

1. Seleccioneu **Suprimeix** i confirmeu la supressió.

El flux de treball se suprimirà. L'[entitat](entities.md) que es va crear quan es va crear el flux de treball persisteix i es pot visualitzar des de la pàgina **Entitats**.

## <a name="results"></a>Resultats

Els resultats d'un flux de treball s'emmagatzemen a l'entitat configurada durant la fase Paràmetre de sortida del model. Podeu accedir a aquestes dades des de la [pàgina d'entitats](entities.md) o amb [accés a l'API](apis.md).

### <a name="api-access"></a>Accés a l'API

Per a la consulta específica d'OData per obtenir dades d'una entitat del model personalitzat, utilitzeu el format següent:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Substituïu `<your instance id>` per l'identificador de l'entorn del Customer Insights, que trobeu a la barra d'adreces del navegador quan accediu al Customer Insights.

1. Substituïu `<custom model output entity>` pel nom de l'entitat que heu proporcionat durant el pas Paràmetres de sortida del model de la configuració del model personalitzat.

1. Substituïu `<guid value>` per l'identificador de client del client al registre del qual voleu accedir. Normalment podeu trobar aquest identificador a la [pàgina de perfils de client](customer-profiles.md) del camp CustomerID.

## <a name="frequently-asked-questions"></a>Preguntes més freqüents

- Per què no puc veure el meu pipeline quan configuro un flux de treball de model personalitzat?    
  Aquest problema el provoca sovint un problema de configuració al pipeline. Assegureu-vos que el [paràmetre d'entrada està configurat](azure-machine-learning-experiments.md#dataset-configuration) i que els [paràmetres de camí i magatzem de dades de sortida](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) també estan configurats.

- Què significa l'error "No s'ha pogut desar el flux de treball d'intel·ligència"?    
  Els usuaris normalment veuen aquest missatge d'error si no tenen privilegis de Propietari o Administrador d'accés d'usuari a l'espai de treball. L'usuari necessita un nivell superior de permisos per permetre al Customer Insights processar el flux de treball com un servei en comptes d'utilitzar les credencials d'usuari per a les execucions posteriors del flux de treball.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
