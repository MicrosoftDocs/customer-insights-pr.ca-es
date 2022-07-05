---
title: Power Automate connector (vista prèvia) | Documents de Microsoft
description: Creeu fluxos al Microsoft Power Automate des del Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29a861dad926072f6f849d738d868f0f3b9306be
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082444"
---
# <a name="power-automate-connector-preview"></a>Connector del Power Automate (visualització prèvia)

Dispareu esdeveniments específics perquè s'activin automàticament quan canviïn les dades i administreu fluxos més complexos directament al [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitacions conegudes

- Pots fer un màxim de 100 trucades per 60 segons. Podeu trucar al punt final de l'API diverses vegades mitjançant el paràmetre $skip. [Obteniu més informació sobre el paràmetre $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Disparadors del Power Automate

Utilitzeu disparadors per crear fluxos de núvol i automatitzar tasques repetitives, com ara notificacions o accions més avançades.

- Disparador per quan no es pot actualitzar la font de dades.
- Disparador per quan la font de dades s'actualitza correctament.
- Disparador per quan se supera un llindar en un segment. El disparador es limita a haver superat el llindar.
- Disparador per quan se supera un llindar en una mesura empresarial. Només són compatibles les mesures empresarials sense cap dimensió. El disparador es limita a haver superat el llindar.
- Disparador per quan hagi finalitzat una actualització completa de (fonts de dades, segments, mesures, etc.).
- Dispara quan es completa una actualització del procés d'unificació.

[Configureu els disparadors al Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Accions del Power Automate

El connector del Power Automate proporciona altres accions que els disparadors disponibles. Per obtenir més informació, vegeu la [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Crear un flux del Power Automate

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A la peça del **Power Automate**, seleccioneu **Configura**.

1. El connector del Customer Insights (versió preliminar) al Power Automate s'obre. **Inicieu la sessió** al Power Automate.

1. Trieu un dels disparadors disponibles i afegiu més passos al flux nou. Per obtenir més informació, vegeu [Crear un flux de núvol al Power Automate](/power-automate/get-started-logic-flow).

Exemples de com utilitzar els fluxos: 
- Publicar un missatge a un canal del Microsoft Teams si es produeix un error en actualitzar la font de dades. 
- Enviar un correu electrònic als propietaris de les dades quan se superi un llindar en un segment.



[!INCLUDE [footer-include](includes/footer-banner.md)]
