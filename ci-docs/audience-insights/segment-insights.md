---
title: Segmentar la informació de segments existents
description: Obtingueu informació sobre els segments existents per veure'n les diferències i els aspectes comuns.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 92e1b05dd08588a5da446af5b17b2d6ce57490ce
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405168"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="73f67-103">Informació dels segments (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="73f67-103">Segment insights (preview)</span></span>

<span data-ttu-id="73f67-104">Descobriu informació addicional i estadístiques sobre els segments existents.</span><span class="sxs-lookup"><span data-stu-id="73f67-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="73f67-105">Esbrineu en què es diferencien dos segments o què tenen en comú.</span><span class="sxs-lookup"><span data-stu-id="73f67-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="73f67-106">Superposició de segments</span><span class="sxs-lookup"><span data-stu-id="73f67-106">Segment overlap</span></span>

<span data-ttu-id="73f67-107">L'anàlisi de superposició de segments mostra quants i quins clients són comuns en dos o més segments.</span><span class="sxs-lookup"><span data-stu-id="73f67-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="73f67-108">Per exemple, com un segment de clients freqüents se superposa amb un segment que conté els clients satisfets amb un producte o servei.</span><span class="sxs-lookup"><span data-stu-id="73f67-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="73f67-109">També podeu analitzar com canvia la superposició per atributs específics.</span><span class="sxs-lookup"><span data-stu-id="73f67-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="73f67-110">Executar una anàlisi de superposició</span><span class="sxs-lookup"><span data-stu-id="73f67-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="73f67-111">Aneu a **Segments** i seleccioneu la pestanya **Informació (versió preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="73f67-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="73f67-112">Seleccioneu **Nou** i trieu l'opció **Superposició** a la subfinestra **Trieu un tipus d'informació**.</span><span class="sxs-lookup"><span data-stu-id="73f67-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="73f67-113">Trieu els segments d'interès i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="73f67-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="73f67-114">Opcionalment, trieu un o diversos camps d'interès per analitzar les superposicions per a cada valor de camp possible i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="73f67-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="73f67-115">Proporcioneu un nom per a l'anàlisi de superposició, un nom de visualització opcional i una descripció.</span><span class="sxs-lookup"><span data-stu-id="73f67-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="73f67-116">Seleccioneu **Desa** per iniciar l'anàlisi.</span><span class="sxs-lookup"><span data-stu-id="73f67-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="73f67-117">L'anàlisi de superposició està preparada quan l'estat canvia d'Actualitzant a Correcte.</span><span class="sxs-lookup"><span data-stu-id="73f67-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="73f67-118">Visualitzar i optimitzar una anàlisi de superposició</span><span class="sxs-lookup"><span data-stu-id="73f67-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="73f67-119">Després de completar l'anàlisi, trobareu detalls sobre aquesta informació a **Segments** > **Informació (versió preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="73f67-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalls de la informació de superposició de segments":::

<span data-ttu-id="73f67-121">Seleccioneu una informació per veure els resultats de l'anàlisi:</span><span class="sxs-lookup"><span data-stu-id="73f67-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="73f67-122">Nombre de membres que solapen els segments seleccionats per a l'anàlisi.</span><span class="sxs-lookup"><span data-stu-id="73f67-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="73f67-123">Nombre de membres que s'inclouen en un dels segments però no a la resta de segments.</span><span class="sxs-lookup"><span data-stu-id="73f67-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="73f67-124">Si heu seleccionat camps en configurar l'anàlisi de superposició, els trobareu a les pestanyes corresponents.</span><span class="sxs-lookup"><span data-stu-id="73f67-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="73f67-125">Podeu utilitzar el filtre desplegable per seleccionar qualsevol nivell d'atribut d'interès i la taula a la part inferior mostrarà les dades corresponents.</span><span class="sxs-lookup"><span data-stu-id="73f67-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="73f67-126">Diferenciadors del segment</span><span class="sxs-lookup"><span data-stu-id="73f67-126">Segment differentiators</span></span>

