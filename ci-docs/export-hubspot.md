---
title: Exporta dades del Customer Insights a HubSpot
description: Obteniu més informació sobre com configurar la connexió i l'exportació a HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588924"
---
# <a name="export-segments-to-hubspot-preview"></a>Exporta segments a HubSpot (vista prèvia)

Exporta segments de perfils de clients unificats a HubSpot i utilitza'ls per al màrqueting per correu electrònic.

## <a name="prerequisites-for-a-connection"></a>Requisits previs per a una connexió

- A [HubSpot compte](https://www.hubspot.com/) i credencials d'administrador corresponents.
- [Clau](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) API de HubSpot.
- [Segments configurats](segments.md) al Customer Insights.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 100.000 perfils de clients per exportació a HubSpot, que pot trigar fins a 15 minuts a completar-se. El nombre de perfils de clients als quals podeu exportar HubSpot depèn i limita el vostre contracte amb HubSpot.
- Només segments.

## <a name="set-up-connection-to-hubspot"></a>Configurar la connexió amb HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **HubSpot** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el vostre HubSpot credencials quan se us demani.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió a HubSpot.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una exportació**.

1. **Al camp Connexió per a l'exportació**, trieu una connexió des de hubSpot secció. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. Repetiu els mateixos passos per a altres camps opcionals.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
