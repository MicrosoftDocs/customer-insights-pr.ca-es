---
title: Exportar dades del Customer Insights a l'Azure Data Lake Storage Gen2
description: Apreneu a configurar la connexió a l'Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596625"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Connector per a l'Azure Data Lake Storage Gen2 (versió preliminar)

Emmagatzemeu les dades del Customer Insights a l'Azure Data Lake Storage Gen2 o utilitzeu-lo per transferir les vostres dades a altres aplicacions.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Configurar el connector per a l'Azure Data Lake Storage Gen2

1. A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.

1. A **Azure Data Lake Storage Gen2**, seleccioneu **Configura**.

1. Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.

1. Introduïu el **nom del compte**, la **clau del compte** i el **contenidor** per a l'Azure Data Lake Storage Gen2.
    - Per aprendre a crear un compte d'emmagatzematge per utilitzar-lo amb l'Azure Data Lake Storage Gen2, vegeu [Crear un compte d'emmagatzematge](/azure/storage/blobs/create-data-lake-storage-account). 
    - Per obtenir més informació sobre com cercar el nom del compte i la clau del compte d'emmagatzematge de l'Azure Data Lake Gen2, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).

1. Seleccioneu **Següent**.

1. Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md#export-data-on-demand). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).