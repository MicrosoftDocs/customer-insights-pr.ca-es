---
title: Exportar segments a Autopilot (versió preliminar)
description: Apreneu a configurar la connexió i exportar a Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 449d2c5e32697e4a5d2c9dff4a5a1cbdb26aeb4d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195048"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportar segments a Autopilot (versió preliminar)

Exporteu segments de perfils de client unificats a Autopilot i utilitzeu-los per al màrqueting per correu electrònic a Autopilot.

## <a name="prerequisites-for-a-connection"></a>Requisits previs per a una connexió

- Un compte [d'Autopilot](https://www.autopilothq.com/) i les credencials d'administrador corresponents.
- Una clau de l'API [d'Autopilot](https://autopilot.docs.apiary.io/#)
- [Segments configurats](segments.md) al Customer Insights.
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 100,000 perfils de clients per exportació a Autopilot, que poden trigar fins a unes hores a completar-se. El nombre de perfils de clients que podeu exportar a Autopilot depèn del vostre contracte amb Autopilot.
- Només segments.

## <a name="set-up-connection-to-autopilot"></a>Configuració de la connexió a Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Pilot automàtic**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu la clau de l'API d'Autopilot.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Autopilot. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client.

1. Opcionalment, exporteu altres camps, com **ara nom** i **cognom**.

1. Seleccioneu els segments que voleu exportar seguint les limitacions conegudes.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
