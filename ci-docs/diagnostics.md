---
title: Auditoria Dynamics 365 Customer Insights amb l'Azure Monitor
description: Obtén informació sobre com pots enviar registres al Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 18fc072d129be6b4fc5470b1057f592dc2638216
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642204"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Inicia la sessió amb l'Azure Dynamics 365 Customer Insights Monitor (Preview)

Dynamics 365 Customer Insights proporciona una integració directa amb l'Azure Monitor. Els registres de recursos de l'Azure Monitor us permeten supervisar i enviar registres a [l'Azure Storage,](https://azure.microsoft.com/services/storage/) l'Azure [Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) o transmetre'ls als [concentradors d'esdeveniments](https://azure.microsoft.com/services/event-hubs/) de l'Azure.

Customer Insights envia els registres d'incidències següents:

- **Esdeveniments d'auditoria**
  - **APIEvent** : permet el seguiment de canvis realitzat a través de la interfície d'usuari Dynamics 365 Customer Insights.
- **Esdeveniments operatius**
  - **WorkflowEvent** : El flux de treball permet configurar orígens [de](data-sources.md) dades, [unificar](data-unification.md) i enriquir [i](enrichment-hub.md), finalment, [exportar](export-destinations.md) dades a altres sistemes. Tots aquests passos es poden fer individualment (per exemple, activar una sola exportació) o orquestrats (per exemple, l'actualització de dades de fonts de dades que desencadenen el procés d'unificació que provocarà enriquiments addicionals i, un cop fetes, exportar les dades a un altre sistema). Per obtenir més informació, vegeu l'esquema [WorkflowEvent](#workflow-event-schema).
  - **APIEvent** : totes les trucades de l'API a la instància dels clients a Dynamics 365 Customer Insights. Per obtenir més detalls, vegeu l'esquema [APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Configura la configuració del diagnòstic

### <a name="prerequisites"></a>Requisits previs

Per configurar el diagnòstic al Customer Insights, s'han de complir els requisits previs següents:

- Teniu una subscripció activa [de l'Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Teniu [permisos d'administrador](permissions.md#admin) a l'Insights del client.
- Teniu la **funció d'administrador de** col·laboradors **i** d'accés a l'usuari al recurs de destinació de l'Azure. El recurs pot ser un compte d'emmagatzematge de l'Azure, un centre d'esdeveniments de l'Azure o una àrea de treball de l'Azure Log Analytics. Per obtenir més informació, vegeu [Afegeix o suprimeix assignacions de funcions de l'Azure mitjançant el portal](/azure/role-based-access-control/role-assignments-portal) de l'Azure.
- [S'han complert els](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) requisits de destinació per a l'Azure Storage, l'Azure Event Hub o l'Azure Log Analytics.
- Teniu com a mínim la **funció Lector** al grup de recursos al qual pertany el recurs.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configura el diagnòstic amb l'Azure Monitor

1. A Customer Insights, seleccioneu **SystemDiagnostics** > **per** veure les destinacions de diagnòstic configurades en aquesta instància.

1. Seleccioneu **Afegeix una destinació**.

   > [!div class="mx-imgBorder"]
   > ![Connexió de diagnòstic](media/diagnostics-pane.png "Connexió de diagnòstic")

1. Proporcioneu un nom al camp Nom per a la destinació **del** diagnòstic.

1. Trieu l'inquilí **de** la subscripció de l'Azure amb el recurs de destinació i seleccioneu **Inicia la** sessió.

1. Seleccioneu el **tipus** de recurs (compte d'emmagatzematge, centre d'esdeveniments o anàlisi de registres).

1. Seleccioneu la **subscripció** per al recurs de destinació.

1. Seleccioneu el **grup de recursos** per al recurs de destinació.

1. Seleccioneu el **recurs**.

1. Confirmeu la **declaració de privadesa i compliment de les** dades.

1. Seleccioneu **Connecta't al sistema** per connectar-te al recurs de destinació. Els registres comencen a aparèixer a la destinació després de 15 minuts, si l'API s'utilitza i genera esdeveniments.

### <a name="remove-a-destination"></a>Suprimir una destinació

1. Aneu a **SystemDiagnostics** > **·**.

1. Seleccioneu la destinació del diagnòstic a la llista.

1. A la **columna Accions**, seleccioneu la **icona Suprimeix**.

1. Confirmeu la supressió per aturar el reenviament de registres. El recurs de la subscripció de l'Azure no se suprimirà. Podeu seleccionar l'enllaç de la **columna Accions** per obrir el portal de l'Azure per al recurs seleccionat i suprimir-lo allà.

## <a name="log-categories-and-event-schemas"></a>Registra categories i esquemes d'esdeveniments

Actualment s'admeten [esdeveniments de l'API](apis.md) i esdeveniments de flux de treball i s'apliquen les categories i esquemes següents.
L'esquema de registre segueix l'esquema comú de l'Azure [Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Categories

Customer Insights proporciona dues categories:

- **Esdeveniments d'auditoria**: [esdeveniments](#api-event-schema) de l'API per fer un seguiment dels canvis de configuració del servei. `POST|PUT|DELETE|PATCH` les operacions entren en aquesta categoria.
- **Esdeveniments operatius**: [esdeveniments de l'API](#api-event-schema) o [esdeveniments de flux de treball generats](#workflow-event-schema) mentre s'utilitzava el servei.  Per exemple, `GET` sol·licituds o els esdeveniments d'execució d'un flux de treball.

## <a name="configuration-on-the-destination-resource"></a>Configuració del recurs de destinació

En funció de la vostra elecció en el tipus de recurs, s'aplicaran automàticament els passos següents:

### <a name="storage-account"></a>Compte d'emmagatzematge

El principal del servei del Customer Insights obté el **permís del col·laborador** del compte d'emmagatzematge al recurs seleccionat i crea dos contenidors a l'espai de noms seleccionat:

- `insight-logs-audit` que conté esdeveniments d'auditoria **·**
- `insight-logs-operational`**Que continguin esdeveniments operatius**

### <a name="event-hub"></a>Centre d'incidències

El director del servei customer insights obté el permís del **propietari** de dades de l'Azure Event Hubs al recurs i crearà dos concentradors d'esdeveniments a l'espai de noms seleccionat:

- `insight-logs-audit` que conté esdeveniments d'auditoria **·**
- `insight-logs-operational`**Que continguin esdeveniments operatius**

### <a name="log-analytics"></a>Anàlisi de registres

El principal del servei d'estadístiques del client obté el permís del **col·laborador d'Analytics** de registre del recurs. Els registres estaran disponibles a **LogsTablesLog** > **·** > **Management** a l'àrea de treball log Analytics seleccionada. Expandiu la **solució Gestió de** registres i localitzeu les `CIEventsAudit` taules i `CIEventsOperational`.

- `CIEventsAudit` que conté esdeveniments d'auditoria **·**
- `CIEventsOperational`**Que continguin esdeveniments operatius**

A la **finestra Consultes**, expandiu la **solució Auditoria** i localitzeu les consultes d'exemple proporcionades cercant `CIEvents`.

## <a name="event-schemas"></a>Esquemes d'incidències

Les incidències de l'API i les incidències del flux de treball tenen una estructura i detalls comuns en què difereixen, vegeu [l'esquema d'incidències](#api-event-schema) de l'API o [l'esquema d'incidències](#workflow-event-schema) del flux de treball.

### <a name="api-event-schema"></a>Esquema d'esdeveniments de l'API

| Camp             | Tipus de dades  | Obligatori/Opcional | Descripció       | Exemple        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Data i hora | Necessari          | Marca horària de l'esdeveniment (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Necessari          | ResourceId de la instància que ha emès l'esdeveniment         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Necessari          | Nom de l'operació representada per aquest esdeveniment.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Necessari          | Registra la categoria de l'esdeveniment. O o `Operational``Audit`. Totes les sol·licituds HTTP POST/PUT/PATCH/DELETE estan etiquetades amb `Audit`, tota la resta amb`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Necessari          | Estat de l'esdeveniment. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Opcional          | Estat del resultat de l'esdeveniment. Si l'operació correspon a una trucada de l'API REST, és el codi d'estat HTTP.        | `200`             |
| `durationMs`      | Long      | Opcional          | Durada de l'operació en mil·lisegons.     | `133`     |
| `callerIpAddress` | String    | Opcional          | Adreça IP de la persona que truca, si l'operació correspon a una trucada API que prové d'una adreça IP disponible públicament.                                                 | `144.318.99.233`         |
| `identity`        | String    | Opcional          | Objecte JSON que descriu la identitat de l'usuari o aplicació que va fer l'operació.       | Vegeu la [secció Identitat](#identity-schema).     |  
| `properties`      | String    | Opcional          | Objecte JSON amb més propietats a la categoria particular d'esdeveniments.      | Vegeu la [secció Propietats](#api-properties-schema).    |
| `level`           | String    | Necessari          | Nivell de gravetat de l'esdeveniment.    | `Informational`, `Warning`, `Error` o `Critical`.           |
| `uri`             | String    | Opcional          | Sol·licitud absoluta URI.    |               |

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
| `Authorization.UserRole`      | Funció assignada per a l'usuari o l'aplicació. Per obtenir més informació, vegeu [els permisos](permissions.md) d'usuari.                                     |
| `Authorization.RequiredRoles` | Funcions necessàries per fer l'operació. `Admin` es permet fer totes les operacions.                                                    |
| `Claims`                      | Reclamacions de l'usuari o aplicació JSON web token (JWT). Les propietats de reclamació varien segons l'organització i la Azure Active Directory configuració. |

#### <a name="api-properties-schema"></a>Esquema de propietats de l'API

[Les incidències de l'API](apis.md) tenen les propietats següents.

| Camp                        | Descripció                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Sempre `ApiEvent`, marcant l'esdeveniment de registre com a esdeveniment DE L'API.                                                                 |
| `properties.userAgent`       | L'agent del navegador que envia la sol·licitud o `unknown`.                                                                        |
| `properties.method`          | Mètode HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Camí relatiu de la sol·licitud.                                                                                          |
| `properties.origin`          | URI indicant d'on ve una obtenció o `unknown`.                                                                  |
| `properties.operationStatus` | `Success` per al codi d'estat HTTP < 400 <br> `ClientError` per al codi d'estat HTTP < 500 <br> `Error` per a l'estat HTTP >= 500 |
| `properties.tenantId`        | Identificador de l’organització                                                                                                        |
| `properties.tenantName`      | Nom de l'organització.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId de la persona que truca.                                                                         |
| `properties.instanceId`      | Estadístiques del client`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Esquema d'incidències del flux de treball

El flux de treball conté diversos passos. [Ingereix les fonts](data-sources.md) de dades, [unifica](data-unification.md), [enriqueix](enrichment-hub.md) i [exporta](export-destinations.md) dades. Tots aquests passos poden executar-se individualment o orquestrats amb els següents processos. 

#### <a name="operation-types"></a>Tipus d'operació

| OperationType     | Agrupa                                     |
| ----------------- | ----------------------------------------- |
| Ingestió         | [Orígens de dades](data-sources.md)           |
| DataPreparation   | [Orígens de dades](data-sources.md)           |
| Assignació               | [Unificació de dades](data-unification.md)   |
| Coincidència             | [Unificació de dades](data-unification.md)   |
| Combinació             | [Unificació de dades](data-unification.md)   |
| PerfilStore      | [Perfils de client](customer-profiles.md) |
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
| ModelManagement   | [Prediccions](custom-models.md)                                           |
| Relació      | [Unificació de dades](relationships.md)                                           |

#### <a name="field-description"></a>Descripció del camp

| Camp           | Tipus de dades  | Obligatori/Opcional | Descripció                                                                                                                                                   | Exemple                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Data i hora | Necessari          | Marca horària de l'esdeveniment (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Necessari          | ResourceId de la instància que ha emès l'esdeveniment.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Necessari          | Nom de l'operació representada per aquest esdeveniment. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Vegeu [Tipus](#operation-types) d'operacions per a la referència. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Necessari          | Registra la categoria de l'esdeveniment. Sempre `Operational` per a esdeveniments del flux de treball                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Necessari          | Estat de l'esdeveniment. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | Opcional          | Durada de l'operació en mil·lisegons.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Opcional          | Objecte JSON amb més propietats a la categoria particular d'esdeveniments.                                                                                        | Vegeu les propietats del flux de treball de la [subsecció](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Necessari          | Nivell de gravetat de l'esdeveniment.                                                                                                                                  | `Informational`, `Warning` o `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Esquema de propietats del flux de treball

Les incidències del flux de treball tenen les propietats següents.

| Camp              | Workflow | Tasca | Descripció            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Sí      | Sí  | Sempre `WorkflowEvent`, marcant l'esdeveniment com a esdeveniment de flux de treball.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Sí      | Sí  | Identificador de l'execució del flux de treball. Tots els esdeveniments del flux de treball i de la tasca dins de l'execució del flux de treball tenen el mateix `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Sí      | Sí  | Identificador de l'operació, vegeu [Tipus](#operation-types) d'operacions.                                                                                                                                                                               |
| `properties.tasksCount`                      | Sí      | No   | Només el flux de treball. Nombre de tasques que activa el flux de treball.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Sí      | No   | Opcional. Només les incidències del flux de treball. L'objectId Azure Active Directory [de l'usuari](/azure/marketplace/find-tenant-object-id#find-user-object-id) que ha activat el flux de treball, vegeu també `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Sí      | No   | `full` o `incremental` refrescar-se.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Sí      | No   | `OnDemand` o `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Sí      | No   | `Running` o `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Sí      | Sí  | Marca horària UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Sí      | Sí  | Marca horària UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Sí      | Sí  | Marca horària UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Sí      | Sí  | Estadístiques del client`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Sí  | - Per a OperationType = `Export`, l'identificador és el guid de la configuració d'exportació. <br> - Per OperationType = `Enrichment`, és el guid de l'enriquiment <br> - Per a OperationType `Measures` i `Segmentation`, l'identificador és el nom de l'entitat. |
| `properties.friendlyName`                    | No       | Sí  | Nom fàcil d'utilitzar de l'exportació o de l'entitat que es processa.                                                                                                                                                                                           |
| `properties.error`                           | No       | Sí  | Opcional. Missatge d'error amb més detalls.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Sí  | Opcional. Només per a OperationType `Export`. Identifica el tipus d'exportació. Per obtenir més informació, vegeu [la visió general de les destinacions](export-destinations.md) d'exportació.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Sí  | Opcional. Només per a OperationType `Export`. Conté una llista d'entitats configurades a l'exportació.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Sí  | Opcional. Només per a OperationType `Export`. Missatge detallat per a l'exportació.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Sí  | Opcional. Només per a OperationType `Segmentation`. Indica el nombre total de membres que té el segment.                                                                                                                                                    |
