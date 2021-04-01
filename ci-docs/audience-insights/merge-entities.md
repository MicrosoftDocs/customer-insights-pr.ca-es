---
title: Combinar entitats a la unificació de dades
description: Combineu entitats per crear perfils de client unificats.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597821"
---
# <a name="merge-entities"></a><span data-ttu-id="ee2d6-103">Combinar entitats</span><span class="sxs-lookup"><span data-stu-id="ee2d6-103">Merge entities</span></span>

<span data-ttu-id="ee2d6-104">La fase de combinació és l'última fase en el procés d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="ee2d6-105">La seva finalitat és la conciliació de dades contradictòries.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="ee2d6-106">Alguns exemples de dades contradictòries són un nom del client que es troba en dos dels vostres conjunts de dades, però apareix una mica diferent a cadascun d'ells ("Grant Marshall" o "Grant Marshal") o un número de telèfon que difereix en el format (617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="ee2d6-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="ee2d6-107">La combinació d'aquests punts de dades conflictius es fa per atribut.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="ee2d6-108">Després de completar la [fase de coincidència](match-entities.md), podeu iniciar la fase de combinació seleccionant la peça **Combinació** a la pàgina **Unifica**.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="ee2d6-109">Revisar les recomanacions del sistema</span><span class="sxs-lookup"><span data-stu-id="ee2d6-109">Review system recommendations</span></span>

<span data-ttu-id="ee2d6-110">A la pàgina **Combinació**, podeu triar i excloure els atributs per combinar a l'entitat de perfil del client unificat (resultat del procés de configuració).</span><span class="sxs-lookup"><span data-stu-id="ee2d6-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="ee2d6-111">El sistema combina automàticament alguns atributs.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="ee2d6-112">Visualitzar els atributs combinats</span><span class="sxs-lookup"><span data-stu-id="ee2d6-112">View merged attributes</span></span>

<span data-ttu-id="ee2d6-113">Per visualitzar els atributs que s'inclouen en un dels atributs combinats automàticament, seleccioneu aquest atribut combinat.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="ee2d6-114">Els dos atributs que componen aquest atribut combinat es mostren en dues files noves sota l'atribut combinat.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ee2d6-115">![Seleccionar un atribut combinat](media/configure-data-merge-profile-attributes.png "Seleccionar un atribut combinat")</span><span class="sxs-lookup"><span data-stu-id="ee2d6-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="ee2d6-116">Separar atributs combinats</span><span class="sxs-lookup"><span data-stu-id="ee2d6-116">Separate merged attributes</span></span>

<span data-ttu-id="ee2d6-117">Per separar o deixar de combinar qualsevol dels atributs combinats automàticament, cerqueu l'atribut a la taula **Atributs de perfil**.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="ee2d6-118">Seleccioneu el botó de punts suspensius (...).</span><span class="sxs-lookup"><span data-stu-id="ee2d6-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="ee2d6-119">A la llista desplegable, seleccioneu **Separa els camps**.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="ee2d6-120">Suprimir atributs combinats</span><span class="sxs-lookup"><span data-stu-id="ee2d6-120">Remove merged attributes</span></span>

<span data-ttu-id="ee2d6-121">Per excloure un atribut de l'entitat de perfil de client final, cerqueu-la a la taula **Atributs del perfil**.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="ee2d6-122">Seleccioneu el botó de punts suspensius (...).</span><span class="sxs-lookup"><span data-stu-id="ee2d6-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="ee2d6-123">A la llista desplegable, seleccioneu **No combinis**.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="ee2d6-124">L'atribut es desplaça a la secció **Suprimit del registre de client**.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="ee2d6-125">Afegir manualment un atribut combinat</span><span class="sxs-lookup"><span data-stu-id="ee2d6-125">Manually add a merged attribute</span></span>

<span data-ttu-id="ee2d6-126">Per afegir un atribut combinat, aneu a la pàgina **Combinació**.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="ee2d6-127">Seleccioneu **Afegeix un atribut combinat**.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="ee2d6-128">Proporcioneu un **Nom** per identificar-lo a la pàgina **Combinació** més endavant.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="ee2d6-129">Opcionalment, proporcioneu un **Nom de visualització** per mostrar a l'entitat de perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="ee2d6-130">Configureu **Selecció d'atributs duplicats** per seleccionar els atributs que voleu combinar de les entitats coincidents.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="ee2d6-131">També podeu cercar atributs.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="ee2d6-132">Definiu la **Classificació segons la importància** per donar prioritat un atribut per sobre dels altres.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="ee2d6-133">Per exemple, si l'entitat *WebAccountCSV* inclou les dades més precises sobre l'atribut *Noms complet*, podríeu donar prioritat a aquesta entitat sobre *ContactCSV* seleccionant *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="ee2d6-134">Com a resultat, *WebAccountCSV* es desplaça a la primera prioritat, mentre que *ContactCSV* es desplaça a la segona prioritat en obtenir valors per a l'atribut *Nom complet*.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="ee2d6-135">Executar la combinació</span><span class="sxs-lookup"><span data-stu-id="ee2d6-135">Run your merge</span></span>

<span data-ttu-id="ee2d6-136">Ja sigui si combineu els atributs manualment o deixeu que el sistema els combini, sempre podeu executar la combinació.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="ee2d6-137">A la pàgina **Combinació**, seleccioneu **Executa** per iniciar el procés.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ee2d6-138">![Desa i executa la combinació de dades](media/configure-data-merge-save-run.png "Desa i executa la combinació de dades")</span><span class="sxs-lookup"><span data-stu-id="ee2d6-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="ee2d6-139">Per fer canvis addicionals i tornar a executar el pas, podeu cancel·lar una combinació en curs.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="ee2d6-140">Seleccioneu **S'està actualitzant...** i seleccioneu **Cancel·la la feina** a la subfinestra lateral que es mostra.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="ee2d6-141">Després que el text **S'està actualitzant...** canviï a **Correcte**, la combinació s'ha completat i ha resolt les contradiccions de les dades d'acord amb les normes que heu definit.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="ee2d6-142">Els atributs combinats i no combinats s'inclouen a l'entitat del perfil unificat.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="ee2d6-143">Els atributs exclosos no s'inclouen a l'entitat del perfil unificat.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="ee2d6-144">Si no fos la primera vegada que executeu una combinació correctament, tots els processos posteriors, incloent-hi l'enriquiment, la segmentació i les mesures es tornaran a executar automàticament.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="ee2d6-145">Després de tornar a executar tots els processos posteriors, els perfils del client reflecteixen els canvis que heu fet.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="ee2d6-146">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ee2d6-147">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ee2d6-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ee2d6-148">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ee2d6-149">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="ee2d6-150">Pas següent</span><span class="sxs-lookup"><span data-stu-id="ee2d6-150">Next Step</span></span>

<span data-ttu-id="ee2d6-151">Configureu [Activitats](activities.md), [Enriquiment](enrichment-microsoft-graph.md) o [Relacions](relationships.md) per obtenir més informació sobre els clients.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="ee2d6-152">Si ja heu configurat activitats, enriquiment o relacions o si heu definit segments, es processaran automàticament per utilitzar les darreres dades dels clients.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]