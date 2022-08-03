---
title: Exportar segments a Google Ads (versió preliminar)
description: Apreneu a configurar la connexió i exportar a Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196566"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segments a Google Ads (versió preliminar)

Exporteu segments de perfils de client unificats a una llista de públics de Google Ads i utilitzeu-los per anunciar-vos a la cerca de Google, Gmail, YouTube i a la Xarxa de Display de Google.

## <a name="prerequisites"></a>Requisits previs

- Un [compte de](https://ads.google.com/) Google Ads i les credencials d'administrador corresponents.
- Un [identificador de client de Google Ads](https://support.google.com/google-ads/answer/1704344).
- Es compleixen els requisits de la [Política de segmentació per llista de](https://support.google.com/adspolicy/answer/6299717) clients.
- Es compleixen els requisits de les mides [de les](https://support.google.com/google-ads/answer/7558048) llistes de remàrqueting.
- [Segments configurats](segments.md).
- Els perfils de client unificats dels segments exportats contenen camps que representen una adreça electrònica, un telèfon, un identificador d'anunciant mòbil, un identificador d'usuari de tercers o una adreça.

## <a name="known-limitations"></a>Limitacions conegudes

- Exporteu fins a 1 milió de perfils de client per exportació a Google Ads, cosa que pot trigar fins a 30 minuts a completar-se a causa de les limitacions del proveïdor.
- Només segments.
- La coincidència a Google Ads pot trigar fins a 48 hores.

## <a name="set-up-connection-to-google-ads"></a>Configuració de la connexió a Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Google Ads**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu l'identificador de client de Google Ads.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Autenticació amb el Google Ads** i indiqueu les vostres credencials de Google Ads.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Google Ads. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Tria si vols utilitzar un públic existent o crear-ne un de nou:
   - Per actualitzar un públic de Google Ads existent, introduïu l'identificador de [públic de](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns) Google Ads.
   - Per crear un públic nou, deixeu el camp Identificador de públic de Google en blanc. Les estadístiques de client crearan automàticament un públic nou al compte de Google Ads i utilitzaran el nom del segment exportat.

1. A la **secció Coincidència** de dades, seleccioneu un o més camps de dades per exportar i seleccioneu el camp que representa els camps de dades corresponents al Customer Insights.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
