---
title: Exportar dades del Customer Insights
description: Administrar les exportacions per compartir dades.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305466"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="08803-103">Informació general sobre exportacions (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="08803-103">Exports (preview) overview</span></span>

<span data-ttu-id="08803-104">A la pàgina **Exportacions** es mostren totes les exportacions configurades.</span><span class="sxs-lookup"><span data-stu-id="08803-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="08803-105">Les exportacions comparteixen dades específiques amb diverses aplicacions.</span><span class="sxs-lookup"><span data-stu-id="08803-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="08803-106">Poden incloure perfils de clients o entitats, esquemes i detalls d'assignació.</span><span class="sxs-lookup"><span data-stu-id="08803-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="08803-107">Cada exportació requereix una [connexió, configurada per un administrador, per administrar l'autenticació i l'accés](connections.md).</span><span class="sxs-lookup"><span data-stu-id="08803-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="08803-108">Aneu a **Dades** > **Exportacions** per visualitzar la pàgina d'exportacions.</span><span class="sxs-lookup"><span data-stu-id="08803-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="08803-109">Totes les funcions d'usuari poden veure les exportacions configurades.</span><span class="sxs-lookup"><span data-stu-id="08803-109">All user roles can view configured exports.</span></span> <span data-ttu-id="08803-110">Utilitzeu el camp de cerca de la barra d'ordres per cercar exportacions pel seu nom, nom de connexió o tipus de connexió.</span><span class="sxs-lookup"><span data-stu-id="08803-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="08803-111">Configurar una exportació nova</span><span class="sxs-lookup"><span data-stu-id="08803-111">Set up a new export</span></span>

<span data-ttu-id="08803-112">Per configurar o editar una exportació, heu de tenir connexions disponibles.</span><span class="sxs-lookup"><span data-stu-id="08803-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="08803-113">Les connexions depenen de la vostra [funció d'usuari](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="08803-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="08803-114">Els administradors tenen accés a totes les connexions.</span><span class="sxs-lookup"><span data-stu-id="08803-114">Administrators have access to all connections.</span></span> <span data-ttu-id="08803-115">També poden crear connexions noves quan configuren una exportació.</span><span class="sxs-lookup"><span data-stu-id="08803-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="08803-116">Els col·laboradors poden tenir accés a connexions específiques.</span><span class="sxs-lookup"><span data-stu-id="08803-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="08803-117">Depenen dels administradors per configurar i compartir connexions.</span><span class="sxs-lookup"><span data-stu-id="08803-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="08803-118">La llista d'exportacions mostra als contribuïdors si poden editar o només visualitzar una exportació a la columna **Els vostres permisos**.</span><span class="sxs-lookup"><span data-stu-id="08803-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="08803-119">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="08803-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="08803-120">Els visualitzadors només poden visualitzar les exportacions existents, però no les poden crear.</span><span class="sxs-lookup"><span data-stu-id="08803-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="08803-121">Definir una exportació nova</span><span class="sxs-lookup"><span data-stu-id="08803-121">Define a new export</span></span>

1. <span data-ttu-id="08803-122">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="08803-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="08803-123">Seleccioneu **Afegeix una exportació** per crear una exportació nova.</span><span class="sxs-lookup"><span data-stu-id="08803-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="08803-124">A la subfinestra **Configura l'exportació**, seleccioneu la connexió que voleu utilitzar.</span><span class="sxs-lookup"><span data-stu-id="08803-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="08803-125">Les [connexions](connections.md)les administren els administradors.</span><span class="sxs-lookup"><span data-stu-id="08803-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="08803-126">Proporcioneu els detalls necessaris i seleccioneu **Desa** per crear l'exportació.</span><span class="sxs-lookup"><span data-stu-id="08803-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="08803-127">Definir una exportació nova basada en una exportació existent</span><span class="sxs-lookup"><span data-stu-id="08803-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="08803-128">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="08803-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="08803-129">A la llista d'exportacions, seleccioneu l'exportació que vulgueu duplicar.</span><span class="sxs-lookup"><span data-stu-id="08803-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="08803-130">Seleccioneu **Crea un duplicat** a la barra d'ordres per obrir la subfinestra **Configura l'exportació** amb els detalls de l'exportació seleccionada.</span><span class="sxs-lookup"><span data-stu-id="08803-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="08803-131">Reviseu i adapteu l'exportació i seleccioneu **Desa** per crear una exportació nova.</span><span class="sxs-lookup"><span data-stu-id="08803-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="08803-132">Editar una exportació</span><span class="sxs-lookup"><span data-stu-id="08803-132">Edit an export</span></span>

1. <span data-ttu-id="08803-133">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="08803-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="08803-134">A la llista d'exportacions, seleccioneu l'exportació que vulgueu editar.</span><span class="sxs-lookup"><span data-stu-id="08803-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="08803-135">Seleccioneu **Edita** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="08803-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="08803-136">Canvieu els valors que voleu actualitzar i seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="08803-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="08803-137">Visualitzar les exportacions i els detalls d'exportació</span><span class="sxs-lookup"><span data-stu-id="08803-137">View exports and export details</span></span>

