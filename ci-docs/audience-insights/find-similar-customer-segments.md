---
title: Cercar clients similars amb IA
description: Cerqueu segments de client semblants amb la intel·ligència artificial.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596763"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="feabc-103">Clients semblants (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="feabc-103">Similar Customers (preview)</span></span>

<span data-ttu-id="feabc-104">Aquesta característica us permet trobar clients semblants a la base de clients mitjançant la intel·ligència artificial.</span><span class="sxs-lookup"><span data-stu-id="feabc-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="feabc-105">Heu de tenir com a mínim un segment creat per utilitzar aquesta característica.</span><span class="sxs-lookup"><span data-stu-id="feabc-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="feabc-106">Expandir els criteris d'un segment existent ajuda a cercar clients que siguin semblants a aquest segment.</span><span class="sxs-lookup"><span data-stu-id="feabc-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="feabc-107">*Cerca clients similars* utilitza mitjans automatitzats per avaluar dades i fer prediccions basades en les dades, i per tant té la capacitat d'utilitzar-se com a mètode de perfilació, tal com es defineix el terme al Reglament general de protecció de dades ("RGPD").</span><span class="sxs-lookup"><span data-stu-id="feabc-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="feabc-108">L'ús del client d'aquesta característica per processar les dades pot estar subjecte a l'RGPD o altres lleis o regulacions.</span><span class="sxs-lookup"><span data-stu-id="feabc-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="feabc-109">Us responsabilitzeu de garantir que l'ús del Dynamics 365 Customer Insights, incloent-hi prediccions, compleixi totes les lleis i normatives aplicables, incloent-hi la legislació relacionada amb la privadesa, les dades personals, les dades biomètriques, la protecció de dades i la confidencialitat de comunicació.</span><span class="sxs-lookup"><span data-stu-id="feabc-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="feabc-110">Cercar clients semblants</span><span class="sxs-lookup"><span data-stu-id="feabc-110">Finding similar customers</span></span>

