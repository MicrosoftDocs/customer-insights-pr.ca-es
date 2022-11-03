---
title: Exporta segments a Klaviyo (previsualització)
description: Més informació sobre com configurar la connexió i l'exportació a Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724565"
---
# <a name="export-segments-to-klaviyo-preview"></a>Exporta segments a Klaviyo (previsualització)

Exporteu segments de perfils de client unificats a Klaviyo i utilitzeu-los per a activitats de màrqueting.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://www.klaviyo.com/) de Klaviyo i les credencials d'administrador corresponents.
- Una [clau de l'API de Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- Un [identificador de llista Klaviyo](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Segments configurats](segments.md) al Customer Insights.
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- No s'admet l'enllaç privat en combinació amb Bring your own storage (BYOS).
- Fins a 1 milió de perfils de clients per exportació a Klaviyo, que poden trigar fins a 20 minuts a completar-se. El nombre de perfils de clients que podeu exportar a Klaviyo depèn del vostre contracte amb Klaviyo.
- Només segments.

## <a name="set-up-connection-to-klaviyo"></a>Configuració de la connexió a Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Klaviyo**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcioneu la clau de l'API del Klaviyo per continuar amb l'inici de sessió.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Autentica amb Klaviyo** i proporcioneu les vostres credencials d'administrador per al Klaviyo.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Klaviyo. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Introduïu el vostre **identificador de llista** Klaviyo.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
