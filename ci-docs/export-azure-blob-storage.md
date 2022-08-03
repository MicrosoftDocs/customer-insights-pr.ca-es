---
title: Exportar dades a un Emmagatzematge blob de l'Azure (visualització prèvia)
description: Apreneu a configurar la connexió i exportar a l'Emmagatzematge blob.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195692"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exportar dades a un Emmagatzematge blob de l'Azure (visualització prèvia)

Emmagatzemeu les dades del Customer Insights a l'Emmagatzematge blob de l'Azure o utilitzeu-lo per transferir les vostres dades a altres aplicacions.

## <a name="prerequisites"></a>Requisits previs

- Un [nom de compte i una clau de compte](/azure/storage/blobs/create-data-lake-storage-account) de l'Azure Blob Storage. Per trobar el nom i la clau, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitacions conegudes

- Per a l'emmagatzematge blob de l'Azure, trieu entre [el nivell de rendiment estàndard i el nivell de rendiment Premium](/azure/storage/blobs/storage-blob-performance-tiers). Si trieu el nivell de rendiment prèmium, seleccioneu els [blobs en bloc prèmium com a tipus de compte](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Configurar la connexió a Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Emmagatzematge blob de l'Azure**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte de l'emmagatzematge blob.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Per configurar aquesta exportació, heu de tenir [permisos](export-destinations.md#set-up-a-new-export) per a aquest tipus de connexió.

> [!IMPORTANT]
> Si heu activat la [configuració](/azure/storage/blobs/soft-delete-blob-enable) de supressió suau per al compte d'emmagatzematge blob de l'Azure, les exportacions fallaran. Desactiveu l'eliminació provisional per exportar dades a blobs.

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió a la secció Emmagatzematge blob de l'Azure. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Introduïu el nom de la carpeta per a l'emmagatzematge Blob.

1. Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Les dades exportades s'emmagatzemen al contenidor de l'Emmagatzematge blob que heu configurat. Els següents camins de carpeta es creen automàticament al contenidor:

- Per a les entitats i entitats d'origen generades pel sistema:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Exemple: Dynamics365Duans/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > L'exportació d'entitats que contenen una gran quantitat de dades pot conduir a diversos fitxers CSV a la mateixa carpeta per a cada exportació. La divisió de les exportacions es produeix per raons de rendiment per minimitzar el temps que triga a completar-se una exportació.

- El model.json per a les entitats exportades resideix al *%ExportDestinationName%* nivell.  
  
  Exemple: Dynamics365Duans/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
