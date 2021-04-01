---
title: Exportar les dades del Customer Insights a l'Adobe Campaign Standard
description: Més informació sobre com utilitzar els segments d'informació sobre el públic a l'Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596303"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="85568-103">Utilitzar els segments del Customer Insights a l'Adobe Campaign Standard (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="85568-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="85568-104">Com a usuari de la informació sobre el públic del Dynamics 365 Customer Insights, pot ser que hàgiu creat segments per fer que les campanyes de màrqueting siguin més eficients adreçant-vos a públics rellevants.</span><span class="sxs-lookup"><span data-stu-id="85568-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="85568-105">Per utilitzar un segment de la informació sobre el públic a l'Adobe Experience Platform i aplicacions com ara l'Adobe Campaign Standard, heu de seguir alguns passos que s'indiquen en aquest article.</span><span class="sxs-lookup"><span data-stu-id="85568-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de procés dels passos que es descriuen en aquest article.":::

## <a name="prerequisites"></a><span data-ttu-id="85568-107">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="85568-107">Prerequisites</span></span>

-   <span data-ttu-id="85568-108">Llicència del Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="85568-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="85568-109">Llicència de l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="85568-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="85568-110">Compte de l'Emmagatzematge blob de l'Azure</span><span class="sxs-lookup"><span data-stu-id="85568-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="85568-111">Informació general de la campanya</span><span class="sxs-lookup"><span data-stu-id="85568-111">Campaign Overview</span></span>

<span data-ttu-id="85568-112">Per comprendre millor com podeu utilitzar els segments de la informació sobre el públic a l'Adobe Experience Platform, plantegem una campanya d'exemple fictícia.</span><span class="sxs-lookup"><span data-stu-id="85568-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="85568-113">Suposem que la vostra empresa ofereix un servei mensual basat en subscripció als seus clients dels Estats Units.</span><span class="sxs-lookup"><span data-stu-id="85568-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="85568-114">Voleu identificar els clients les subscripcions dels qual s'han de renovar en els propers vuit dies però que encara no han renovat la seva subscripció.</span><span class="sxs-lookup"><span data-stu-id="85568-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="85568-115">Per mantenir aquests clients, heu d'enviar-los una oferta promocional per correu electrònic, mitjançant l'Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="85568-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="85568-116">En aquest exemple, volem executar la campanya promocional de correu electrònic d'un cop.</span><span class="sxs-lookup"><span data-stu-id="85568-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="85568-117">En aquest article no es cobreix el cas d'ús de l'execució de la campanya més d'una vegada.</span><span class="sxs-lookup"><span data-stu-id="85568-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="85568-118">No obstant això, la informació sobre el públic i l'Adobe Campaign Standard es poden configurar per treballar també per a un escenari de campanya periòdica.</span><span class="sxs-lookup"><span data-stu-id="85568-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="85568-119">Identificar el públic destinatari</span><span class="sxs-lookup"><span data-stu-id="85568-119">Identify your target audience</span></span>

<span data-ttu-id="85568-120">Al nostre escenari, suposem que les adreces electròniques dels clients estan disponibles a la informació sobre el públic i s'han analitzat les seves preferències promocionals per identificar els membres del segment.</span><span class="sxs-lookup"><span data-stu-id="85568-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="85568-121">El [segment que heu definit a la informació sobre el públic](segments.md) s'anomena **ChurnProneCustomers** i voleu enviar a aquests clients la promoció per correu electrònic.</span><span class="sxs-lookup"><span data-stu-id="85568-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la pàgina de segments amb el segment ChurnProneCustomers creat.":::

<span data-ttu-id="85568-123">El correu electrònic d'oferta que voleu enviar inclourà el nom, el cognom i la data de finalització de la subscripció del client.</span><span class="sxs-lookup"><span data-stu-id="85568-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="85568-124">Informa els clients sobre el descompte que obtindran si renoven la subscripció abans que finalitzi.</span><span class="sxs-lookup"><span data-stu-id="85568-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="85568-125">Exportar el públic destinatari</span><span class="sxs-lookup"><span data-stu-id="85568-125">Export your target audience</span></span>

<span data-ttu-id="85568-126">Un cop identificat el públic destinatari, podem configurar l'exportació des de la informació sobre el públic a un compte de l'Emmagatzematge blob de l'Azure.</span><span class="sxs-lookup"><span data-stu-id="85568-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="85568-127">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="85568-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="85568-128">A la peça **Adobe Campaign**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="85568-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Peça de configuració per a l'Adobe Campaign Standard.":::

1. <span data-ttu-id="85568-130">Proporcioneu un **Nom de visualització** per a aquesta nova destinació d'exportació i, a continuació, introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte d'Emmagatzematge blob de l'Azure al qual voleu exportar el segment.</span><span class="sxs-lookup"><span data-stu-id="85568-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuració del compte d'emmagatzematge."::: 

   - <span data-ttu-id="85568-132">Per obtenir més informació sobre com trobar el nom i la clau del compte de l'emmagatzematge blob de l'Azure, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="85568-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="85568-133">Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="85568-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="85568-134">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="85568-134">Select **Next**.</span></span>

1. <span data-ttu-id="85568-135">Trieu el segment que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="85568-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="85568-136">En aquest exemple, és **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="85568-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfície d'usuari de selecció de segments amb el segment ChurnProneCustomers seleccionat.":::

