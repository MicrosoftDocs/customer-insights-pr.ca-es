---
title: Exemples de consulta OData per a les API del Customer Insights
description: Exemples d'ús comú de per a l'Open Data Protocol (OData) per consultar les API del Customer Insights per revisar les dades.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54ba9f4e9baeb4b7021bb8c20a706bbb6eb1529f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083158"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Exemples de consulta OData per a les API del Customer Insights

L'Open Data Protocol (OData) és un protocol d'accés a dades basat en protocols bàsics com HTTP. Utilitza metodologies comunament acceptades com REST per a la web. Hi ha diversos tipus de biblioteques i eines que es poden utilitzar per consumir serveis OData.

En aquest article s'enumeren algunes consultes d'exemple sol·licitades amb freqüència per ajudar-vos a crear les vostres pròpies implementacions basades en les [API del Customer Insights](apis.md).

Heu de modificar les mostres de consulta per fer-les funcionar en els entorns de destinació: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` on {instanceId} és el GUID de l'entorn Customer Insights que voleu consultar. L'operació [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) us permet trobar a qui {InstanceId} teniu accés.
- {CID}: GUID d'un registre de client unificat. Exemple:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: identificador de la clau principal d'un registre de client en un font de dades. Exemple: `CNTID_1002`
- {DSname}: cadena amb el nom de l'entitat d'un font de dades que s'ingereix al Customer Insights. Exemple:`Website_contacts`.
- {SegmentName}: cadena amb el nom de l'entitat de sortida d'un segment a Customer Insights. Exemple:`Male_under_40`.

## <a name="customer"></a>Client

La taula següent conté un conjunt de consultes d'exemple per a l'entitat *Client*.

|Tipus de consulta |Exemple  | Nota  |
|---------|---------|---------|
|Identificador d'un sol client     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Clau alternativa    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Persisteixen les tecles alternatives a l'entitat de client unificada       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|D'aquí a    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Clau alternativa + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Cercar  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Retorna els 10 primers resultats d'una cadena de cerca      |
|Pertinença al segment  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Retorna un nombre predefinit de files de l'entitat de segmentació.      |

## <a name="unified-activity"></a>Activitat unificada

La taula següent conté un conjunt de consultes d'exemple per a l'entitat *UnifiedActivity*.

|Tipus de consulta |Exemple  | Nota  |
|---------|---------|---------|
|Activitat del CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Llista les activitats d'un perfil de client específic |
|Període de temps de l'activitat    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Activitats d'un perfil de client en un període de temps       |
|Tipus d’activitat    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Activitat pel nom de visualització     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Ordenació d'activitats    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Ordena les activitats ascendents o descendents       |
|L'activitat s'ha ampliat des de la pertinença al segment  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Altres exemples

La taula següent conté un conjunt de consultes d'exemple per a altres entitats.

|Tipus de consulta |Exemple  | Nota  |
|---------|---------|---------|
|Mesures del CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Marques enriquides del CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Interessos enriquits del CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Expandeix     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Consultes OData no admeses

Les consultes següents no són compatibles amb el Customer Insights:

- `$filter` sobre les entitats d'origen ingerides. Només podeu executar consultes $filter a les entitats del sistema que crea el Customer Insights.
- `$expand` d'una `$search` consulta. Exemple: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` des de `$select` si només se selecciona un subconjunt d'atributs. Exemple: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` afinitats de marca o interessos enriquits per un client determinat. Exemple: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Consulta predicció les entitats de sortida del model a través de clau alternativa. Exemple: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
