---
title: Exportar segments a Criteo (preview)
description: Aprèn a configurar la connexió i exportar a Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 61435030254638965fbeb7980312e73695416aa2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724777"
---
# <a name="export-segments-to-criteo-preview"></a>Exportar segments a Criteo (preview)

Exporta segments de perfils de clients unificats per generar campanyes, proporcionar email màrqueting i utilitzar grups específics de clients amb Criteo.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://www.criteo.com/login/) de Criteo Dynamics Retargeting i les credencials d'administrador corresponents.
- [Segments configurats](segments.md).
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- No s'admet l'enllaç privat en combinació amb Bring your own storage (BYOS).
- Fins a 1 milió de perfils de clients per exportació a Criteo, que poden trigar fins a 30 minuts a completar-se. El nombre de perfils de clients que pots exportar a Criteo depèn del teu contracte amb Criteo.
- Només segments.

## <a name="set-up-connection-to-criteo"></a>Establir connexió amb Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Selecciona **Afegeix connexió** i tria **Criteo**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Autentica't amb Criteo** i proporciona el teu nom d'usuari d'administrador i les credencials per a Criteo.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. **Al camp Connexió per a l'exportació**, trieu una connexió de la secció Criteo. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
