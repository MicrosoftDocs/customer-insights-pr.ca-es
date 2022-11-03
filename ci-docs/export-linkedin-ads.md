---
title: Exportar segments a LinkedIn Ads (versió preliminar)
description: Apreneu a configurar la connexió i exportar a LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725296"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportar segments a LinkedIn Ads (versió preliminar)

Exporteu segments de perfils de client unificats a LinkedIn Ads per crear públics coincidents. Utilitzeu els públics coincidents per a la destinació de l'empresa i la destinació de contactes.

## <a name="prerequisites"></a>Requisits previs

- Un [LinkedIn Campaign Manager compte](https://business.linkedin.com/marketing-solutions/ads) i les credencials d'administrador corresponents.
- Un [LinkedIn Campaign Manager identificador de compte](https://www.linkedin.com/help/lms/answer/a424270).
- [Segments configurats](segments.md) al Customer Insights.
- Els segments exportats necessiten almenys un camp específic en funció de si trieu la segmentació per [contacte o](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) la [segmentació per](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) empresa a LinkedIn. Els camps possibles es mostren al pas Coincidència de dades **en**[configurar l'exportació](#configure-an-export).

## <a name="known-limitations"></a>Limitacions conegudes

- No s'admet l'enllaç privat en combinació amb Bring your own storage (BYOS).
- Fins a 100.000 perfils de clients per exportació a LinkedIn Ads, que poden trigar fins a 10 minuts a completar-se.
- Només segments. Un segment ha de contenir almenys 300 perfils únics.

## <a name="set-up-connection-to-linkedin-ads"></a>Configurar la connexió amb LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **LinkedIn Ads**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcioneu l'identificador LinkedIn Campaign Manager del compte.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Autentica amb LinkedIn** i proporcioneu les vostres credencials d'administrador per a LinkedIn Campaign Manager.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció LinkedIn Ads. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Trieu si voleu exportar les dades per fer [segmentació de contactes](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [segmentació d'empreses](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) a LinkedIn.

1. A la secció **Coincidència de dades**, per a la destinació dels contactes, seleccioneu com a mínim un camp que representi l'adreça electrònica, l'identificador d'anunci d'Apple, l'identificador d'anunci de Google, l'identificador d'usuari de Google o nom i cognom d'un client. Si trieu la destinació d'empresa, seleccioneu com a mínim un camp que representi un nom d'empresa, un domini de correu electrònic, l'URL de la pàgina del LinkedIn, el símbol borsari o el lloc web.

1. Opcionalment, afegiu camps per definir encara més l'exportació. Seleccioneu **Afegeix un atribut** per assignar aquests camps.

1. Seleccioneu els segments que voleu exportar. Els públics coincidents al LinkedIn Campaign Manager es crearan automàticament amb el nom dels segments que heu seleccionat per exportar. Cada segment serà un públic coincident diferent.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
