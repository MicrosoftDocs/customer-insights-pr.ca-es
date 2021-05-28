---
title: Segments suggerits basats en l'activitat.
description: Deixeu que l'aprenentatge automàtic trobi segments nous i interessants basats en l'activitat del client.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034051"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="c744a-103">Segments suggerits basats en les dades d'activitat (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="c744a-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="c744a-104">Descobriu segments rellevants dels clients segons les dades d'activitat del client que s'incorporen al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c744a-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="c744a-105">Alguns exemples de dades d'activitat són transaccions, duració de les trucades de suport, compres o devolucions.</span><span class="sxs-lookup"><span data-stu-id="c744a-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="c744a-106">Per suggerir segments, les dades d'activitats s'analitzen per aconseguir una recuperació, una freqüència i un valor monetari (o una duració).</span><span class="sxs-lookup"><span data-stu-id="c744a-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="c744a-107">O bé, es poden generar [segments suggerits per millorar una mesura o comprendre millor què influeix en un atribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="c744a-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Pestanya de segments suggerits que mostra els suggeriments de segments per a segments basats en l'activitat i basats en atributs.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="c744a-109">Classificar els clients per activitat</span><span class="sxs-lookup"><span data-stu-id="c744a-109">Categorize customers by activity</span></span>

<span data-ttu-id="c744a-110">Amb les [dades d'activitat](activities.md) disponibles al Customer Insights, podem generar suggeriments que representin grups de clients:</span><span class="sxs-lookup"><span data-stu-id="c744a-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="c744a-111">clients més actius</span><span class="sxs-lookup"><span data-stu-id="c744a-111">most active customers</span></span> 
- <span data-ttu-id="c744a-112">clients que han realitzat més compres</span><span class="sxs-lookup"><span data-stu-id="c744a-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="c744a-113">clients que han generat més ingressos</span><span class="sxs-lookup"><span data-stu-id="c744a-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="c744a-114">clients que no han estat actius darrerament</span><span class="sxs-lookup"><span data-stu-id="c744a-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="c744a-115">clients que interactuen sovint amb el vostre negoci</span><span class="sxs-lookup"><span data-stu-id="c744a-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="c744a-116">Si teniu una empresa minorista, podríeu esbrinar quins clients generen més ingressos i recompensar-los amb un descompte.</span><span class="sxs-lookup"><span data-stu-id="c744a-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="c744a-117">O bé podeu identificar clients ocasionals i oferir-los que s'uneixin a un programa de recompenses per tal que visitin el vostre negoci amb més freqüència.</span><span class="sxs-lookup"><span data-stu-id="c744a-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="c744a-118">Si sou del sector de l'atenció sanitària, oferiu atenció sanitària públic i el vostre objectiu és minimitzar les despeses dels pacients individuals.</span><span class="sxs-lookup"><span data-stu-id="c744a-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="c744a-119">Una manera de fer-ho podria ser reduir les visites periòdiques oferint la millor atenció possible amb el mínim de visites.</span><span class="sxs-lookup"><span data-stu-id="c744a-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="c744a-120">En aquest cas, el vostre objectiu és mantenir la freqüència de visita baixa i reduir al mínim el cost periòdic dels pacients.</span><span class="sxs-lookup"><span data-stu-id="c744a-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="c744a-121">O bé, podeu identificar pacients que tenen cites freqüents i uns costos periòdics alts, i analitzar aquests casos per millorar la satisfacció de cada persona.</span><span class="sxs-lookup"><span data-stu-id="c744a-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="c744a-122">Dades obligatòries</span><span class="sxs-lookup"><span data-stu-id="c744a-122">Required data</span></span>

<span data-ttu-id="c744a-123">Els suggeriments es generen a partir de les dades d'entrada seleccionades.</span><span class="sxs-lookup"><span data-stu-id="c744a-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="c744a-124">Perfils de client: tots els clients o membres d'un segment específic.</span><span class="sxs-lookup"><span data-stu-id="c744a-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="c744a-125">Període de temps: darrer mes, darrer any o període de temps personalitzat.</span><span class="sxs-lookup"><span data-stu-id="c744a-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="c744a-126">Tipus d'activitat: compres, transaccions al detall, transaccions en línia, casos de suport al client, subscripcions, entre altres.</span><span class="sxs-lookup"><span data-stu-id="c744a-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="c744a-127">Entitat al Customer Insights que conté les dades d'activitat: l'entitat UnifiedActivity o l'entitat per a una activitat específica.</span><span class="sxs-lookup"><span data-stu-id="c744a-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="c744a-128">Les mètriques que s'inclouen són: recent, freqüència o control monetari, segons les vostres necessitats empresarials.</span><span class="sxs-lookup"><span data-stu-id="c744a-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="c744a-129">Generar segments suggerits</span><span class="sxs-lookup"><span data-stu-id="c744a-129">Generate suggested segments</span></span>

1. <span data-ttu-id="c744a-130">Aneu a **Segments**.</span><span class="sxs-lookup"><span data-stu-id="c744a-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="c744a-131">Seleccioneu la pestanya **Suggeriments (versió preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="c744a-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="c744a-132">Seleccioneu **Cerca suggeriments nous** i trieu **Veure o anticipar el comportament del client**.</span><span class="sxs-lookup"><span data-stu-id="c744a-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="c744a-133">Seleccioneu **Comença** per executar l'experiència guiada.</span><span class="sxs-lookup"><span data-stu-id="c744a-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primer pas de l'auxiliar de configuració d'un segment suggerit segons l'activitat.":::

1. <span data-ttu-id="c744a-135">Proporcioneu les dades d'entrada necessàries i seleccioneu **Següent** per continuar.</span><span class="sxs-lookup"><span data-stu-id="c744a-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="c744a-136">Trieu els clients: incloeu tots els clients o un segment concret.</span><span class="sxs-lookup"><span data-stu-id="c744a-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="c744a-137">Trieu l'activitat: seleccioneu el tipus d'activitat i les entitats que descriuen l'activitat.</span><span class="sxs-lookup"><span data-stu-id="c744a-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="c744a-138">Preferències: definiu el període de temps que cal tenir en compte, els factors dels suggeriments i assigneu els atributs.</span><span class="sxs-lookup"><span data-stu-id="c744a-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="c744a-139">Reviseu les entrades i seleccioneu **Executa** per executar el model i generar suggeriments.</span><span class="sxs-lookup"><span data-stu-id="c744a-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="c744a-140">Segons el nombre de perfils de client i de les activitats seleccionades, pot trigar uns minuts a completar-se.</span><span class="sxs-lookup"><span data-stu-id="c744a-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="c744a-141">Després de generar els suggeriments, podeu filtrar-los per la condició o el valor que més us interessi.</span><span class="sxs-lookup"><span data-stu-id="c744a-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="c744a-142">Veure els detalls del segment suggerit</span><span class="sxs-lookup"><span data-stu-id="c744a-142">View details of a suggested segment</span></span>

<span data-ttu-id="c744a-143">Un cop generats els suggeriments, els trobareu enumerats a la secció **Segments** > **Suggeriments (versió preliminar)** a la secció **Suggeriments basats en l'activitat**.</span><span class="sxs-lookup"><span data-stu-id="c744a-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Subfinestra lateral expandida que mostra dades detallades d'un segment suggerit.":::

<span data-ttu-id="c744a-145">Seleccioneu **Vegeu el suggeriment** en un segment suggerit per visualitzar-ne els detalls.</span><span class="sxs-lookup"><span data-stu-id="c744a-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="c744a-146">La subfinestra lateral proporciona detalls com l'extensió de cada propietat en comparació amb el grup de destinació.</span><span class="sxs-lookup"><span data-stu-id="c744a-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="c744a-147">També destaca el nombre de membres potencials del segment i el percentatge corresponent del total de clients.</span><span class="sxs-lookup"><span data-stu-id="c744a-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="c744a-148">Si voleu conservar el suggeriment com a segment, seleccioneu **Crea un segment**.</span><span class="sxs-lookup"><span data-stu-id="c744a-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="c744a-149">Desar un suggeriment com a segment</span><span class="sxs-lookup"><span data-stu-id="c744a-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="c744a-150">Aneu a **Segments** > **Suggeriments (versió preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="c744a-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="c744a-151">Seleccioneu el segment que voleu desar.</span><span class="sxs-lookup"><span data-stu-id="c744a-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="c744a-152">A la subfinestra lateral, seleccioneu **Crea un segment**.</span><span class="sxs-lookup"><span data-stu-id="c744a-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="c744a-153">Després de desar el segment, es mostrarà a la llista de segments a la pestanya **Tots els segments**. Ara es pot [actualitzar o suprimir com qualsevol altre segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c744a-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="c744a-154">No podeu editar els detalls del segment.</span><span class="sxs-lookup"><span data-stu-id="c744a-154">You can't edit the segment details.</span></span> <span data-ttu-id="c744a-155">No obstant això, podeu canviar els criteris d'entrada dels suggeriments i generar suggeriments diferents.</span><span class="sxs-lookup"><span data-stu-id="c744a-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="c744a-156">Actualitzar o editar un conjunt de suggeriments</span><span class="sxs-lookup"><span data-stu-id="c744a-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="c744a-157">Aneu a **Segments** > **Suggeriments (versió preliminar)** i cerqueu el segment a la secció **Suggeriments basats en l'activitat**.</span><span class="sxs-lookup"><span data-stu-id="c744a-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="c744a-158">Seleccioneu **Actualitza els suggeriments** per actualitzar els suggeriments mantenint els atributs configurats.</span><span class="sxs-lookup"><span data-stu-id="c744a-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="c744a-159">O seleccioneu **Edita els suggeriments** per modificar els atributs configurats.</span><span class="sxs-lookup"><span data-stu-id="c744a-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="c744a-160">El sistema tornarà a executar el procés, generarà suggeriments de segments basats en les dades més recents i substituirà els suggeriments actuals.</span><span class="sxs-lookup"><span data-stu-id="c744a-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
