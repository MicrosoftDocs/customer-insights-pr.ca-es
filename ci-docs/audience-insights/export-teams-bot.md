---
title: Bot per al Microsoft Teams
description: Cerqueu els perfils de client unificats al Microsoft Teams amb l'ajuda d'un bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e563619f40be859f3f02638adbd60b80423182b3
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554338"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot del Teams per al Dynamics 365 Customer Insights (versió preliminar)

Connecteu amb el Microsoft Teams per permetre que un bot cerqui perfils de client unificats a canals del Teams.

> [!div class="mx-imgBorder"]
> ![Bot del Teams que mostra un registre de client.](media/teams-bot.png "Bot del Teams que mostra un registre de client")

## <a name="prerequisites"></a>Requisits previs

Per configurar i configurar el bot, cal complir els requisits previs següents:

- S'ha afegit com a mínim una [font de dades](data-sources.md).
- El [procés d'unificació](data-unification.md) s'ha completat.
- S'han afegit camps a l'[índex de cerca i filtratge](search-filter-index.md).
- El Customer Insights i el Teams es troben a la mateixa organització.

## <a name="configure-the-bot"></a>Configurar el bot

1. A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.
1. A la peça del Microsoft Teams, seleccioneu **Configura**.
1. Se us redirigirà a l'àrea **Aplicacions** del Teams. També podeu obrir el Teams i seleccionar **Aplicacions** a la cantonada inferior esquerra o [obtenir-ho des d'AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directament.
1. Cerqueu **Customer Insights** i seleccioneu l'aplicació.
1. Seleccioneu **Afegeix**.
1. Després d'iniciar la sessió al Customer Insights al Teams, veureu un missatge de benvinguda i podreu començar.

## <a name="things-you-can-do-with-the-bot"></a>Què podeu fer amb el bot

El bot proporciona la capacitat de cerca de perfils unificats de client.

- Introduïu **cerca** seguit d'un nom, una adreça de correu electrònic o qualsevol altre camp al perfil del client unificat que s'hagi afegit a l'índex de cerca i de filtratge.

  Obtindreu una targeta amb fins a 15 camps del perfil de client resultant. Les coincidències múltiples retornen una llista de resultats on podeu seleccionar un perfil. Podeu afegir el terme de cerca entre cometes dobles per cercar una coincidència exacta.

- Si l'organització manté diversos entorns del Customer Insights a la mateixa organització, podeu introduir **switchinstance** per triar a quin entorn voleu connectar el bot.

- Introduïu **ajuda** per veure una llista de les ordres disponibles per al bot.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]