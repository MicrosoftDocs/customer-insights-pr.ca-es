---
title: Exportar segments a Campaign Monitor (versió preliminar)
description: Apreneu a configurar la connexió i exportar a Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196290"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportar segments a Campaign Monitor (versió preliminar)

Exporteu segments de perfils de client unificats a Campaign Monitor i utilitzeu-los per a activitats de màrqueting.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://www.campaignmonitor.com/) de Campaign Monitor i les credencials d'administrador corresponents.
- Un identificador [de llista de monitor de campanya](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Una [clau d'API](https://www.campaignmonitor.com/api/getting-started/) generada des de Configuració **del** compte al Campaign Monitor per obtenir l'identificador de llista de l'API.
- [Segments configurats](segments.md) al Customer Insights.
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 1 milió de perfils de clients per exportació a Campaign Monitor, que poden trigar fins a 20 minuts a completar-se. El nombre de perfils de clients que podeu exportar a Campaign Monitor depèn del contracte que tingueu amb Campaign Monitor.
- Només segments.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurar la connexió a Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Campaign Monitor**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a Campaign Monitor.

1. Seleccioneu **Autentica amb Campaign Monitor** i proporcioneu les vostres credencials d'administració per a Campaign Monitor.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Campaign Monitor. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Introduïu l'identificador **de** la llista de monitors de campanya.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. Cal que exporteu segments a Campaign Monitor.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
