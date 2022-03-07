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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350395"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Límits de servei a les capacitats del Customer Insights

En aquest article es descriuen els límits incorporats al servei del Customer Insights que s'han dissenyat per garantir la fiabilitat i l'estabilitat del servei. Qualsevol sol·licitud de canvi es pot fer a través del [Fòrum d'idees](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Conclusions sobre el públic

| Àrees  | Límits  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments, mesures i prediccions | 300  | El nombre total de [segments](audience-insights/segments.md), [mesures](audience-insights/measures.md) i [prediccions combinats](audience-insights/predictions.md) no pot superar els 300.  |
| Relacions | 20 nivells de profunditat en les relacions en camins d'entitat. | En crear [segments](audience-insights/segments.md) o [mesures](audience-insights/measures.md) mitjançant la interfície del constructor, els camins d'entitat poden tenir fins a 20 salts de relació entre l'entitat inicial i l'entitat de destinació.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
