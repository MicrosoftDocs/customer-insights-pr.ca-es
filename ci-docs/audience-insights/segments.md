---
title: Crear i administrar segments
description: Creeu segments de clients per agrupar-los segons diversos atributs.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405175"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="83294-103">Crear i administrar segments</span><span class="sxs-lookup"><span data-stu-id="83294-103">Create and manage segments</span></span>

<span data-ttu-id="83294-104">Els segments us permeten agrupar els clients segons atributs demogràfics, de transaccions o de comportament.</span><span class="sxs-lookup"><span data-stu-id="83294-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="83294-105">Podeu utilitzar segments per orientar les campanyes promocionals, les activitats de vendes i les accions d'atenció al client per assolir els vostres objectius empresarials.</span><span class="sxs-lookup"><span data-stu-id="83294-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="83294-106">Podeu definir filtres complexos sobre l'entitat Perfil del client i les entitats relacionades.</span><span class="sxs-lookup"><span data-stu-id="83294-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="83294-107">Cada segment, després del processament, crea un conjunt de registres de client que podeu exportar i on podeu prendre mesures.</span><span class="sxs-lookup"><span data-stu-id="83294-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="83294-108">S'apliquen [límits de servei](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="83294-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="83294-109">Si no s'indica el contrari, tots els segments són **Segments dinàmics**, que s'actualitzen segons una planificació periòdica.</span><span class="sxs-lookup"><span data-stu-id="83294-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="83294-110">A l'exemple següent s'il·lustra l'ús de la capacitat de segmentació.</span><span class="sxs-lookup"><span data-stu-id="83294-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="83294-111">Hem definit un segment per a clients que han encarregat com a mínim 500 USD de mercaderies en els últims 90 dies *i* que han participat en una trucada al servei d'atenció al client que s'ha derivat.</span><span class="sxs-lookup"><span data-stu-id="83294-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83294-112">![Diversos grups](media/segmentation-group1-2.png "Diversos grups")</span><span class="sxs-lookup"><span data-stu-id="83294-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="83294-113">Crear un segment nou</span><span class="sxs-lookup"><span data-stu-id="83294-113">Create a new segment</span></span>

<span data-ttu-id="83294-114">Els segments s'administren a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="83294-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="83294-115">A les conclusions del públic, aneu a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="83294-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="83294-116">Seleccioneu **Nou** > **Segment en blanc**.</span><span class="sxs-lookup"><span data-stu-id="83294-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="83294-117">A la subfinestra **Segment nou**, trieu un tipus de segment i proporcioneu un **Nom**.</span><span class="sxs-lookup"><span data-stu-id="83294-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="83294-118">Opcionalment, proporcioneu un nom de visualització i una descripció que ajudi a identificar el segment.</span><span class="sxs-lookup"><span data-stu-id="83294-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="83294-119">Seleccioneu **Següent** per accedir a la pàgina **Creador de segments** on definiu un grup.</span><span class="sxs-lookup"><span data-stu-id="83294-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="83294-120">Un grup és un conjunt de clients.</span><span class="sxs-lookup"><span data-stu-id="83294-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="83294-121">Trieu l'entitat que inclou l'atribut pel qual voleu segmentar.</span><span class="sxs-lookup"><span data-stu-id="83294-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="83294-122">Trieu l'atribut pel qual voleu segmentar.</span><span class="sxs-lookup"><span data-stu-id="83294-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="83294-123">Aquest atribut pot tenir un de quatre tipus de valors: numèric, cadena, data o booleà.</span><span class="sxs-lookup"><span data-stu-id="83294-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="83294-124">Trieu un operador i un valor per a l'atribut seleccionat.</span><span class="sxs-lookup"><span data-stu-id="83294-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="83294-125">![Filtre de grup personalitzat](media/customer-group-numbers.png "Filtre de grup de client")</span><span class="sxs-lookup"><span data-stu-id="83294-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="83294-126">Número</span><span class="sxs-lookup"><span data-stu-id="83294-126">Number</span></span> |<span data-ttu-id="83294-127">Definició</span><span class="sxs-lookup"><span data-stu-id="83294-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="83294-128">1</span><span class="sxs-lookup"><span data-stu-id="83294-128">1</span></span>     |<span data-ttu-id="83294-129">Entity</span><span class="sxs-lookup"><span data-stu-id="83294-129">Entity</span></span>          |
   |<span data-ttu-id="83294-130">2</span><span class="sxs-lookup"><span data-stu-id="83294-130">2</span></span>     |<span data-ttu-id="83294-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="83294-131">Attribute</span></span>          |
   |<span data-ttu-id="83294-132">3</span><span class="sxs-lookup"><span data-stu-id="83294-132">3</span></span>    |<span data-ttu-id="83294-133">Operador</span><span class="sxs-lookup"><span data-stu-id="83294-133">Operator</span></span>         |
   |<span data-ttu-id="83294-134">4</span><span class="sxs-lookup"><span data-stu-id="83294-134">4</span></span>    |<span data-ttu-id="83294-135">Valor</span><span class="sxs-lookup"><span data-stu-id="83294-135">Value</span></span>         |

8. <span data-ttu-id="83294-136">Si l'entitat està connectada a l'entitat de client unificada per [relacions](relationships.md), heu de definir el camí de la relació per crear un segment vàlid.</span><span class="sxs-lookup"><span data-stu-id="83294-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="83294-137">Afegiu les entitats del camí de la relació fins que pugueu seleccionar l'entitat **Client: CustomerInsights** del menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="83294-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="83294-138">A continuació, trieu **Tots els registres** per a cada condició.</span><span class="sxs-lookup"><span data-stu-id="83294-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="83294-139">![Camí de la relació durant la creació del segment](media/segments-multiple-relationships.png "Camí de la relació durant la creació del segment")</span><span class="sxs-lookup"><span data-stu-id="83294-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="83294-140">Seleccioneu **Desa** per desar el segment.</span><span class="sxs-lookup"><span data-stu-id="83294-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="83294-141">El segment es desa i es processa si es validen tots els requisits.</span><span class="sxs-lookup"><span data-stu-id="83294-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="83294-142">Altrament, es desarà com a esborrany.</span><span class="sxs-lookup"><span data-stu-id="83294-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="83294-143">Seleccioneu **Torna als segments** per tornar a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="83294-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="83294-144">Administrar segments existents</span><span class="sxs-lookup"><span data-stu-id="83294-144">Manage existing segments</span></span>

<span data-ttu-id="83294-145">A la pàgina **Segments**, podeu visualitzar tots els segments desats i administrar-los.</span><span class="sxs-lookup"><span data-stu-id="83294-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="83294-146">Cada segment està representat per una fila que inclou informació addicional sobre el segment.</span><span class="sxs-lookup"><span data-stu-id="83294-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="83294-147">Podeu ordenar els segments en una columna seleccionant la capçalera de la columna.</span><span class="sxs-lookup"><span data-stu-id="83294-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="83294-148">Utilitzeu el quadre **Cerca** de la cantonada superior dreta per filtrar els segments.</span><span class="sxs-lookup"><span data-stu-id="83294-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83294-149">![Opcions per administrar un segment existent](media/segments-selected-segment.png "Opcions per administrar un segment existent")</span><span class="sxs-lookup"><span data-stu-id="83294-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="83294-150">L'acció següent està disponible quan seleccioneu un segment:</span><span class="sxs-lookup"><span data-stu-id="83294-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="83294-151">**Visualitzar** els detalls del segment, incloent-hi la tendència de recompte de membres per obtenir la visualització prèvia dels membres del segment.</span><span class="sxs-lookup"><span data-stu-id="83294-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="83294-152">**Editar** el segment per canviar-ne les propietats.</span><span class="sxs-lookup"><span data-stu-id="83294-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="83294-153">**Actualitzar** el segment per incloure-hi les dades més recents.</span><span class="sxs-lookup"><span data-stu-id="83294-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="83294-154">**Activar** o **desactivar** el segment.</span><span class="sxs-lookup"><span data-stu-id="83294-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="83294-155">Els segments tenen dos estats possibles: actiu o inactiu.</span><span class="sxs-lookup"><span data-stu-id="83294-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="83294-156">Aquests estats són útils en editar un segment.</span><span class="sxs-lookup"><span data-stu-id="83294-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="83294-157">Per als segments inactius, la definició del segment existeix però encara no conté cap client.</span><span class="sxs-lookup"><span data-stu-id="83294-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="83294-158">Quan s'activa un segment, el seu estat canvia d'"inactiu" a "actiu" i comença a cercar clients que coincideixin amb la definició del segment.</span><span class="sxs-lookup"><span data-stu-id="83294-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="83294-159">Si es configura una [actualització planificada](system.md#schedule-tab), els segments inactius tenen l'**estat** **Omès**, indicant que ni tan sols s'ha intentat una actualització.</span><span class="sxs-lookup"><span data-stu-id="83294-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="83294-160">Quan s'activi un segment inactiu, s'actualitzarà i s'inclourà en les actualitzacions programades.</span><span class="sxs-lookup"><span data-stu-id="83294-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="83294-161">Alternativament, podeu utilitzar la funcionalitat **Planifica més tard** al desplegable **Activa o desactiva** per especificar una data i hora futura per a l'activació i la desactivació d'un segment concret.</span><span class="sxs-lookup"><span data-stu-id="83294-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="83294-162">**Canviar el nom** del segment.</span><span class="sxs-lookup"><span data-stu-id="83294-162">**Rename** the segment.</span></span>
- <span data-ttu-id="83294-163">**Baixar** la llista de membres com a fitxer .CSV.</span><span class="sxs-lookup"><span data-stu-id="83294-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="83294-164">L'opció **Afegeix a** envia la llista d'identificadors de clients al segment per al processament en una altra aplicació.</span><span class="sxs-lookup"><span data-stu-id="83294-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="83294-165">**Suprimir** el segment.</span><span class="sxs-lookup"><span data-stu-id="83294-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="83294-166">Actualitzar els segments</span><span class="sxs-lookup"><span data-stu-id="83294-166">Refresh segments</span></span>

<span data-ttu-id="83294-167">Per actualitzar tots els segments a la vegada, seleccioneu **Actualitza-ho tot** a la pàgina **Segments**; o bé, podeu actualitzar un o diversos segments quan els seleccioneu i trieu **Actualitza** a les opcions.</span><span class="sxs-lookup"><span data-stu-id="83294-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="83294-168">O bé, podeu configurar una actualització periòdica a la planificació a **Administració** > **Sistema** > **Planificació**.</span><span class="sxs-lookup"><span data-stu-id="83294-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="83294-169">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="83294-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="83294-170">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="83294-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="83294-171">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="83294-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="83294-172">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.</span><span class="sxs-lookup"><span data-stu-id="83294-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="83294-173">Baixar i exportar segments</span><span class="sxs-lookup"><span data-stu-id="83294-173">Download and export segments</span></span>

<span data-ttu-id="83294-174">Podeu baixar els segments en un fitxer CSV o exportar-lo al Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="83294-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="83294-175">Baixar els segments a un fitxer CSV</span><span class="sxs-lookup"><span data-stu-id="83294-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="83294-176">A les conclusions del públic, aneu a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="83294-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="83294-177">Seleccioneu els punts suspensius de la peça d'un segment específic.</span><span class="sxs-lookup"><span data-stu-id="83294-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="83294-178">Seleccioneu **Baixa com a CSV** a la llista desplegable d'accions.</span><span class="sxs-lookup"><span data-stu-id="83294-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="83294-179">Exportar segments al Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="83294-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="83294-180">Abans d'exportar els segments al Dynamics 365 Sales, un administrador ha de [crear la destinació d'exportació](export-destinations.md) per al Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="83294-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="83294-181">A les conclusions del públic, aneu a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="83294-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="83294-182">Seleccioneu els punts suspensius de la peça d'un segment específic.</span><span class="sxs-lookup"><span data-stu-id="83294-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="83294-183">Seleccioneu **Afegeix a** de la llista desplegable d'accions i seleccioneu la destinació d'exportació a la qual voleu enviar les dades.</span><span class="sxs-lookup"><span data-stu-id="83294-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="83294-184">Mode d'esborrany per a segments</span><span class="sxs-lookup"><span data-stu-id="83294-184">Draft mode for segments</span></span>

<span data-ttu-id="83294-185">Si no es compleixen tots els requisits per processar un segment, podeu desar el segment com a esborrany i accedir-hi des de la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="83294-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="83294-186">Es desarà com a segment inactiu i no es podrà activar fins que sigui vàlid.</span><span class="sxs-lookup"><span data-stu-id="83294-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="83294-187">Afegir més condicions a un grup</span><span class="sxs-lookup"><span data-stu-id="83294-187">Add more conditions to a group</span></span>

<span data-ttu-id="83294-188">Per afegir més condicions a un grup, podeu utilitzar dos operadors lògics:</span><span class="sxs-lookup"><span data-stu-id="83294-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="83294-189">Operador **AND**: cal complir ambdues condicions com a part del procés de segmentació.</span><span class="sxs-lookup"><span data-stu-id="83294-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="83294-190">Aquesta opció és més útil quan definiu les condicions entre diverses entitats diferents.</span><span class="sxs-lookup"><span data-stu-id="83294-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="83294-191">Operador **OR**: una de les condicions ha de complir-se com a part del procés de segmentació.</span><span class="sxs-lookup"><span data-stu-id="83294-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="83294-192">Aquesta opció és més útil quan definiu diverses condicions per a la mateixa entitat.</span><span class="sxs-lookup"><span data-stu-id="83294-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="83294-193">![Operador OR quan s'ha de complir qualsevol condició](media/segmentation-either-condition.png "Operador OR quan s'ha de complir qualsevol condició")</span><span class="sxs-lookup"><span data-stu-id="83294-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="83294-194">Actualment és possible imbricar un operador **OR** en un operador **AND**, però no a l'inrevés.</span><span class="sxs-lookup"><span data-stu-id="83294-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="83294-195">Combinar diversos grups</span><span class="sxs-lookup"><span data-stu-id="83294-195">Combine multiple groups</span></span>

<span data-ttu-id="83294-196">Cada grup produeix un conjunt específic de clients.</span><span class="sxs-lookup"><span data-stu-id="83294-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="83294-197">Podeu combinar aquests grups per incloure els clients necessaris per al cas empresarial.</span><span class="sxs-lookup"><span data-stu-id="83294-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="83294-198">A les conclusions del públic, aneu a la pàgina **Segments** i seleccioneu un segment.</span><span class="sxs-lookup"><span data-stu-id="83294-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="83294-199">Seleccioneu **Afegeix un grup**.</span><span class="sxs-lookup"><span data-stu-id="83294-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="83294-200">![Afegir un grup a un grup de clients](media/customer-group-add-group.png "Afegir un grup a un grup de clients")</span><span class="sxs-lookup"><span data-stu-id="83294-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="83294-201">Seleccioneu un dels operadors de conjunt següents: **Unió**, **Intersecció** o **Excepció**.</span><span class="sxs-lookup"><span data-stu-id="83294-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="83294-202">![Afegir una unió a un grup de clients](media/customer-group-union.png "Afegir una unió a un grup de clients")</span><span class="sxs-lookup"><span data-stu-id="83294-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="83294-203">Seleccioneu un operador de conjunt per definir un grup nou.</span><span class="sxs-lookup"><span data-stu-id="83294-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="83294-204">Deseu diversos grups per determinar quines dades es conserven:</span><span class="sxs-lookup"><span data-stu-id="83294-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="83294-205">**Unió** uneix els dos grups.</span><span class="sxs-lookup"><span data-stu-id="83294-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="83294-206">**Intersecció** solapa els dos grups.</span><span class="sxs-lookup"><span data-stu-id="83294-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="83294-207">Només es conserven al grup unificat les dades *que siguin comunes* a tots dos grups.</span><span class="sxs-lookup"><span data-stu-id="83294-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="83294-208">**Excepte** combina els dos grups.</span><span class="sxs-lookup"><span data-stu-id="83294-208">**Except** combines the two groups.</span></span> <span data-ttu-id="83294-209">Només es conserven les dades del grup A que *no siguin comunes* a les dades del grup B.</span><span class="sxs-lookup"><span data-stu-id="83294-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="83294-210">Visualitzar l'historial de processament i els membres del segment</span><span class="sxs-lookup"><span data-stu-id="83294-210">View processing history and segment members</span></span>

<span data-ttu-id="83294-211">Podeu veure les dades consolidades d'un segment revisant-ne els detalls.</span><span class="sxs-lookup"><span data-stu-id="83294-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="83294-212">A la pàgina **Segments**, seleccioneu el segment que voleu revisar.</span><span class="sxs-lookup"><span data-stu-id="83294-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="83294-213">A la part superior de la pàgina s'inclou una gràfica de tendències que visualitza els canvis al recompte de membres.</span><span class="sxs-lookup"><span data-stu-id="83294-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="83294-214">Passeu el cursor per sobre dels punts de dades per veure el recompte de membres en una data concreta.</span><span class="sxs-lookup"><span data-stu-id="83294-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="83294-215">Podeu actualitzar el període de temps de la visualització.</span><span class="sxs-lookup"><span data-stu-id="83294-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83294-216">![Interval de temps del segment](media/segment-time-range.png "Interval de temps del segment")</span><span class="sxs-lookup"><span data-stu-id="83294-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="83294-217">La part inferior conté una llista dels membres del segment.</span><span class="sxs-lookup"><span data-stu-id="83294-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="83294-218">Els camps que apareixen en aquesta llista es basen en els atributs de les entitats del vostre segment.</span><span class="sxs-lookup"><span data-stu-id="83294-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="83294-219">La llista és una visualització prèvia dels membres del segment coincidents i mostra els primers 100 registres del segment per tal que pugueu avaluar-lo ràpidament i revisar-ne les definicions si cal.</span><span class="sxs-lookup"><span data-stu-id="83294-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="83294-220">Per veure tots els registres coincidents, heu d'[exportar el segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="83294-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="83294-221">Segments ràpids</span><span class="sxs-lookup"><span data-stu-id="83294-221">Quick segments</span></span>

<span data-ttu-id="83294-222">A banda del creador de segments, hi ha un altre mètode per crear segments.</span><span class="sxs-lookup"><span data-stu-id="83294-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="83294-223">Els segments ràpids permeten la creació de segments simples (amb un únic operador) amb rapidesa i informació instantània.</span><span class="sxs-lookup"><span data-stu-id="83294-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="83294-224">A la pàgina **Segments**, seleccioneu **Nou** > **Crea ràpidament des de**.</span><span class="sxs-lookup"><span data-stu-id="83294-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="83294-225">Seleccioneu l'opció **Perfils** per crear un segment que es basi en l'entitat Client unificada.</span><span class="sxs-lookup"><span data-stu-id="83294-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="83294-226">Seleccioneu l'opció **Mesures** per crear un segment sobre cada tipus d'atribut de client de les mesures que heu creat prèviament a la pàgina **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="83294-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="83294-227">Seleccioneu l'opció **Intel·ligència** per crear un segment sobre una de les entitats de sortida que heu generat mitjançant les funcionalitats **Prediccions** o **Models personalitzats**.</span><span class="sxs-lookup"><span data-stu-id="83294-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="83294-228">Al quadre de diàleg **Crea un segment ràpid**, seleccioneu un atribut del desplegable **Camp**.</span><span class="sxs-lookup"><span data-stu-id="83294-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="83294-229">El sistema proporcionarà alguna informació addicional que us ajudarà a crear millors segments dels vostres clients.</span><span class="sxs-lookup"><span data-stu-id="83294-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="83294-230">Per als camps categòrics, mostrarem 10 comptes de clients principals.</span><span class="sxs-lookup"><span data-stu-id="83294-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="83294-231">Seleccioneu un **Valor** i seleccioneu **Revisa**.</span><span class="sxs-lookup"><span data-stu-id="83294-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="83294-232">Per a un atribut numèric, el sistema mostrarà quin valor de l'atribut queda en el percentil de cada client.</span><span class="sxs-lookup"><span data-stu-id="83294-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="83294-233">Trieu un **Operador** i un **Valor** i, a continuació, seleccioneu **Revisa**.</span><span class="sxs-lookup"><span data-stu-id="83294-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="83294-234">El sistema us proporcionarà una **Mida de segment aproximada**.</span><span class="sxs-lookup"><span data-stu-id="83294-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="83294-235">Podeu triar si voleu generar el segment que heu definit o, en primer lloc, tornar a examinar-lo per aconseguir una mida diferent del segment.</span><span class="sxs-lookup"><span data-stu-id="83294-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="83294-236">![Nom i estimació per a un segment ràpid](media/quick-segment-name.png "Nom i estimació per a un segment ràpid")</span><span class="sxs-lookup"><span data-stu-id="83294-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="83294-237">Proporcioneu un **Nom** per al segment.</span><span class="sxs-lookup"><span data-stu-id="83294-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="83294-238">Opcionalment, proporcioneu un **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="83294-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="83294-239">Seleccioneu **Desa** per crear el segment.</span><span class="sxs-lookup"><span data-stu-id="83294-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="83294-240">Quan el segment s'hagi acabat de processar, podeu visualitzar-lo com qualsevol altre segment que hàgiu creat.</span><span class="sxs-lookup"><span data-stu-id="83294-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="83294-241">Per a les situacions següents, aconsellem utilitzar el creador de segments en comptes de la funció de segments recomanats:</span><span class="sxs-lookup"><span data-stu-id="83294-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="83294-242">Crear segments amb filtres en camps categòrics on l'operador és diferent de l'operador **És**</span><span class="sxs-lookup"><span data-stu-id="83294-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="83294-243">Crear segments amb filtres en camps numèrics on l'operador és diferent d'**Entre**, **Més gran que** i **Més petit que**</span><span class="sxs-lookup"><span data-stu-id="83294-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="83294-244">Crear segments amb filtres en camps de tipus de data</span><span class="sxs-lookup"><span data-stu-id="83294-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="83294-245">Passos següents</span><span class="sxs-lookup"><span data-stu-id="83294-245">Next steps</span></span>

<span data-ttu-id="83294-246">[Exporteu un segment](export-destinations.md) i exploreu la [targeta del client](customer-card-add-in.md) i els [connectors](export-power-bi.md) per obtenir informació al nivell del client.</span><span class="sxs-lookup"><span data-stu-id="83294-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
