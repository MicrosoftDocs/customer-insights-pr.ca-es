---
title: Exportar dades del Customer Insights a l'Azure Synapse Analytics
description: Apreneu a configurar la connexió amb l'Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977365"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="175c1-103">Exportar dades a l'Azure Synapse Analytics (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="175c1-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="175c1-104">L'Azure Synapse és un servei d'analítica que accelera el temps per obtenir informació sobre els magatzems de dades i els sistemes de macrodades.</span><span class="sxs-lookup"><span data-stu-id="175c1-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="175c1-105">Podeu ingerir i utilitzar les dades del Customer Insights a l'[Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="175c1-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="175c1-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="175c1-106">Prerequisites</span></span>

<span data-ttu-id="175c1-107">S'han de complir els requisits previs següents per configurar la connexió del Customer Insights a l'Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="175c1-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="175c1-108">Assegureu-vos de definir totes les **assignacions de funcions** tal com es descriuen.</span><span class="sxs-lookup"><span data-stu-id="175c1-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="175c1-109">Requisits previs al Customer Insights</span><span class="sxs-lookup"><span data-stu-id="175c1-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="175c1-110">Teniu una funció d'**Administrador** als coneixements del públic.</span><span class="sxs-lookup"><span data-stu-id="175c1-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="175c1-111">Més informació quant a [la configuració de permisos d'usuari als coneixements del públic](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="175c1-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="175c1-112">A l’Azure:</span><span class="sxs-lookup"><span data-stu-id="175c1-112">In Azure:</span></span> 

- <span data-ttu-id="175c1-113">Una subscripció activa de l'Azure.</span><span class="sxs-lookup"><span data-stu-id="175c1-113">An active Azure subscription.</span></span>

- <span data-ttu-id="175c1-114">Si s'utilitza un compte de l'Azure Data Lake Storage Gen2 nou, l'*entitat de seguretat del servei per als coneixements del públic* necessita permisos de **Col·laborador de dades BLOB d'emmagatzematge**.</span><span class="sxs-lookup"><span data-stu-id="175c1-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="175c1-115">Obteniu més informació sobre com [podeu connectar-vos a un compte de l'Azure Data Lake Storage Gen2 amb l'enitat de seguretat del servei de l'Azure per als coneixements del públic](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="175c1-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="175c1-116">El Data Lake Storage Gen2 **ha de tenir** habilitat l'[espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="175c1-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="175c1-117">Al grup de recursos on es troba l'àrea de treball de l'Azure Synapse, l'*entitat de seguretat del servei* i l'*usuari per als coneixements del públic* han de tenir assignats com a mínim permisos de **Lector**.</span><span class="sxs-lookup"><span data-stu-id="175c1-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="175c1-118">Per obtenir més informació, vegeu [Assignar funcions de l'Azure mitjançant el portal de l'Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="175c1-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="175c1-119">L'*usuari* necessita permisos del **Col·laborador de dades BLOB d'emmagatzematge** al compte de l'Azure Data Lake Storage Gen2 on es troben les dades i s'enllacen a l'àrea de treball de l'Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="175c1-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="175c1-120">Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="175c1-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="175c1-121">L'*[entitat gestionada per l'àrea de treball de l'Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* necessita permisos del **Col·laborador de dades BLOB d'emmagatzematge** al compte de l'Azure Data Lake Storage Gen2 on es troben les dades i s'enllacen a l'àrea de treball de l'Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="175c1-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="175c1-122">Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="175c1-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="175c1-123">A l'àrea de treball de l'Azure Synapse, l'*entitat de seguretat del servei per als coneixements del públic* necessita la funció **Administrador del Synapse** assignada.</span><span class="sxs-lookup"><span data-stu-id="175c1-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="175c1-124">Per obtenir més informació, vegeu [Com configurar el control d'accés per a l'àrea de treball del Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="175c1-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="175c1-125">Configurar la connexió i exportar a l'Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="175c1-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="175c1-126">Configurar una connexió</span><span class="sxs-lookup"><span data-stu-id="175c1-126">Configure a connection</span></span>

1. <span data-ttu-id="175c1-127">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="175c1-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="175c1-128">Seleccioneu **Afegeix una connexió** i trieu **Azure Synapse Analytics** o seleccioneu **Configuració** a la peça de l'**Azure Synapse Analytics** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="175c1-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="175c1-129">Doneu a la connexió un nom reconeixible al camp Nom de visualització.</span><span class="sxs-lookup"><span data-stu-id="175c1-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="175c1-130">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="175c1-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="175c1-131">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="175c1-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="175c1-132">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="175c1-132">Choose who can use this connection.</span></span> <span data-ttu-id="175c1-133">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="175c1-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="175c1-134">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="175c1-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="175c1-135">Seleccioneu o cerqueu la subscripció a la qual voleu utilitzar les dades del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="175c1-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="175c1-136">Tan aviat com se seleccioni una subscripció, també podeu seleccionar **Àrea de treball**, **Compte d'emmagatzematge** i **Contenidor**.</span><span class="sxs-lookup"><span data-stu-id="175c1-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="175c1-137">Seleccioneu **Desa** per desar la connexió.</span><span class="sxs-lookup"><span data-stu-id="175c1-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="175c1-138">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="175c1-138">Configure an export</span></span>

<span data-ttu-id="175c1-139">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="175c1-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="175c1-140">Per obtenir més informació, vegeu [permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="175c1-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="175c1-141">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="175c1-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="175c1-142">Per crear una exportació nova, seleccioneu **Afegeix una exportació**.</span><span class="sxs-lookup"><span data-stu-id="175c1-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="175c1-143">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="175c1-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="175c1-144">Si no veieu aquest nom de secció, no hi ha cap [connexió](connections.md) d'aquest tipus disponible per a vós.</span><span class="sxs-lookup"><span data-stu-id="175c1-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="175c1-145">Proporcioneu un **Nom de visualització** recognoscible per a l'exportació i un **Nom de la base de dades**.</span><span class="sxs-lookup"><span data-stu-id="175c1-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="175c1-146">Seleccioneu les entitats que voleu exportar a l'Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="175c1-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="175c1-147">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="175c1-147">Select **Save**.</span></span>

<span data-ttu-id="175c1-148">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="175c1-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="175c1-149">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="175c1-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="175c1-150">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="175c1-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="175c1-151">Actualitzar una exportació</span><span class="sxs-lookup"><span data-stu-id="175c1-151">Update an export</span></span>

1. <span data-ttu-id="175c1-152">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="175c1-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="175c1-153">Seleccioneu **Edita** a l'exportació que voleu actualitzar.</span><span class="sxs-lookup"><span data-stu-id="175c1-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="175c1-154">**Afegiu** o **suprimiu** entitats de la selecció.</span><span class="sxs-lookup"><span data-stu-id="175c1-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="175c1-155">Si les entitats se suprimeixen de la selecció, no se suprimeixen de la base de dades del Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="175c1-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="175c1-156">No obstant això, les actualitzacions de dades futures no actualitzaran les entitats suprimides en aquesta base de dades.</span><span class="sxs-lookup"><span data-stu-id="175c1-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="175c1-157">Si **canvieu el nom de la base de dades**, es crea una base de dades nova del Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="175c1-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="175c1-158">La base de dades amb el nom que s'ha configurat abans no rebrà cap actualització en actualitzacions futures.</span><span class="sxs-lookup"><span data-stu-id="175c1-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
