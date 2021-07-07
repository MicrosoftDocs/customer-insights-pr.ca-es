---
title: Segments als coneixements del públic
description: Informació general sobre els segments i com crear-ne i administrar-los.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306245"
---
# <a name="segments-overview"></a><span data-ttu-id="17970-103">Descripció general dels segments</span><span class="sxs-lookup"><span data-stu-id="17970-103">Segments overview</span></span>

<span data-ttu-id="17970-104">Els segments us permeten agrupar els clients segons atributs demogràfics, de transaccions o de comportament.</span><span class="sxs-lookup"><span data-stu-id="17970-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="17970-105">Podeu utilitzar segments per orientar les campanyes promocionals, les activitats de vendes i les accions d'atenció al client per assolir els vostres objectius empresarials.</span><span class="sxs-lookup"><span data-stu-id="17970-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="17970-106">Els perfils de client que coincideixen amb els filtres d'una definició de segment es coneixen com a *membres* d'un segment.</span><span class="sxs-lookup"><span data-stu-id="17970-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="17970-107">S'apliquen [límits de servei](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="17970-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="17970-108">Crear un segment nou</span><span class="sxs-lookup"><span data-stu-id="17970-108">Create a new segment</span></span>

<span data-ttu-id="17970-109">Hi ha diverses maneres de crear un segment nou:</span><span class="sxs-lookup"><span data-stu-id="17970-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="17970-110">Segment complex amb el creador de segments: [segment en blanc](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="17970-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="17970-111">Segments senzills amb un operador: [segment ràpid](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="17970-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="17970-112">Forma amb tecnologia d'IA per trobar clients semblants: [clients semblants](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="17970-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="17970-113">Suggeriments amb tecnologia d'IA basats en mesures o atributs: [segments suggerits per millorar mesures](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="17970-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="17970-114">Suggeriments basats en activitats: [segments suggerits segons l'activitat del client](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="17970-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="17970-115">Administrar segments existents</span><span class="sxs-lookup"><span data-stu-id="17970-115">Manage existing segments</span></span>

<span data-ttu-id="17970-116">Aneu a la pàgina **Segments** per visualitzar tots els segments desats i administrar-los.</span><span class="sxs-lookup"><span data-stu-id="17970-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="17970-117">Cada segment està representat per una fila que inclou informació addicional sobre el segment.</span><span class="sxs-lookup"><span data-stu-id="17970-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segment seleccionat amb la llista desplegable d'opcions i opcions disponibles.":::

<span data-ttu-id="17970-119">L'acció següent està disponible quan seleccioneu un segment:</span><span class="sxs-lookup"><span data-stu-id="17970-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="17970-120">**Visualitzar** els detalls del segment, incloent-hi la tendència de recompte de membres per obtenir la visualització prèvia dels membres del segment.</span><span class="sxs-lookup"><span data-stu-id="17970-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="17970-121">**Editar** el segment per canviar-ne les propietats.</span><span class="sxs-lookup"><span data-stu-id="17970-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="17970-122">**Crear un duplicat** d'un segment.</span><span class="sxs-lookup"><span data-stu-id="17970-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="17970-123">Podeu editar-ne les propietats immediatament o simplement desar el duplicat.</span><span class="sxs-lookup"><span data-stu-id="17970-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="17970-124">**Actualitzar** el segment per incloure-hi les dades més recents.</span><span class="sxs-lookup"><span data-stu-id="17970-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="17970-125">**Activar** o **desactivar** el segment.</span><span class="sxs-lookup"><span data-stu-id="17970-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="17970-126">Els segments tenen dos estats possibles: actiu o inactiu.</span><span class="sxs-lookup"><span data-stu-id="17970-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="17970-127">Aquests estats són útils en editar un segment.</span><span class="sxs-lookup"><span data-stu-id="17970-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="17970-128">Per als segments inactius, la definició del segment existeix però encara no conté cap client.</span><span class="sxs-lookup"><span data-stu-id="17970-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="17970-129">Quan s'activa un segment, el seu estat canvia d'"inactiu" a "actiu" i comença a cercar clients que coincideixin amb la definició del segment.</span><span class="sxs-lookup"><span data-stu-id="17970-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="17970-130">Si es configura una [actualització planificada](system.md#schedule-tab), els segments inactius tenen l'**estat** **Omès**, indicant que ni tan sols s'ha intentat una actualització.</span><span class="sxs-lookup"><span data-stu-id="17970-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="17970-131">Quan s'activi un segment inactiu, s'actualitzarà i s'inclourà en les actualitzacions programades.</span><span class="sxs-lookup"><span data-stu-id="17970-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="17970-132">Alternativament, podeu utilitzar la funcionalitat **Planifica més tard** al desplegable **Activa o desactiva** per especificar una data i hora futura per a l'activació i la desactivació d'un segment concret.</span><span class="sxs-lookup"><span data-stu-id="17970-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="17970-133">**Canviar el nom** del segment.</span><span class="sxs-lookup"><span data-stu-id="17970-133">**Rename** the segment.</span></span>
- <span data-ttu-id="17970-134">**Baixar** la llista de membres com a fitxer .CSV.</span><span class="sxs-lookup"><span data-stu-id="17970-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="17970-135">**Administreu exportacions** per veure el segment relacionat amb les exportacions i administrar-les.</span><span class="sxs-lookup"><span data-stu-id="17970-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="17970-136">Més informació sobre les exportacions</span><span class="sxs-lookup"><span data-stu-id="17970-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="17970-137">**Suprimir** el segment.</span><span class="sxs-lookup"><span data-stu-id="17970-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="17970-138">Actualitzar els segments</span><span class="sxs-lookup"><span data-stu-id="17970-138">Refresh segments</span></span>

<span data-ttu-id="17970-139">Per actualitzar tots els segments a la vegada, seleccioneu **Actualitza-ho tot** a la pàgina **Segments**; o bé, podeu actualitzar un o diversos segments quan els seleccioneu i trieu **Actualitza** a les opcions.</span><span class="sxs-lookup"><span data-stu-id="17970-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="17970-140">O bé, podeu configurar una actualització periòdica a la planificació a **Administració** > **Sistema** > **Planificació**.</span><span class="sxs-lookup"><span data-stu-id="17970-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="17970-141">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="17970-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="17970-142">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="17970-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="17970-143">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="17970-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="17970-144">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.</span><span class="sxs-lookup"><span data-stu-id="17970-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="17970-145">Exportar segments</span><span class="sxs-lookup"><span data-stu-id="17970-145">Export segments</span></span>

<span data-ttu-id="17970-146">Podeu exportar un segment des de la pàgina de segments o des de la [pàgina d'exportació](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="17970-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="17970-147">Aneu a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="17970-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="17970-148">Seleccioneu **Mostra'n més [...]** al segment que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="17970-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="17970-149">Seleccioneu **Administra les exportacions** a la llista desplegable d'accions.</span><span class="sxs-lookup"><span data-stu-id="17970-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="17970-150">S'obre la pàgina **Exportacions (versió preliminar) per al segment**.</span><span class="sxs-lookup"><span data-stu-id="17970-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="17970-151">Podeu veure totes les exportacions configurades agrupades per exportacions que contenen el segment actual o que no les contenen.</span><span class="sxs-lookup"><span data-stu-id="17970-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="17970-152">Per afegir el segment seleccionat a una exportació, seleccioneu l'exportació a la llista i seleccioneu **Afegeix un segment**.</span><span class="sxs-lookup"><span data-stu-id="17970-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="17970-153">Per crear una exportació nova amb el segment seleccionat, seleccioneu **Afegeix l'exportació**.</span><span class="sxs-lookup"><span data-stu-id="17970-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="17970-154">Per obtenir més informació sobre la creació d'exportacions, vegeu [Configurar una exportació nova](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="17970-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="17970-155">Seleccioneu **Enrere** per tornar a la pàgina principal per als segments.</span><span class="sxs-lookup"><span data-stu-id="17970-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="17970-156">Visualitzar l'historial de processament i els membres del segment</span><span class="sxs-lookup"><span data-stu-id="17970-156">View processing history and segment members</span></span>

<span data-ttu-id="17970-157">Podeu veure les dades consolidades d'un segment revisant-ne els detalls.</span><span class="sxs-lookup"><span data-stu-id="17970-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="17970-158">A la pàgina **Segments**, seleccioneu el segment que voleu revisar.</span><span class="sxs-lookup"><span data-stu-id="17970-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="17970-159">A la part superior de la pàgina s'inclou una gràfica de tendències que visualitza els canvis al recompte de membres.</span><span class="sxs-lookup"><span data-stu-id="17970-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="17970-160">Passeu el cursor per sobre dels punts de dades per veure el recompte de membres en una data concreta.</span><span class="sxs-lookup"><span data-stu-id="17970-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="17970-161">Podeu actualitzar el període de temps de la visualització.</span><span class="sxs-lookup"><span data-stu-id="17970-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="17970-162">![Interval de temps del segment](media/segment-time-range.png "Interval de temps del segment")</span><span class="sxs-lookup"><span data-stu-id="17970-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="17970-163">La part inferior conté una llista dels membres del segment.</span><span class="sxs-lookup"><span data-stu-id="17970-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="17970-164">Els camps que apareixen en aquesta llista es basen en els atributs de les entitats del vostre segment.</span><span class="sxs-lookup"><span data-stu-id="17970-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="17970-165">La llista és una visualització prèvia dels membres del segment coincidents i mostra els primers 100 registres del segment per tal que pugueu avaluar-lo ràpidament i revisar-ne les definicions si cal.</span><span class="sxs-lookup"><span data-stu-id="17970-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="17970-166">Per veure tots els registres coincidents, heu d'[exportar el segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="17970-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
