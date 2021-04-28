---
title: Exportar dades del Customer Insights
description: Administrar les exportacions per compartir dades.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896131"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="810a7-103">Informació general sobre exportacions (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="810a7-103">Exports (preview) overview</span></span>

<span data-ttu-id="810a7-104">A la pàgina **Exportacions** es mostren totes les exportacions configurades.</span><span class="sxs-lookup"><span data-stu-id="810a7-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="810a7-105">Les exportacions comparteixen dades específiques amb diverses aplicacions.</span><span class="sxs-lookup"><span data-stu-id="810a7-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="810a7-106">Poden incloure perfils de clients o entitats, esquemes i detalls d'assignació.</span><span class="sxs-lookup"><span data-stu-id="810a7-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="810a7-107">Cada exportació requereix una [connexió, configurada per un administrador, per administrar l'autenticació i l'accés](connections.md).</span><span class="sxs-lookup"><span data-stu-id="810a7-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="810a7-108">Fins al març de 2021, les exportacions creaven una connexió al servei corresponent de manera automàtica.</span><span class="sxs-lookup"><span data-stu-id="810a7-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="810a7-109">Ara les exportacions requereixen una [connexió, creada i compartida per un administrador](connections.md) per poder-les crear.</span><span class="sxs-lookup"><span data-stu-id="810a7-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="810a7-110">Aneu a **Dades** > **Exportacions** per visualitzar la pàgina d'exportacions.</span><span class="sxs-lookup"><span data-stu-id="810a7-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="810a7-111">Totes les funcions d'usuari tenen accés per visualitzar les exportacions configurades.</span><span class="sxs-lookup"><span data-stu-id="810a7-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="810a7-112">Utilitzeu el camp de cerca a la barra d'ordres per cercar les exportacions pel seu nom, nom de connexió o tipus de connexió.</span><span class="sxs-lookup"><span data-stu-id="810a7-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="810a7-113">Configurar una exportació nova</span><span class="sxs-lookup"><span data-stu-id="810a7-113">Set up a new export</span></span>

<span data-ttu-id="810a7-114">Per configurar o editar una exportació, heu de tenir connexions disponibles.</span><span class="sxs-lookup"><span data-stu-id="810a7-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="810a7-115">Les connexions depenen de la vostra [funció d'usuari](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="810a7-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="810a7-116">Els administradors tenen accés a totes les connexions.</span><span class="sxs-lookup"><span data-stu-id="810a7-116">Administrators have access to all connections.</span></span> <span data-ttu-id="810a7-117">També poden crear connexions noves quan configuren una exportació.</span><span class="sxs-lookup"><span data-stu-id="810a7-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="810a7-118">Els col·laboradors poden tenir accés a connexions específiques.</span><span class="sxs-lookup"><span data-stu-id="810a7-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="810a7-119">Depenen dels administradors per configurar i compartir connexions.</span><span class="sxs-lookup"><span data-stu-id="810a7-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="810a7-120">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="810a7-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="810a7-121">Els visualitzadors només poden visualitzar les exportacions existents, però no les poden crear.</span><span class="sxs-lookup"><span data-stu-id="810a7-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="810a7-122">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="810a7-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="810a7-123">Seleccioneu **Afegeix una exportació** per crear una destinació d'exportació nova.</span><span class="sxs-lookup"><span data-stu-id="810a7-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="810a7-124">A la subfinestra **Configura l'exportació**, seleccioneu la connexió que voleu utilitzar.</span><span class="sxs-lookup"><span data-stu-id="810a7-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="810a7-125">Les [connexions](connections.md)les administren els administradors.</span><span class="sxs-lookup"><span data-stu-id="810a7-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="810a7-126">Proporcioneu els detalls necessaris i seleccioneu **Desa** per crear l'exportació.</span><span class="sxs-lookup"><span data-stu-id="810a7-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="810a7-127">Editar una exportació</span><span class="sxs-lookup"><span data-stu-id="810a7-127">Edit an export</span></span>

1. <span data-ttu-id="810a7-128">Seleccioneu els punt suspensius verticals de la destinació d'exportació que voleu editar.</span><span class="sxs-lookup"><span data-stu-id="810a7-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="810a7-129">Al menú desplegable, seleccioneu **Edita**.</span><span class="sxs-lookup"><span data-stu-id="810a7-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="810a7-130">Canvieu els valors que voleu actualitzar i seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="810a7-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="810a7-131">Visualitzar les exportacions i els detalls d'exportació</span><span class="sxs-lookup"><span data-stu-id="810a7-131">View Exports and export details</span></span>

<span data-ttu-id="810a7-132">Un cop creades les destinacions d'exportació, es mostren a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="810a7-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="810a7-133">Tots els usuaris poden veure quines dades es comparteixen i el seu estat més recent.</span><span class="sxs-lookup"><span data-stu-id="810a7-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="810a7-134">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="810a7-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="810a7-135">Els usuaris sense permisos d'edició seleccionen **Visualització** en lloc d'**Edició** per veure els detalls de l'exportació.</span><span class="sxs-lookup"><span data-stu-id="810a7-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="810a7-136">Aquesta subfinestra lateral mostra la configuració d'aquesta exportació.</span><span class="sxs-lookup"><span data-stu-id="810a7-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="810a7-137">Sense permisos d'edició, els valors no es poden canviar.</span><span class="sxs-lookup"><span data-stu-id="810a7-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="810a7-138">Seleccioneu **Tanca** per tornar a la pàgina d'exportacions.</span><span class="sxs-lookup"><span data-stu-id="810a7-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="810a7-139">Executar exportacions segons la demanda</span><span class="sxs-lookup"><span data-stu-id="810a7-139">Run exports on demand</span></span>

<span data-ttu-id="810a7-140">Després de configurar una exportació, s'executarà amb cada [actualització planificada](system.md#schedule-tab) sempre que tingui una connexió que funcioni.</span><span class="sxs-lookup"><span data-stu-id="810a7-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="810a7-141">Per exportar dades sense esperar una actualització planificada, aneu a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="810a7-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="810a7-142">Teniu dues opcions:</span><span class="sxs-lookup"><span data-stu-id="810a7-142">You have two options:</span></span>

- <span data-ttu-id="810a7-143">Per executar totes les exportacions, seleccioneu **Executa-ho tot** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="810a7-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="810a7-144">Per executar una sola exportació, seleccioneu els punts suspensius (...) d'un element de llista i, a continuació, trieu **Executa**.</span><span class="sxs-lookup"><span data-stu-id="810a7-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="810a7-145">Suprimir una exportació</span><span class="sxs-lookup"><span data-stu-id="810a7-145">Remove an Export</span></span>

1. <span data-ttu-id="810a7-146">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="810a7-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="810a7-147">Seleccioneu els punt suspensius verticals de l'exportació que voleu suprimir.</span><span class="sxs-lookup"><span data-stu-id="810a7-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="810a7-148">Seleccioneu **Suprimeix** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="810a7-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="810a7-149">Confirmeu la supressió seleccionant **Suprimeix** a la pantalla de confirmació.</span><span class="sxs-lookup"><span data-stu-id="810a7-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
