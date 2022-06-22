---
title: Límits de servei a Customer Insights
description: Entendre els límits i les restriccions del servei SaaS del Customer Insights.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940656"
---
# <a name="service-limits-in-customer-insights"></a>Límits de servei a Customer Insights

En aquest article es descriuen els límits incorporats al servei del Customer Insights que s'han dissenyat per garantir la fiabilitat i l'estabilitat del servei. Qualsevol sol·licitud de canvi es pot fer a través del [Fòrum d'idees](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Àrees  | Límits  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments, mesures i prediccions | 300  | El nombre total de [segments](segments.md), [mesures](measures.md) i [prediccions combinats](predictions.md) no pot superar els 300.  |
| Relacions | 20 nivells de profunditat en les relacions en camins d'entitat. | En crear [segments](segments.md) o [mesures](measures.md) mitjançant la interfície del constructor, els camins d'entitat poden tenir fins a 20 salts de relació entre l'entitat inicial i l'entitat de destinació.  |

## <a name="fair-scheduling-of-jobs"></a>Programació justa de llocs de treball

Customer Insights és un servei SaaS que utilitza recursos compartits de l'Azure. Els clients tendeixen a tenir càrregues de treball d'intensitat variable i en diferents horaris. Per garantir un accés just als recursos subjacents, ens assegurem que els processos del sistema s'executin en un ordre just. Exemples de processos del sistema són treballs relacionats amb la unificació de dades, actualitzacions de segments o càlcul de mesures. La planificació justa us protegeix de la cua de recursos si hi ha un augment de llocs de treball sol·licitats. Al mateix temps, customer insights no garanteix que totes les feines que feu cua es processin en paral·lel.

[!INCLUDE [footer-include](includes/footer-banner.md)]
