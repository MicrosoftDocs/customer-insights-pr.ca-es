---
title: Enriquiment amb l'enriquiment de tercers d'Experian
description: Informació general sobre l'enriquiment de tercers d'Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309808"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="dae3f-103">Enriquir els perfils de client amb dades demogràfiques d'Experian (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="dae3f-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="dae3f-104">Experian és un líder global en informes de crèdit d'empreses i consumidors i serveis de màrqueting.</span><span class="sxs-lookup"><span data-stu-id="dae3f-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="dae3f-105">Amb els serveis d'enriquiment de dades dels clients d'Experian, podeu entendre millor els vostres clients enriquint els perfils dels clients amb dades demogràfiques com ara la mida de la llar, els ingressos i més.</span><span class="sxs-lookup"><span data-stu-id="dae3f-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dae3f-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="dae3f-106">Prerequisites</span></span>

<span data-ttu-id="dae3f-107">Per configurar Experian, cal complir els requisits previs següents:</span><span class="sxs-lookup"><span data-stu-id="dae3f-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dae3f-108">Heu de tenir una subscripció activa d'Experian.</span><span class="sxs-lookup"><span data-stu-id="dae3f-108">You have an active Experian subscription.</span></span> <span data-ttu-id="dae3f-109">Per obtenir una subscripció, [poseu-vos en contacte directament amb Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="dae3f-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="dae3f-110">[Obteniu més informació sobre l'enriquiment de dades d'Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="dae3f-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="dae3f-111">Un administrador ja ha configurat una connexió d'Experian *o* teniu permisos d'[administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="dae3f-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="dae3f-112">També necessiteu l'identificador d'usuari, l'identificador del grup i el número de model per al compte de Secure Transport (ST) habilitat per a SSH que Experian ha creat.</span><span class="sxs-lookup"><span data-stu-id="dae3f-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="dae3f-113">Països o regions admesos</span><span class="sxs-lookup"><span data-stu-id="dae3f-113">Supported countries/regions</span></span>

<span data-ttu-id="dae3f-114">Actualment admetem l'enriquiment de perfils de clients només als Estats Units.</span><span class="sxs-lookup"><span data-stu-id="dae3f-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="dae3f-115">Configurar l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="dae3f-115">Configure the enrichment</span></span>

1. <span data-ttu-id="dae3f-116">Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="dae3f-117">Seleccioneu **Enriqueix les meves dades** a la peça d'Experian.</span><span class="sxs-lookup"><span data-stu-id="dae3f-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dae3f-118">![Peça del Experian](media/experian-tile.png "Peça del Experian")</span><span class="sxs-lookup"><span data-stu-id="dae3f-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="dae3f-119">Seleccioneu una [connexió](connections.md) a la llista desplegable.</span><span class="sxs-lookup"><span data-stu-id="dae3f-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="dae3f-120">Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.</span><span class="sxs-lookup"><span data-stu-id="dae3f-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="dae3f-121">Si sou administrador, podeu crear una connexió seleccionant **Afegeix una connexió** i triant a la llista desplegable Experian.</span><span class="sxs-lookup"><span data-stu-id="dae3f-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="dae3f-122">Seleccioneu **Connecta a Experian** per confirmar la selecció de la connexió.</span><span class="sxs-lookup"><span data-stu-id="dae3f-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="dae3f-123">Seleccioneu **Següent** i trieu el **conjunt de dades de client** del qual voleu enriquir les dades demogràfiques d'Experian.</span><span class="sxs-lookup"><span data-stu-id="dae3f-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="dae3f-124">Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.</span><span class="sxs-lookup"><span data-stu-id="dae3f-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. <span data-ttu-id="dae3f-126">Seleccioneu **Següent** i definiu els tipus de camps dels perfils unificats que s'han d'utilitzar per cercar dades demogràfiques coincidents a Experian.</span><span class="sxs-lookup"><span data-stu-id="dae3f-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="dae3f-127">Cal com a mínim un dels camps **Nom i adreça**, **Telèfon** o **Correu electrònic**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="dae3f-128">Per tenir una precisió de coincidència superior, es poden afegir fins a dos camps més.</span><span class="sxs-lookup"><span data-stu-id="dae3f-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="dae3f-129">Aquesta selecció afectarà els camps d'assignació als quals teniu accés al pas següent.</span><span class="sxs-lookup"><span data-stu-id="dae3f-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="dae3f-130">Com més atributs d'identificador clau s'enviïn a Experian, més probable és que hi hagi un percentatge de coincidència superior.</span><span class="sxs-lookup"><span data-stu-id="dae3f-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="dae3f-131">Seleccioneu **Següent** per iniciar l'assignació de camp.</span><span class="sxs-lookup"><span data-stu-id="dae3f-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="dae3f-132">Definiu quins camps dels perfils unificats que s'han d'utilitzar per cercar dades demogràfiques coincidents a Experian.</span><span class="sxs-lookup"><span data-stu-id="dae3f-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="dae3f-133">Els camps obligatoris estan marcats.</span><span class="sxs-lookup"><span data-stu-id="dae3f-133">Required fields are marked.</span></span>

