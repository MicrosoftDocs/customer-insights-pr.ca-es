---
title: Exportar dades del Customer Insights a Google Ads
description: Apreneu a configurar la connexió a Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598235"
---
# <a name="connector-for-google-ads-preview"></a>Connector per a Google Ads (versió preliminar)

Exporteu els segments de perfils de client unificats a la llista de públics de Google Ads i utilitzeu-los per anunciar-vos a la Cerca de Google, Gmail, YouTube i la Xarxa de Display de Google. 

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte de Google Ads](https://ads.google.com/) i les credencials d'administrador corresponents.
-   Hi ha públics a Google Ads amb els identificadors corresponents. Per obtenir més informació, vegeu [Públics de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Teniu [segments configurats](segments.md).
-   Els perfils de client unificats dels segments exportats contenen camps que representen una adreça electrònica, el nom i el cognom.

## <a name="connect-to-google-ads"></a>Connecta a Google Ads

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A **Google Ads**, seleccioneu **Configura**.

1. Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.

1. Introduïu el vostre **[ID de client de Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Introduïu el **[testimoni de desenvolupador autoritzat de Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Introduïu el vostre **[Identificador de públic de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i seleccioneu **Connecta't** per inicialitzar la connexió a Google Ads.

1. Seleccioneu **Autenticació amb el Google Ads** i indiqueu les vostres credencials de Google Ads.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Captura de pantalla d'exportació per a la connexió a Google Ads":::

1. Seleccioneu **Següent** per configurar l'exportació.

## <a name="configure-the-connector"></a>Configurar el connector

1. A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client. Repetiu els mateixos passos per als camps **Nom** i **Cognom**.

1. Seleccioneu els segments que voleu exportar. Podeu exportar fins a un total d'un milió de perfils de client a Google Ads.

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab). A Google Ads, ara podeu cercar els segments als [públics de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a un milió de perfils per exportació a Google Ads.
- L'exportació a Google Ads es limita als segments.
- L'exportació de segments amb un total d'un milió de perfils pot durar fins a 5 minuts a causa de les possibles limitacions del proveïdor. 
- Les coincidències a Google Ads poden trigar fins a 48 hores.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a Google Ads, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Google Ads compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]