---
title: Límits de servei a Dynamics 365 Customer Insights
description: Coneixeu els límits i les restriccions.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791970"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Límits de servei a les capacitats del Customer Insights

En aquest article es descriuen els límits incorporats al servei del Customer Insights que s'han dissenyat per garantir la fiabilitat i l'estabilitat del servei. Qualsevol sol·licitud de canvi es pot fer a través del [Fòrum d'idees](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Conclusions sobre el públic

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Límits de servei en la capacitat d'informació de l'audiència Dynamics 365 Customer Insights

| Àrees  | Límits  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments, mesures i prediccions | 300  | El nombre total de [...](audience-insights/segments.md) segments, mesures i [...](audience-insights/measures.md)[prediccions](audience-insights/predictions.md) combinades no pot superar els 300.  |
| Relacions | 20 nivells de profunditat en les relacions en camins d'entitat. | En crear [segments](audience-insights/segments.md) o [mesures](audience-insights/measures.md) mitjançant la interfície del constructor, els camins d'entitat poden tenir fins a 20 salts de relació entre l'entitat inicial i l'entitat de destinació.  |


## <a name="engagement-insights"></a>Conclusions d'interacció

### <a name="workspace-and-event-quotas"></a>Quotes de l'àrea de treball i de la incidència

Els coneixements d'interacció són una aplicació altament escalable que pot donar suport a milions d'incidències per segon. Durant la versió preliminar pública, les incidències tenen un llindar de volum. També hi ha un límit pel que fa al nombre d'àrees de treball d'una organització.

### <a name="engagement-insights-limits"></a>Límits dels coneixements d'interacció

- Volum màxim d'incidències per àrea de treball = 100 incidències per segon

- Nombre màxim d'àrees de treball per organització = 100

Quan les incidències superen el llindar, pot provocar la pèrdua de dades dels informes que es basen en aquestes incidències. Podeu [contactar amb el servei d'atenció al client](https://go.microsoft.com/fwlink/?linkid=2145734) per sol·licitar un augment del volum abans d'excedir els límits. Treballarem amb vós per determinar la vostra necessitat d'augment de volum i per donar suport a la vostra sol·licitud.


[!INCLUDE[footer-include](includes/footer-banner.md)]
