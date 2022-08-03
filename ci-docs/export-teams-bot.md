---
title: Bot del Teams per al Dynamics 365 Customer Insights (versió preliminar)
description: Cerqueu els perfils de client unificats al Microsoft Teams amb l'ajuda d'un bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195830"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot del Teams per al Dynamics 365 Customer Insights (versió preliminar)

Connecteu amb el Microsoft Teams per permetre que un bot cerqui perfils de client unificats a canals del Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot del Teams que mostra un registre de client":::

## <a name="prerequisites"></a>Requisits previs

- S'hi ha afegit almenys un [font de dades](data-sources.md).
- El [procés d'unificació](data-unification.md) s'ha completat.
- Els camps s'afegeixen a l'índex de [cerca i filtre](search-filter-index.md).
- El Customer Insights i el Teams es troben a la mateixa organització.
- L'entorn té definits com a públic de destinació principal clients individuals. Els comptes empresarials no estan admesos.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Configurar el bot

1. Aneu a **Administració** > **Connexions**.
1. A la peça del Microsoft Teams, seleccioneu **Configura**.
1. Se us redirigirà a l'àrea **Aplicacions** del Teams. També podeu obrir el Teams i seleccionar **Aplicacions** a la cantonada inferior esquerra o [obtenir-ho des d'AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directament.
1. Cerqueu **Customer Insights** i seleccioneu l'aplicació.
1. Seleccioneu **Afegeix**.
1. Inicieu sessió a Customer Insights al Teams. Es mostra un missatge de benvinguda.

## <a name="things-you-can-do-with-the-bot"></a>Què podeu fer amb el bot

El bot proporciona la capacitat de cerca de perfils unificats de client.

- Introduïu **la cerca** seguida d'un nom, una adreça electrònica o qualsevol altre camp del perfil de client unificat que s'afegeixi a l'índex de cerca i filtre.

  Obtindreu una targeta amb fins a 15 camps del perfil de client resultant. Les coincidències múltiples retornen una llista de resultats on podeu seleccionar un perfil. Per cercar una coincidència exacta, afegiu el terme de cerca entre cometes dobles.

- Si la vostra organització manté diversos entorns del Customer Insights a la mateixa organització, introduïu **switchinstance** per triar a quin entorn voleu connectar el bot.

- Introduïu **ajuda** per veure una llista de les ordres disponibles per al bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]