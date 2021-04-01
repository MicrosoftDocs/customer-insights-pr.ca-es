---
title: Esquemes d'entitats del Customer Insights al Common Data Model
description: Treballeu amb entitats al Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596349"
---
# <a name="entity-schemas-in-common-data-model"></a>Esquemes d'entitats al Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

El [Common Data Model](/common-data-model/) és una especificació declarativa i una definició d'entitats estàndard que representen conceptes i activitats utilitzats habitualment entre aplicacions de negoci i de productivitat. Aquest model també s'amplia a les dades observacionals i d'anàlisi. El Common Data Model proporciona entitats empresarials definides, modulars i extensibles, com ara compte, unitat de negoci, cas, contacte, client potencial, oportunitat i producte, així com interaccions amb proveïdors, treballadors i clients, com ara activitats i acords de nivell de servei. Qualsevol persona pot crear i ampliar les definicions del Common Data Model per captar idees addicionals específiques de l'empresa.

Es tracta d'un model de dades compartit que permet que les aplicacions i els integradors de dades col·laborin més fàcilment proporcionant una definició unificada de les dades. El Common Data Model inclou un ric sistema de metadades amb les entitats, les relacions, les jerarquies, els trets i altres característiques, entre d'altres. Es va originar a partir de les aplicacions del Dynamics 365 i és de codi obert a GitHub amb més de 260 entitats estàndard. Un gran sistema d'associats interns i externs aporten conceptes específics del sector al Common Data Model.

Actualment, diversos sistemes i plataformes implementen el Common Data Model, incloent-hi els fluxos de dades del Power BI i els serveis de dades de l'Azure. Ja s'admet al Common Data Service, el Dynamics 365, el Power Apps, el Power BI i els serveis de dades de l'Azure disponibles pròximament, i acumula valor directament cap a l'[Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Esquemes d'entitat del Customer Insights

Per establir una visualització de 360 graus del client i fer que els models del Customer Insights estiguin disponibles al Common Data Model per a l'extensibilitat, hem publicat els següents esquemes d'entitat:

| Entitat | Descripció |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Activitat realitzada per un usuari que té un valor d'observacional per a l'empresa. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Una persona o una organització que hagi tingut o tingui el potencial de participar en activitats empresarials. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definició dels KPI que s'han dividit entre zero o més dimensions (com ara els usuaris actius mensuals, la inversió total per client, el cost d'adquisició del client mitjà) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Defineix un grup de membres amb característiques comunes. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Membres que participen en un segment determinat. |

Per obtenir més informació, vegeu la documentació sobre els [Esquemes d'entitat del Customer Insights al Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Visualitzar entitats mitjançant el navegador d'entitats del Common Data Model

Podeu visualitzar entitats al [navegador d'entitats del Common Data Model](https://microsoft.github.io/CDM/). Seleccioneu el botó **Carrega des de GitHub!** i aneu a **foundationCommon** > **crmCommon** > **solutions** > **customerInsights**, on trobareu la llista d'entitats del Customer Insights i les seves definicions.
> [!div class="mx-imgBorder"]
> ![Navegador d'entitats del CDM que mostra l'entitat CustomerActivity](media/CDM-entity-navigator.png "Navegador d'entitats del CDM que mostra l'entitat CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]