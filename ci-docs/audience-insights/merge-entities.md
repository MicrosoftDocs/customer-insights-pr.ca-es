---
title: Combinar entitats a la unificació de dades
description: Combineu entitats per crear perfils de client unificats.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085564"
---
# <a name="merge-entities"></a><span data-ttu-id="75bcc-103">Combinar entitats</span><span class="sxs-lookup"><span data-stu-id="75bcc-103">Merge entities</span></span>

<span data-ttu-id="75bcc-104">La fase de combinació és l'última fase en el procés d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="75bcc-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="75bcc-105">La seva finalitat és la conciliació de dades contradictòries.</span><span class="sxs-lookup"><span data-stu-id="75bcc-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="75bcc-106">Alguns exemples de dades contradictòries són un nom del client que es troba en dos dels vostres conjunts de dades, però apareix una mica diferent a cadascun d'ells ("Grant Marshall" o "Grant Marshal") o un número de telèfon que difereix en el format (617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="75bcc-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="75bcc-107">La combinació d'aquests punts de dades conflictius es fa per atribut.</span><span class="sxs-lookup"><span data-stu-id="75bcc-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Combineu la pàgina al procés d'unificació de dades que mostra la taula amb camps combinats que defineixen el perfil de client unificat.":::

<span data-ttu-id="75bcc-109">Després de completar la [fase de coincidència](match-entities.md), podeu iniciar la fase de combinació seleccionant la peça **Combinació** a la pàgina **Unifica**.</span><span class="sxs-lookup"><span data-stu-id="75bcc-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="75bcc-110">Revisar les recomanacions del sistema</span><span class="sxs-lookup"><span data-stu-id="75bcc-110">Review system recommendations</span></span>

<span data-ttu-id="75bcc-111">A **Dades** > **Unifica** > **Combina**, trieu i excloueu els atributs que es combinaran a l'entitat de perfil de client unificada.</span><span class="sxs-lookup"><span data-stu-id="75bcc-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="75bcc-112">El perfil de client unificat és el resultat del procés d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="75bcc-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="75bcc-113">El sistema combina automàticament alguns atributs.</span><span class="sxs-lookup"><span data-stu-id="75bcc-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="75bcc-114">Per visualitzar els atributs que s'inclouen en un dels atributs combinats automàticament, seleccioneu aquest atribut combinat a la pestanya de la taula **Camps de client**.</span><span class="sxs-lookup"><span data-stu-id="75bcc-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="75bcc-115">Els atributs que componen aquest atribut combinat es mostren en dues files noves sota l'atribut combinat.</span><span class="sxs-lookup"><span data-stu-id="75bcc-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="75bcc-116">Separar camps combinats, canviar-ne el nom, excloure'ls i editar-los</span><span class="sxs-lookup"><span data-stu-id="75bcc-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="75bcc-117">Podeu canviar com el sistema processa els atributs combinats per generar el perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="75bcc-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="75bcc-118">Seleccioneu **Mostra'n més** i trieu què voleu canviar.</span><span class="sxs-lookup"><span data-stu-id="75bcc-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opcions del menú desplegable Mostra'n més per gestionar atributs combinats.":::

<span data-ttu-id="75bcc-120">Per obtenir més informació, vegeu les seccions següents.</span><span class="sxs-lookup"><span data-stu-id="75bcc-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="75bcc-121">Separar camps combinats</span><span class="sxs-lookup"><span data-stu-id="75bcc-121">Separate merged fields</span></span>

<span data-ttu-id="75bcc-122">Per separar els camps combinats, cerqueu l'atribut a la taula.</span><span class="sxs-lookup"><span data-stu-id="75bcc-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="75bcc-123">Els camps separats es mostren com a punts de dades individuals al perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="75bcc-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="75bcc-124">Seleccioneu el camp combinat.</span><span class="sxs-lookup"><span data-stu-id="75bcc-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="75bcc-125">Seleccioneu **Mostra'n més** i trieu **Separa els camps**.</span><span class="sxs-lookup"><span data-stu-id="75bcc-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="75bcc-126">Confirmeu la separació.</span><span class="sxs-lookup"><span data-stu-id="75bcc-126">Confirm the separation.</span></span>

1. <span data-ttu-id="75bcc-127">Seleccioneu **Desa** i **Executa** per processar els canvis.</span><span class="sxs-lookup"><span data-stu-id="75bcc-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="75bcc-128">Canviar el nom dels camps combinats</span><span class="sxs-lookup"><span data-stu-id="75bcc-128">Rename merged fields</span></span>

<span data-ttu-id="75bcc-129">Canvieu el nom de visualització dels atributs combinats.</span><span class="sxs-lookup"><span data-stu-id="75bcc-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="75bcc-130">No podeu canviar el nom de l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="75bcc-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="75bcc-131">Seleccioneu el camp combinat.</span><span class="sxs-lookup"><span data-stu-id="75bcc-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="75bcc-132">Seleccioneu **Mostra'n més** i trieu **Canvia'n el nom**.</span><span class="sxs-lookup"><span data-stu-id="75bcc-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="75bcc-133">Confirmeu el nom de visualització canviat.</span><span class="sxs-lookup"><span data-stu-id="75bcc-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="75bcc-134">Seleccioneu **Desa** i **Executa** per processar els canvis.</span><span class="sxs-lookup"><span data-stu-id="75bcc-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="75bcc-135">Excloure camps combinats</span><span class="sxs-lookup"><span data-stu-id="75bcc-135">Exclude merged fields</span></span>

<span data-ttu-id="75bcc-136">Excloeu un atribut del perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="75bcc-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="75bcc-137">Si el camp s'utilitza en altres processos, per exemple, en un segment, suprimiu-lo d'aquests processos abans d'excloure'l del perfil de client.</span><span class="sxs-lookup"><span data-stu-id="75bcc-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="75bcc-138">Seleccioneu el camp combinat.</span><span class="sxs-lookup"><span data-stu-id="75bcc-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="75bcc-139">Seleccioneu **Mostra'n més** i trieu **Exclou**.</span><span class="sxs-lookup"><span data-stu-id="75bcc-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="75bcc-140">Confirmeu l'exclusió.</span><span class="sxs-lookup"><span data-stu-id="75bcc-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="75bcc-141">Seleccioneu **Desa** i **Executa** per processar els canvis.</span><span class="sxs-lookup"><span data-stu-id="75bcc-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="75bcc-142">A la pàgina **Combina**, seleccioneu **Camps exclosos** per veure la llista de tots els camps exclosos.</span><span class="sxs-lookup"><span data-stu-id="75bcc-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="75bcc-143">Aquesta subfinestra us permet tornar a afegir camps exclosos.</span><span class="sxs-lookup"><span data-stu-id="75bcc-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="75bcc-144">Combinar camps manualment</span><span class="sxs-lookup"><span data-stu-id="75bcc-144">Manually combine fields</span></span>

<span data-ttu-id="75bcc-145">Especifiqueu un atribut combinat manualment.</span><span class="sxs-lookup"><span data-stu-id="75bcc-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="75bcc-146">A la pàgina **Combina**, seleccioneu **Combina els camps**.</span><span class="sxs-lookup"><span data-stu-id="75bcc-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="75bcc-147">Proporcioneu un **Nom** i un **Nom de camp de sortida**.</span><span class="sxs-lookup"><span data-stu-id="75bcc-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="75bcc-148">Trieu un camp per afegir-lo.</span><span class="sxs-lookup"><span data-stu-id="75bcc-148">Choose a field to add.</span></span> <span data-ttu-id="75bcc-149">Seleccioneu **Afegeix camps** per combinar-ne més.</span><span class="sxs-lookup"><span data-stu-id="75bcc-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="75bcc-150">Confirmeu l'exclusió.</span><span class="sxs-lookup"><span data-stu-id="75bcc-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="75bcc-151">Seleccioneu **Desa** i **Executa** per processar els canvis.</span><span class="sxs-lookup"><span data-stu-id="75bcc-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="75bcc-152">Canviar l'ordre dels camps</span><span class="sxs-lookup"><span data-stu-id="75bcc-152">Change the order of fields</span></span>

<span data-ttu-id="75bcc-153">Algunes entitats contenen més detalls que altres.</span><span class="sxs-lookup"><span data-stu-id="75bcc-153">Some entities contain more details than others.</span></span> <span data-ttu-id="75bcc-154">Si una entitat inclou les dades més recents d'un camp, podeu prioritzar-la sobre altres entitats quan es combinen valors.</span><span class="sxs-lookup"><span data-stu-id="75bcc-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="75bcc-155">Seleccioneu el camp combinat.</span><span class="sxs-lookup"><span data-stu-id="75bcc-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="75bcc-156">Seleccioneu **Mostra'n més** i trieu **Edita**.</span><span class="sxs-lookup"><span data-stu-id="75bcc-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="75bcc-157">A la subfinestra **Combina els camps**, seleccioneu **Desplaça amunt/avall** per definir l'ordre o arrossegueu-los i deixeu-los anar a la posició desitjada.</span><span class="sxs-lookup"><span data-stu-id="75bcc-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="75bcc-158">Confirmeu el canvi.</span><span class="sxs-lookup"><span data-stu-id="75bcc-158">Confirm the change.</span></span>

1. <span data-ttu-id="75bcc-159">Seleccioneu **Desa** i **Executa** per processar els canvis.</span><span class="sxs-lookup"><span data-stu-id="75bcc-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="75bcc-160">Executar la combinació</span><span class="sxs-lookup"><span data-stu-id="75bcc-160">Run your merge</span></span>

<span data-ttu-id="75bcc-161">Ja sigui si combineu els atributs manualment o deixeu que el sistema els combini, sempre podeu executar la combinació.</span><span class="sxs-lookup"><span data-stu-id="75bcc-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="75bcc-162">A la pàgina **Combinació**, seleccioneu **Executa** per iniciar el procés.</span><span class="sxs-lookup"><span data-stu-id="75bcc-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="75bcc-163">![Desa i executa la combinació de dades](media/configure-data-merge-save-run.png "Desa i executa la combinació de dades")</span><span class="sxs-lookup"><span data-stu-id="75bcc-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="75bcc-164">Trieu **Executa només la combinació** si només voleu veure la sortida reflectida a l'entitat de client unificada.</span><span class="sxs-lookup"><span data-stu-id="75bcc-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="75bcc-165">Els processos descendents s'actualitzaran segons [ho defineixi la planificació d'actualització](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="75bcc-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="75bcc-166">Trieu **Executa la combinació i els processos descendents** per actualitzar el sistema amb els canvis.</span><span class="sxs-lookup"><span data-stu-id="75bcc-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="75bcc-167">Tots els processos, incloent-hi l'enriquiment, els segments i les mesures, es tornaran a executar automàticament.</span><span class="sxs-lookup"><span data-stu-id="75bcc-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="75bcc-168">Un cop completats tots els processos descendents, els perfils de client reflecteixen els canvis que heu fet.</span><span class="sxs-lookup"><span data-stu-id="75bcc-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="75bcc-169">Per fer més canvis i tornar a executar el pas, podeu cancel·lar una combinació en curs.</span><span class="sxs-lookup"><span data-stu-id="75bcc-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="75bcc-170">Seleccioneu **S'està actualitzant...** i seleccioneu **Cancel·la la feina** a la subfinestra lateral que es mostra.</span><span class="sxs-lookup"><span data-stu-id="75bcc-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="75bcc-171">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="75bcc-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="75bcc-172">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="75bcc-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="75bcc-173">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="75bcc-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="75bcc-174">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.</span><span class="sxs-lookup"><span data-stu-id="75bcc-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="75bcc-175">Pas següent</span><span class="sxs-lookup"><span data-stu-id="75bcc-175">Next Step</span></span>

<span data-ttu-id="75bcc-176">Configureu [Activitats](activities.md), [Enriquiment](enrichment-hub.md) o [Relacions](relationships.md) per obtenir més informació sobre els clients.</span><span class="sxs-lookup"><span data-stu-id="75bcc-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="75bcc-177">Si ja heu configurat activitats, enriquiments o segments, es processaran automàticament per utilitzar les dades de client més recents.</span><span class="sxs-lookup"><span data-stu-id="75bcc-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
