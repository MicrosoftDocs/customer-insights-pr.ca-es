---
title: Exportar dades del Customer Insights a un emmagatzematge blob de l'Azure
description: Més informació sobre com configurar la connexió a l'emmagatzematge de blob de l'Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667127"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Connector per a l'emmagatzematge de blob de l'Azure (visualització prèvia)

Emmagatzemeu les dades del Customer Insights a un emmagatzematge blob de l'Azure o utilitzeu-lo per transferir les vostres dades a altres aplicacions.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Configurar el connector per a l'emmagatzematge de blob de l'Azure

1. A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.

1. A **Emmagatzematge de blob de l'Azure**, seleccioneu **Configura**.

1. Introduïu el **nom del compte**, la **clau del compte** i el **contenidor** per al compte d'emmagatzematge de blob de l'Azure.
    - Per obtenir més informació sobre com trobar el nom i la clau del compte de l'emmagatzematge blob de l'Azure, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.

1. Seleccioneu **Següent**.

1. Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.

1. Seleccioneu **Desa**.

Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge de blob de l'Azure que heu configurat. Els següents camins de carpeta es creen automàticament al contenidor:

- Per a les entitats i entitats d'origen generades pel sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Exemple: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- El fitxer model.json per a les entitats exportades residirà en el nivell %ExportDestinationName%
  - Exemple: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](/export-destinations.md#export-data-on-demand). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).
