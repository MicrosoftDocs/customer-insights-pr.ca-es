---
title: Exportar dades del Customer Insights a InMobi
description: Obteniu més informació sobre com configurar la connexió i exportar a InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195876"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Exportar dades del Customer Insights a InMobi (visualització prèvia)

Exporta llistes de segments o altres dades de la instància del Customer Insights a [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Requisits previs

- Un compte [InMobi](https://www.inmobi.com/) i credencials d'administrador.
- Un [nom de compte i una clau de compte](/azure/storage/blobs/create-data-lake-storage-account) de l'Azure Blob Storage. Per trobar el nom i la clau, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).
- Un [contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) d'emmagatzematge blob de l'Azure per exportar dades d'InMobi.
- InMobi crearà una connexió directa amb el vostre Emmagatzematge blob i configurarà una importació automàtica de les vostres dades a InMobi. Poseu-vos en contacte amb el vostre representant d'InMobi per iniciar el procés.

## <a name="known-limitations"></a>Limitacions conegudes

- Per a l'emmagatzematge blob de l'Azure, trieu entre [el nivell de rendiment estàndard i el nivell de rendiment Premium](/azure/storage/blobs/storage-blob-performance-tiers). Si trieu el nivell de rendiment prèmium, seleccioneu els [blobs en bloc prèmium com a tipus de compte](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Configuració de la connexió a l'Emmagatzematge blob de l'Azure

[Configureu una connexió a l'Emmagatzematge blob de l'Azure](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Configurar una exportació

[Configura una exportació](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
