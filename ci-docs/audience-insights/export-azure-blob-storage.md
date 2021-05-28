---
title: Exportar dades del Customer Insights a un Emmagatzematge blob de l'Azure
description: Apreneu a configurar la connexió i exportar a l'Emmagatzematge blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976122"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Exportar la llista de segments i altres dades a l'Emmagatzematge blob de l'Azure (versió preliminar)

Emmagatzemeu les dades del Customer Insights a l'Emmagatzematge blob de l'Azure o utilitzeu-lo per transferir les vostres dades a altres aplicacions.

## <a name="set-up-the-connection-to-blob-storage"></a>Configurar la connexió a l'Emmagatzematge blob

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Emmagatzematge blob de l'Azure** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte de l'Emmagatzematge blob.
    - Per obtenir més informació sobre com trobar el compte i la clau del compte de l'Emmagatzematge blob, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).
    - Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccioneu **Desa** per completar la connexió. 

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió a la secció Emmagatzematge blob de l'Azure. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).     
També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 

Les dades exportades s'emmagatzemen al contenidor de l'Emmagatzematge blob que heu configurat. Els següents camins de carpeta es creen automàticament al contenidor:

- Per a les entitats i entitats d'origen generades pel sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Exemple: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- El model.json de les entitats exportades estarà al nivell %ExportDestinationName%
  - Exemple: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
