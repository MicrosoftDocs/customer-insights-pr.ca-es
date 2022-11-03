---
title: Exportar segments a Braze (previsualització)
description: Obteniu més informació sobre com configurar la connexió i exportar a Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725204"
---
# <a name="export-segments-to-braze-preview"></a>Exportar segments a Braze (previsualització)

Exporta segments de perfils de clients unificats a Braze i utilitza'ls per a activitats de màrqueting.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://www.braze.com/) de Braze i les credencials d'administrador corresponents.
- Una [clau d'API de Braze](https://www.braze.com/docs/api/basics/)
- El teu [punt final DE FRENS REST](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Segments configurats](segments.md) al Customer Insights.
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica i un identificador de client de Braze.

## <a name="known-limitations"></a>Limitacions conegudes

- No s'admet l'enllaç privat en combinació amb Bring your own storage (BYOS).
- Fins a 1 milió de perfils de clients a Braze, que poden trigar fins a 40 minuts a completar-se. El nombre de perfils de clients que podeu exportar a Braze depèn del vostre contracte amb Braze.
- Només segments.
- L'Azure Private Link no és compatible amb l'exportació braze.

## <a name="set-up-connection-to-braze"></a>Configurar la connexió amb Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Braze**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcioneu la vostra clau API braze per continuar iniciant la sessió.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. **Al camp Connexió per a l'exportació**, trieu una connexió de la secció Braze. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu el punt final REST al camp Nom de l'amfitrió **en** el format següent:`rest.iad-03.braze.com`.

1. Introduïu un nom per a l'exportació.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. Al camp Identificador **de** client, seleccioneu el camp que representa l'identificador Braze del client. Els segments de Braze es crearan amb el mateix nom del segment que a Dynamics 365 Customer Insights. Podeu triar més camps opcionals per a les dades coincidents.

1. Seleccioneu les entitats o segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
