---
title: Exportar registres de diagnòstic (visualització prèvia)
description: Obteniu informació sobre com podeu enviar registres a Microsoft Azure Monitor.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245913"
---
# <a name="export-diagnostic-logs-preview"></a>Exportar registres de diagnòstic (visualització prèvia)

Reenviar registres des del Customer Insights mitjançant l'Azure Monitor. Els registres de recursos de l'Azure Monitor us permeten supervisar i enviar registres a l'Emmagatzematge de l'Azure, [l'Azure](https://azure.microsoft.com/services/storage/)[Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) o transferir-los als [centres d'esdeveniments de l'Azure](https://azure.microsoft.com/services/event-hubs/).

El Customer Insights envia els registres d'esdeveniments següents:

- **Auditoria d'esdeveniments**
  - **APIEvent** - permet el seguiment de canvis a través de la interfície d'usuari Dynamics 365 Customer Insights.
- **Esdeveniments operatius**
  - **WorkflowEvent** : us permet configurar [fonts de](data-sources.md) dades, [unificar](data-unification.md), [enriquir](enrichment-hub.md) i [exportar](export-destinations.md) dades a altres sistemes. Aquests passos es poden fer individualment (per exemple, activar una única exportació). També es poden executar orquestrats (per exemple, l'actualització de dades de fonts de dades que desencadenen el procés d'unificació, que generarà enriquiments i exportarà les dades a un altre sistema). Per obtenir més informació, vegeu l'esquema [WorkflowEvent](#workflow-event-schema).
  - **APIEvent** - envia totes les trucades API de la instància de clients a Dynamics 365 Customer Insights. Per a més informació, consulteu l'Esquema [APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Configurar la configuració de diagnòstic

### <a name="prerequisites"></a>Requisits previs

- Una subscripció activa [de l'Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Permisos d'administrador](permissions.md#admin) al Customer Insights.
- [Funció d'administrador](/azure/role-based-access-control/role-assignments-portal) de col·laborador i accés d'usuari al recurs de destinació de l'Azure. El recurs pot ser un compte, un Azure Data Lake Storage centre d'esdeveniments de l'Azure o una àrea de treball de l'Azure log Analytics. Aquest permís és necessari mentre es configura la configuració de diagnòstic al Customer Insights, però es pot canviar després d'una configuració correcta.
- [Es compleixen els requisits](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) de destinació per a l'emmagatzematge de l'Azure, el centre d'esdeveniments de l'Azure o l'Azure log Analytics.
- Almenys la funció **lector** en el grup de recursos al qual pertany el recurs.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configuració dels diagnòstics amb l'Azure Monitor

1. A Customer Insights, aneu a **Sistema d'administració** > **i** seleccioneu la **pestanya Diagnòstic**.

1. Seleccioneu **Afegeix una destinació**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Connexió diagnòstica.":::

1. Proporcioneu un nom al camp Nom per a la **destinació** del diagnòstic.

1. Seleccioneu el **tipus** de recurs (compte d'emmagatzematge, centre d'esdeveniments o anàlisi de registre).

1. Seleccioneu la **subscripció**, **el grup** de recursos i **el recurs** per al recurs de destinació. Vegeu [Configuració del recurs de destinació per obtenir](#configuration-on-the-destination-resource) permisos i informació de registre.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta al sistema** per connectar-vos al recurs de destinació. Els registres comencen a aparèixer a la destinació al cap de 15 minuts, si l'API està en ús i genera esdeveniments.

## <a name="configuration-on-the-destination-resource"></a>Configuració al recurs de destinació

Segons la vostra elecció del tipus de recurs, es produeixen automàticament els canvis següents:

### <a name="storage-account"></a>Compte d'emmagatzematge

El director del servei del Customer Insights obté el **permís de col·laborador** del compte d'emmagatzematge del recurs seleccionat i crea dos contenidors sota l'espai de noms seleccionat:

- `insight-logs-audit` que conté esdeveniments d'auditoria **·**
- `insight-logs-operational`**que conté esdeveniments operatius**

### <a name="event-hub"></a>Centre d'incidències

El director del servei del Customer Insights obté el permís del **propietari** de dades dels centres d'esdeveniments de l'Azure sobre el recurs i crea dos centres d'esdeveniments sota l'espai de noms seleccionat:

- `insight-logs-audit` que conté esdeveniments d'auditoria **·**
- `insight-logs-operational`**que conté esdeveniments operatius**

### <a name="log-analytics"></a>Anàlisi de registres

El director del servei del Customer Insights obté el permís de **col·laborador** de log Analytics sobre el recurs. Els registres estan disponibles a **Gestió de registres de taules** > **·** > **de registres** a l'àrea de treball de Log Analytics seleccionada. Amplieu la solució Gestió de **registres** i localitzeu les taules i `CIEventsAudit` les `CIEventsOperational` taules.

- `CIEventsAudit` que conté esdeveniments d'auditoria **·**
- `CIEventsOperational`**que conté esdeveniments operatius**

A la **finestra Consultes**, amplieu la **solució Auditoria** i localitzeu les consultes d'exemple proporcionades cercant `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Suprimir una destinació de diagnòstic

1. Aneu a **Sistema d'administració** > **i** seleccioneu la **pestanya Diagnòstic**.

1. Seleccioneu la destinació del diagnòstic a la llista.

   > [!TIP]
   > L'eliminació de la destinació atura el reenviament de registre, però no suprimeix el recurs de la subscripció de l'Azure. Per suprimir el recurs a l'Azure, seleccioneu l'enllaç a la **columna Accions** per obrir el portal de l'Azure per al recurs seleccionat i suprimiu-lo allà. A continuació, suprimiu la destinació del diagnòstic.

1. A la **columna Accions**, seleccioneu la **icona Suprimeix**.

1. Confirmeu la supressió per eliminar la destinació i aturar el reenviament del registre.

## <a name="log-categories-and-event-schemas"></a>Categories de registre i esquemes d'esdeveniments

Actualment s'admeten [esdeveniments](apis.md) de l'API i esdeveniments de flux de treball i s'apliquen les categories i esquemes següents.
L'esquema de registre segueix l'esquema [comú de l'Azure](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema) Monitor.

### <a name="categories"></a>Categories

El Customer Insights proporciona dues categories:

- **Audit events**: [Esdeveniments](#api-event-schema) API per fer un seguiment dels canvis de configuració del servei. `POST|PUT|DELETE|PATCH` les operacions entren en aquesta categoria.
- **Esdeveniments operatius**: [esdeveniments](#api-event-schema) de l'API o [esdeveniments de flux de treball generats](#workflow-event-schema) durant l'ús del servei.  Per exemple, `GET` les sol·licituds o els esdeveniments d'execució d'un flux de treball.

## <a name="event-schemas"></a>Esquemes d'esdeveniments

Els esdeveniments de l'API i els esdeveniments de flux de treball tenen una estructura comuna, però amb algunes diferències. Per obtenir més informació, vegeu [Esquema d'esdeveniments de l'API o](#api-event-schema) Esquema [d](#workflow-event-schema)'esdeveniments del flux de treball.

### <a name="api-event-schema"></a>Esquema d'esdeveniments API

| Camp             | Tipus de dades  | Obligatori/Opcional | Descripció       | Exemple        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Data i hora | Necessari          | Marca de temps de l'esdeveniment (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Necessari          | Recurs d'alçada de la instància que va emetre l'acte         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Necessari          | Nom de l'operació representada per aquest esdeveniment.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Necessari          | Categoria de registre de l'esdeveniment. Ja sigui `Operational` o `Audit` bé. Totes les sol·licituds POST / PUT / PATCH / DELETE HTTP s'etiqueten amb `Audit`, tota la resta amb`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Necessari          | Estat de l'esdeveniment. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Opcional          | Estat del resultat de l'esdeveniment. Si l'operació correspon a una trucada DE L'API REST, és el codi d'estat HTTP.        | `200`             |
| `durationMs`      | Long      | Opcional          | Durada de l'operació en mil·lisegons.     | `133`     |
| `callerIpAddress` | String    | Opcional          | Adreça IP de la persona que truca, si l'operació correspon a una trucada API que prové d'una adreça IP disponible públicament.                                                 | `144.318.99.233`         |
| `identity`        | String    | Opcional          | Objecte JSON que descriu la identitat de l'usuari o aplicació que va fer l'operació.       | Vegeu [la secció Identitat](#identity-schema).     |  
| `properties`      | String    | Opcional          | Objecte JSON amb més propietats a la categoria particular d'esdeveniments.      | Vegeu [la secció Propietats](#api-properties-schema).    |
| `level`           | String    | Necessari          | Nivell de severitat de l'esdeveniment.    | `Informational`, `Warning`, `Error`, o `Critical`.           |
| `uri`             | String    | Opcional          | URI de sol·licitud absoluta.    |               |

#### <a name="identity-schema"></a>Esquema d'identitat

L'objecte `identity` JSON té la següent estructura

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Camp                         | Descripció                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Funció assignada per a l'usuari o l'aplicació. Per obtenir més informació, vegeu [permisos](permissions.md) d'usuari.                                     |
| `Authorization.RequiredRoles` | Rols necessaris per fer l'operació. `Admin` rol es permet fer totes les operacions.                                                    |
| `Claims`                      | Reclamacions de l'usuari o del testimoni web JSON de l'aplicació (JWT). Les propietats de reclamació varien segons l'organització i la Azure Active Directory configuració. |

#### <a name="api-properties-schema"></a>Esquema de propietats de l'API

[Els esdeveniments DE L'API](apis.md) tenen les propietats següents.

| Camp                        | Descripció                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Sempre `ApiEvent`, marcant l'esdeveniment de registre com a esdeveniment API.                                                                 |
| `properties.userAgent`       | L'agent del navegador que envia la sol·licitud o `unknown`.                                                                        |
| `properties.method`          | Mètode HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Trajectòria relativa de la sol·licitud.                                                                                          |
| `properties.origin`          | URI que indica d'on prové un fetch o `unknown`.                                                                  |
| `properties.operationStatus` | `Success` per al codi d'estat HTTP < 400 <br> `ClientError` per al codi d'estat HTTP < 500 <br> `Error` per a l'estat HTTP > = 500 |
| `properties.tenantId`        | Identificador de l’organització                                                                                                        |
| `properties.tenantName`      | Nom de l'organització.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjecteId de la persona que truca.                                                                         |
| `properties.instanceId`      | Estadístiques del client`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Esquema d'esdeveniments de flux de treball

El flux de treball conté diversos passos. [Ingerir fonts de](data-sources.md) dades, [unificar](data-unification.md), [enriquir](enrichment-hub.md) i [exportar](export-destinations.md) dades. Tots aquests passos es poden executar individualment o orquestrats amb els processos següents.

#### <a name="operation-types"></a>Tipus d'operació

| OperationType     | Agrupa                                     |
| ----------------- | ----------------------------------------- |
| Ingestió         | [Fonts de dades](data-sources.md)           |
| DataPreparation   | [Fonts de dades](data-sources.md)           |
| Assignació               | [Unificació de dades](data-unification.md)   |
| Coincidència             | [Unificació de dades](data-unification.md)   |
| Combinació             | [Unificació de dades](data-unification.md)   |
| ProfileStore      | [Perfils de client](customer-profiles.md) |
| Cercar            | [Perfils de client](customer-profiles.md) |
| Activitat          | [Activitats](activities.md)                  |
| AttributeMeasures | [Segments i mesures](segments.md)      |
| EntityMeasures    | [Segments i mesures](segments.md)      |
| Mesures          | [Segments i mesures](segments.md)      |
| Segmentació      | [Segments i mesures](segments.md)      |
| Enriquiment        | [Enriquiment](enrichment-hub.md)                                          |
| Intel·ligència      | [Prediccions](predictions-overview.md)                                          |
| AiBuilder         | [Prediccions](predictions-overview.md)                                          |
| Informació detallada          | [Prediccions](predictions-overview.md)                                          |
| Export            | [Exportacions](export-destinations.md)                                          |
| Gestió de models   | [Prediccions](custom-models.md)                                           |
| Relació      | [Unificació de dades](relationships.md)                                           |

#### <a name="field-description"></a>Descripció del camp

| Camp           | Tipus de dades  | Obligatori/Opcional | Descripció                                                                                                                                                   | Exemple                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Data i hora | Necessari          | Marca de temps de l'esdeveniment (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Necessari          | ResourceId de la instància que va emetre l'acte.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Necessari          | Nom de l'operació representada per aquest esdeveniment. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Vegeu [Tipus](#operation-types) d'operacions com a referència. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Necessari          | Categoria de registre de l'esdeveniment. Sempre `Operational` per a esdeveniments de flux de treball                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Necessari          | Estat de l'esdeveniment. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | Opcional          | Durada de l'operació en mil·lisegons.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Opcional          | Objecte JSON amb més propietats a la categoria particular d'esdeveniments.                                                                                        | Vegeu la subsecció [Propietats del flux de treball](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Necessari          | Nivell de severitat de l'esdeveniment.                                                                                                                                  | `Informational`, `Warning` o `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Esquema de propietats del flux de treball

Els esdeveniments de flux de treball tenen les propietats següents.

| Camp              | Workflow | Tasca | Descripció            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Sí      | Sí  | Sempre `WorkflowEvent`, marcant l'esdeveniment com a esdeveniment de flux de treball.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Sí      | Sí  | Identificador de l'execució del flux de treball. Tots els esdeveniments de flux de treball i tasques dins de l'execució del flux de treball tenen el mateix `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Sí      | Sí  | Identificador de l'operació, vegeu [Tipus](#operation-types) d'operació.                                                                                                                                                                               |
| `properties.tasksCount`                      | Sí      | No   | Només flux de treball. Nombre de tasques que desencadena el flux de treball.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Sí      | No   | Opcional. Només esdeveniments de flux de treball. L'objectId Azure Active Directory [de l'usuari](/azure/marketplace/find-tenant-object-id#find-user-object-id) que ha activat el flux de treball, vegeu també `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Sí      | No   | `full` o `incremental` refrescar.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Sí      | No   | `OnDemand` o `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Sí      | No   | `Running` o `Successful` bé.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Sí      | Sí  | Marca de temps UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Sí      | Sí  | Marca de temps UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Sí      | Sí  | Marca de temps UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Sí      | Sí  | Estadístiques del client`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Sí  | - Per a OperationType = `Export`, l'identificador és la interfície gràfica de la configuració d'exportació. <br> - Per OperacióType = `Enrichment`, és la disfressa de l'enriquiment <br> - Per a OperationType `Measures` i `Segmentation`, l'identificador és el nom de l'entitat. |
| `properties.friendlyName`                    | No       | Sí  | Nom fàcil d'utilitzar de l'exportació o de l'entitat que es processa.                                                                                                                                                                                           |
| `properties.error`                           | No       | Sí  | Opcional. Missatge d'error amb més detalls.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Sí  | Opcional. Només per a OperationType `Export`. Identifica el tipus d'exportació. Per obtenir més informació, vegeu [informació general de les destinacions](export-destinations.md) d'exportació.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Sí  | Opcional. Només per a OperationType `Export`. Conté una llista d'entitats configurades a l'exportació.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Sí  | Opcional. Només per a OperationType `Export`. Missatge detallat per a l'exportació.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Sí  | Opcional. Només per a OperationType `Segmentation`. Indica el nombre total de membres que té el segment.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
