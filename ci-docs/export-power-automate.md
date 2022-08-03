---
title: Power Automate connector (vista prèvia) | Documents de Microsoft
description: Creeu fluxos al Microsoft Power Automate des del Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196106"
---
# <a name="power-automate-connector-preview"></a>Connector del Power Automate (visualització prèvia)

Dispareu esdeveniments específics perquè s'activin automàticament quan canviïn les dades i administreu fluxos més complexos directament al [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitacions conegudes

- Un màxim de 100 trucades per cada 60 segons. Utilitzeu el [paràmetre](/connectors/customerinsights/#get-items-from-an-entity) $skip per trucar al punt final de l'API diverses vegades.

## <a name="power-automate-triggers"></a>Disparadors del Power Automate

Utilitzeu disparadors per crear fluxos de núvol i automatitzar tasques repetitives, com ara notificacions o accions més avançades. Utilitzeu activadors quan:

- Falla una actualització font de dades.
- Una actualització font de dades triomfa.
- Es creua un llindar en un segment. El disparador es limita a haver superat el llindar.
- Es creua un llindar en una mesura empresarial. Només són compatibles les mesures empresarials sense cap dimensió. El disparador es limita a haver superat el llindar.
- Es completa una actualització completa programada. Aquest activador no funciona per a les actualitzacions iniciades manualment.
- Es completa una actualització del procés d'unificació.

[Configureu els disparadors al Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Accions del Power Automate

El connector del Power Automate proporciona altres accions que els disparadors disponibles. Per obtenir més informació, vegeu la [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Crear un flux del Power Automate

1. Aneu a **Administració** > **Connexions**.

1. A la peça del **Power Automate**, seleccioneu **Configura**.

1. El connector del Customer Insights (versió preliminar) al Power Automate s'obre. **Inicieu la sessió** al Power Automate.

1. Trieu un dels disparadors disponibles i afegiu més passos al flux nou. Per obtenir més informació, vegeu [Crear un flux de núvol al Power Automate](/power-automate/get-started-logic-flow).

Exemples de com utilitzar els fluxos: 
- Publicar un missatge a un canal del Microsoft Teams si es produeix un error en actualitzar la font de dades. 
- Enviar un correu electrònic als propietaris de les dades quan se superi un llindar en un segment.

[!INCLUDE [footer-include](includes/footer-banner.md)]
