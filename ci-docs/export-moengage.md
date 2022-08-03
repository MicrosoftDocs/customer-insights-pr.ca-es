---
title: Segments d'exportació a MoEngage
description: Obtén informació sobre com configurar la connexió i exportar a MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199185"
---
# <a name="export-segments-to-moengage-preview"></a>Exportar segments a MoEngage (previsualització)

Exporta segments de perfils de clients unificats a MoEngage i utilitza'ls per a email màrqueting a MoEngage.

## <a name="prerequisites-for-a-connection"></a>Requisits previs per a una connexió

- [Compte de MoEngage](https://www.moengage.com/) i credencials d'administrador corresponents.
- Clau d'API de MoEngage des de Settings > API a MoEngage.
- [Segments configurats](segments.md) al Customer Insights.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 100.000 perfils de clients per exportació a MoEngage, que poden trigar fins a 15 minuts. El nombre de perfils de clients que pots exportar a MoEngage depèn del teu contracte amb MoEngage.
- Només segments.

## <a name="set-up-connection-to-moengage"></a>Configurar la connexió amb MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **MoEngage** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu la clau [API i identificador de l'API de MoEngage Data](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió a MoEngage.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una exportació**.

1. **Al camp Connexió per a l'exportació**, trieu una connexió de la secció MoEngage. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. Repetiu els mateixos passos per a altres camps opcionals.

1. Seleccioneu els segments que voleu exportar. Crearem un o més segments amb el mateix nom que els segments seleccionats a MoEngage a **Segments** > **personalitzats**.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
