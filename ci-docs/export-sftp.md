---
title: Exporta dades a amfitrions SFTP (previsualització) (conté vídeo)
description: Apreneu a configurar la connexió i exportar a una ubicació SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207217"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Exportar dades a amfitrions SFTP (visualització prèvia)

Utilitzeu les dades de client en aplicacions de tercers exportant-les a una ubicació de Protocol de transferència segura de fitxers (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Requisits previs

- Disponibilitat d'un amfitrió SFTP i les credencials corresponents.

## <a name="known-limitations"></a>Limitacions conegudes

- Actualment, les destinacions SFTP darrere dels tallafocs no són compatibles.
- El temps d'execució d'una exportació depèn del rendiment del sistema. Us recomanem dos nuclis de CPU i 1 Gb de memòria com a configuració mínima del vostre servidor.
- Fins a 100 milions de perfils de clients, que poden trigar 90 minuts en utilitzar la configuració mínima recomanada de dos nuclis de CPU i 1 Gb de memòria.
- Si utilitzeu una clau SSH per a l'autenticació, assegureu-vos [de crear la clau](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) privada com a format PEM o SSH.COM. Si utilitzeu Putty, convertir la vostra clau privada exportant és com Open SSH. S'admeten els següents formats de clau privada:
  - RSA en format PEM i ssh.com OpenSSL
  - DSA en format PEM i ssh.com OpenSSL
  - ECDSA 256/384/521 en format PEM OpenSSL
  - ED25519 i RSA en format clau OpenSSH

## <a name="set-up-connection-to-sftp"></a>Configuració de la connexió a SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **SFTP**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Trieu si voleu autenticar-vos mitjançant SSH o nom d'usuari/contrasenya per a la vostra connexió i proporcioneu els detalls necessaris. Si utilitzeu una clau SSH per a l'autenticació, assegureu-vos [de crear la clau](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) privada com a format PEM o SSH.COM. Si utilitzeu Putty, convertir la vostra clau privada exportant és com Open SSH. S'admeten els següents formats de clau privada:
   - RSA en format PEM i ssh.com OpenSSL
   - DSA en format PEM i ssh.com OpenSSL
   - ECDSA 256/384/521 en format PEM OpenSSL
   - ED25519 i RSA en format clau OpenSSH

1. Seleccioneu **Verifica** per provar la connexió.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció SFTP. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Trieu si voleu exportar les dades **Comprimides** o **Descomprimides** i el **delimitador de camp** per als fitxers exportats.

1. Seleccioneu les entitats, per exemple els segments, que voleu exportar.

   > [!NOTE]
   > Cada entitat seleccionada es dividirà en un màxim de cinc fitxers de sortida quan s'exporti.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> L'exportació d'entitats que contenen una gran quantitat de dades pot conduir a diversos fitxers CSV a la mateixa carpeta per a cada exportació. La divisió de les exportacions es produeix per raons de rendiment per minimitzar el temps que triga a completar-se una exportació.

[!INCLUDE [footer-include](includes/footer-banner.md)]
