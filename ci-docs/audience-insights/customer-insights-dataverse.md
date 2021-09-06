---
title: Dades del Customer Insights al Microsoft Dataverse
description: Utilitzeu les entitats del Customer Insights com a taules al Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 45535a7368b89e19a91f08fcd825bda9d57a8709653104bf4043c29ffa14d0b8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032884"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Treballar amb dades del Customer Insights al Microsoft Dataverse

El Customer Insights ofereix l'opció de fer que les entitats de sortida estiguin disponibles al [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Aquesta integració permet l'ús compartit fàcil de dades i el desenvolupament personalitzat mitjançant un mètode de poc codi/sense codi. Les entitats de sortida estaran disponibles com a taules al Dataverse. Aquestes taules permeten escenaris com ara [fluxos de treball automatitzats mitjançant el Power Automate](/power-automate/getting-started), [aplicacions impulsades per models](/powerapps/maker/model-driven-apps/) i [aplicacions de llenç](/powerapps/maker/canvas-apps/) mitjançant el Power Apps. Podeu utilitzar les dades de qualsevol altra aplicació basada en taules del Dataverse. La implementació actual admet principalment consultes on es poden obtenir dades de les entitats de coneixements del públic disponibles per a un identificador de client determinat.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Adjuntar un entorn del Dataverse al Customer Insights

**Organitzacions amb entorns del Dataverse existents**

Les organitzacions que ja utilitzen el Dataverse poden [utilitzar un dels entorns del Dataverse existents](get-started-paid.md) quan un administrador configura conclusions del públic. En proporcionar l'adreça URL a l'entorn del Dataverse, s'adjunta a l'entorn nou de les conclusions del públic. Per garantir el millor rendiment possible, els entorns del Customer Insights i del Dataverse s'han d'allotjar a la mateixa regió.

Per adjuntar un entorn del Dataverse, expandiu la **Configuració avançada** en crear l'entorn de les conclusions del públic. Proporcioneu l'**adreça URL de l'entorn del Microsoft Dataverse** i activeu la casella de selecció per **Habilitar l'ús compartit de dades**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Organització nova**

Si creeu una organització nova en configurar el Customer Insights, obtindreu automàticament un entorn del Dataverse nou.

> [!NOTE]
> Si les organitzacions ja utilitzen el Dataverse al seu inquilí, és important recordar que [la creació de l'entorn del Dataverse està controlada per un administrador](/power-platform/admin/control-environment-creation.md). Per exemple, si configureu un entorn nou de conclusions del públic amb el vostre compte de l'organització i l'administrador ha inhabilitat la creació d'entorns de prova del Dataverse per a tots els usuaris, tret dels administradors, no podreu crear cap entorn de prova nou.
> 
> Els entorns de prova del Dataverse creats al Customer Insights tenen 3 GB d'emmagatzematge que no es compten per a la capacitat global de l'inquilí. Les subscripcions pagades tenen dret de 15 GB al Dataverse per a la base de dades i 20 GB per a l'emmagatzematge de fitxers.

## <a name="output-entities"></a>Entitats de sortida

Algunes entitats de sortida dels coneixements del públic estan disponibles com a taules al Dataverse. Les seccions següents descriuen l'esquema esperat d'aquestes taules.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquiment](#enrichment)
- [Predicció](#prediction)


### <a name="customerprofile"></a>CustomerProfile

Aquesta taula conté el perfil de client unificat del Customer Insights. L'esquema d'un perfil de client unificat depèn de les entitats i els atributs utilitzats en el procés de combinació. Un esquema de perfil de client sol contenir un subconjunt dels atributs de la [definició del model de dades comú del CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

La taula AlternativeKey conté les claus de les entitats que han participat en el procés d'unificació.

|Column  |Type  |Descripció  |
|---------|---------|---------|
|DataSourceName    |String         | Nom de la font de dades. Per exemple: `datasource5`        |
|EntityName        | String        | Nom de l'entitat als coneixements del públic. Per exemple: `contact1`        |
|AlternateValue    |String         |Identificador alternatiu assignat a l'identificador de client. Exemple: `cntid_1078`         |
|KeyRing           | Text de diverses línies        | Valor JSON  </br> Exemple: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
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
