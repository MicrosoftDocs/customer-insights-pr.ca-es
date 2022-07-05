---
title: Esquemes d'entitats al Common Data Model
description: Treballeu amb entitats al Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 92d37fc0950fefcb5c2a5d26214a469d3693980d
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054742"
---
# <a name="entity-schemas-in-common-data-model"></a>Esquemes d'entitats al Common Data Model

El [Common Data Model](/common-data-model/) és una especificació declarativa i una definició d'entitats estàndard que representen conceptes i activitats utilitzats habitualment entre aplicacions de negoci i de productivitat. Aquest model també s'amplia a les dades observacionals i d'anàlisi. El Common Data Model proporciona entitats empresarials definides, modulars i extensibles, com ara compte, unitat de negoci, cas, contacte, client potencial, oportunitat i producte, així com interaccions amb proveïdors, treballadors i clients, com ara activitats i acords de nivell de servei. Qualsevol persona pot crear i ampliar les definicions del Common Data Model per captar idees addicionals específiques de l'empresa.

Es tracta d'un model de dades compartit que permet que les aplicacions i els integradors de dades col·laborin més fàcilment proporcionant una definició unificada de les dades. El Common Data Model inclou un ric sistema de metadades amb les entitats, les relacions, les jerarquies, els trets i altres característiques, entre d'altres. Es va originar a partir de les aplicacions del Dynamics 365 i és de codi obert a GitHub amb més de 260 entitats estàndard. Un gran sistema d'associats interns i externs aporten conceptes específics del sector al Common Data Model.

En l'actualitat, diversos sistemes i plataformes implementen el Common Data Model, incloent-hi els fluxos de dades del Power BI i els serveis de dades de l'Azure. Ja és compatible amb el Microsoft Dataverse, el Dynamics 365, el Power Apps, el Power BI i els propers serveis de dades de l'Azure, cosa que acumular valor directament vers l'[Open Data Initiative](https://dynamics.microsoft.com/en-us/open-data-initiative/).

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

Podeu visualitzar entitats al [navegador d'entitats del Common Data Model](https://microsoft.github.io/CDM/). Seleccioneu una entitat de la secció Aplicació de l'Insights per obtenir la llista d'entitats del Customer Insights i les seves definicions.
> [!div class="mx-imgBorder"]
> ![Navegador d'entitats del CDM que mostra l'entitat CustomerActivity.](media/CDM-entity-navigator.png "Navegador d'entitats del CDM que mostra l'entitat CustomerActivity")


[!INCLUDE [footer-include](includes/footer-banner.md)]
