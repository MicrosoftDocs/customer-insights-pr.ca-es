---
title: Veure perfils de client
description: Obtingueu una visualització combinada de les dades unificades del client.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596855"
---
# <a name="customer-profiles"></a><span data-ttu-id="159da-103">Perfils de client</span><span class="sxs-lookup"><span data-stu-id="159da-103">Customer profiles</span></span>

<span data-ttu-id="159da-104">A la pàgina **Clients** es mostra una visualització combinada dels clients basada en les dades de perfil recopilades de [les diferents fonts de dades](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="159da-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="159da-105">Els perfils de client estaran disponibles un cop [hàgiu creat l'entitat Client unificada](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="159da-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="159da-106">Assegureu-vos de completar el procés d'unificació de dades per obtenir visualitzacions més riques dels clients.</span><span class="sxs-lookup"><span data-stu-id="159da-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="159da-107">La pàgina també us permet cercar clients.</span><span class="sxs-lookup"><span data-stu-id="159da-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="159da-108">Els clients poden ser persones o organitzacions (visualització prèvia).</span><span class="sxs-lookup"><span data-stu-id="159da-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="159da-109">Cada client o perfil d'organització està representat per una peça.</span><span class="sxs-lookup"><span data-stu-id="159da-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="159da-110">Seleccioneu una peça per veure informació addicional sobre aquest client o organització en concret.</span><span class="sxs-lookup"><span data-stu-id="159da-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="159da-111">Utilitzeu els controls de pàgina de la part inferior de la pàgina per veure registres addicionals.</span><span class="sxs-lookup"><span data-stu-id="159da-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="159da-112">![Perfils de client B2C](media/profiles-customers.png "Perfils de client B2C")</span><span class="sxs-lookup"><span data-stu-id="159da-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="159da-113">Organitzacions (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="159da-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="159da-114">![Perfils de client B2B](media/profile-customers-b2b.png "Perfils de client B2B")</span><span class="sxs-lookup"><span data-stu-id="159da-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="159da-115">Si no podeu veure les peces del en seleccionar **Clients** a la navegació, l'administrador ha de [definir com a mínim un atribut que es pugui cercar](search-filter-index.md) a l'**Índex de cerca i filtratge**.</span><span class="sxs-lookup"><span data-stu-id="159da-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="159da-116">Cercar clients</span><span class="sxs-lookup"><span data-stu-id="159da-116">Search for customers</span></span>

<span data-ttu-id="159da-117">Cerqueu clients introduint un nom o algun altre atribut al quadre de cerca.</span><span class="sxs-lookup"><span data-stu-id="159da-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="159da-118">La cerca només funciona dins de l'entitat Perfil de client creada durant el procés d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="159da-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="159da-119">Com a administrador, podeu configurar els atributs que es poden cercar amb la pàgina **Índex de cerca i filtre**.</span><span class="sxs-lookup"><span data-stu-id="159da-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="159da-120">Per obtenir més informació, vegeu [Administrar l'índex de cerca i filtre](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="159da-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="159da-121">Filtrar clients</span><span class="sxs-lookup"><span data-stu-id="159da-121">Filter customers</span></span>

<span data-ttu-id="159da-122">Podeu filtrar clients pels camps de l'entitat Perfil de client.</span><span class="sxs-lookup"><span data-stu-id="159da-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="159da-123">De forma similar a la cerca, l'administrador primer haurà de definir els camps com a filtrables mitjançant la pàgina **Índex de cerca i filtre**.</span><span class="sxs-lookup"><span data-stu-id="159da-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="159da-124">Seleccioneu **Filtra** a la pàgina **Clients**.</span><span class="sxs-lookup"><span data-stu-id="159da-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="159da-125">Activeu les caselles que hi ha al costat dels atributs pels quals voleu filtrar els clients.</span><span class="sxs-lookup"><span data-stu-id="159da-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="159da-126">![Perfils de client](media/profiles-customers3.png "Perfils de client")</span><span class="sxs-lookup"><span data-stu-id="159da-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="159da-127">Per suprimir els filtres, seleccioneu **Esborra els filtres** a la pàgina **Clients**.</span><span class="sxs-lookup"><span data-stu-id="159da-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="159da-128">Pàgina Detalls del client</span><span class="sxs-lookup"><span data-stu-id="159da-128">Customer details page</span></span>

<span data-ttu-id="159da-129">Seleccioneu qualsevol de les peces del client per obrir la **pàgina Detalls del client**.</span><span class="sxs-lookup"><span data-stu-id="159da-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="159da-130">Aquesta visualització conté informació unificada del client seleccionat.</span><span class="sxs-lookup"><span data-stu-id="159da-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="159da-131">Els detalls del client inclouen:</span><span class="sxs-lookup"><span data-stu-id="159da-131">Customer details include:</span></span>

-   <span data-ttu-id="159da-132">**Peça del perfil del client:** En aquesta peça es mostren els diferents valors de l'entitat unificada del perfil del client.</span><span class="sxs-lookup"><span data-stu-id="159da-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="159da-133">Entre aquests detalls s'inclouen l'adreça de correu electrònic, el nom, la ciutat, etc.</span><span class="sxs-lookup"><span data-stu-id="159da-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="159da-134">**Possibles interessos, possibles marques:** Mostra si heu configurat un enriquiment principal.</span><span class="sxs-lookup"><span data-stu-id="159da-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="159da-135">Representa els possibles interessos i afinitats per a les marques que podria tenir un client amb un perfil semblant a aquest client.</span><span class="sxs-lookup"><span data-stu-id="159da-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="159da-136">Per obtenir més informació, vegeu [Enriquir els perfils de clients amb afinitats de marca i interès](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="159da-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="159da-137">**Mesures:** Mostra si heu configurat una o més mesures d'un tipus concret: mesures d'atribut de client.</span><span class="sxs-lookup"><span data-stu-id="159da-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="159da-138">Inclouen KPI calculats sobre els vostres clients per a cada client individual.</span><span class="sxs-lookup"><span data-stu-id="159da-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="159da-139">Per obtenir més informació, vegeu [Definir i administrar mesures](measures.md).</span><span class="sxs-lookup"><span data-stu-id="159da-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="159da-140">**Cronologia d'activitat:** Mostra si heu configurat activitats.</span><span class="sxs-lookup"><span data-stu-id="159da-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="159da-141">La visualització de cronologia conté activitats d'aquest client ordenades cronològicament, començant per l'activitat més recent.</span><span class="sxs-lookup"><span data-stu-id="159da-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="159da-142">Per obtenir més informació, vegeu [Activitats del client](activities.md).</span><span class="sxs-lookup"><span data-stu-id="159da-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="159da-143">Seleccioneu **Torna als clients** per tornar a la pàgina de cerca de clients.</span><span class="sxs-lookup"><span data-stu-id="159da-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="159da-144">Passos següents</span><span class="sxs-lookup"><span data-stu-id="159da-144">Next steps</span></span>

<span data-ttu-id="159da-145">[Afegiu més fonts de dades](data-sources.md) o [creeu segments de client](segments.md).</span><span class="sxs-lookup"><span data-stu-id="159da-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]