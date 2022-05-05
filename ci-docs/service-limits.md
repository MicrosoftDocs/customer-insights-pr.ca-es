---
title: Límits de servei al Dynamics 365 Customer Insights
description: Coneixeu els límits i les restriccions.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641750"
---
# <a name="service-limits-in-customer-insights"></a>Límits de servei a Customer Insights

En aquest article es descriuen els límits incorporats al servei del Customer Insights que s'han dissenyat per garantir la fiabilitat i l'estabilitat del servei. Qualsevol sol·licitud de canvi es pot fer a través del [Fòrum d'idees](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Àrees  | Límits  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments, mesures i prediccions | 300  | El nombre total de [segments](segments.md), [mesures](measures.md) i [prediccions combinats](predictions.md) no pot superar els 300.  |
| Relacions | 20 nivells de profunditat en les relacions en camins d'entitat. | En crear [segments](segments.md) o [mesures](measures.md) mitjançant la interfície del constructor, els camins d'entitat poden tenir fins a 20 salts de relació entre l'entitat inicial i l'entitat de destinació.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
