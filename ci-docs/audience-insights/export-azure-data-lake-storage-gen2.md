---
title: Exportar dades del Customer Insights a l'Azure Data Lake Storage Gen2
description: Apreneu a configurar la connexió a l'Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605891"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Exportar la llista de segments i altres dades a l'Azure Data Lake Storage Gen2 (versió preliminar)

Emmagatzemeu les dades del Customer Insights en un compte del Data Lake Storage Gen2 o utilitzeu-lo per transferir les vostres dades a altres aplicacions.

## <a name="known-limitations"></a>Limitacions conegudes

1. Per a l'Azure Data Lake Storage Gen2 podeu triar entre [rendiment estàndard i nivell de rendiment Premium](/azure/storage/blobs/create-data-lake-storage-account) quan esteu creant un compte d'emmagatzematge per al vostre emmagatzematge de dades. Si trieu el nivell de rendiment prèmium, seleccioneu els blobs en bloc prèmium com a tipus de compte. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Configurar la connexió a l'Azure Data Lake Storage Gen2 


1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Azure Data Lake Gen 2** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el **nom del compte**, la **clau del compte** i el **contenidor** per a l'Azure Data Lake Storage Gen2.
    - Per aprendre a crear un compte d'emmagatzematge per utilitzar-lo amb l'Azure Data Lake Storage Gen2, vegeu [Crear un compte d'emmagatzematge](/azure/storage/blobs/create-data-lake-storage-account). 
    - Per obtenir més informació sobre el nom del compte i la clau del compte d'emmagatzematge de l'Azure Data Lake Gen2, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).

1. Seleccioneu **Desa** per completar la connexió. 

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió a la secció **Azure Data Lake**. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 

Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge de l'Azure Data Lake Gen 2 que heu configurat. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
