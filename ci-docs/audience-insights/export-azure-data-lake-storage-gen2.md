---
title: Exportar dades del Customer Insights a l'Azure Data Lake Storage Gen2
description: Apreneu a configurar la connexió a l'Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477167"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="1b30c-103">Connector per a l'Azure Data Lake Storage Gen2 (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="1b30c-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="1b30c-104">Emmagatzemeu les dades del Customer Insights a l'Azure Data Lake Storage Gen2 o utilitzeu-lo per transferir les vostres dades a altres aplicacions.</span><span class="sxs-lookup"><span data-stu-id="1b30c-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="1b30c-105">Configurar el connector per a l'Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="1b30c-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="1b30c-106">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="1b30c-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1b30c-107">A **Azure Data Lake Storage Gen2**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="1b30c-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="1b30c-108">Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="1b30c-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1b30c-109">Introduïu el **nom del compte**, la **clau del compte** i el **contenidor** per a l'Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="1b30c-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="1b30c-110">Per aprendre a crear un compte d'emmagatzematge per utilitzar-lo amb l'Azure Data Lake Storage Gen2, vegeu [Crear un compte d'emmagatzematge](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="1b30c-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="1b30c-111">Per obtenir més informació sobre com cercar el nom del compte i la clau del compte d'emmagatzematge de l'Azure Data Lake Gen2, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1b30c-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="1b30c-112">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="1b30c-112">Select **Next**.</span></span>

1. <span data-ttu-id="1b30c-113">Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.</span><span class="sxs-lookup"><span data-stu-id="1b30c-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="1b30c-114">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="1b30c-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1b30c-115">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="1b30c-115">Export the data</span></span>

<span data-ttu-id="1b30c-116">Podeu [exportar les dades segons demanda](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1b30c-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="1b30c-117">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1b30c-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
