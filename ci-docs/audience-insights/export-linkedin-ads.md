---
title: Exportar dades del Customer Insights a LinkedIn Ads
description: Apreneu a configurar la connexió i exportar a LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 867a6541734746f75a35faaa8d3861e0479d6114
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866876"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportar segments a LinkedIn Ads (versió preliminar)

Exporteu segments de perfils de client unificats a LinkedIn Ads per crear públics coincidents. Utilitzeu els públics coincidents per a la destinació de l'empresa i la destinació de contactes.

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) i les credencials d'administrador corresponents.
-   Teniu [segments configurats](segments.md) a les conclusions del públic.
-   Els perfils de client als segments exportats contenen un camp amb una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- El segment de Customer Insights ha de contenir com a mínim 300 perfils únics. 
- Podeu exportar fins a 100.000 perfils de client per exportació a LinkedIn Ads.
- L'exportació a LinkedIn Ads es limita als segments.
- L'exportació de fins a 100.000 perfils de client a LinkedIn Ads pot trigar fins a 10 minuts a completar-se. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Configurar la connexió a LinkedIn Ads

1. A les conclusions del públic, aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **LinkedIn Ads** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte és administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcioneu [l'identificador del compte LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a Campaign Monitor.

1. Seleccioneu **AUTENTICA amb el LinkedIn** i proporcioneu les vostres credencials d'administrador per a LinkedIn Campaign Manager.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar una exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció LinkedIn Ads. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Trieu si voleu exportar les dades per fer [segmentació de contactes](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [segmentació d'empreses](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) a LinkedIn. 

1. A la secció **Coincidència de dades**, per a la destinació dels contactes, seleccioneu com a mínim un camp que representi l'adreça electrònica, l'identificador d'anunci d'Apple, l'identificador d'anunci de Google, l'identificador d'usuari de Google o nom i cognom d'un client. Si trieu la destinació d'empresa, seleccioneu com a mínim un camp que representi un nom d'empresa, un domini de correu electrònic, l'URL de la pàgina del LinkedIn, el símbol borsari o el lloc web. Es poden seleccionar altres camps per definir encara més l'exportació. 

1. Seleccioneu els segments que voleu exportar. Els públics coincidents de LinkedIn Campaign Manager es crearan automàticament amb el nom dels segments que heu seleccionat per exportar. Cada segment serà un públic coincident diferent. 

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan activeu Dynamics 365 Customer Insights transmetre dades a LinkedIn Ads, permeteu la transferència de dades fora del límit de compliment de Dynamics 365 Customer Insights, incloses dades potencialment sensibles, com ara dades personals. Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que LinkedIn Ads compleixi les obligacions de privadesa o de seguretat que pugueu teniu. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per aturar l'ús d'aquesta funcionalitat.
