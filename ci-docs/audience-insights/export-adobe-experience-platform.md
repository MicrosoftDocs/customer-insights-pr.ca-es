---
title: Exportar les dades del Customer Insights a l'Adobe Experience Platform
description: Més informació sobre com utilitzar els segments d'informació sobre el públic a l'Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596257"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="b226d-103">Utilitzar els segments del Customer Insights a l'Adobe Experience Platform (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="b226d-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="b226d-104">Com a usuari de la informació sobre el públic del Dynamics 365 Customer Insights, pot ser que hàgiu creat segments per fer que les campanyes de màrqueting siguin més eficients adreçant-vos a públics rellevants.</span><span class="sxs-lookup"><span data-stu-id="b226d-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="b226d-105">Per utilitzar un segment de la informació sobre el públic a l'Adobe Experience Platform i aplicacions com ara l'Adobe Campaign Standard, heu de seguir alguns passos que s'indiquen en aquest article.</span><span class="sxs-lookup"><span data-stu-id="b226d-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de procés dels passos que es descriuen en aquest article.":::

## <a name="prerequisites"></a><span data-ttu-id="b226d-107">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="b226d-107">Prerequisites</span></span>

-   <span data-ttu-id="b226d-108">Llicència del Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b226d-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="b226d-109">Llicència de l'Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="b226d-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="b226d-110">Llicència de l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="b226d-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="b226d-111">Compte de l'Emmagatzematge blob de l'Azure</span><span class="sxs-lookup"><span data-stu-id="b226d-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="b226d-112">Informació general de la campanya</span><span class="sxs-lookup"><span data-stu-id="b226d-112">Campaign Overview</span></span>

<span data-ttu-id="b226d-113">Per comprendre millor com podeu utilitzar els segments de la informació sobre el públic a l'Adobe Experience Platform, plantegem una campanya d'exemple fictícia.</span><span class="sxs-lookup"><span data-stu-id="b226d-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="b226d-114">Suposem que la vostra empresa ofereix un servei mensual basat en subscripció als seus clients dels Estats Units.</span><span class="sxs-lookup"><span data-stu-id="b226d-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="b226d-115">Voleu identificar els clients les subscripcions dels qual s'han de renovar en els propers vuit dies però que encara no han renovat la seva subscripció.</span><span class="sxs-lookup"><span data-stu-id="b226d-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="b226d-116">Per mantenir aquests clients, heu d'enviar-los una oferta promocional per correu electrònic, mitjançant l'Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="b226d-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="b226d-117">En aquest exemple, volem executar la campanya promocional de correu electrònic d'un cop.</span><span class="sxs-lookup"><span data-stu-id="b226d-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="b226d-118">En aquest article no es cobreix el cas d'ús de l'execució de la campanya més d'una vegada.</span><span class="sxs-lookup"><span data-stu-id="b226d-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="b226d-119">Identificar el públic destinatari</span><span class="sxs-lookup"><span data-stu-id="b226d-119">Identify your target audience</span></span>

<span data-ttu-id="b226d-120">Al nostre escenari, suposem que les adreces electròniques dels clients estan disponibles a la informació sobre el públic i s'han analitzat les seves preferències promocionals per identificar els membres del segment.</span><span class="sxs-lookup"><span data-stu-id="b226d-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="b226d-121">El [segment que heu definit a la informació sobre el públic](segments.md) s'anomena **ChurnProneCustomers** i voleu enviar a aquests clients la promoció per correu electrònic.</span><span class="sxs-lookup"><span data-stu-id="b226d-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la pàgina de segments amb el segment ChurnProneCustomers creat.":::

<span data-ttu-id="b226d-123">El correu electrònic d'oferta que voleu enviar inclourà el nom, el cognom i la data de finalització de la subscripció del client.</span><span class="sxs-lookup"><span data-stu-id="b226d-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="b226d-124">Informa els clients sobre el descompte que obtindran si renoven la subscripció abans que finalitzi.</span><span class="sxs-lookup"><span data-stu-id="b226d-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="b226d-125">Exportar el públic destinatari</span><span class="sxs-lookup"><span data-stu-id="b226d-125">Export your target audience</span></span>

