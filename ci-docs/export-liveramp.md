---
title: Exportar segments a LiveRamp (versió preliminar)
description: Apreneu a configurar la connexió i exportar a LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196704"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportar segments a LiveRamp&reg; (versió preliminar)

Activeu les vostres dades a LiveRamp per connectar-vos amb més de 500 plataformes entre digital, social i televisió. Treballeu amb les dades de LiveRamp per orientar, suprimir i personalitzar les campanyes publicitàries.

## <a name="prerequisites"></a>Requisits previs

- Una subscripció liveRamp per utilitzar aquest connector. Per obtenir una subscripció, [poseu-vos en contacte amb LiveRamp](https://liveramp.com/contact/) directament. [Més informació sobre la incorporació a LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Limitacions conegudes

- L'exportació de LiveRamp utilitza una exportació SFTP. Actualment, les destinacions SFTP darrere dels tallafocs no són compatibles.
- Si utilitzeu una clau SSH per a l'autenticació, assegureu-vos [de crear la clau](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) privada com a format PEM o SSH.COM. Si utilitzeu Putty, convertir la vostra clau privada exportant és com Open SSH. S'admeten els següents formats de clau privada:
  - RSA en format PEM i ssh.com OpenSSL
  - DSA en format PEM i ssh.com OpenSSL
  - ECDSA 256/384/521 en format PEM OpenSSL
  - ED25519 i RSA en format clau OpenSSH
- El temps d'execució d'una exportació depèn del rendiment del sistema. Us recomanem dos nuclis de CPU i 1 Gb de memòria com a configuració mínima del vostre servidor.
- L'exportació d'entitats amb fins a 100 milions de perfils de clients pot tardar 90 minuts quan s'utilitza la configuració mínima recomanada de dos nuclis de CPU i 1 Gb de memòria.
- El nombre real de perfils (o dades) que podeu exportar al LiveRamp depèn de la vostra subscripció amb liveRamp.

## <a name="set-up-connection-to-liveramp"></a>Configuració de la connexió a LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **LiveRamp**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Trieu si voleu autenticar-vos mitjançant SSH o nom d'usuari/contrasenya per a la vostra connexió i proporcioneu els detalls necessaris.

1. Seleccioneu **Verifica** per provar la connexió amb LiveRamp.

1. Després de la verificació correcta, reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció LiveRamp. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Al camp Connecta dades **, seleccioneu** Correu electrònic **,** Nom i adreça **o** Telèfon **per enviar-lo al LiveRamp per a la resolució de la** identitat.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Connector de LiveRamp amb l'assignació d'atributs.":::

1. Assigneu els atributs corresponents de l'entitat *Client* per a l'identificador de clau seleccionat.

1. Seleccioneu **Afegeix un atribut** per assignar més atributs per enviar-los a LiveRamp.

   > [!TIP]
   > Si envieu més atributs d'identificador clau a LiveRamp, és possible que obtingueu una taxa de concordança més alta.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
