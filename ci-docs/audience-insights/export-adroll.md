---
title: Exportar dades del Customer Insights a AdRoll
description: Apreneu a configurar la connexió i exportar a AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a318750077c71a17e5a47c40722f6153e6640f3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227608"
---
# <a name="export-segments-to-adroll-preview"></a>Exportar segments a AdRoll (versió preliminar)

Exporteu segments de perfils de client unificats a AdRoll i utilitzeu-los per a la publicitat. 

## <a name="prerequisites-for-a-connection"></a>Requisits previs per a una connexió

-   Teniu un [compte d'AdRoll](https://www.adroll.com/) i les credencials d'administrador corresponents.
-   Teniu [segments configurats](segments.md) a les conclusions del públic.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Podeu exportar fins a 250.000 perfils de client alhora a AdRoll.
- No podeu exportar segments amb menys de 100 perfils de client a AdRoll. 
- L'exportació a AdRoll es limita als segments.
- L'exportació de fins a 250.000 perfils de client a AdRoll pot trigar fins a 10 minuts a completar-se. 
- El nombre de perfils de client que podeu exportar a AdRoll depèn del vostre contracte amb AdRoll.

## <a name="set-up-connection-to-adroll"></a>Configuració de la connexió a AdRoll

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **AdRoll** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a AdRoll.

1. Seleccioneu **Autenticació amb AdRoll** i indiqueu les vostres credencials d'administrador d'AdRoll. 

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció AdRoll. Si no veieu aquest nom de secció, no hi ha disponible cap connexió d'aquest tipus.

1. Introduïu l'**ID d'anunciant d'AdRoll**. Per obtenir més informació, vegeu [Perfils d'anunciant d'AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. Cal que exporteu segments a AdRoll.

1. Seleccioneu els segments que voleu exportar. Seleccioneu un segment amb un mínim de 100 membres. No podeu exportar segments més petits. A més, la mida màxima d'un segment que s'ha d'exportar és de 250.000 membres per exportació. 

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). 

També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a AdRoll, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que AdRoll compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
