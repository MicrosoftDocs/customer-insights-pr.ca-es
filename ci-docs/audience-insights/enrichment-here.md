---
title: Enriquiment de amb l'enriquiment de tercers de HERE Technologies
description: Informació general sobre l'enriquiment de tercers de HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896039"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="237f5-103">Enriquiment de perfils de client amb HERE Technologies (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="237f5-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="237f5-104">HERE Technologies és una empresa de plataformes d'ubicació que proporciona dades i serveis centrats en la ubicació.</span><span class="sxs-lookup"><span data-stu-id="237f5-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="237f5-105">Amb els serveis d'enriquiment de dades de HERE Technologies, podeu crear una localització més precisa dels clients amb la normalització d'adreces o l'extracció de la latitud i la longitud, entre d'altres.</span><span class="sxs-lookup"><span data-stu-id="237f5-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="237f5-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="237f5-106">Prerequisites</span></span>

<span data-ttu-id="237f5-107">Per poder configurar els enriquiments de HERE Technologies, s'han de complir els requisits previs següents:</span><span class="sxs-lookup"><span data-stu-id="237f5-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="237f5-108">Heu de tenir una subscripció activa amb HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="237f5-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="237f5-109">Per obtenir una subscripció, podeu [registrar-vos aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [posar-vos en contacte directament amb HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="237f5-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="237f5-110">Més informació sobre l'enriquiment d'ubicació de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="237f5-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="237f5-111">Hi ha una [connexió](connections.md) de HERE disponible *o* teniu permisos d'[administrador](permissions.md#administrator) i la clau API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="237f5-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="237f5-112">Configurar l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="237f5-112">Configure the enrichment</span></span>

1. <span data-ttu-id="237f5-113">Aneu a **Dades** > **Enriquiment**.</span><span class="sxs-lookup"><span data-stu-id="237f5-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="237f5-114">Seleccioneu **Enriqueix les meves dades** a la peça HERE Technologies i seleccioneu **Comença**.</span><span class="sxs-lookup"><span data-stu-id="237f5-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="237f5-115">![Peça de HERE Technologies](media/HERE-tile.png "Peça de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="237f5-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="237f5-116">Seleccioneu una [connexió](connections.md) a la llista desplegable.</span><span class="sxs-lookup"><span data-stu-id="237f5-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="237f5-117">Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.</span><span class="sxs-lookup"><span data-stu-id="237f5-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="237f5-118">Si sou administrador, podeu crear una connexió seleccionant **Afegeix una connexió**.</span><span class="sxs-lookup"><span data-stu-id="237f5-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="237f5-119">Trieu **HERE Tecnologies** a la llista desplegable.</span><span class="sxs-lookup"><span data-stu-id="237f5-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="237f5-120">Seleccioneu **Connecta't a HERE Technologies** per confirmar la selecció.</span><span class="sxs-lookup"><span data-stu-id="237f5-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="237f5-121">Seleccioneu **Següent** i trieu el **Conjunt de dades de client** que voleu enriquir amb les dades d'ubicació de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="237f5-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="237f5-122">Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.</span><span class="sxs-lookup"><span data-stu-id="237f5-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. <span data-ttu-id="237f5-124">Trieu si voleu assignar camps a l'adreça principal o secundària.</span><span class="sxs-lookup"><span data-stu-id="237f5-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="237f5-125">Podeu especificar una assignació de camps per a ambdues adreces i enriquir els perfils de les dues adreces per separat.</span><span class="sxs-lookup"><span data-stu-id="237f5-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="237f5-126">Per exemple, si hi ha una casa i una adreça de negoci.</span><span class="sxs-lookup"><span data-stu-id="237f5-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="237f5-127">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="237f5-127">Select **Next**.</span></span>

1. <span data-ttu-id="237f5-128">Definiu els camps dels perfils unificats que s'hauran d'utilitzar per cercar dades d'ubicació coincidents des de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="237f5-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="237f5-129">Els camps **Carrer 1** i **Codi postal** són obligatoris per a l'adreça principal o secundària seleccionada.</span><span class="sxs-lookup"><span data-stu-id="237f5-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="237f5-130">Per augmentar la precisió de la coincidència, es poden afegir més camps.</span><span class="sxs-lookup"><span data-stu-id="237f5-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="237f5-131">![Pàgina de configuració d'enriquiment de HERE Technologies](media/enrichment-HERE-configuration.png "Pàgina de configuració d'enriquiment de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="237f5-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="237f5-132">Seleccioneu **Següent** per completar l'assignació de camp.</span><span class="sxs-lookup"><span data-stu-id="237f5-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="237f5-133">Proporcioneu un nom per a l'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="237f5-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="237f5-134">1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.</span><span class="sxs-lookup"><span data-stu-id="237f5-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="237f5-135">Configurar la connexió per a HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="237f5-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="237f5-136">Heu de ser administrador per configurar les connexions.</span><span class="sxs-lookup"><span data-stu-id="237f5-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="237f5-137">Seleccioneu **Afegeix una connexió** en configurar un enriquiment *o* aneu a **Administració** > **Connexions** i seleccioneu **Configuració** a la peça HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="237f5-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="237f5-138">Introduïu un nom per a la connexió al quadre **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="237f5-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="237f5-139">Proporcioneu una clau d'API vàlida de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="237f5-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="237f5-140">Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**</span><span class="sxs-lookup"><span data-stu-id="237f5-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="237f5-141">Seleccioneu **Verifica** per validar la configuració.</span><span class="sxs-lookup"><span data-stu-id="237f5-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="237f5-142">Després de completar la verificació, seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="237f5-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="237f5-143">![Pàgina de configuració de la connexió de HERE Technologies](media/enrichment-HERE-connection.png "Pàgina de configuració de la connexió de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="237f5-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="237f5-144">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="237f5-144">Enrichment results</span></span>

<span data-ttu-id="237f5-145">Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="237f5-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="237f5-146">També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="237f5-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="237f5-147">El temps de processament dependrà de la mida de les dades del client i dels temps de resposta de l'API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="237f5-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="237f5-148">Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**.</span><span class="sxs-lookup"><span data-stu-id="237f5-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="237f5-149">A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.</span><span class="sxs-lookup"><span data-stu-id="237f5-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="237f5-150">Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.</span><span class="sxs-lookup"><span data-stu-id="237f5-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="237f5-151">Passos següents</span><span class="sxs-lookup"><span data-stu-id="237f5-151">Next steps</span></span>

<span data-ttu-id="237f5-152">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="237f5-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="237f5-153">Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="237f5-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="237f5-154">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="237f5-154">Data privacy and compliance</span></span>

<span data-ttu-id="237f5-155">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a HERE Technologies, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="237f5-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="237f5-156">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que HERE Technologies compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="237f5-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="237f5-157">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="237f5-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="237f5-158">L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="237f5-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
