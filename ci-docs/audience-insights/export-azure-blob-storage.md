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
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="a20fd-103">Exportar la llista de segments i altres dades a l'Emmagatzematge blob de l'Azure (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="a20fd-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="a20fd-104">Emmagatzemeu les dades del Customer Insights a l'Emmagatzematge blob de l'Azure o utilitzeu-lo per transferir les vostres dades a altres aplicacions.</span><span class="sxs-lookup"><span data-stu-id="a20fd-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="a20fd-105">Configurar la connexió a l'Emmagatzematge blob</span><span class="sxs-lookup"><span data-stu-id="a20fd-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="a20fd-106">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="a20fd-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a20fd-107">Seleccioneu **Afegeix una connexió** i trieu **Emmagatzematge blob de l'Azure** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="a20fd-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="a20fd-108">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="a20fd-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a20fd-109">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="a20fd-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a20fd-110">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="a20fd-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a20fd-111">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="a20fd-111">Choose who can use this connection.</span></span> <span data-ttu-id="a20fd-112">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="a20fd-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a20fd-113">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a20fd-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a20fd-114">Introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte de l'Emmagatzematge blob.</span><span class="sxs-lookup"><span data-stu-id="a20fd-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="a20fd-115">Per obtenir més informació sobre com trobar el compte i la clau del compte de l'Emmagatzematge blob, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="a20fd-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="a20fd-116">Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="a20fd-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="a20fd-117">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="a20fd-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="a20fd-118">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="a20fd-118">Configure an export</span></span>

<span data-ttu-id="a20fd-119">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="a20fd-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a20fd-120">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a20fd-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a20fd-121">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="a20fd-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a20fd-122">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="a20fd-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a20fd-123">Al camp **Connexió per a l'exportació**, trieu una connexió a la secció Emmagatzematge blob de l'Azure.</span><span class="sxs-lookup"><span data-stu-id="a20fd-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="a20fd-124">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="a20fd-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a20fd-125">Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.</span><span class="sxs-lookup"><span data-stu-id="a20fd-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="a20fd-126">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="a20fd-126">Select **Save**.</span></span>

<span data-ttu-id="a20fd-127">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="a20fd-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a20fd-128">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a20fd-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="a20fd-129">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a20fd-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="a20fd-130">Les dades exportades s'emmagatzemen al contenidor de l'Emmagatzematge blob que heu configurat.</span><span class="sxs-lookup"><span data-stu-id="a20fd-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="a20fd-131">Els següents camins de carpeta es creen automàticament al contenidor:</span><span class="sxs-lookup"><span data-stu-id="a20fd-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="a20fd-132">Per a les entitats i entitats d'origen generades pel sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="a20fd-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="a20fd-133">Exemple: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="a20fd-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="a20fd-134">El model.json de les entitats exportades estarà al nivell %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="a20fd-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="a20fd-135">Exemple: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="a20fd-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
