---
title: Exportar segments a Snapchat (versió preliminar)
description: Apreneu a configurar la connexió i exportar a Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195370"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportar segments a Snapchat (versió preliminar)

Exporteu segments de perfils de client unificats a Snapchat i utilitzeu-los per a la publicitat.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://business.snapchat.com/) de Snapchat Business, un [compte](https://ads.snapchat.com/) de Snapchat Ads i les credencials d'administrador corresponents. Com a mínim heu de ser membre d'un compte d'organització i gestor de dades d'un compte d'anunci específic.
- Almenys un públic de Snapchat gestor d'audiències del tipus SAM (Snap Audience Match).
- L'identificador [de segment / públic de Snapchat](https://businesshelp.snapchat.com/s/article/custom-audiences). L'identificador del públic es pot trobar a l'URL després de seleccionar el públic al gestor d'audiències de Snapchat.
- [Segments configurats](segments.md) al Customer Insights.
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 1 milió de perfils de clients, que poden trigar fins a 15 minuts a completar-se.
- Només segments.

## <a name="set-up-connection-to-snapchat"></a>Configuració de la connexió a Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Snapchat**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Autentica amb Snapchat** i proporcioneu les vostres credencials d'administració per a Snapchat.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Snapchat. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Introduïu l'identificador **de segment / públic de** Snapchat.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
