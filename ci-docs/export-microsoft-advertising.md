---
title: Exportar segments al Microsoft Advertising (versió preliminar)
description: Apreneu a configurar la connexió i exportar al Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196520"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportar segments al Microsoft Advertising (versió preliminar)

Exporteu els segments del Customer Insights al Microsoft Advertising per crear públics del Customer Match. Utilitzeu aquests públics per a les campanyes publicitàries.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://ads.microsoft.com/) de Microsoft Advertising i les credencials d'administrador corresponents.
- Identificador de client i identificador de compte de Microsoft Advertising. Cerqueu l'ID de client (`cid`) i l'identificador de compte (`aid`) als paràmetres de l'adreça URL quan hàgiu iniciat la sessió al Microsoft Advertising.
- S'accepten les condicions d'ús de La segmentació per llista de clients.
- [Segments configurats](segments.md) al Customer Insights.
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 500.000 perfils de client per exportació a Microsoft Advertising, que poden trigar fins a 10 minuts.
- Només segments.

## <a name="set-up-connection-to-microsoft-advertising"></a>Configurar la connexió amb Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Microsoft Advertising**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte són els administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu l'identificador **de** client de Microsoft Advertising.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Autentica amb el Microsoft Advertising** i proporcioneu les vostres credencials d'administració per al Microsoft Advertising.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció del Microsoft Advertising. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Seleccioneu els segments que voleu exportar. Els públics del Customer Match al Microsoft Advertising es creen automàticament amb el nom dels segments seleccionats per a l'exportació. Cada segment serà un públic diferent al Customer Match.

1. Introduïu **l'identificador de client i l'identificador de compte de Microsoft Advertising**.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp amb l'adreça electrònica d'un client.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
