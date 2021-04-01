---
title: Exportar dades del Customer Insights a un emmagatzematge blob de l'Azure
description: Més informació sobre com configurar la connexió a l'emmagatzematge de blob de l'Azure.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596165"
---
# <a name="connector-for-azure-blob-storage-preview"></a><span data-ttu-id="e83b4-103">Connector per a l'emmagatzematge de blob de l'Azure (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="e83b4-103">Connector for Azure Blob storage (preview)</span></span>

<span data-ttu-id="e83b4-104">Emmagatzemeu les dades del Customer Insights a un emmagatzematge blob de l'Azure o utilitzeu-lo per transferir les vostres dades a altres aplicacions.</span><span class="sxs-lookup"><span data-stu-id="e83b4-104">Store your Customer Insights data in an Azure Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-blob-storage"></a><span data-ttu-id="e83b4-105">Configurar el connector per a l'emmagatzematge de blob de l'Azure</span><span class="sxs-lookup"><span data-stu-id="e83b4-105">Configure the connector for Azure Blob storage</span></span>

1. <span data-ttu-id="e83b4-106">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="e83b4-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e83b4-107">A **Emmagatzematge de blob de l'Azure**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="e83b4-107">Under **Azure Blob Storage**, select **Set up**.</span></span>

1. <span data-ttu-id="e83b4-108">Introduïu el **nom del compte**, la **clau del compte** i el **contenidor** per al compte d'emmagatzematge de blob de l'Azure.</span><span class="sxs-lookup"><span data-stu-id="e83b4-108">Enter **Account name**, **Account key**, and **Container** for your Azure Blob storage account.</span></span>
    - <span data-ttu-id="e83b4-109">Per obtenir més informació sobre com trobar el nom i la clau del compte de l'emmagatzematge blob de l'Azure, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e83b4-109">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="e83b4-110">Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="e83b4-110">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="e83b4-111">Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="e83b4-111">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e83b4-112">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="e83b4-112">Select **Next**.</span></span>

1. <span data-ttu-id="e83b4-113">Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.</span><span class="sxs-lookup"><span data-stu-id="e83b4-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="e83b4-114">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="e83b4-114">Select **Save**.</span></span>

<span data-ttu-id="e83b4-115">Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge de blob de l'Azure que heu configurat.</span><span class="sxs-lookup"><span data-stu-id="e83b4-115">Exported data is stored in the Azure Blob storage container you configured.</span></span> <span data-ttu-id="e83b4-116">Els següents camins de carpeta es creen automàticament al contenidor:</span><span class="sxs-lookup"><span data-stu-id="e83b4-116">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="e83b4-117">Per a les entitats i entitats d'origen generades pel sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="e83b4-117">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="e83b4-118">Exemple: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="e83b4-118">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="e83b4-119">El model.json de les entitats exportades residirà al nivell %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="e83b4-119">The model.json for the exported entities will reside at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="e83b4-120">Exemple: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="e83b4-120">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e83b4-121">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="e83b4-121">Export the data</span></span>

<span data-ttu-id="e83b4-122">Podeu [exportar les dades segons demanda](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e83b4-122">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="e83b4-123">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e83b4-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]