---
title: Exportar dades del Customer Insights a un Emmagatzematge blob de l'Azure
description: Apreneu a configurar la connexió i exportar a l'Emmagatzematge blob.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 623926bf520b19ee4156b7a05e953241cd819e9e
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947126"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Exportar la llista de segments i altres dades a l'Emmagatzematge blob de l'Azure (versió preliminar)

Emmagatzemeu les dades del Customer Insights a l'Emmagatzematge blob de l'Azure o utilitzeu-lo per transferir les vostres dades a altres aplicacions.

## <a name="known-limitations"></a>Limitacions conegudes

1. Per a l'Azure Blob Storage podeu triar entre el [nivell de rendiment estàndard i el de rendiment prèmium](/azure/storage/blobs/storage-blob-performance-tiers). Si trieu el nivell de rendiment prèmium, seleccioneu els [blobs en bloc prèmium com a tipus de compte](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Configurar la connexió a l'emmagatzematge blob

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Emmagatzematge blob de l'Azure** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte de l'emmagatzematge blob.
    - Per obtenir més informació sobre com trobar el compte i la clau del compte de l'emmagatzematge blob, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).
    - Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccioneu **Desa** per completar la connexió. 

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Si heu activat la configuració d'eliminació provisional del compte de l'Emmagatzematge de l'Azure BLOB, les exportacions fallaran. Desactiveu l'eliminació provisional per exportar dades a blobs. Per obtenir més informació, vegeu [Habilitar l'eliminació provisional del blob](/azure/storage/blobs/soft-delete-blob-enable)

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió a la secció Emmagatzematge blob de l'Azure. Si no veieu aquest nom de secció, no hi ha disponible cap connexió d'aquest tipus.

1. Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).

També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).

Les dades exportades s'emmagatzemen al contenidor de l'Emmagatzematge blob que heu configurat. Els següents camins de carpeta es creen automàticament al contenidor:

- Per a les entitats i entitats d'origen generades pel sistema:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Exemple: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
  
  > [!TIP]
  > L'exportació d'entitats que contenen una gran quantitat de dades pot donar lloc a diversos fitxers CSV a la mateixa carpeta per a cada exportació. La divisió de les exportacions es produeix per raons de rendiment per minimitzar el temps que triga una exportació a completar-se.

- El model.json de les entitats exportades estarà al nivell %ExportDestinationName%.  
  - Exemple: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
