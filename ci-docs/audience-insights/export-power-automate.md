---
title: Connector del Power Automate | Microsoft Docs
description: Creeu fluxos al Microsoft Power Automate des del Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405123"
---
# <a name="power-automate-connector-preview"></a>Connector del Power Automate (visualització prèvia)

Dispareu esdeveniments específics perquè s'activin automàticament quan canviïn les dades i administreu fluxos més complexos directament al [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Disparadors del Power Automate

Podeu utilitzar diversos disparadors que us permeten crear fluxos per automatitzar tasques repetitives, com ara notificacions o accions més avançades. 

- Disparador per quan no es pot actualitzar la font de dades. 
- Disparador per quan la font de dades s'actualitza correctament.
- Disparador per quan se supera un llindar en un segment. El disparador es limita a haver superat el llindar.
- Disparador per quan se supera un llindar en una mesura empresarial. El disparador es limita a haver superat el llindar.
- Disparador per quan hagi finalitzat una actualització completa de (fonts de dades, segments, mesures, etc.).
- Es dispara quan s'ha completat una actualització del procés d'unificació (assignació, coincidència i combinació).

[Configureu els disparadors al Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Accions del Power Automate
El connector del Power Automate proporciona altres accions que els disparadors disponibles. Per obtenir més informació, vegeu la [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Crear un flux del Power Automate a les conclusions del públic

1. A les conclusions del públic, aneu a **Administració** > **Sistema**.

1. A la pàgina **Sistema**, seleccioneu la pestanya **Estat**.

1. A la secció **Fonts de dades**, seleccioneu **Fluxos** i seleccioneu **Crea un flux** a la llista desplegable.
   > [!div class="mx-imgBorder"]
   > ![Connector del Power Automate que mostra l'acció Crea un flux](media/power-automate-connector-create-flow.png "Connector del Power Automate que mostra l'acció Crea un flux")

1. Al Power Automate, seleccioneu un dels disparadors disponibles per crear el vostre flux preferit. Si esteu creant el vostre primer flux, haureu d'autenticar-vos primer amb el connector del Power Automate.
