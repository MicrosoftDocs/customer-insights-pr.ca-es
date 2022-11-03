---
title: Exportar segments a Sendinblue (versió preliminar)
description: Més informació sobre com configurar la connexió i l'exportació a Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724882"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportar segments a Sendinblue (versió preliminar)

Exporteu els segments de perfils de client unificats per generar campanyes, proporcionar contingut de màrqueting per correu electrònic i utilitzar grups específics de clients amb Sendinblue.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://www.sendinblue.com/) de Sendinblue i les credencials d'administrador corresponents.
- Una [clau d'API de SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Llistes existents a Sendinblue i els identificadors corresponents.
- [Segments configurats](segments.md).
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- No s'admet l'enllaç privat en combinació amb Bring your own storage (BYOS).
- Fins a 1 milió de perfils de clients per exportació a Sendinblue, que pot trigar fins a 90 minuts a completar-se. El nombre de perfils de clients als quals podeu exportar Sendinblue depèn del vostre contracte amb Sendinblue.
- Només segments.

## <a name="set-up-connection-to-sendinblue"></a>Configuració de la connexió a Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Sendinblue**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu la vostra **clau** d'API de SendinBlue.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Sendinblue. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Introduïu el vostre **identificador de** llista Sendinblue.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client.

1. Opcionalment, exporteu **nom**, **cognom** i **Telèfon** per crear correus electrònics més personalitzats. Seleccioneu **Afegeix un atribut** per assignar aquests camps.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
