---
title: Enriquiment de amb l'enriquiment de tercers de HERE Technologies
description: Informació general sobre l'enriquiment de tercers de HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668666"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="cbe78-103">Enriquiment de perfils de client amb HERE Technologies (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="cbe78-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="cbe78-104">HERE Technologies és una empresa de plataformes d'ubicació que proporciona dades i serveis centrats en la ubicació.</span><span class="sxs-lookup"><span data-stu-id="cbe78-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="cbe78-105">Amb els serveis d'enriquiment de dades de HERE Technologies, podeu crear una localització més precisa dels clients amb la normalització d'adreces o l'extracció de la latitud i la longitud, entre d'altres.</span><span class="sxs-lookup"><span data-stu-id="cbe78-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cbe78-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="cbe78-106">Prerequisites</span></span>

<span data-ttu-id="cbe78-107">Per poder configurar els enriquiments de HERE Technologies, s'han de complir els requisits previs següents:</span><span class="sxs-lookup"><span data-stu-id="cbe78-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="cbe78-108">Heu de tenir una subscripció activa amb HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="cbe78-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="cbe78-109">Per obtenir una subscripció, podeu [registrar-vos aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [posar-vos en contacte directament amb HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="cbe78-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="cbe78-110">Més informació sobre l'enriquiment d'ubicació de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="cbe78-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="cbe78-111">Teniu la clau d'API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="cbe78-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="cbe78-112">Teniu permisos d'[Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="cbe78-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="cbe78-113">Configuració</span><span class="sxs-lookup"><span data-stu-id="cbe78-113">Configuration</span></span>

1. <span data-ttu-id="cbe78-114">Aneu a **Dades** > **Enriquiment**.</span><span class="sxs-lookup"><span data-stu-id="cbe78-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="cbe78-115">Seleccioneu **Enriqueix les meves dades** a la peça de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="cbe78-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cbe78-116">![Peça de HERE Technologies](media/HERE-tile.png "Peça de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="cbe78-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="cbe78-117">Introduïu una **Clau de l'API de HERE Technologies** activa.</span><span class="sxs-lookup"><span data-stu-id="cbe78-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="cbe78-118">Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**.</span><span class="sxs-lookup"><span data-stu-id="cbe78-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="cbe78-119">Confirmeu totes dues entrades seleccionant **Connecta a HERE**.</span><span class="sxs-lookup"><span data-stu-id="cbe78-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="cbe78-120">Seleccioneu **Afegeix dades** i trieu si voleu assignar camps a l'adreça principal o secundària.</span><span class="sxs-lookup"><span data-stu-id="cbe78-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="cbe78-121">Podeu especificar una assignació de camps per a totes dues adreces (per exemple, una adreça particular i de la feina) i enriquir els perfils per a ambdues adreces de manera separada.</span><span class="sxs-lookup"><span data-stu-id="cbe78-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="cbe78-122">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="cbe78-122">Select **Next**.</span></span>

1. <span data-ttu-id="cbe78-123">Definiu els camps dels perfils unificats que s'hauran d'utilitzar per cercar dades d'ubicació coincidents des de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="cbe78-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="cbe78-124">Els camps **Carrer 1** i **Codi postal** són obligatoris per a l'adreça principal o secundària seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cbe78-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="cbe78-125">Per augmentar la precisió de la coincidència, es poden afegir més camps.</span><span class="sxs-lookup"><span data-stu-id="cbe78-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cbe78-126">![Pàgina de configuració d'enriquiment de HERE Technologies](media/enrichment-HERE-configuration.png "Pàgina de configuració d'enriquiment de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="cbe78-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="cbe78-127">Seleccioneu **Aplica** per completar l'assignació de camps.</span><span class="sxs-lookup"><span data-stu-id="cbe78-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="cbe78-128">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="cbe78-128">Enrichment results</span></span>

<span data-ttu-id="cbe78-129">Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="cbe78-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="cbe78-130">També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cbe78-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cbe78-131">El temps de processament dependrà de la mida de les dades del client i dels temps de resposta de l'API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="cbe78-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="cbe78-132">Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**.</span><span class="sxs-lookup"><span data-stu-id="cbe78-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="cbe78-133">A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.</span><span class="sxs-lookup"><span data-stu-id="cbe78-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="cbe78-134">Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.</span><span class="sxs-lookup"><span data-stu-id="cbe78-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cbe78-135">Passos següents</span><span class="sxs-lookup"><span data-stu-id="cbe78-135">Next steps</span></span>

<span data-ttu-id="cbe78-136">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="cbe78-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="cbe78-137">Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="cbe78-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cbe78-138">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="cbe78-138">Data privacy and compliance</span></span>

<span data-ttu-id="cbe78-139">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a HERE Technologies, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="cbe78-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cbe78-140">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que HERE Technologies compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="cbe78-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="cbe78-141">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cbe78-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cbe78-142">L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="cbe78-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
