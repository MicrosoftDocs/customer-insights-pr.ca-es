---
title: Enriquir els perfils de client amb dades de Microsoft
description: Utilitzeu dades propietat de Microsoft per enriquir les dades dels vostres clients amb similituds de marca i d'interessos.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305144"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="b2bdb-103">Enriquir els perfils de client amb afinitats de marca i d'interès (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="b2bdb-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="b2bdb-104">Utilitzeu dades propietat de Microsoft per enriquir les dades dels vostres clients amb similituds de marca i d'interessos.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="b2bdb-105">Aquestes afinitats es basen en les dades de persones en un grup demogràfic similar als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="b2bdb-106">Aquesta informació us ajudarà a conèixer i segmentar millor els vostres clients segons les seves afinitats amb determinades marques i interessos.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="b2bdb-107">A les conclusions del públic, aneu a **Dades** > **Enriquiment** per [configurar i visualitzar els enriquiments](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="b2bdb-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="b2bdb-108">Per configurar l'enriquiment d'afinitats de marques, aneu a la pestanya **Detecta** i seleccioneu **Enriqueix les meves dades** a la peça **Marques**.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="b2bdb-109">Per configurar l'enriquiment d'afinitats d'interessos, aneu a la pestanya **Detecta** i seleccioneu **Enriqueix les meves dades** a la peça **Interessos**.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b2bdb-110">![Peces de marques i interessos](media/BrandsInterest-tile-Hub.png "Peces de marques i interessos")</span><span class="sxs-lookup"><span data-stu-id="b2bdb-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="b2bdb-111">Com determinem les similituds</span><span class="sxs-lookup"><span data-stu-id="b2bdb-111">How we determine affinities</span></span>

<span data-ttu-id="b2bdb-112">Utilitzem les dades de la cerca en línia de Microsoft per trobar similituds per a marques i interessos en diversos segments demogràfics (definits per edat, gènere o ubicació).</span><span class="sxs-lookup"><span data-stu-id="b2bdb-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="b2bdb-113">El volum de cerques en línia d'una marca o un interès determina la quantitat d'afinitat d'un segment demogràfic, en comparació amb altres segments, que té a aquesta marca o interès.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="b2bdb-114">Nivell d'afinitat i puntuació</span><span class="sxs-lookup"><span data-stu-id="b2bdb-114">Affinity level and score</span></span>

<span data-ttu-id="b2bdb-115">A cada perfil de client enriquit, proporcionem dos valors relacionats: el nivell d'afinitat i la puntuació d'afinitat.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="b2bdb-116">Aquests valors us ajuden a determinar la robustesa d'afinitat del segment demogràfic d'aquest perfil, d'una marca o interès, en comparació amb altres segments demogràfics.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="b2bdb-117">El *nivell d'afinitat* consta de quatre nivells i una *puntuació d'afinitat* es calcula a una escala de 100 punts que s'assigna als nivells d'afinitat.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="b2bdb-118">Nivell d'afinitat</span><span class="sxs-lookup"><span data-stu-id="b2bdb-118">Affinity level</span></span> |<span data-ttu-id="b2bdb-119">Puntuació d'afinitat</span><span class="sxs-lookup"><span data-stu-id="b2bdb-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="b2bdb-120">Molt alta</span><span class="sxs-lookup"><span data-stu-id="b2bdb-120">Very high</span></span>     | <span data-ttu-id="b2bdb-121">85-100</span><span class="sxs-lookup"><span data-stu-id="b2bdb-121">85-100</span></span>       |
|<span data-ttu-id="b2bdb-122">Alta</span><span class="sxs-lookup"><span data-stu-id="b2bdb-122">High</span></span>     | <span data-ttu-id="b2bdb-123">70-84</span><span class="sxs-lookup"><span data-stu-id="b2bdb-123">70-84</span></span>        |
|<span data-ttu-id="b2bdb-124">Mitjà</span><span class="sxs-lookup"><span data-stu-id="b2bdb-124">Medium</span></span>     | <span data-ttu-id="b2bdb-125">35-69</span><span class="sxs-lookup"><span data-stu-id="b2bdb-125">35-69</span></span>        |
|<span data-ttu-id="b2bdb-126">Baixa</span><span class="sxs-lookup"><span data-stu-id="b2bdb-126">Low</span></span>     | <span data-ttu-id="b2bdb-127">1-34</span><span class="sxs-lookup"><span data-stu-id="b2bdb-127">1-34</span></span>        |

<span data-ttu-id="b2bdb-128">Depenent de la granularitat que voleu per mesurar l'afinitat, podeu utilitzar el nivell d'afinitat o la puntuació.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="b2bdb-129">La puntuació d'afinitat us proporciona un control més precís.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="b2bdb-130">Països o regions admesos</span><span class="sxs-lookup"><span data-stu-id="b2bdb-130">Supported countries/regions</span></span>

<span data-ttu-id="b2bdb-131">Actualment, admeten a les següents opcions de país o regió: Austràlia, Canadà (anglès), França, Alemanya, Regne Unit o Estats Units (anglès).</span><span class="sxs-lookup"><span data-stu-id="b2bdb-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="b2bdb-132">Per seleccionar un país o regió, obriu **Enriquiment de marques** o **Enriquiment d'interessos** i seleccioneu **Canvia** al costat de **País/Regió**.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="b2bdb-133">A la subfinestra **Configuració de país o regió**, trieu una opció i seleccioneu **Aplica**.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="b2bdb-134">Implicacions relacionades amb la selecció de països o regions</span><span class="sxs-lookup"><span data-stu-id="b2bdb-134">Implications related to country selection</span></span>

- <span data-ttu-id="b2bdb-135">Quan [trieu les vostres pròpies marques](#define-your-brands-or-interests), el sistema ofereix suggeriments basats en el país o regió seleccionat.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="b2bdb-136">A l'hora de [triar un sector](#define-your-brands-or-interests), obtindreu les marques o els interessos més rellevants en funció del país o regió seleccionat.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="b2bdb-137">En [enriquir els perfils](#refresh-enrichment), enriquirem tots els perfils de clients per als quals obtenim dades per a les marques i els interessos seleccionats, incloent-hi els perfils que no es troben al país o regió seleccionats.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="b2bdb-138">Per exemple, si heu seleccionat Alemanya, enriquirem els perfils ubicats als Estats Units si tenim dades disponibles per a les marques i els interessos seleccionats als EUA.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="b2bdb-139">Configurar l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="b2bdb-139">Configure enrichment</span></span>

<span data-ttu-id="b2bdb-140">Una experiència guiada us ajuda a través de la configuració dels enriquiments.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="b2bdb-141">Definir les marques o els interessos</span><span class="sxs-lookup"><span data-stu-id="b2bdb-141">Define your brands or interests</span></span>

<span data-ttu-id="b2bdb-142">Trieu fins a cinc marques o interessos utilitzant una opció o totes dues:</span><span class="sxs-lookup"><span data-stu-id="b2bdb-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="b2bdb-143">**Sector**: seleccioneu el sector a la llista desplegable i trieu entre les marques o els interessos principals del sector.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="b2bdb-144">**Trieu la vostra pròpia**: introduïu una marca o un interès rellevant per a la vostra organització i trieu entre els suggeriments de coincidència.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="b2bdb-145">Si no enumerem una marca o un interès que cerqueu, envieu-nos els vostres comentaris mitjançant l'enllaç **Suggereix**.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="b2bdb-146">Revisar les preferències de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="b2bdb-146">Review enrichment preferences</span></span>

<span data-ttu-id="b2bdb-147">Reviseu les vostres preferències d'enriquiment per defecte i actualitzeu-les segons calgui.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla de la finestra de preferències d'enriquiment.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="b2bdb-149">Seleccionar l'entitat que voleu enriquir</span><span class="sxs-lookup"><span data-stu-id="b2bdb-149">Select entity to enrich</span></span>

<span data-ttu-id="b2bdb-150">Seleccioneu **Entitat enriquida** i trieu el conjunt de dades que voleu enriquir amb les dades de l'empresa des de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="b2bdb-151">Podeu seleccionar l'entitat Client per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="b2bdb-152">Assignació dels camps</span><span class="sxs-lookup"><span data-stu-id="b2bdb-152">Map your fields</span></span>

<span data-ttu-id="b2bdb-153">Assigneu els camps de l'entitat de client unificada per definir el segment demogràfic que voleu que el sistema utilitzi per enriquir les dades de client.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="b2bdb-154">Assigneu els atributs País/Regió i, com a mínim, Data de naixement o Gènere.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="b2bdb-155">A més, heu d'assignar almenys un entre Ciutat (i Província o estat) o Codi postal.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="b2bdb-156">Seleccioneu **Edita** per definir l'assignació dels camps i seleccioneu **Aplica** quan acabeu.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="b2bdb-157">Seleccioneu **Desa** per completar l'assignació de camps.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="b2bdb-158">S'admeten els valors i els formats que es mostren a continuació; els valors no distingeixen entre majúscules i minúscules:</span><span class="sxs-lookup"><span data-stu-id="b2bdb-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="b2bdb-159">**Data de naixement**: us recomanem que la data de naixement es converteixi al tipus Data/Hora durant la ingestió de dades.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="b2bdb-160">Com a alternativa, pot ser una cadena en format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" or "aaaa-MM-ddTHH:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="b2bdb-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="b2bdb-161">**Gènere**: masculí, femení, desconegut.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="b2bdb-162">**Codi postal**: codis postals de cinc dígits per als Estats Units, codi postal estàndard a tot el món.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="b2bdb-163">**Ciutat**: nom de la ciutat en anglès.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-163">**City**: City name in English.</span></span>
- <span data-ttu-id="b2bdb-164">**Província o estat**: abreviatura de dues lletres per als Estats Units i Canadà.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="b2bdb-165">Abreviatura de dues o tres lletres per a Austràlia.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="b2bdb-166">No s'aplica per a França, Alemanya o el Regne Unit.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="b2bdb-167">**País o regió**:</span><span class="sxs-lookup"><span data-stu-id="b2bdb-167">**Country/Region**:</span></span>

  - <span data-ttu-id="b2bdb-168">US: Estats Units d'Amèrica, Estats Units, EUA</span><span class="sxs-lookup"><span data-stu-id="b2bdb-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="b2bdb-169">CA: Canadà, CA</span><span class="sxs-lookup"><span data-stu-id="b2bdb-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="b2bdb-170">GB: Regne Unit, UK, Gran Bretanya, GB, Regne Unit de la Gran Bretanya i Irlanda del Nord, Regne Unit de la Gran Bretanya</span><span class="sxs-lookup"><span data-stu-id="b2bdb-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="b2bdb-171">AU: Austràlia, AU, Commonwealth d'Austràlia</span><span class="sxs-lookup"><span data-stu-id="b2bdb-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="b2bdb-172">FR: França, FR, República Francesa</span><span class="sxs-lookup"><span data-stu-id="b2bdb-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="b2bdb-173">DE: Alemanya, Alemany, Deutschland, Allemagne, DE, República Federal d'Alemanya, República d'Alemanya</span><span class="sxs-lookup"><span data-stu-id="b2bdb-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="b2bdb-174">Revisar i donar nom a l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="b2bdb-174">Review and name the enrichment</span></span>

<span data-ttu-id="b2bdb-175">Finalment, podeu revisar la informació i proporcionar un nom per a l'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pàgina de revisió i nom.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="b2bdb-177">Actualitzar l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="b2bdb-177">Refresh enrichment</span></span>

<span data-ttu-id="b2bdb-178">Executeu l'enriquiment un cop hàgiu configurat les marques, els interessos i l'assignació de camps de les dades demogràfiques.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="b2bdb-179">Per iniciar el procés, seleccioneu **Executa** a la pàgina de configuració de l'interès o la marca.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="b2bdb-180">A més, podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una actualització planificada.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="b2bdb-181">En funció de la mida de les dades dels clients, l'execució d'enriquiment pot trigar uns quants minuts a completar-se.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="b2bdb-182">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b2bdb-183">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b2bdb-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b2bdb-184">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b2bdb-185">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, última data de processament i tots els errors i advertiments associats amb la tasca.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b2bdb-186">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="b2bdb-186">Enrichment results</span></span>

<span data-ttu-id="b2bdb-187">Després de l'execució del procés d'enriquiment, aneu a **Els meus enriquiments** per revisar el nombre total de clients enriquits i un desglossament de les marques o els interessos dels perfils de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Visualització prèvia dels resultats després d'executar el procés d'enriquiment":::

<span data-ttu-id="b2bdb-189">Reviseu les dades enriquides seleccionant **Visualitza les dades enriquides** al gràfic.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="b2bdb-190">Les dades enriquits per a les marques van a l'entitat **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="b2bdb-191">Les dades d'interès es troben a l'entitat **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="b2bdb-192">També trobareu aquestes entitats enumerades al grup **Enriquiment** a **Dades** > **Entitats**.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="b2bdb-193">Veure dades d'enriquiment a la targeta del client</span><span class="sxs-lookup"><span data-stu-id="b2bdb-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="b2bdb-194">Les afinitats de marca i d'interès també es poden visualitzar en targetes de clients individuals.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="b2bdb-195">Aneu a **Clients** i seleccioneu un perfil de client.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="b2bdb-196">A la targeta del client, trobareu gràfics per a les marques o els interessos per als quals els usuaris del perfil demogràfic del client tenen afinitat.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Targeta del client amb dades enriquides":::

## <a name="next-steps"></a><span data-ttu-id="b2bdb-198">Passos següents</span><span class="sxs-lookup"><span data-stu-id="b2bdb-198">Next steps</span></span>

<span data-ttu-id="b2bdb-199">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b2bdb-200">Creeu [segments](segments.md) i [mesures](measures.md) i, fins i tot, [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="b2bdb-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
