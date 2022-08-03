---
title: Exportar dades a Azure Data Lake Storage Gen2 (vista prèvia)
description: Apreneu a configurar la connexió a l'Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196428"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Exportar dades a Azure Data Lake Storage Gen2 (vista prèvia)

Emmagatzemeu les dades del Customer Insights en un compte del Data Lake Storage Gen2 o utilitzeu-lo per transferir les vostres dades a altres aplicacions.

## <a name="prerequisites"></a>Requisits previs

- Un [compte d'emmagatzematge per utilitzar amb l'Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Per trobar el nom i la clau del compte d'emmagatzematge, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitacions conegudes

- Per a Azure Data Lake Storage Gen2, trieu entre [el nivell de rendiment estàndard i el nivell de rendiment Premium](/azure/storage/blobs/create-data-lake-storage-account). Si trieu el nivell de rendiment prèmium, seleccioneu els [blobs en bloc prèmium com a tipus de compte](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Configurar la connexió a Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Azure Data Lake Gen 2**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el **nom del compte**, la **clau del compte** i el **contenidor** per a l'Azure Data Lake Storage Gen2.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp Connexió per a l'exportació **·**, trieu una connexió de la secció Del llac de dades de l'Azure. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Introduïu el nom de la carpeta per a l'emmagatzematge Azure Data Lake Storage Gen2.

1. Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge de l'Azure Data Lake Gen 2 que heu configurat.

> [!TIP]
> L'exportació d'entitats que contenen una gran quantitat de dades pot conduir a diversos fitxers CSV a la mateixa carpeta per a cada exportació. La divisió de les exportacions es produeix per raons de rendiment per minimitzar el temps que triga a completar-se una exportació.

[!INCLUDE [footer-include](includes/footer-banner.md)]
