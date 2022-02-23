---
title: Dades del Customer Insights a Microsoft Dataverse
description: Utilitzeu les entitats del Customer Insights com a taules a Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866922"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Treballar amb les dades del Customer Insights a Microsoft Dataverse

Customer Insights proporciona l'opció de fer que les entitats de sortida estiguin disponibles a [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Aquesta integració permet l'ús compartit fàcil de dades i el desenvolupament personalitzat mitjançant un mètode de poc codi/sense codi. Les entitats de sortida estaran disponibles com a taules a Dataverse. Aquestes taules permeten escenaris com [ara fluxos de treball automatitzats a través de Power Automate](/power-automate/getting-started), aplicacions [basades en models i aplicacions de](/powerapps/maker/model-driven-apps/) llenç a través de [Power](/powerapps/maker/canvas-apps/) Apps. Podeu utilitzar les dades per a qualsevol altra aplicació que es basi en taules Dataverse. La implementació actual admet principalment consultes on es poden obtenir dades de les entitats de coneixements del públic disponibles per a un identificador de client determinat.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Adjuntar un entorn de Dataverse al Customer Insights

**Organitzacions amb entorns Dataverse existents**

Les organitzacions que ja utilitzen Dataverse poden [utilitzar un dels seus entorns Dataverse existents quan un administrador configura](create-environment.md) estadístiques de públic. En proporcionar l'URL a l'entorn Dataverse, s'adjunta al seu nou entorn d'estadístiques de públic. Per garantir el millor rendiment possible, les estadístiques del client i els entorns Dataverse s'han d'allotjar a la mateixa regió.

**Organització nova**

Si creeu una organització nova en configurar el Customer Insights, obtindreu automàticament un entorn de Dataverse nou.

> [!NOTE]
> Si les vostres organitzacions ja utilitzen Dataverse al seu inquilí, és important recordar que [Dataverse creació d'entorn està controlada per un administrador](/power-platform/admin/control-environment-creation.md) . Per exemple, si esteu configurant un entorn d'estadístiques de públic nou amb el vostre compte d'organització i l'administrador ha desactivat la creació d'entorns de prova Dataverse per a tothom, excepte els administradors, no podeu crear un entorn de prova nou.
> 
> Els entorns de prova Dataverse creats al Customer Insights tenen 3 GB d'emmagatzematge que no comptaran per a la capacitat global amb dret a l'inquilí. Les subscripcions pagades obtenen Dataverse dret de 15 GB per a la base de dades i de 20 GB per a l'emmagatzematge d'arxius.

## <a name="output-entities"></a>Entitats de sortida

Algunes entitats de sortida de les estadístiques de públic estan disponibles com a taules a Dataverse. Les seccions següents descriuen l'esquema esperat d'aquestes taules.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquiment](#enrichment)
- [Predicció](#prediction)
- [Pertinença al segment](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Aquesta taula conté el perfil de client unificat del Customer Insights. L'esquema d'un perfil de client unificat depèn de les entitats i els atributs utilitzats en el procés de combinació. Un esquema de perfil de client sol contenir un subconjunt dels atributs de la [definició del model de dades comú del CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

La taula AlternativeKey conté les claus de les entitats que han participat en el procés d'unificació.

|Column  |Type  |Descripció  |
|---------|---------|---------|
|DataSourceName    |String         | Nom de la font de dades. Per exemple: `datasource5`        |
|EntityName        | String        | Nom de l'entitat als coneixements del públic. Per exemple: `contact1`        |
|AlternateValue    |String         |Identificador alternatiu assignat a l'identificador de client. Exemple: `cntid_1078`         |
|KeyRing           | Text de diverses línies        | Valor JSON  </br> Exemple: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"claus":[" cntid_1078"]}]       |
|CustomerId         | String        | Identificador del perfil de client unificat.         |
|AlternateKeyId     | GUID         |  GUID determinista d'AlternateKey basat en msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemple: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Aquesta taula conté activitats dels usuaris que estan disponibles al Customer Insights.

| Column            | Type        | Descripció                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Identificador del perfil del client                                                                      |
| ActivityId        | String      | Identificador intern de l'activitat de client (clau principal)                                       |
| SourceEntityName  | String      | Nom de l'entitat d'origen                                                                |
| SourceActivityId  | String      | Clau principal de l'entitat d'origen                                                       |
| ActivityType      | String      | Tipus d'activitat administrada o nom de l'activitat personalitzada                                        |
| ActivityTimeStamp | DATETIME    | Marca de temps de l'activitat                                                                      |
| Càrrec             | String      | Títol o nom de l'activitat                                                               |
| Descripció       | String      | Descripció d'activitat                                                                     |
| Adreça URL               | String      | Enllaçar amb una adreça URL externa específica de l'activitat                                         |
| SemanticData      | Cadena JSON | Inclou una llista de parelles de valors clau per als camps d'assignació semàntica específics del tipus d'activitat |
| RangeIndex        | String      | Marca de temps unix utilitzada per ordenar la cronologia de l'activitat i les consultes d'interval eficaces |
| mydynci_unifiedactivityid   | GUID | Identificador intern de l'activitat de client (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Aquesta taula conté les dades de sortida de les mesures basades en atributs del client.

| Column             | Type             | Descripció                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Identificador del perfil del client        |
| Mesures           | Cadena JSON      | Inclou una llista de parelles de valors clau per al nom de mesura i els valors del client determinat | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Identificador del perfil del client |


### <a name="enrichment"></a>Enriquiment

Aquesta taula conté la sortida del procés d'enriquiment.

| Column               | Type             |  Descripció                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Identificador del perfil del client                                 |
| EnrichmentProvider   | String           | Nom del proveïdor de l'enriquiment                                  |
| EnrichmentType       | String           | Tipus d'enriquiment                                      |
| Valors               | Cadena JSON      | Llista d'atributs produïts pel procés d'enriquiment |
| msdynci_enrichmentid | GUID             | GUID determinista generat a partir de msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predicció

Aquesta taula conté la sortida de les prediccions de models.

| Column               | Type        | Descripció                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Identificador del perfil del client                                  |
| ModelProvider        | String      | Nom del proveïdor del model                                      |
| Model                | String      | Nom del model                                                |
| Valors               | Cadena JSON | Llista d'atributs produïts pel model |
| msdynci_predictionid | GUID        | GUID determinista generat a partir de msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Pertinença al segment

Aquesta taula conté informació de pertinença al segment dels perfils de clients.

| Column        | Type | Descripció                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Identificador del perfil del client        |
| SegmentProvider      | String       | Aplicació que publica els segments. Per defecte: estadístiques del públic         |
| SegmentMembershipType | String       | Tipus de client d'aquest registre de pertinença al segment. Admet diversos tipus, com ara client, contacte o compte. Per defecte: client  |
| Segments       | Cadena JSON  | Llista de segments únics dels que el perfil de client és membre      |
| msdynci_identifier  | String   | Identificador únic del registre de pertinença al segment. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinista generat a partir de`msdynci_identifier`          |
