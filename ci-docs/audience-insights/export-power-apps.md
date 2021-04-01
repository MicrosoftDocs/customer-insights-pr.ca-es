---
title: Connector del Power Apps
description: Connecteu amb el Power Apps i el Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598143"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="fd616-103">Connector del Microsoft Power Apps (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="fd616-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="fd616-104">Incorporeu perfils de client unificats a les vostres aplicacions personalitzades amb el Power Apps.</span><span class="sxs-lookup"><span data-stu-id="fd616-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="fd616-105">Connectar el Power Apps i el Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fd616-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="fd616-106">El Customer Insights és una de les diverses [fonts de dades disponibles al Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="fd616-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="fd616-107">Consulteu la documentació del Power Apps per obtenir més informació sobre com [afegir una connexió de dades a una aplicació](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="fd616-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="fd616-108">També us recomanem que reviseu [com utilitza el Power Apps la delegació per gestionar grans conjunts de dades a les aplicacions de llenç](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="fd616-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="fd616-109">Entitats disponibles</span><span class="sxs-lookup"><span data-stu-id="fd616-109">Available entities</span></span>

<span data-ttu-id="fd616-110">Després d'afegir el Customer Insights com a connexió de dades, podeu triar les entitats següents al Power Apps:</span><span class="sxs-lookup"><span data-stu-id="fd616-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="fd616-111">Client: per utilitzar les dades del [perfil del client unificat](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="fd616-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="fd616-112">UnifiedActivity: per mostrar la [cronologia d'activitat](activities.md) a l'aplicació.</span><span class="sxs-lookup"><span data-stu-id="fd616-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="fd616-113">Limitacions</span><span class="sxs-lookup"><span data-stu-id="fd616-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="fd616-114">Entitats recuperables</span><span class="sxs-lookup"><span data-stu-id="fd616-114">Retrievable entities</span></span>

<span data-ttu-id="fd616-115">Només podeu recuperar les entitats **Client**, **UnifiedActivity** i **Segments** a través del connector del Power Apps.</span><span class="sxs-lookup"><span data-stu-id="fd616-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="fd616-116">Es mostren altres entitats perquè el connector subjacent els admet mitjançant activacions al Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fd616-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="fd616-117">Delegació</span><span class="sxs-lookup"><span data-stu-id="fd616-117">Delegation</span></span>

<span data-ttu-id="fd616-118">La delegació funciona per a l'entitat Client i UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="fd616-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="fd616-119">Delegació per a l'entitat **Client**: per utilitzar la delegació per a aquesta entitat, els camps s'han d'indexar a [Cerca i filtra l'índex](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="fd616-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="fd616-120">Delegació per a **UnifiedActivity**: la delegació per a aquesta entitat només funciona per als camps **ActivityId** i **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="fd616-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="fd616-121">Per obtenir més informació sobre la delegació, vegeu [Funcions i operacions delegables del Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="fd616-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="fd616-122">Exemple de control de galeria</span><span class="sxs-lookup"><span data-stu-id="fd616-122">Example gallery control</span></span>

<span data-ttu-id="fd616-123">Per exemple, afegiu perfils de client a un [control de galeria](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="fd616-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="fd616-124">Afegiu un control de **Galeria** a una aplicació que estigueu creant.</span><span class="sxs-lookup"><span data-stu-id="fd616-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fd616-125">![Afegir un element de galeria](media/connector-powerapps9.png "Afegir un element de galeria")</span><span class="sxs-lookup"><span data-stu-id="fd616-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="fd616-126">Seleccioneu **Client** com a font de dades dels elements.</span><span class="sxs-lookup"><span data-stu-id="fd616-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fd616-127">![Seleccioneu un origen de dades](media/choose-datasource-powerapps.png "Seleccioneu un origen de dades")</span><span class="sxs-lookup"><span data-stu-id="fd616-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="fd616-128">Podeu canviar la subfinestra de dades a la dreta per seleccionar quin camp de l'entitat Client es mostrarà a la galeria.</span><span class="sxs-lookup"><span data-stu-id="fd616-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="fd616-129">Si voleu mostrar qualsevol camp del client seleccionat a la galeria, empleneu la propietat Text d'una etiqueta: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="fd616-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="fd616-130">Exemple: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="fd616-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="fd616-131">Per mostrar la cronologia unificada d'un client, afegiu-hi un element Galeria i afegiu la propietat Items: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="fd616-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="fd616-132">Exemple: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="fd616-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]