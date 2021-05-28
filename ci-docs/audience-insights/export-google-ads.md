---
title: Exportar dades del Customer Insights a Google Ads
description: Apreneu a configurar la connexió i exportar a Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976306"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segments a Google Ads (versió preliminar)

Exporteu els segments de perfils de client unificats a la llista de públics de Google Ads i utilitzeu-los per anunciar-vos a la Cerca de Google, Gmail, YouTube i la Xarxa de Display de Google. 

## <a name="prerequisites-for-connection"></a>Requisits previs per a la connexió

-   Teniu un [compte de Google Ads](https://ads.google.com/) i les credencials d'administrador corresponents.
-   Teniu un [testimoni aprovat de Google Ads per a desenvolupadors](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   Compliu els requisits de la [Política de segments de clients](https://support.google.com/adspolicy/answer/6299717)
-   Compliu els requisits de les [mides de la llista de remàrqueting](https://support.google.com/google-ads/answer/7558048) 

-   Hi ha públics a Google Ads amb els identificadors corresponents. Per obtenir més informació, vegeu [Públics de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Teniu [segments configurats](segments.md).
-   Els perfils de client unificats dels segments exportats contenen camps que representen una adreça electrònica, el nom i el cognom.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a un milió de perfils per exportació a Google Ads.
- L'exportació a Google Ads es limita als segments.
- L'exportació de segments amb un total d'un milió de perfils pot durar fins a 5 minuts a causa de les possibles limitacions del proveïdor. 
- Les coincidències a Google Ads poden trigar fins a 48 hores.

## <a name="set-up-connection-to-google-ads"></a>Configuració de la connexió a Google Ads

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Google Ads** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el vostre **[ID de client de Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Introduïu el **[testimoni de desenvolupador autoritzat de Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Autenticació amb el Google Ads** i indiqueu les vostres credencials de Google Ads.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió. 

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Google Ads. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Introduïu el vostre **[Identificador de públic de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i seleccioneu **Connecta't** per inicialitzar la connexió a Google Ads.

1. A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client. Repetiu els mateixos passos per als camps **Nom** i **Cognom**.

1. Seleccioneu els segments que voleu exportar. Podeu exportar fins a un total d'un milió de perfils de client a Google Ads.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a Google Ads, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Google Ads compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
