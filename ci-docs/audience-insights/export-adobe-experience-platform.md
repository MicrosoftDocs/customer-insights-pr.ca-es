---
title: Exportar les dades del Customer Insights a l'Adobe Experience Platform
description: Apreneu a utilitzar els segments de conclusions del públic a l'Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305512"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="cd405-103">Utilitzar els segments del Customer Insights a l'Adobe Experience Platform (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="cd405-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="cd405-104">Com a usuari de les conclusions del públic al Dynamics 365 Customer Insights, pot ser que hàgiu creat segments per fer que les campanyes de màrqueting siguin més eficients adreçant-vos a públics rellevants.</span><span class="sxs-lookup"><span data-stu-id="cd405-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="cd405-105">Per utilitzar un segment de la informació sobre el públic a l'Adobe Experience Platform i aplicacions com ara l'Adobe Campaign Standard, heu de seguir alguns passos que s'indiquen en aquest article.</span><span class="sxs-lookup"><span data-stu-id="cd405-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de procés dels passos que es descriuen en aquest article.":::

## <a name="prerequisites"></a><span data-ttu-id="cd405-107">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="cd405-107">Prerequisites</span></span>

-   <span data-ttu-id="cd405-108">Llicència del Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="cd405-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="cd405-109">Llicència de l'Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="cd405-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="cd405-110">Llicència de l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="cd405-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="cd405-111">Compte de l'Emmagatzematge blob de l'Azure</span><span class="sxs-lookup"><span data-stu-id="cd405-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="cd405-112">Informació general de la campanya</span><span class="sxs-lookup"><span data-stu-id="cd405-112">Campaign Overview</span></span>

<span data-ttu-id="cd405-113">Per comprendre millor com podeu utilitzar els segments de la informació sobre el públic a l'Adobe Experience Platform, plantegem una campanya d'exemple fictícia.</span><span class="sxs-lookup"><span data-stu-id="cd405-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="cd405-114">Suposem que la vostra empresa ofereix un servei mensual basat en subscripció als seus clients dels Estats Units.</span><span class="sxs-lookup"><span data-stu-id="cd405-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="cd405-115">Voleu identificar els clients les subscripcions dels qual s'han de renovar en els propers vuit dies però que encara no han renovat la seva subscripció.</span><span class="sxs-lookup"><span data-stu-id="cd405-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="cd405-116">Per mantenir aquests clients, heu d'enviar-los una oferta promocional per correu electrònic, mitjançant l'Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="cd405-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="cd405-117">En aquest exemple, volem executar la campanya promocional de correu electrònic d'un cop.</span><span class="sxs-lookup"><span data-stu-id="cd405-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="cd405-118">En aquest article no es cobreix el cas d'ús de l'execució de la campanya més d'una vegada.</span><span class="sxs-lookup"><span data-stu-id="cd405-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="cd405-119">Identificar el públic destinatari</span><span class="sxs-lookup"><span data-stu-id="cd405-119">Identify your target audience</span></span>

<span data-ttu-id="cd405-120">Al nostre escenari, suposem que les adreces electròniques dels clients estan disponibles a la informació sobre el públic i s'han analitzat les seves preferències promocionals per identificar els membres del segment.</span><span class="sxs-lookup"><span data-stu-id="cd405-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="cd405-121">El [segment que heu definit a la informació sobre el públic](segments.md) s'anomena **ChurnProneCustomers** i voleu enviar a aquests clients la promoció per correu electrònic.</span><span class="sxs-lookup"><span data-stu-id="cd405-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la pàgina de segments amb el segment ChurnProneCustomers creat.":::

<span data-ttu-id="cd405-123">El correu electrònic d'oferta que voleu enviar inclourà el nom, el cognom i la data de finalització de la subscripció del client.</span><span class="sxs-lookup"><span data-stu-id="cd405-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="cd405-124">Informa els clients sobre el descompte que obtindran si renoven la subscripció abans que finalitzi.</span><span class="sxs-lookup"><span data-stu-id="cd405-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="cd405-125">Exportar el públic destinatari</span><span class="sxs-lookup"><span data-stu-id="cd405-125">Export your target audience</span></span>

<span data-ttu-id="cd405-126">Un cop identificat el públic destinatari, podem configurar l'exportació des de la informació sobre el públic a un compte de l'Emmagatzematge blob de l'Azure.</span><span class="sxs-lookup"><span data-stu-id="cd405-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="cd405-127">Configurar una connexió</span><span class="sxs-lookup"><span data-stu-id="cd405-127">Configure a connection</span></span>

1. <span data-ttu-id="cd405-128">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="cd405-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cd405-129">Seleccioneu **Afegeix una connexió** i trieu **Emmagatzematge de blob de l'Azure** o seleccioneu **Configura** a la peça **Emmagatzematge de blob de l'Azure** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="cd405-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Peça de configuració de l'Emmagatzematge blob de l'Azure."::: 

1. <span data-ttu-id="cd405-131">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="cd405-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cd405-132">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="cd405-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cd405-133">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="cd405-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cd405-134">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="cd405-134">Choose who can use this connection.</span></span> <span data-ttu-id="cd405-135">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="cd405-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="cd405-136">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cd405-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="cd405-137">Introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte d'emmagatzematge blob al qual voleu exportar el segment.</span><span class="sxs-lookup"><span data-stu-id="cd405-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuració del compte d'emmagatzematge."::: 
   
    - <span data-ttu-id="cd405-139">Per obtenir més informació sobre com trobar el compte i la clau del compte de l'emmagatzematge blob, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="cd405-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="cd405-140">Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="cd405-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="cd405-141">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="cd405-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="cd405-142">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="cd405-142">Configure an export</span></span>

<span data-ttu-id="cd405-143">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="cd405-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cd405-144">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cd405-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cd405-145">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="cd405-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cd405-146">Per crear una exportació nova, seleccioneu **Afegeix una exportació**.</span><span class="sxs-lookup"><span data-stu-id="cd405-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="cd405-147">Al camp **Connexió per a l'exportació**, trieu una connexió a la secció Emmagatzematge blob de l'Azure.</span><span class="sxs-lookup"><span data-stu-id="cd405-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="cd405-148">Si no veieu aquest nom de secció, no hi ha disponible cap connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="cd405-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="cd405-149">Trieu el segment que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="cd405-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="cd405-150">En aquest exemple, és **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="cd405-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfície d'usuari de selecció de segments amb el segment ChurnProneCustomers seleccionat.":::

1. <span data-ttu-id="cd405-152">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="cd405-152">Select **Save**.</span></span>

<span data-ttu-id="cd405-153">Després de desar la destinació d'exportació, la trobeu a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="cd405-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="cd405-154">Ara podeu [exportar el segment a petició](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cd405-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="cd405-155">L'exportació també s'executarà amb cada [actualització planificada](system.md).</span><span class="sxs-lookup"><span data-stu-id="cd405-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cd405-156">Assegureu-vos que el nombre de registres del segment exportat es troba dins del límit permès de la llicència de l'Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="cd405-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="cd405-157">Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge blob de l'Azure que heu configurat anteriorment.</span><span class="sxs-lookup"><span data-stu-id="cd405-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="cd405-158">Al contenidor es crea automàticament el camí de carpeta següent:</span><span class="sxs-lookup"><span data-stu-id="cd405-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="cd405-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="cd405-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="cd405-160">Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="cd405-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="cd405-161">El *model.json* de les entitats exportades resideix al nivell *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="cd405-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="cd405-162">Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="cd405-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="cd405-163">Definir el model de dades d'experiència (XDM) a l'Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="cd405-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="cd405-164">Abans que les dades exportades des de la informació sobre el públic es puguin utilitzar a l'Adobe Experience Platform, hem de definir l'esquema del Model de dades d'experiència i [configurar les dades del perfil de client en temps real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="cd405-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="cd405-165">Apreneu [què és l'XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i compreneu els [conceptes bàsics de la composició de l'esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="cd405-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="cd405-166">Importar dades a l'Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="cd405-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="cd405-167">Ara que tot està al seu lloc, hem d'importar les dades del públic preparades des de la informació del públic a l'Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="cd405-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="cd405-168">En primer lloc, [creeu una connexió d'origen d'emmagatzematge blob de l'Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="cd405-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="cd405-169">Després de definir la connexió d'origen, [configureu un flux de dades](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) per a una connexió per lots d'emmagatzematge en el núvol per importar la sortida del segment de la informació sobre el públic a l'Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="cd405-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="cd405-170">Crear un públic a l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="cd405-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="cd405-171">Per enviar el correu electrònic d'aquesta campanya, utilitzarem l'Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="cd405-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="cd405-172">Després d'importar les dades a l'Adobe Experience Platform, hem de [crear un públic](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) a l'Adobe Campaign Standard utilitzant les dades de l'Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="cd405-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="cd405-173">Apreneu a [utilitzar el constructor de segments](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) a l'Adobe Campaign Standard per definir un públic a partir de les dades de l'Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="cd405-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="cd405-174">Crear i enviar el correu electrònic mitjançant l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="cd405-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="cd405-175">Creeu el contingut del correu electrònic i, a continuació, [proveu i envieu](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) el correu electrònic.</span><span class="sxs-lookup"><span data-stu-id="cd405-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Correu electrònic d'exemple amb oferta de renovació de l'Adobe Campaign Standard.":::