<span data-ttu-id="08803-138">Un cop creades les destinacions d'exportació, es mostren a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="08803-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="08803-139">Tots els usuaris poden veure quines dades es comparteixen i el seu estat més recent.</span><span class="sxs-lookup"><span data-stu-id="08803-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="08803-140">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="08803-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="08803-141">Els usuaris sense editar permisos seleccionen **Visualitza** en comptes d'**Edita** per veure els detalls de l'exportació.</span><span class="sxs-lookup"><span data-stu-id="08803-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="08803-142">A la subfinestra lateral es mostra la configuració d'una exportació.</span><span class="sxs-lookup"><span data-stu-id="08803-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="08803-143">Sense permisos d'edició, els valors no es poden canviar.</span><span class="sxs-lookup"><span data-stu-id="08803-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="08803-144">Seleccioneu **Tanca** per tornar a la pàgina d'exportacions.</span><span class="sxs-lookup"><span data-stu-id="08803-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="08803-145">Planificar i executar exportacions</span><span class="sxs-lookup"><span data-stu-id="08803-145">Schedule and run exports</span></span>

<span data-ttu-id="08803-146">Cada exportació que configureu té una planificació d'actualització.</span><span class="sxs-lookup"><span data-stu-id="08803-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="08803-147">Durant una actualització, el sistema cerca dades noves o actualitzades per incloure-les en una exportació.</span><span class="sxs-lookup"><span data-stu-id="08803-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="08803-148">Per defecte, les exportacions s'executen com a part de cada [actualització del sistema planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="08803-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="08803-149">Podeu personalitzar la planificació d'actualització o desactivar-la per executar les exportacions manualment.</span><span class="sxs-lookup"><span data-stu-id="08803-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="08803-150">Les planificacions d'exportació depenen de l'estat del vostre entorn.</span><span class="sxs-lookup"><span data-stu-id="08803-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="08803-151">Si hi ha actualitzacions en curs en [dependències](system.md#refresh-policies) quan s'hagi d'iniciar una exportació planificada, el sistema finalitzarà primer les actualitzacions i executarà l'exportació.</span><span class="sxs-lookup"><span data-stu-id="08803-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="08803-152">Podeu veure quan s'ha actualitzat per darrer cop una exportació a la columna **Actualitzat**.</span><span class="sxs-lookup"><span data-stu-id="08803-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="08803-153">Exportacions planificades</span><span class="sxs-lookup"><span data-stu-id="08803-153">Schedule exports</span></span>

<span data-ttu-id="08803-154">Podeu definir planificacions d'actualització personalitzades per a exportacions individuals o diverses exportacions alhora.</span><span class="sxs-lookup"><span data-stu-id="08803-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="08803-155">La planificació definida actualment es mostra a la columna **Planificació** de la llista d'exportació.</span><span class="sxs-lookup"><span data-stu-id="08803-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="08803-156">El permís per canviar la planificació és el mateix que per [editar i definir exportacions](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="08803-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="08803-157">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="08803-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="08803-158">Seleccioneu l'exportació que voleu planificar.</span><span class="sxs-lookup"><span data-stu-id="08803-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="08803-159">Seleccioneu **Planifica** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="08803-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="08803-160">A la subfinestra **Planifica l'exportació**, definiu l'**Execució planificada** com a **Activada** per executar l'exportació automàticament.</span><span class="sxs-lookup"><span data-stu-id="08803-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="08803-161">Definiu-la com a **Desactivada** per actualitzar-la manualment.</span><span class="sxs-lookup"><span data-stu-id="08803-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="08803-162">Per actualitzar automàticament les exportacions, trieu un valor de **Periodicitat** i especifiqueu-ne els detalls.</span><span class="sxs-lookup"><span data-stu-id="08803-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="08803-163">El temps definit s'aplica a totes les instàncies d'una periodicitat.</span><span class="sxs-lookup"><span data-stu-id="08803-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="08803-164">És el moment en què una exportació hauria de començar a actualitzar-se.</span><span class="sxs-lookup"><span data-stu-id="08803-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="08803-165">Per aplicar i activar els canvis, seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="08803-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="08803-166">Quan editeu la planificació de diverses exportacions, heu de fer una selecció a **Conserva o substitueix les planificacions**:</span><span class="sxs-lookup"><span data-stu-id="08803-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="08803-167">**Conserva planificacions individuals**: mantingueu la planificació definida prèviament per a les exportacions seleccionades i només les inhabiliteu o habiliteu.</span><span class="sxs-lookup"><span data-stu-id="08803-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="08803-168">**Defineix una planificació nova per a totes les exportacions seleccionades**: substituïu les planificacions existents de les exportacions seleccionades.</span><span class="sxs-lookup"><span data-stu-id="08803-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="08803-169">Executar exportacions segons la demanda</span><span class="sxs-lookup"><span data-stu-id="08803-169">Run exports on demand</span></span>

<span data-ttu-id="08803-170">Per exportar dades sense esperar una actualització planificada, aneu a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="08803-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="08803-171">Per executar totes les exportacions, seleccioneu **Executa-ho tot** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="08803-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="08803-172">Aquesta acció només executarà les exportacions que tenen una planificació activa.</span><span class="sxs-lookup"><span data-stu-id="08803-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="08803-173">Per executar una única exportació, seleccioneu-la a la llista i seleccioneu **Executa** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="08803-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="08803-174">Així s'executen les exportacions sense planificacions actives.</span><span class="sxs-lookup"><span data-stu-id="08803-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="08803-175">Suprimir una exportació</span><span class="sxs-lookup"><span data-stu-id="08803-175">Remove an Export</span></span>

1. <span data-ttu-id="08803-176">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="08803-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="08803-177">Seleccioneu l'exportació que voleu suprimir.</span><span class="sxs-lookup"><span data-stu-id="08803-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="08803-178">Seleccioneu **Elimina** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="08803-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="08803-179">Confirmeu la supressió seleccionant **Suprimeix** a la pantalla de confirmació.</span><span class="sxs-lookup"><span data-stu-id="08803-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