1. <span data-ttu-id="dae3f-134">Proporcioneu un nom per a l'enriquiment i un nom per a l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="dae3f-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="dae3f-135">Seleccioneu **Desa l'enriquiment** després de revisar les opcions.</span><span class="sxs-lookup"><span data-stu-id="dae3f-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="dae3f-136">Configurar la connexió per a Experian</span><span class="sxs-lookup"><span data-stu-id="dae3f-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="dae3f-137">Heu de ser administrador per configurar les connexions.</span><span class="sxs-lookup"><span data-stu-id="dae3f-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="dae3f-138">Seleccioneu **Afegeix una connexió** en configurar un enriquiment *o* aneu a **Administració** > **Connexions** i seleccioneu **Configura** a la peça d'Experian.</span><span class="sxs-lookup"><span data-stu-id="dae3f-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="dae3f-139">Seleccioneu **Introducció**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="dae3f-140">Introduïu un nom per a la connexió al quadre **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="dae3f-141">Introduïu l'identificador d'usuari, l'identificador del grup i el número de model vàlids per al compte de Secure Transport d'Experian.</span><span class="sxs-lookup"><span data-stu-id="dae3f-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="dae3f-142">Reviseu i proporcioneu el vostre consentiment per a la **Privadesa de les dades i conformitat** seleccionant **Accepta**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="dae3f-143">Seleccioneu **Verifica** per validar la configuració.</span><span class="sxs-lookup"><span data-stu-id="dae3f-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="dae3f-144">Després de completar la verificació, seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Subfinestra de configuració de connexió a Experian":::

## <a name="enrichment-results"></a><span data-ttu-id="dae3f-146">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="dae3f-146">Enrichment results</span></span>

<span data-ttu-id="dae3f-147">Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="dae3f-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dae3f-148">També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dae3f-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dae3f-149">El temps de processament depèn de la mida de les dades dels clients i dels processos d'enriquiment configurats per al vostre compte per Experian.</span><span class="sxs-lookup"><span data-stu-id="dae3f-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="dae3f-150">Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="dae3f-151">A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.</span><span class="sxs-lookup"><span data-stu-id="dae3f-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dae3f-152">Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.</span><span class="sxs-lookup"><span data-stu-id="dae3f-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dae3f-153">Passos següents</span><span class="sxs-lookup"><span data-stu-id="dae3f-153">Next steps</span></span>

<span data-ttu-id="dae3f-154">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="dae3f-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dae3f-155">Creeu [segments](segments.md) i [mesures](measures.md) i, fins i tot, [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="dae3f-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dae3f-156">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="dae3f-156">Data privacy and compliance</span></span>

<span data-ttu-id="dae3f-157">Quan permeteu que el Dynamics 365 Customer Insights transmeti dades a Experian, permeteu la transferència de dades fora del límit de conformitat per al Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals.</span><span class="sxs-lookup"><span data-stu-id="dae3f-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dae3f-158">Microsoft transferirà aquestes dades segons la vostra instrucció, però sou responsable d'assegurar que Experian compleixi les obligacions de privadesa o seguretat que tingueu.</span><span class="sxs-lookup"><span data-stu-id="dae3f-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dae3f-159">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dae3f-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dae3f-160">L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="dae3f-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
