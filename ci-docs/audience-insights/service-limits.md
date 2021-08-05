---
title: Límits de servei
description: Coneixeu els límits i les restriccions.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604357"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Límits de servei de la capacitat de conclusions del públic del Dynamics 365 Customer Insights

En aquest article es descriuen els límits incorporats al servei del Customer Insights que s'han dissenyat per garantir la fiabilitat i l'estabilitat del servei. Qualsevol sol·licitud de canvi es pot fer a través del [Fòrum d'idees](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Àrees  | Límits  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments i mesures | 100 segments o mesures. | El nombre total de [segments](segments.md) i [mesures](measures.md) actius combinats no pot superar els 100.  |
| Relacions | 20 nivells de profunditat en les relacions en camins d'entitat. | En crear [segments](segments.md) o [mesures](measures.md) mitjançant la interfície del constructor, els camins d'entitat poden tenir fins a 20 salts de relació entre l'entitat inicial i l'entitat de destinació.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]