<span data-ttu-id="73f67-127">Els diferenciadors del segment us ajudaran a descobrir els elements diferencials d'un segment de la resta de clients o d'un altre segment.</span><span class="sxs-lookup"><span data-stu-id="73f67-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="73f67-128">Només heu de seleccionar un segment i el sistema identificarà els atributs i les mesures de perfil que distingeixen el segment seleccionat.</span><span class="sxs-lookup"><span data-stu-id="73f67-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="73f67-129">Executar una anàlisi diferenciadora</span><span class="sxs-lookup"><span data-stu-id="73f67-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="73f67-130">Aneu a **Segments** i seleccioneu la pestanya **Informació (versió preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="73f67-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="73f67-131">Seleccioneu **Nou** i trieu l'opció **Superposició** a la subfinestra **Trieu un tipus d'informació**.</span><span class="sxs-lookup"><span data-stu-id="73f67-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="73f67-132">Trieu el segment que voleu analitzar com a **Segment principal** i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="73f67-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="73f67-133">Trieu **Tots els clients** o un **segment secundari** per comparar amb el segment principal i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="73f67-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="73f67-134">Opcionalment, trieu un o diversos camps d'interès per centrar l'anàlisi sobre els atributs específics i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="73f67-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="73f67-135">Proporcioneu un nom per a l'anàlisi de superposició, un nom de visualització opcional i una descripció.</span><span class="sxs-lookup"><span data-stu-id="73f67-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="73f67-136">Seleccioneu **Desa** per iniciar l'anàlisi.</span><span class="sxs-lookup"><span data-stu-id="73f67-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="73f67-137">L'anàlisi de superposició està preparada quan l'estat canvia d'Actualitzant a Correcte.</span><span class="sxs-lookup"><span data-stu-id="73f67-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="73f67-138">Visualitzar i optimitzar una anàlisi de diferenciadors</span><span class="sxs-lookup"><span data-stu-id="73f67-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="73f67-139">Després de completar l'anàlisi, trobareu detalls sobre aquesta informació a **Segments** > **Informació (versió preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="73f67-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalls de la informació de diferenciador de segments":::

<span data-ttu-id="73f67-141">Seleccioneu una informació per veure els resultats de l'anàlisi.</span><span class="sxs-lookup"><span data-stu-id="73f67-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="73f67-142">Una anàlisi de diferenciador inclou dues pestanyes.</span><span class="sxs-lookup"><span data-stu-id="73f67-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="73f67-143">La pestanya **Atributs** enumera els atributs del perfil considerats com a diferenciadors.</span><span class="sxs-lookup"><span data-stu-id="73f67-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="73f67-144">La pestanya **Mesures** enumera els diferenciadors.</span><span class="sxs-lookup"><span data-stu-id="73f67-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="73f67-145">Cada pestanya inclou els detalls següents:</span><span class="sxs-lookup"><span data-stu-id="73f67-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="73f67-146">Llista classificada de diferenciadors, ordenats per la puntuació de la diferència.</span><span class="sxs-lookup"><span data-stu-id="73f67-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="73f67-147">La **Puntuació de la diferència** per a cada diferenciador.</span><span class="sxs-lookup"><span data-stu-id="73f67-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="73f67-148">La puntuació de diferència representa el grau de diferència d'un atribut entre dos segments.</span><span class="sxs-lookup"><span data-stu-id="73f67-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="73f67-149">Com més gran sigui la puntuació, més difereixen els atributs entre els dos segments.</span><span class="sxs-lookup"><span data-stu-id="73f67-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="73f67-150">Seleccioneu una puntuació per obrir la subfinestra **Puntuació de diferència** amb les distribucions de valors per a l'atribut.</span><span class="sxs-lookup"><span data-stu-id="73f67-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="73f67-151">Administrar la informació detallada de segments</span><span class="sxs-lookup"><span data-stu-id="73f67-151">Manage segment insights</span></span>

<span data-ttu-id="73f67-152">Podeu utilitzar les opcions següents sobre la informació a la barra d'ordres:</span><span class="sxs-lookup"><span data-stu-id="73f67-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="73f67-153">**Enrere** per tornar a la llista d'informació</span><span class="sxs-lookup"><span data-stu-id="73f67-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="73f67-154">**Actualitza** per tornar a executar l'anàlisi</span><span class="sxs-lookup"><span data-stu-id="73f67-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="73f67-155">**Suprimeix** per suprimir aquesta informació</span><span class="sxs-lookup"><span data-stu-id="73f67-155">**Delete** to remove this insight</span></span>
