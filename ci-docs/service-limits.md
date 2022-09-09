---
title: Límits de servei al Customer Insights
description: Entendre els límits i les restriccions del servei SaaS del Customer Insights.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411728"
---
# <a name="service-limits-in-customer-insights"></a>Límits de servei al Customer Insights

 El Customer Insights té límits integrats dissenyats per garantir la fiabilitat i l'estabilitat del servei. Qualsevol sol·licitud de canvi es pot fer a través del [Fòrum d'idees](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Àrees  | Límits  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments, mesures i prediccions | 300  | El nombre total de [segments](segments.md), [mesures](measures.md) i [prediccions](predictions-overview.md) combinades no pot superar els 300.  |
| Relacions | 20 nivells de profunditat en les relacions en camins d'entitat. | En crear [segments](segments.md) o [mesures](measures.md) mitjançant la interfície del constructor, els camins d'entitat poden tenir fins a 20 salts de relació entre l'entitat inicial i l'entitat de destinació.  |

## <a name="fair-scheduling-of-jobs"></a>Programació justa de llocs de treball

El Customer Insights és un servei SaaS que utilitza recursos compartits de l'Azure. Els clients solen tenir càrregues de treball d'intensitat variable i en horaris diferents. Per garantir un accés just als recursos subjacents, ens assegurem que els processos del sistema s'executin en ordre just. Exemples de processos del sistema són treballs relacionats amb la unificació de dades, actualitzacions de segments o càlcul de mesures. La programació justa us protegeix de fer cues per obtenir recursos si hi ha un pic de llocs de treball sol·licitats. Al mateix temps, el Customer Insights no garanteix que tots els treballs que feu a la cua es processin en paral·lel.

[!INCLUDE [footer-include](includes/footer-banner.md)]