1. <span data-ttu-id="feabc-111">A les conclusions del públic, aneu a **Segments** i seleccioneu el segment en què voleu basar el nou segment.</span><span class="sxs-lookup"><span data-stu-id="feabc-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="feabc-112">Aquest és el vostre *segment d'origen*.</span><span class="sxs-lookup"><span data-stu-id="feabc-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="feabc-113">A la barra d'accions, seleccioneu **Cerca clients similars**.</span><span class="sxs-lookup"><span data-stu-id="feabc-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="feabc-114">Reviseu el nom suggerit per al segment nou i canvieu-lo si cal.</span><span class="sxs-lookup"><span data-stu-id="feabc-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="feabc-115">Reviseu els camps que defineixen el segment nou.</span><span class="sxs-lookup"><span data-stu-id="feabc-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="feabc-116">Aquests camps defineixen la base en què el sistema tractarà de cercar clients semblants al vostre segment d'origen.</span><span class="sxs-lookup"><span data-stu-id="feabc-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="feabc-117">El sistema seleccionarà els camps recomanats per defecte.</span><span class="sxs-lookup"><span data-stu-id="feabc-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="feabc-118">Els camps que poden reduir significativament el rendiment del model s'exclouen automàticament:</span><span class="sxs-lookup"><span data-stu-id="feabc-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="feabc-119">Camps amb els tipus de dades següents: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="feabc-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="feabc-120">Camps amb una cardinalitat (nombre d'elements d'un camp) de menys de 2 o més de 30</span><span class="sxs-lookup"><span data-stu-id="feabc-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="feabc-121">Trieu si voleu incloure **tots els clients** o només els clients d'un **segment existent específic** al segment nou.</span><span class="sxs-lookup"><span data-stu-id="feabc-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="feabc-122">Excloeu els clients del segment d'origen seleccionant la casella de selecció **Exclou tothom del segment d'origen**.</span><span class="sxs-lookup"><span data-stu-id="feabc-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="feabc-123">Per defecte, el sistema suggereix incloure només el 20% de la mida del públic de destinació a la sortida.</span><span class="sxs-lookup"><span data-stu-id="feabc-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="feabc-124">Editeu aquest llindar segons calgui.</span><span class="sxs-lookup"><span data-stu-id="feabc-124">Edit this threshold as needed.</span></span> <span data-ttu-id="feabc-125">Si augmenteu el llindar, es reduirà la precisió.</span><span class="sxs-lookup"><span data-stu-id="feabc-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="feabc-126">Seleccioneu **Executa** a la part inferior de la pàgina per iniciar una tasca de classificació binària (un mètode d'aprenentatge automàtic) que analitza el conjunt de dades.</span><span class="sxs-lookup"><span data-stu-id="feabc-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="feabc-127">Visualitzar el segment similar</span><span class="sxs-lookup"><span data-stu-id="feabc-127">View the similar segment</span></span>

<span data-ttu-id="feabc-128">Després de processar el segment similar, trobareu el nou segment a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="feabc-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="feabc-129">![Segment de clients similars](media/expanded-segment.png "Segment de clients similars")</span><span class="sxs-lookup"><span data-stu-id="feabc-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="feabc-130">Seleccioneu **Visualitza** a la barra d'accions per obrir el detall del segment.</span><span class="sxs-lookup"><span data-stu-id="feabc-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="feabc-131">Aquesta visualització conté informació sobre la distribució dels resultats en les [puntuacions de similitud](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="feabc-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="feabc-132">També trobareu els valors de puntuació de similitud a la **Visualització prèvia dels membres del segment**.</span><span class="sxs-lookup"><span data-stu-id="feabc-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="feabc-133">Utilitzar la sortida d'un segment similar</span><span class="sxs-lookup"><span data-stu-id="feabc-133">Use the output of a similar segment</span></span>

<span data-ttu-id="feabc-134">Podeu [treballar amb la sortida d'un segment semblant](segments.md) com ho feu amb altres segments.</span><span class="sxs-lookup"><span data-stu-id="feabc-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="feabc-135">Per exemple, exporteu el segment o creeu una mesura.</span><span class="sxs-lookup"><span data-stu-id="feabc-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="feabc-136">Actualitzar i editar un segment similar</span><span class="sxs-lookup"><span data-stu-id="feabc-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="feabc-137">Per actualitzar un segment similar, seleccioneu-lo a la pàgina **Segments** i seleccioneu **Actualitza** a la barra d'accions.</span><span class="sxs-lookup"><span data-stu-id="feabc-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="feabc-138">En editar un segment semblant s'han de tornar a processar les dades.</span><span class="sxs-lookup"><span data-stu-id="feabc-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="feabc-139">El segment creat prèviament s'actualitza amb les dades actualitzades.</span><span class="sxs-lookup"><span data-stu-id="feabc-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="feabc-140">Per editar un segment similar, seleccioneu-lo a la pàgina **Segments** i seleccioneu **Edita** a la barra d'accions.</span><span class="sxs-lookup"><span data-stu-id="feabc-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="feabc-141">Apliqueu els canvis i seleccioneu **Executa** per iniciar el processament.</span><span class="sxs-lookup"><span data-stu-id="feabc-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="feabc-142">Suprimir un segment similar</span><span class="sxs-lookup"><span data-stu-id="feabc-142">Delete a similar segment</span></span>

<span data-ttu-id="feabc-143">Seleccioneu el segment a la pàgina **Segments** i seleccioneu **Suprimeix** a la barra d'accions.</span><span class="sxs-lookup"><span data-stu-id="feabc-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="feabc-144">A continuació, confirmeu la supressió.</span><span class="sxs-lookup"><span data-stu-id="feabc-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="feabc-145">Quant a les puntuacions de similitud</span><span class="sxs-lookup"><span data-stu-id="feabc-145">About similarity scores</span></span>

<span data-ttu-id="feabc-146">El model d'aprenentatge automàtic de classificació binària assigna una puntuació als clients al segment semblant.</span><span class="sxs-lookup"><span data-stu-id="feabc-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="feabc-147">La puntuació es basa en la similitud amb els clients del segment d'origen.</span><span class="sxs-lookup"><span data-stu-id="feabc-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="feabc-148">Les puntuacions de similitud per sota de 0,55 són clients que el sistema ha classificat com a *no similars* als clients del segment d'origen</span><span class="sxs-lookup"><span data-stu-id="feabc-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="feabc-149">Les puntuacions de similitud entre 0,55-0,7 es classifiquen com a *força semblants*</span><span class="sxs-lookup"><span data-stu-id="feabc-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="feabc-150">Les puntuacions de similitud entre 0,7-0,85 es classifiquen com a *semblants*</span><span class="sxs-lookup"><span data-stu-id="feabc-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="feabc-151">Les puntuacions de similitud entre 0,85-1 són clients que el sistema ha classificat com a *molt semblants*</span><span class="sxs-lookup"><span data-stu-id="feabc-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="feabc-152">Els clients amb resultats de similitud per sota de 0,4 no s'inclouen a la sortida del model.</span><span class="sxs-lookup"><span data-stu-id="feabc-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="feabc-153">El sistema no els considera prou semblants al segment d'origen.</span><span class="sxs-lookup"><span data-stu-id="feabc-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]