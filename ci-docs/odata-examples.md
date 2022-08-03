---
title: Exemples de consulta d'OData per a les API del Customer Insights
description: S'utilitzen habitualment exemples de protocol de dades obertes (OData) per consultar les API del Customer Insights per revisar les dades.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8843fc04e4e6eaba0019d932c54f62561ffbdb92
ms.sourcegitcommit: f3c12ad445d5f91a88f91a7bbc40790ebcfaa826
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "9121550"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Exemples de consulta d'OData per a les API del Customer Insights

L'Open Data Protocol (OData) és un protocol d'accés a dades basat en protocols bàsics com HTTP. Utilitza metodologies comunament acceptades com REST per a la web. Hi ha diversos tipus de biblioteques i eines que es poden utilitzar per consumir serveis OData.

En aquest article s'enumeren algunes consultes d'exemple sol·licitades amb freqüència per ajudar-vos a crear les vostres pròpies implementacions basades en les API del [Customer Insights](apis.md).

Heu de modificar les mostres de consulta perquè funcionin en els entorns de destinació: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` on {instanceId} és el GUID de l'entorn del Customer Insights que voleu consultar. L'operació [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) us permet trobar el {InstanceId} que teniu accés.
- {CID} GUID d'un registre de client unificat. Exemple:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identificador de la clau principal d'un registre de client en un font de dades. Exemple: `CNTID_1002`
- {DSname}: Cadena amb el nom d'entitat d'una font de dades que s'ingereix al Customer Insights. Exemple:`Website_contacts`.
- {SegmentName}: Cadena amb el nom de l'entitat de sortida d'un segment al Customer Insights. Exemple:`Male_under_40`.

## <a name="customer"></a>Client

La taula següent conté un conjunt de consultes d'exemple per a l'entitat *Client*.

|Tipus de consulta |Exemple  | Nota  |
|---------|---------|---------|
|Identificador de client únic     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Clau alternativa    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Les claus alternatives es mantenen a l'entitat client unificada       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|D'aquí a    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Clau alternativa + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Cercar  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Retorna els 10 primers resultats d'una cadena de cerca      |
|Pertinença al segment  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Retorna un nombre predefinit de files de l'entitat de segmentació.      |
|Segmentar la pertinença a un client | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Retorna el perfil del client si és membre del segment indicat     |

## <a name="unified-activity"></a>Activitat unificada

La taula següent conté un conjunt de consultes d'exemple per a l'entitat *UnifiedActivity*.

|Tipus de consulta |Exemple  | Nota  |
|---------|---------|---------|
|Activitat del CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Llistar activitats d'un perfil de client específic |
|Període de temps de l'activitat    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Activitats d'un perfil de client en un període de temps       |
|Tipus d’activitat    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Activitat per nom de visualització     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Ordenació d'activitats    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Ordenar les activitats ascendents o descendents       |
|Activitat ampliada a partir de la pertinença al segment  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Altres exemples

La taula següent conté un conjunt de consultes d'exemple per a altres entitats.

|Tipus de consulta |Exemple  | Nota  |
|---------|---------|---------|
|Mesures del CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Marques enriquides del CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Interessos enriquits del CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Clàusula in + Ampliar     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>No s'admeten consultes d'OData

Les consultes següents no són compatibles amb el Customer Insights:

- `$filter` en entitats d'origen ingerides. Només podeu executar consultes $filter a les entitats del sistema que crea el Customer Insights.
- `$expand` a partir d'una `$search` consulta. Exemple: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` de `$select` si només se selecciona un subconjunt d'atributs. Exemple: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` afinitats de marca enriquides o d'interès per a un client determinat. Exemple: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Consulta predicció model d'entitats de sortida mitjançant clau alternativa. Exemple: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