1. <span data-ttu-id="85568-138">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="85568-138">Select **Next**.</span></span>

1. <span data-ttu-id="85568-139">Ara assignem els camps **Origen** del segment d'informació del públic als noms de camp de **Destinació** de l'esquema de perfils de l'Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="85568-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Assignació de camps per al connector de l'Adobe Campaign Standard.":::

   <span data-ttu-id="85568-141">Si voleu afegir més atributs, seleccioneu **Afegeix un atribut**.</span><span class="sxs-lookup"><span data-stu-id="85568-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="85568-142">El nom de destinació pot ser diferent del nom del camp d'origen per tal que pugueu assignar la sortida del segment de la informació del públic a l'Adobe Campaign Standard encara que els camps no tinguin el mateix nom als dos sistemes.</span><span class="sxs-lookup"><span data-stu-id="85568-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="85568-143">L'adreça electrònica s'utilitza com a camp d'identitat, però podeu utilitzar qualsevol altre identificador del perfil del client de la informació del públic per assignar dades a l'Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="85568-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="85568-144">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="85568-144">Select **Save**.</span></span>

<span data-ttu-id="85568-145">Després de desar la destinació de l'exportació, la trobareu a **Administració** > **Exportacions** > **Les meves destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="85568-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Captura de pantalla amb la llista d'exportacions i alguns segments d'exemple destacats.":::

<span data-ttu-id="85568-147">Ara podeu [exportar el segment a petició](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="85568-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="85568-148">L'exportació també s'executarà amb cada [actualització planificada](system.md).</span><span class="sxs-lookup"><span data-stu-id="85568-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="85568-149">Assegureu-vos que el nombre de registres del segment exportat es troba dins del límit permès de la llicència de l'Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="85568-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="85568-150">Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge blob de l'Azure que heu configurat anteriorment.</span><span class="sxs-lookup"><span data-stu-id="85568-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="85568-151">Al contenidor es crea automàticament el camí de carpeta següent:</span><span class="sxs-lookup"><span data-stu-id="85568-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="85568-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="85568-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="85568-153">Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="85568-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="85568-154">Configurar l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="85568-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="85568-155">Quan s'exporta un segment de la informació del públic, conté les columnes que heu seleccionat en definir la destinació d'exportació al pas anterior.</span><span class="sxs-lookup"><span data-stu-id="85568-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="85568-156">Aquestes dades es poden utilitzar per [crear perfils a l'Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="85568-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="85568-157">Per utilitzar el segment a l'Adobe Campaign Standard, hem d'ampliar l'esquema de perfil de l'Adobe Campaign Standard per incloure-hi dos camps addicionals.</span><span class="sxs-lookup"><span data-stu-id="85568-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="85568-158">Apreneu a [ampliar el recurs de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) amb camps nous a l'Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="85568-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="85568-159">Al nostre exemple, aquests camps són *Nom del segment i Data del segment (opcional).*</span><span class="sxs-lookup"><span data-stu-id="85568-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="85568-160">Utilitzarem aquests camps per identificar els perfils de l'Adobe Campaign Standard als quals volem adreçar aquesta campanya.</span><span class="sxs-lookup"><span data-stu-id="85568-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="85568-161">Si no hi ha cap altre registre a l'Adobe Campaign Standard a banda del que importareu, podeu ometre aquest pas.</span><span class="sxs-lookup"><span data-stu-id="85568-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="85568-162">Importar dades a l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="85568-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="85568-163">Ara que tot està al seu lloc, hem d'importar les dades del públic preparades des de la informació del públic a l'Adobe Campaign Standard per crear perfils.</span><span class="sxs-lookup"><span data-stu-id="85568-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="85568-164">Apreneu a [importar perfils a l'Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) utilitzant un flux de treball.</span><span class="sxs-lookup"><span data-stu-id="85568-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="85568-165">El flux de treball d'importació de la imatge següent s'ha configurat per executar-se cada 8 hores i cerca segments d'informació del públic exportats (fitxer .csv a l'Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="85568-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="85568-166">El flux de treball extreu el contingut del fitxer .csv en un ordre de columnes especificat.</span><span class="sxs-lookup"><span data-stu-id="85568-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="85568-167">Aquest flux de treball s'ha creat per realitzar la gestió bàsica d'errors i assegurar que cada registre té una adreça electrònica abans de transmetre les dades a l'Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="85568-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="85568-168">El flux de treball també extreu el nom del segment del nom de fitxer abans d'actualitzar les dades de perfil d'ACS.</span><span class="sxs-lookup"><span data-stu-id="85568-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla d'un flux de treball d'importació a la interfície d'usuari de l'Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="85568-170">Recuperar el públic a l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="85568-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="85568-171">Quan les dades s'importen a l'Adobe Campaign Standard, [podeu crear un flux de treball](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) els clients per *Nom del segment* i *Data del segment* per seleccionar els perfils que s'han identificat per a la campanya d'exemple.</span><span class="sxs-lookup"><span data-stu-id="85568-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="85568-172">Crear i enviar el correu electrònic mitjançant l'Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="85568-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="85568-173">Creeu el contingut del correu electrònic i, a continuació, [proveu i envieu](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) el correu electrònic.</span><span class="sxs-lookup"><span data-stu-id="85568-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Correu electrònic d'exemple amb oferta de renovació de l'Adobe Campaign Standard.":::