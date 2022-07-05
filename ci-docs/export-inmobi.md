---
title: Exporta les dades de Customer Insights a l'InMobi
description: Obtén informació sobre com configurar la connexió i exportar a l'InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059605"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Exporta la llista de segments i altres dades a l'InMobi (previsualització)

Exporta llistes de segments o altres dades de la instància del Customer Insights a l'InMobi [...](https://www.inmobi.com/).

## <a name="prerequisites"></a>Requisits previs

1. Teniu un [compte](https://www.inmobi.com/) InMobi i credencials d'administrador.
1. Teniu un nom de compte d'emmagatzematge de l'Azure Blob i la clau de compte corresponent. Per obtenir més informació, vegeu [Administra la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage). Hi ha un contenidor al compte d'emmagatzematge al qual exportar les dades de l'inMobi. Per obtenir més informació, vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi crearà una connexió directa al vostre Emmagatzematge Blob i configurarà una importació automàtica de les vostres dades a InMobi. Poseu-vos en contacte amb el vostre representant d'InMobi per iniciar el procés.

## <a name="known-limitations"></a>Limitacions conegudes

1. Per a l'Emmagatzematge Blob de l'Azure, podeu triar entre [el rendiment estàndard i el nivell](/azure/storage/blobs/storage-blob-performance-tiers) de rendiment Premium. Si trieu el nivell de rendiment prèmium, seleccioneu els [blobs en bloc prèmium com a tipus de compte](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Configura la connexió a l'emmagatzematge blob de l'Azure i configura una exportació

1. Seguiu les instruccions per [configurar una connexió amb l'emmagatzematge blob de l'Azure](export-azure-blob-storage.md).
2. Seguiu les instruccions per [configurar una exportació](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