<span data-ttu-id="b226d-126">Un cop identificat el públic destinatari, podem configurar l'exportació des de la informació sobre el públic a un compte de l'Emmagatzematge blob de l'Azure.</span><span class="sxs-lookup"><span data-stu-id="b226d-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="b226d-127">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="b226d-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b226d-128">A la peça **Emmagatzematge blob de l'Azure**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="b226d-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Peça de configuració de l'Emmagatzematge blob de l'Azure.":::

1. <span data-ttu-id="b226d-130">Proporcioneu un **Nom de visualització** per a aquesta nova destinació d'exportació i, a continuació, introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte d'Emmagatzematge blob de l'Azure al qual voleu exportar el segment.</span><span class="sxs-lookup"><span data-stu-id="b226d-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuració del compte d'emmagatzematge."::: 

   - <span data-ttu-id="b226d-132">Per obtenir més informació sobre com trobar el nom i la clau del compte de l'emmagatzematge blob de l'Azure, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="b226d-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="b226d-133">Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="b226d-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="b226d-134">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="b226d-134">Select **Next**.</span></span>

1. <span data-ttu-id="b226d-135">Trieu el segment que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="b226d-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="b226d-136">En aquest exemple, és **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="b226d-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfície d'usuari de selecció de segments amb el segment ChurnProneCustomers seleccionat.":::

1. <span data-ttu-id="b226d-138">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="b226d-138">Select **Save**.</span></span>

<span data-ttu-id="b226d-139">Després de desar la destinació de l'exportació, la trobareu a **Administració** > **Exportacions** > **Les meves destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="b226d-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Captura de pantalla amb la llista d'exportacions i alguns segments d'exemple destacats.":::

<span data-ttu-id="b226d-141">Ara podeu [exportar el segment a petició](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b226d-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="b226d-142">L'exportació també s'executarà amb cada [actualització planificada](system.md).</span><span class="sxs-lookup"><span data-stu-id="b226d-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b226d-143">Assegureu-vos que el nombre de registres del segment exportat es troba dins del límit permès de la llicència de l'Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="b226d-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="b226d-144">Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge blob de l'Azure que heu configurat anteriorment.</span><span class="sxs-lookup"><span data-stu-id="b226d-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="b226d-145">Al contenidor es crea automàticament el camí de carpeta següent:</span><span class="sxs-lookup"><span data-stu-id="b226d-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="b226d-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="b226d-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="b226d-147">Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="b226d-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="b226d-148">El *model.json* de les entitats exportades resideix al nivell *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="b226d-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="b226d-149">Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="b226d-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="b226d-150">Definir el model de dades d'experiència (XDM) a l'Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="b226d-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="b226d-151">Abans que les dades exportades des de la informació sobre el públic es puguin utilitzar a l'Adobe Experience Platform, hem de definir l'esquema del Model de dades d'experiència i [configurar les dades del perfil de client en temps real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="b226d-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="b226d-152">Apreneu [què és l'XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i compreneu els [conceptes bàsics de la composició de l'esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="b226d-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="b226d-153">Importar dades a l'Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="b226d-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="b226d-154">Ara que tot està al seu lloc, hem d'importar les dades del públic preparades des de la informació del públic a l'Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="b226d-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="b226d-155">En primer lloc, [creeu una connexió d'origen d'emmagatzematge blob de l'Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="b226d-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="b226d-156">Després de definir la connexió d'origen, [configureu un flux de dades](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) per a una connexió per lots d'emmagatzematge en el núvol per importar la sortida del segment de la informació sobre el públic a l'Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="b226d-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="b226d-157">Crear un públic a l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="b226d-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="b226d-158">Per enviar el correu electrònic d'aquesta campanya, utilitzarem l'Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="b226d-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="b226d-159">Després d'importar les dades a l'Adobe Experience Platform, hem de [crear un públic](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) a l'Adobe Campaign Standard utilitzant les dades de l'Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="b226d-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="b226d-160">Apreneu a [utilitzar el constructor de segments](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) a l'Adobe Campaign Standard per definir un públic a partir de les dades de l'Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="b226d-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="b226d-161">Crear i enviar el correu electrònic mitjançant l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="b226d-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="b226d-162">Creeu el contingut del correu electrònic i, a continuació, [proveu i envieu](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) el correu electrònic.</span><span class="sxs-lookup"><span data-stu-id="b226d-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Correu electrònic d'exemple amb oferta de renovació de l'Adobe Campaign Standard.":::