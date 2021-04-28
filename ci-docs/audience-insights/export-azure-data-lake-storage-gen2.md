---
title: Exportar dades del Customer Insights a l'Azure Data Lake Storage Gen2
description: Apreneu a configurar la connexió a l'Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760039"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="f2d70-103">Configurar la connexió amb l'Azure Data Lake Storage Gen2 (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="f2d70-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="f2d70-104">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="f2d70-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f2d70-105">Seleccioneu **Afegeix una connexió** i trieu **Azure Data Lake Gen 2** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="f2d70-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="f2d70-106">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="f2d70-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f2d70-107">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="f2d70-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f2d70-108">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="f2d70-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f2d70-109">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="f2d70-109">Choose who can use this connection.</span></span> <span data-ttu-id="f2d70-110">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="f2d70-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f2d70-111">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f2d70-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f2d70-112">Introduïu el **nom del compte**, la **clau del compte** i el **contenidor** per a l'Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="f2d70-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="f2d70-113">Per aprendre a crear un compte d'emmagatzematge per utilitzar-lo amb l'Azure Data Lake Storage Gen2, vegeu [Crear un compte d'emmagatzematge](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="f2d70-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="f2d70-114">Per obtenir més informació sobre el nom del compte i la clau del compte d'emmagatzematge de l'Azure Data Lake Gen2, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="f2d70-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="f2d70-115">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="f2d70-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f2d70-116">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="f2d70-116">Configure an export</span></span>

<span data-ttu-id="f2d70-117">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="f2d70-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f2d70-118">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f2d70-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f2d70-119">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="f2d70-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f2d70-120">Per crear una exportació nova, seleccioneu **Afegeix una exportació**.</span><span class="sxs-lookup"><span data-stu-id="f2d70-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="f2d70-121">Al camp **Connexió per a l'exportació**, trieu una connexió a la secció **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="f2d70-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="f2d70-122">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="f2d70-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f2d70-123">Marqueu la casella que hi ha al costat de cadascuna de les entitats que voleu exportar a aquesta destinació.</span><span class="sxs-lookup"><span data-stu-id="f2d70-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="f2d70-124">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="f2d70-124">Select **Save**.</span></span>

<span data-ttu-id="f2d70-125">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="f2d70-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f2d70-126">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f2d70-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f2d70-127">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f2d70-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="f2d70-128">Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge de l'Azure Data Lake Gen 2 que heu configurat.</span><span class="sxs-lookup"><span data-stu-id="f2d70-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
