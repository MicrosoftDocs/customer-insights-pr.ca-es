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
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034852"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Límits de servei de la capacitat de conclusions del públic del Dynamics 365 Customer Insights

En aquest article es descriuen els límits incorporats al servei del Customer Insights que s'han dissenyat per garantir la fiabilitat i l'estabilitat del servei. Qualsevol sol·licitud de canvi es pot fer a través del [Fòrum d'idees](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Àrees  | Límits  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments i mesures | 100 segments o mesures. | El nombre total de [segments](segments.md) i [mesures](measures.md) actius combinats no pot superar els 100.  |
| Relacions | 20 nivells de profunditat en les relacions en camins d'entitat. | En crear [segments](segments.md) o [mesures](measures.md) mitjançant la interfície del constructor, els camins d'entitat poden tenir fins a 20 salts de relació entre l'entitat inicial i l'entitat de destinació.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]