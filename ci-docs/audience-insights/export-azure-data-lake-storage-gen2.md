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
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="e7867-103">Connector per a l'Azure Data Lake Storage Gen2 (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="e7867-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="e7867-104">Emmagatzemeu les dades del Customer Insights a l'Azure Data Lake Storage Gen2 o utilitzeu-lo per transferir les vostres dades a altres aplicacions.</span><span class="sxs-lookup"><span data-stu-id="e7867-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="e7867-105">Configurar el connector per a l'Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="e7867-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="e7867-106">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="e7867-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e7867-107">A **Azure Data Lake Storage Gen2**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="e7867-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="e7867-108">Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="e7867-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e7867-109">Introduïu el **nom del compte**, la **clau del compte** i el **contenidor** per a l'Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="e7867-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="e7867-110">Per aprendre a crear un compte d'emmagatzematge per utilitzar-lo amb l'Azure Data Lake Storage Gen2, vegeu [Crear un compte d'emmagatzematge](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="e7867-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="e7867-111">Per obtenir més informació sobre com cercar el nom del compte i la clau del compte d'emmagatzematge de l'Azure Data Lake Gen2, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e7867-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="e7867-112">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="e7867-112">Select **Next**.</span></span>

1. <span data-ttu-id="e7867-113">Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.</span><span class="sxs-lookup"><span data-stu-id="e7867-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="e7867-114">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="e7867-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e7867-115">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="e7867-115">Export the data</span></span>

<span data-ttu-id="e7867-116">Podeu [exportar les dades segons demanda](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e7867-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="e7867-117">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e7867-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>