---
title: Crear i administrar segments
description: Creeu segments de clients per agrupar-los segons diversos atributs.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597039"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="c5e61-103">Crear i administrar segments</span><span class="sxs-lookup"><span data-stu-id="c5e61-103">Create and manage segments</span></span>

<span data-ttu-id="c5e61-104">Els segments us permeten agrupar els clients segons atributs demogràfics, de transaccions o de comportament.</span><span class="sxs-lookup"><span data-stu-id="c5e61-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="c5e61-105">Podeu utilitzar segments per orientar les campanyes promocionals, les activitats de vendes i les accions d'atenció al client per assolir els vostres objectius empresarials.</span><span class="sxs-lookup"><span data-stu-id="c5e61-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="c5e61-106">Podeu definir filtres complexos sobre l'entitat Perfil del client i les entitats relacionades.</span><span class="sxs-lookup"><span data-stu-id="c5e61-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="c5e61-107">Cada segment, després del processament, crea un conjunt de registres de client que podeu exportar i on podeu prendre mesures.</span><span class="sxs-lookup"><span data-stu-id="c5e61-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="c5e61-108">S'apliquen [límits de servei](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c5e61-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="c5e61-109">Si no s'indica el contrari, tots els segments són **Segments dinàmics**, que s'actualitzen segons una planificació periòdica.</span><span class="sxs-lookup"><span data-stu-id="c5e61-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="c5e61-110">A l'exemple següent s'il·lustra l'ús de la capacitat de segmentació.</span><span class="sxs-lookup"><span data-stu-id="c5e61-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="c5e61-111">Hem definit un segment per a clients que han encarregat com a mínim 500 USD de mercaderies en els últims 90 dies *i* que han participat en una trucada al servei d'atenció al client que s'ha derivat.</span><span class="sxs-lookup"><span data-stu-id="c5e61-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c5e61-112">![Diversos grups](media/segmentation-group1-2.png "Diversos grups")</span><span class="sxs-lookup"><span data-stu-id="c5e61-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="c5e61-113">Crear un segment nou</span><span class="sxs-lookup"><span data-stu-id="c5e61-113">Create a new segment</span></span>

<span data-ttu-id="c5e61-114">Els segments s'administren a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="c5e61-115">A les conclusions del públic, aneu a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="c5e61-116">Seleccioneu **Nou** > **Segment en blanc**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="c5e61-117">A la subfinestra **Segment nou**, trieu un tipus de segment i proporcioneu un **Nom**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="c5e61-118">Opcionalment, proporcioneu un nom de visualització i una descripció que ajudi a identificar el segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="c5e61-119">Seleccioneu **Següent** per accedir a la pàgina **Creador de segments** on definiu un grup.</span><span class="sxs-lookup"><span data-stu-id="c5e61-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="c5e61-120">Un grup és un conjunt de clients.</span><span class="sxs-lookup"><span data-stu-id="c5e61-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="c5e61-121">Trieu l'entitat que inclou l'atribut pel qual voleu segmentar.</span><span class="sxs-lookup"><span data-stu-id="c5e61-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="c5e61-122">Trieu l'atribut pel qual voleu segmentar.</span><span class="sxs-lookup"><span data-stu-id="c5e61-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="c5e61-123">Aquest atribut pot tenir un de quatre tipus de valors: numèric, cadena, data o booleà.</span><span class="sxs-lookup"><span data-stu-id="c5e61-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="c5e61-124">Trieu un operador i un valor per a l'atribut seleccionat.</span><span class="sxs-lookup"><span data-stu-id="c5e61-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c5e61-125">![Filtre de grup personalitzat](media/customer-group-numbers.png "Filtre de grup de client")</span><span class="sxs-lookup"><span data-stu-id="c5e61-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="c5e61-126">Número</span><span class="sxs-lookup"><span data-stu-id="c5e61-126">Number</span></span> |<span data-ttu-id="c5e61-127">Definició</span><span class="sxs-lookup"><span data-stu-id="c5e61-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="c5e61-128">1</span><span class="sxs-lookup"><span data-stu-id="c5e61-128">1</span></span>     |<span data-ttu-id="c5e61-129">Entity</span><span class="sxs-lookup"><span data-stu-id="c5e61-129">Entity</span></span>          |
   |<span data-ttu-id="c5e61-130">2</span><span class="sxs-lookup"><span data-stu-id="c5e61-130">2</span></span>     |<span data-ttu-id="c5e61-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="c5e61-131">Attribute</span></span>          |
   |<span data-ttu-id="c5e61-132">3</span><span class="sxs-lookup"><span data-stu-id="c5e61-132">3</span></span>    |<span data-ttu-id="c5e61-133">Operador</span><span class="sxs-lookup"><span data-stu-id="c5e61-133">Operator</span></span>         |
   |<span data-ttu-id="c5e61-134">4</span><span class="sxs-lookup"><span data-stu-id="c5e61-134">4</span></span>    |<span data-ttu-id="c5e61-135">Valor</span><span class="sxs-lookup"><span data-stu-id="c5e61-135">Value</span></span>         |

8. <span data-ttu-id="c5e61-136">Si l'entitat està connectada a l'entitat de client unificada per [relacions](relationships.md), heu de definir el camí de la relació per crear un segment vàlid.</span><span class="sxs-lookup"><span data-stu-id="c5e61-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="c5e61-137">Afegiu les entitats del camí de la relació fins que pugueu seleccionar l'entitat **Client: CustomerInsights** del menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="c5e61-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="c5e61-138">A continuació, trieu **Tots els registres** per a cada condició.</span><span class="sxs-lookup"><span data-stu-id="c5e61-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c5e61-139">![Camí de la relació durant la creació del segment](media/segments-multiple-relationships.png "Camí de la relació durant la creació del segment")</span><span class="sxs-lookup"><span data-stu-id="c5e61-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="c5e61-140">Per defecte, els segments generen una entitat de sortida que conté tots els atributs dels perfils de client que coincideixen amb els filtres definits.</span><span class="sxs-lookup"><span data-stu-id="c5e61-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="c5e61-141">Si un segment es basa en entitats que no són l'entitat *Client*, podeu afegir més atributs d'aquestes entitats a l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="c5e61-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="c5e61-142">Seleccioneu **Atributs del projecte** per triar els atributs que s'annexaran a l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="c5e61-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="c5e61-143">Exemple: un segment es basa en una entitat que conté dades d'activitat de client relacionades amb l'entitat *Client*.</span><span class="sxs-lookup"><span data-stu-id="c5e61-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="c5e61-144">El segment cerca tots els clients que han trucat al servei d'assistència durant els darrers 60 dies.</span><span class="sxs-lookup"><span data-stu-id="c5e61-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="c5e61-145">Podeu triar si voleu annexar la durada de la trucada i el nombre de trucades a tots els registres de client coincidents de l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="c5e61-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="c5e61-146">Aquesta informació pot ser útil per enviar correus electrònics amb enllaços útils als articles d'ajuda en línia i preguntes freqüents als clients que truquen sovint.</span><span class="sxs-lookup"><span data-stu-id="c5e61-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="c5e61-147">Seleccioneu **Desa** per desar el segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="c5e61-148">El segment es desa i es processa si es validen tots els requisits.</span><span class="sxs-lookup"><span data-stu-id="c5e61-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="c5e61-149">Altrament, es desarà com a esborrany.</span><span class="sxs-lookup"><span data-stu-id="c5e61-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="c5e61-150">Seleccioneu **Torna als segments** per tornar a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="c5e61-151">Administrar segments existents</span><span class="sxs-lookup"><span data-stu-id="c5e61-151">Manage existing segments</span></span>

<span data-ttu-id="c5e61-152">A la pàgina **Segments**, podeu visualitzar tots els segments desats i administrar-los.</span><span class="sxs-lookup"><span data-stu-id="c5e61-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="c5e61-153">Cada segment està representat per una fila que inclou informació addicional sobre el segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="c5e61-154">Podeu ordenar els segments en una columna seleccionant la capçalera de la columna.</span><span class="sxs-lookup"><span data-stu-id="c5e61-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="c5e61-155">Utilitzeu el quadre **Cerca** de la cantonada superior dreta per filtrar els segments.</span><span class="sxs-lookup"><span data-stu-id="c5e61-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c5e61-156">![Opcions per administrar un segment existent](media/segments-selected-segment.png "Opcions per administrar un segment existent")</span><span class="sxs-lookup"><span data-stu-id="c5e61-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="c5e61-157">L'acció següent està disponible quan seleccioneu un segment:</span><span class="sxs-lookup"><span data-stu-id="c5e61-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="c5e61-158">**Visualitzar** els detalls del segment, incloent-hi la tendència de recompte de membres per obtenir la visualització prèvia dels membres del segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="c5e61-159">**Editar** el segment per canviar-ne les propietats.</span><span class="sxs-lookup"><span data-stu-id="c5e61-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="c5e61-160">**Crear un duplicat** d'un segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="c5e61-161">Podeu editar-ne les propietats immediatament o simplement desar el duplicat.</span><span class="sxs-lookup"><span data-stu-id="c5e61-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="c5e61-162">**Actualitzar** el segment per incloure-hi les dades més recents.</span><span class="sxs-lookup"><span data-stu-id="c5e61-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="c5e61-163">**Activar** o **desactivar** el segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="c5e61-164">Els segments tenen dos estats possibles: actiu o inactiu.</span><span class="sxs-lookup"><span data-stu-id="c5e61-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="c5e61-165">Aquests estats són útils en editar un segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="c5e61-166">Per als segments inactius, la definició del segment existeix però encara no conté cap client.</span><span class="sxs-lookup"><span data-stu-id="c5e61-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="c5e61-167">Quan s'activa un segment, el seu estat canvia d'"inactiu" a "actiu" i comença a cercar clients que coincideixin amb la definició del segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="c5e61-168">Si es configura una [actualització planificada](system.md#schedule-tab), els segments inactius tenen l'**estat** **Omès**, indicant que ni tan sols s'ha intentat una actualització.</span><span class="sxs-lookup"><span data-stu-id="c5e61-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="c5e61-169">Quan s'activi un segment inactiu, s'actualitzarà i s'inclourà en les actualitzacions programades.</span><span class="sxs-lookup"><span data-stu-id="c5e61-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="c5e61-170">Alternativament, podeu utilitzar la funcionalitat **Planifica més tard** al desplegable **Activa o desactiva** per especificar una data i hora futura per a l'activació i la desactivació d'un segment concret.</span><span class="sxs-lookup"><span data-stu-id="c5e61-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="c5e61-171">**Canviar el nom** del segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-171">**Rename** the segment.</span></span>
- <span data-ttu-id="c5e61-172">**Baixar** la llista de membres com a fitxer .CSV.</span><span class="sxs-lookup"><span data-stu-id="c5e61-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="c5e61-173">L'opció **Afegeix a** envia la llista d'identificadors de clients al segment per al processament en una altra aplicació.</span><span class="sxs-lookup"><span data-stu-id="c5e61-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="c5e61-174">**Suprimir** el segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="c5e61-175">Actualitzar els segments</span><span class="sxs-lookup"><span data-stu-id="c5e61-175">Refresh segments</span></span>

<span data-ttu-id="c5e61-176">Per actualitzar tots els segments a la vegada, seleccioneu **Actualitza-ho tot** a la pàgina **Segments**; o bé, podeu actualitzar un o diversos segments quan els seleccioneu i trieu **Actualitza** a les opcions.</span><span class="sxs-lookup"><span data-stu-id="c5e61-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="c5e61-177">O bé, podeu configurar una actualització periòdica a la planificació a **Administració** > **Sistema** > **Planificació**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="c5e61-178">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="c5e61-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c5e61-179">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c5e61-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c5e61-180">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="c5e61-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c5e61-181">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.</span><span class="sxs-lookup"><span data-stu-id="c5e61-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="c5e61-182">Baixar i exportar segments</span><span class="sxs-lookup"><span data-stu-id="c5e61-182">Download and export segments</span></span>

<span data-ttu-id="c5e61-183">Podeu baixar els segments en un fitxer CSV o exportar-lo al Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c5e61-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="c5e61-184">Baixar els segments a un fitxer CSV</span><span class="sxs-lookup"><span data-stu-id="c5e61-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="c5e61-185">A les conclusions del públic, aneu a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c5e61-186">Seleccioneu els punts suspensius de la peça d'un segment específic.</span><span class="sxs-lookup"><span data-stu-id="c5e61-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c5e61-187">Seleccioneu **Baixa com a CSV** a la llista desplegable d'accions.</span><span class="sxs-lookup"><span data-stu-id="c5e61-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="c5e61-188">Exportar segments al Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c5e61-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="c5e61-189">Abans d'exportar els segments al Dynamics 365 Sales, un administrador ha de [crear la destinació d'exportació](export-destinations.md) per al Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c5e61-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="c5e61-190">A les conclusions del públic, aneu a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c5e61-191">Seleccioneu els punts suspensius de la peça d'un segment específic.</span><span class="sxs-lookup"><span data-stu-id="c5e61-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c5e61-192">Seleccioneu **Afegeix a** de la llista desplegable d'accions i seleccioneu la destinació d'exportació a la qual voleu enviar les dades.</span><span class="sxs-lookup"><span data-stu-id="c5e61-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="c5e61-193">Mode d'esborrany per a segments</span><span class="sxs-lookup"><span data-stu-id="c5e61-193">Draft mode for segments</span></span>

<span data-ttu-id="c5e61-194">Si no es compleixen tots els requisits per processar un segment, podeu desar el segment com a esborrany i accedir-hi des de la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="c5e61-195">Es desarà com a segment inactiu i no es podrà activar fins que sigui vàlid.</span><span class="sxs-lookup"><span data-stu-id="c5e61-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="c5e61-196">Afegir més condicions a un grup</span><span class="sxs-lookup"><span data-stu-id="c5e61-196">Add more conditions to a group</span></span>

<span data-ttu-id="c5e61-197">Per afegir més condicions a un grup, podeu utilitzar dos operadors lògics:</span><span class="sxs-lookup"><span data-stu-id="c5e61-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="c5e61-198">Operador **AND**: cal complir ambdues condicions com a part del procés de segmentació.</span><span class="sxs-lookup"><span data-stu-id="c5e61-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="c5e61-199">Aquesta opció és més útil quan definiu les condicions entre diverses entitats diferents.</span><span class="sxs-lookup"><span data-stu-id="c5e61-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="c5e61-200">Operador **OR**: una de les condicions ha de complir-se com a part del procés de segmentació.</span><span class="sxs-lookup"><span data-stu-id="c5e61-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="c5e61-201">Aquesta opció és més útil quan definiu diverses condicions per a la mateixa entitat.</span><span class="sxs-lookup"><span data-stu-id="c5e61-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c5e61-202">![Operador OR quan s'ha de complir qualsevol condició](media/segmentation-either-condition.png "Operador OR quan s'ha de complir qualsevol condició")</span><span class="sxs-lookup"><span data-stu-id="c5e61-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="c5e61-203">Actualment és possible imbricar un operador **OR** en un operador **AND**, però no a l'inrevés.</span><span class="sxs-lookup"><span data-stu-id="c5e61-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="c5e61-204">Combinar diversos grups</span><span class="sxs-lookup"><span data-stu-id="c5e61-204">Combine multiple groups</span></span>

<span data-ttu-id="c5e61-205">Cada grup produeix un conjunt específic de clients.</span><span class="sxs-lookup"><span data-stu-id="c5e61-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="c5e61-206">Podeu combinar aquests grups per incloure els clients necessaris per al cas empresarial.</span><span class="sxs-lookup"><span data-stu-id="c5e61-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="c5e61-207">A les conclusions del públic, aneu a la pàgina **Segments** i seleccioneu un segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="c5e61-208">Seleccioneu **Afegeix un grup**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c5e61-209">![Afegir un grup a un grup de clients](media/customer-group-add-group.png "Afegir un grup a un grup de clients")</span><span class="sxs-lookup"><span data-stu-id="c5e61-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="c5e61-210">Seleccioneu un dels operadors de conjunt següents: **Unió**, **Intersecció** o **Excepció**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c5e61-211">![Afegir una unió a un grup de clients](media/customer-group-union.png "Afegir una unió a un grup de clients")</span><span class="sxs-lookup"><span data-stu-id="c5e61-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="c5e61-212">Seleccioneu un operador de conjunt per definir un grup nou.</span><span class="sxs-lookup"><span data-stu-id="c5e61-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="c5e61-213">Deseu diversos grups per determinar quines dades es conserven:</span><span class="sxs-lookup"><span data-stu-id="c5e61-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="c5e61-214">**Unió** uneix els dos grups.</span><span class="sxs-lookup"><span data-stu-id="c5e61-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="c5e61-215">**Intersecció** solapa els dos grups.</span><span class="sxs-lookup"><span data-stu-id="c5e61-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="c5e61-216">Només es conserven al grup unificat les dades *que siguin comunes* a tots dos grups.</span><span class="sxs-lookup"><span data-stu-id="c5e61-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="c5e61-217">**Excepte** combina els dos grups.</span><span class="sxs-lookup"><span data-stu-id="c5e61-217">**Except** combines the two groups.</span></span> <span data-ttu-id="c5e61-218">Només es conserven les dades del grup A que *no siguin comunes* a les dades del grup B.</span><span class="sxs-lookup"><span data-stu-id="c5e61-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="c5e61-219">Visualitzar l'historial de processament i els membres del segment</span><span class="sxs-lookup"><span data-stu-id="c5e61-219">View processing history and segment members</span></span>

<span data-ttu-id="c5e61-220">Podeu veure les dades consolidades d'un segment revisant-ne els detalls.</span><span class="sxs-lookup"><span data-stu-id="c5e61-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="c5e61-221">A la pàgina **Segments**, seleccioneu el segment que voleu revisar.</span><span class="sxs-lookup"><span data-stu-id="c5e61-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="c5e61-222">A la part superior de la pàgina s'inclou una gràfica de tendències que visualitza els canvis al recompte de membres.</span><span class="sxs-lookup"><span data-stu-id="c5e61-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="c5e61-223">Passeu el cursor per sobre dels punts de dades per veure el recompte de membres en una data concreta.</span><span class="sxs-lookup"><span data-stu-id="c5e61-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="c5e61-224">Podeu actualitzar el període de temps de la visualització.</span><span class="sxs-lookup"><span data-stu-id="c5e61-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c5e61-225">![Interval de temps del segment](media/segment-time-range.png "Interval de temps del segment")</span><span class="sxs-lookup"><span data-stu-id="c5e61-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="c5e61-226">La part inferior conté una llista dels membres del segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="c5e61-227">Els camps que apareixen en aquesta llista es basen en els atributs de les entitats del vostre segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="c5e61-228">La llista és una visualització prèvia dels membres del segment coincidents i mostra els primers 100 registres del segment per tal que pugueu avaluar-lo ràpidament i revisar-ne les definicions si cal.</span><span class="sxs-lookup"><span data-stu-id="c5e61-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="c5e61-229">Per veure tots els registres coincidents, heu d'[exportar el segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c5e61-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="c5e61-230">Segments ràpids</span><span class="sxs-lookup"><span data-stu-id="c5e61-230">Quick segments</span></span>

<span data-ttu-id="c5e61-231">A banda del creador de segments, hi ha un altre mètode per crear segments.</span><span class="sxs-lookup"><span data-stu-id="c5e61-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="c5e61-232">Els segments ràpids permeten la creació de segments simples (amb un únic operador) amb rapidesa i informació instantània.</span><span class="sxs-lookup"><span data-stu-id="c5e61-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="c5e61-233">A la pàgina **Segments**, seleccioneu **Nou** > **Crea ràpidament des de**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="c5e61-234">Seleccioneu l'opció **Perfils** per crear un segment que es basi en l'entitat Client unificada.</span><span class="sxs-lookup"><span data-stu-id="c5e61-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="c5e61-235">Seleccioneu l'opció **Mesures** per crear un segment sobre cada tipus d'atribut de client de les mesures que heu creat prèviament a la pàgina **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="c5e61-236">Seleccioneu l'opció **Intel·ligència** per crear un segment sobre una de les entitats de sortida que heu generat mitjançant les funcionalitats **Prediccions** o **Models personalitzats**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="c5e61-237">Al quadre de diàleg **Crea un segment ràpid**, seleccioneu un atribut del desplegable **Camp**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="c5e61-238">El sistema proporcionarà alguna informació addicional que us ajudarà a crear millors segments dels vostres clients.</span><span class="sxs-lookup"><span data-stu-id="c5e61-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="c5e61-239">Per als camps categòrics, mostrarem 10 comptes de clients principals.</span><span class="sxs-lookup"><span data-stu-id="c5e61-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="c5e61-240">Seleccioneu un **Valor** i seleccioneu **Revisa**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="c5e61-241">Per a un atribut numèric, el sistema mostrarà quin valor de l'atribut queda en el percentil de cada client.</span><span class="sxs-lookup"><span data-stu-id="c5e61-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="c5e61-242">Trieu un **Operador** i un **Valor** i, a continuació, seleccioneu **Revisa**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="c5e61-243">El sistema us proporcionarà una **Mida de segment aproximada**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="c5e61-244">Podeu triar si voleu generar el segment que heu definit o, en primer lloc, tornar a examinar-lo per aconseguir una mida diferent del segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c5e61-245">![Nom i estimació per a un segment ràpid](media/quick-segment-name.png "Nom i estimació per a un segment ràpid")</span><span class="sxs-lookup"><span data-stu-id="c5e61-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="c5e61-246">Proporcioneu un **Nom** per al segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="c5e61-247">Opcionalment, proporcioneu un **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="c5e61-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="c5e61-248">Seleccioneu **Desa** per crear el segment.</span><span class="sxs-lookup"><span data-stu-id="c5e61-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="c5e61-249">Quan el segment s'hagi acabat de processar, podeu visualitzar-lo com qualsevol altre segment que hàgiu creat.</span><span class="sxs-lookup"><span data-stu-id="c5e61-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="c5e61-250">Per a les situacions següents, aconsellem utilitzar el creador de segments en comptes de la funció de segments recomanats:</span><span class="sxs-lookup"><span data-stu-id="c5e61-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="c5e61-251">Crear segments amb filtres en camps categòrics on l'operador és diferent de l'operador **És**</span><span class="sxs-lookup"><span data-stu-id="c5e61-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="c5e61-252">Crear segments amb filtres en camps numèrics on l'operador és diferent d'**Entre**, **Més gran que** i **Més petit que**</span><span class="sxs-lookup"><span data-stu-id="c5e61-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="c5e61-253">Crear segments amb filtres en camps de tipus de data</span><span class="sxs-lookup"><span data-stu-id="c5e61-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="c5e61-254">Passos següents</span><span class="sxs-lookup"><span data-stu-id="c5e61-254">Next steps</span></span>

<span data-ttu-id="c5e61-255">[Exporteu un segment](export-destinations.md) i exploreu la [targeta del client](customer-card-add-in.md) i els [connectors](export-power-bi.md) per obtenir informació al nivell del client.</span><span class="sxs-lookup"><span data-stu-id="c5e61-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]