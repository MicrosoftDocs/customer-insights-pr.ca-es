---
title: Models d'aprenentatge automàtic personalitzats | Microsoft Docs
description: Treballeu amb models personalitzats de l'Aprenentatge automàtic de l'Azure al Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609727"
---
# <a name="custom-machine-learning-models"></a>Models d'aprenentatge automàtic personalitzats

> [!NOTE]
> El suport per a Aprenentatge automàtic Studio (clàssic) finalitzarà el 31 d'agost de 2024. Us recomanem que feu la transició a l'Azure [Aprenentatge automàtic](/azure/machine-learning/overview-what-is-azure-machine-learning) abans d'aquesta data.
>
> A partir de l'1 de desembre de 2021, no podreu crear recursos nous Aprenentatge automàtic Studio (clàssics). Fins al 31 d'agost de 2024, pots continuar utilitzant els recursos existents Aprenentatge automàtic Studio (clàssics). Per obtenir més informació, vegeu [Migració a l'Azure Aprenentatge automàtic](/azure/machine-learning/migrate-overview).

Els models personalitzats us permeten gestionar els fluxos de treball basats en models de l'Azure Aprenentatge automàtic. Els fluxos de treball us ajuden a triar les dades a partir de les quals voleu generar conclusions i assignar els resultats a les dades unificades del client. Per obtenir més informació sobre la creació de models de ML personalitzats, vegeu [Utilitzar models basats en l'aprenentatge automàtic de l'Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Requisits previs

- Serveis web publicats a través de [l'Azure Aprenentatge automàtic per lots](/azure/machine-learning/concept-ml-pipelines).
- La canonada s'ha de publicar sota un punt final de [canonada](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Un [compte](/azure/storage/blobs/data-lake-storage-quickstart-create-account) d'emmagatzematge de l'Azure Data Lake Gen2 associat a la instància de l'Azure Studio.
- Per a l'Azure Aprenentatge automàtic espais de treball amb canalitzacions, permisos d'administrador d'accés de propietari o d'usuari a l'espai de treball de l'Azure Aprenentatge automàtic.

  > [!NOTE]
  > Les dades es transfereixen entre les vostres instàncies del Customer Insights i els pipelines o serveis web de l'Azure seleccionats al flux de treball. Quan transferiu dades a un servei de l'Azure, assegureu-vos que el servei estigui configurat per processar les dades de la manera i la ubicació necessàries per complir tots els requisits legals o normatius per a les dades en aquesta organització.

## <a name="add-a-new-workflow"></a>Afegir un flux de treball nou

1. Aneu a **Intel·ligència** > **Models personalitzats** i seleccioneu **Flux de treball nou**.

1. Proporcioneu un nom **reconeixible**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Captura de pantalla de la subfinestra Flux de treball nou.":::

1. Seleccioneu l'organització que conté el servei web a **Inquilí que conté el servei web**.

1. Si la subscripció a l'Azure Machine Learning és en un inquilí diferent del Customer Insights, seleccioneu **Inicia la sessió** amb les credencials de l'organització seleccionada.

1. Seleccioneu els **Espais de treball** associats amb el servei web.

1. Trieu la canalització de l'Azure Aprenentatge automàtic al **servei web que conté el menú desplegable del model**. A continuació, seleccioneu **Següent**.
   Més informació sobre [la publicació d'un pipeline a l'aprenentatge automàtic de l'Azure mitjançant el dissenyador](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) o l'[SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Per a cada **Entrada de servei web**, seleccioneu l'**Entitat** coincident del Customer Insights. A continuació, seleccioneu **Següent**.
   > [!NOTE]
   > El flux de treball del model personalitzat aplicarà heurística per assignar els camps d'entrada del servei web als atributs de l'entitat segons el nom i el tipus de dades del camp. Veureu un error si un camp del servei web no es pot assignar a una entitat.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Configurar un flux de treball.":::

1. Per als **paràmetres** de sortida del model, definiu les propietats següents:
   - **Nom** de l'entitat per als resultats de sortida de la canonada
   - **Sortida magatzem de dades nom** del paràmetre de la canonada per lots
   - **Nom del paràmetre** Camí de sortida de la canonada per lots

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Subfinestra Paràmetre de sortida del model.":::

1. Seleccioneu l'atribut coincident del **Customer ID als resultats** que identifiquen els clients i seleccioneu **Desa**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Subfinestra Relacioneu els resultats amb les dades del client.":::

   La **pantalla Flux de treball desat** mostra detalls sobre el flux de treball. Si heu configurat un flux de treball per a una canalització de l'Azure Aprenentatge automàtic, el Customer Insights s'adjunta a l'espai de treball que conté la canalització. El Customer Insights obtindrà una funció **de col·laborador** a l'espai de treball de l'Azure.

1. Seleccioneu **Fet**. Es **mostra la pàgina Models** personalitzats.

1. Seleccioneu els punts suspensius verticals (&vellip;) per al flux de treball i seleccioneu **Executa**. El vostre flux de treball també s'executa automàticament amb cada [actualització](schedule-refresh.md) programada.

## <a name="manage-an-existing-workflow"></a>Gestionar un flux de treball existent

Aneu a **Models** > **personalitzats d'Intel·ligència** per veure els fluxos de treball que heu creat.

Seleccioneu un flux de treball per veure les accions disponibles.

- **Editar** un flux de treball
- **Executar** un flux de treball
- [**Suprimir**](#delete-a-workflow) un flux de treball

### <a name="edit-a-workflow"></a>Editar un flux de treball

1. Aneu a **Models** > **personalitzats d'intel·ligència**.

1. Al costat del flux de treball que vulgueu actualitzar, seleccioneu els punts suspensius verticals (&vellip;) i seleccioneu **Edita**.

1. Canvieu **el nom** de visualització, si cal, i seleccioneu **Següent**.

1. Per a cada **entrada de servei web**, actualitzeu l'entitat **coincident** des del Customer Insights, si cal. A continuació, seleccioneu **Següent**.

1. Per als **paràmetres** de sortida del model, canvieu una de les opcions següents:
   - **Nom** de l'entitat per als resultats de sortida de la canonada
   - **Sortida magatzem de dades nom** del paràmetre de la canonada per lots
   - **Nom del paràmetre** Camí de sortida de la canonada per lots

1. Canvieu l'atribut coincident de Customer **ID als resultats** per identificar els clients. Trieu un atribut de la sortida d'inferència que tingui valors similars a la columna ID de client de l'Entitat del client. Si no teniu aquesta columna al conjunt de dades, trieu un atribut que identifiqui de manera única la fila.

1. Seleccioneu **Desa**

### <a name="delete-a-workflow"></a>Suprimir un flux de treball

1. Aneu a **Models** > **personalitzats d'intel·ligència**.

1. Al costat del flux de treball que vulgueu suprimir, seleccioneu els punts suspensius verticals (&vellip;) i seleccioneu **Suprimeix**.

1. Confirmeu la supressió.

El flux de treball se suprimirà. L'entitat [que](entities.md) es va crear quan vau crear el flux de treball continua i es pot visualitzar des de la **pàgina Entitats** > **de dades**.

## <a name="view-the-results"></a>Veure els resultats

Els resultats d'un flux de treball s'emmagatzemen al nom de l'entitat definit per als **paràmetres** de sortida del model. Accediu a aquestes dades des de la pàgina Entitats de dades [**o amb** > **accés a l'API**.](entities.md)[...](apis.md)

### <a name="api-access"></a>Accés a l'API

Per a la consulta específica d'OData per obtenir dades d'una entitat del model personalitzat, utilitzeu el format següent:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Substituïu-lo per `<your instance id>` l'identificador de l'entorn Customer Insights, que es mostra a la barra d'adreces del navegador quan accediu al Customer Insights.

1. Substituïu-lo pel `<custom model output entity>` nom d'entitat que heu proporcionat per als **paràmetres de sortida del model**.

1. Substituïu-lo `<guid value>` per l'identificador de client del client al qual voleu accedir. Aquest identificador es mostra a la pàgina [perfils de](customer-profiles.md) client del camp CustomerID.

## <a name="frequently-asked-questions"></a>Preguntes més freqüents

- Per què no puc veure el meu pipeline quan configuro un flux de treball de model personalitzat?
  Aquest problema el provoca sovint un problema de configuració al pipeline. Assegureu-vos que el [paràmetre d'entrada està configurat](azure-machine-learning-experiments.md#dataset-configuration) i que els [paràmetres de camí i magatzem de dades de sortida](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) també estan configurats.

- Què significa l'error "No s'ha pogut desar el flux de treball d'intel·ligència"? 
  Els usuaris normalment veuen aquest missatge d'error si no tenen privilegis de Propietari o Administrador d'accés d'usuari a l'espai de treball. L'usuari necessita un nivell superior de permisos per permetre al Customer Insights processar el flux de treball com un servei en comptes d'utilitzar les credencials d'usuari per a les execucions posteriors del flux de treball.

- S'admet un punt final privat / enllaç privat per al meu flux de treball de model personalitzat?
  Actualment, el Customer Insights no admet el punt final privat per als models personalitzats, però hi ha disponible una solució manual. Poseu-vos en contacte amb el servei d'assistència per obtenir més informació.

## <a name="responsible-ai"></a>IA responsable

Les prediccions ofereixen capacitats per crear experiències dels clients més positives, i millorar les capacitats empresarials i les fonts d'ingressos. Us recomanem que feu un balanç del valor de la vostra predicció davant el seu impacte i les desviacions que es podrien introduir d'una manera ètica. Informeu-vos sobre com Microsoft està [responent a la qüestió d'una IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Informeu-vos també sobre [les tècniques i els processos per a un aprenentatge automàtic responsable](/azure/machine-learning/concept-responsible-ml) específics de l'aprenentatge automàtic de l'Azure.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
