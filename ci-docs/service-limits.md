---
title: Límits de servei al Dynamics 365 Customer Insights
description: Coneixeu els límits i les restriccions.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483645"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Límits de servei a les capacitats del Customer Insights

En aquest article es descriuen els límits incorporats al servei del Customer Insights que s'han dissenyat per garantir la fiabilitat i l'estabilitat del servei. Qualsevol sol·licitud de canvi es pot fer a través del [Fòrum d'idees](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Conclusions sobre el públic

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Límits de servei de la capacitat de conclusions del públic del Dynamics 365 Customer Insights

| Àrees  | Límits  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments i mesures | 100 segments o mesures. | El nombre total de [segments](audience-insights/segments.md) i [mesures](audience-insights/measures.md) actius combinats no pot superar els 100.  |
| Relacions | 20 nivells de profunditat en les relacions en camins d'entitat. | En crear [segments](audience-insights/segments.md) o [mesures](audience-insights/measures.md) mitjançant la interfície del constructor, els camins d'entitat poden tenir fins a 20 salts de relació entre l'entitat inicial i l'entitat de destinació.  |


## <a name="engagement-insights"></a>Conclusions d'interacció

### <a name="workspace-and-event-quotas"></a>Quotes de l'àrea de treball i de la incidència

Els coneixements d'interacció són una aplicació altament escalable que pot donar suport a milions d'incidències per segon. Durant la versió preliminar pública, les incidències tenen un llindar de volum. També hi ha un límit pel que fa al nombre d'àrees de treball d'una organització.

### <a name="engagement-insights-limits"></a>Límits dels coneixements d'interacció

- Volum màxim d'incidències per àrea de treball = 100 incidències per segon

- Nombre màxim d'àrees de treball per organització = 100

Quan les incidències superen el llindar, pot provocar la pèrdua de dades dels informes que es basen en aquestes incidències. Podeu [contactar amb el servei d'atenció al client](https://go.microsoft.com/fwlink/?linkid=2145734) per sol·licitar un augment del volum abans d'excedir els límits. Treballarem amb vós per determinar la vostra necessitat d'augment de volum i per donar suport a la vostra sol·licitud.


[!INCLUDE[footer-include](includes/footer-banner.md)]