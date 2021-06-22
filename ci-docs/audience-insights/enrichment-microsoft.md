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
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245695"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="805a8-103">Enriquir els perfils de client amb afinitats de marca i d'interès (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="805a8-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="805a8-104">Utilitzeu dades propietat de Microsoft per enriquir les dades dels vostres clients amb similituds de marca i d'interessos.</span><span class="sxs-lookup"><span data-stu-id="805a8-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="805a8-105">Aquestes afinitats es determinen segons les dades de les persones amb dades demogràfiques similars als clients.</span><span class="sxs-lookup"><span data-stu-id="805a8-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="805a8-106">Aquesta informació us ajudarà a conèixer i segmentar millor els vostres clients segons les seves afinitats amb determinades marques i interessos.</span><span class="sxs-lookup"><span data-stu-id="805a8-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="805a8-107">A les conclusions del públic, aneu a **Dades** > **Enriquiment** per [configurar i visualitzar els enriquiments](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="805a8-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="805a8-108">Per configurar l'enriquiment d'afinitats de marques, aneu a la pestanya **Detecta** i seleccioneu **Enriqueix les meves dades** a la peça **Marques**.</span><span class="sxs-lookup"><span data-stu-id="805a8-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="805a8-109">Per configurar l'enriquiment d'afinitats d'interessos, aneu a la pestanya **Detecta** i seleccioneu **Enriqueix les meves dades** a la peça **Interessos**.</span><span class="sxs-lookup"><span data-stu-id="805a8-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="805a8-110">![Peces de marques i interessos](media/BrandsInterest-tile-Hub.png "Peces de marques i interessos")</span><span class="sxs-lookup"><span data-stu-id="805a8-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="805a8-111">Com determinem les similituds</span><span class="sxs-lookup"><span data-stu-id="805a8-111">How we determine affinities</span></span>

<span data-ttu-id="805a8-112">Utilitzem les dades de la cerca en línia de Microsoft per trobar similituds per a marques i interessos en diversos segments demogràfics (definits per edat, gènere o ubicació).</span><span class="sxs-lookup"><span data-stu-id="805a8-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="805a8-113">El volum de cerques en línia d'una marca o un interès determina la quantitat d'afinitat d'un segment demogràfic, en comparació amb altres segments, que té a aquesta marca o interès.</span><span class="sxs-lookup"><span data-stu-id="805a8-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="805a8-114">Nivell d'afinitat i puntuació</span><span class="sxs-lookup"><span data-stu-id="805a8-114">Affinity level and score</span></span>

<span data-ttu-id="805a8-115">A cada perfil de client enriquit, proporcionem dos valors relacionats: el nivell d'afinitat i la puntuació d'afinitat.</span><span class="sxs-lookup"><span data-stu-id="805a8-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="805a8-116">Aquests valors us ajuden a determinar la robustesa d'afinitat del segment demogràfic d'aquest perfil, d'una marca o interès, en comparació amb altres segments demogràfics.</span><span class="sxs-lookup"><span data-stu-id="805a8-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="805a8-117">El *nivell d'afinitat* consta de quatre nivells i una *puntuació d'afinitat* es calcula a una escala de 100 punts que s'assigna als nivells d'afinitat.</span><span class="sxs-lookup"><span data-stu-id="805a8-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="805a8-118">Nivell d'afinitat</span><span class="sxs-lookup"><span data-stu-id="805a8-118">Affinity level</span></span> |<span data-ttu-id="805a8-119">Puntuació d'afinitat</span><span class="sxs-lookup"><span data-stu-id="805a8-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="805a8-120">Molt alta</span><span class="sxs-lookup"><span data-stu-id="805a8-120">Very high</span></span>     | <span data-ttu-id="805a8-121">85-100</span><span class="sxs-lookup"><span data-stu-id="805a8-121">85-100</span></span>       |
|<span data-ttu-id="805a8-122">Alta</span><span class="sxs-lookup"><span data-stu-id="805a8-122">High</span></span>     | <span data-ttu-id="805a8-123">70-84</span><span class="sxs-lookup"><span data-stu-id="805a8-123">70-84</span></span>        |
|<span data-ttu-id="805a8-124">Mitjà</span><span class="sxs-lookup"><span data-stu-id="805a8-124">Medium</span></span>     | <span data-ttu-id="805a8-125">35-69</span><span class="sxs-lookup"><span data-stu-id="805a8-125">35-69</span></span>        |
|<span data-ttu-id="805a8-126">Baixa</span><span class="sxs-lookup"><span data-stu-id="805a8-126">Low</span></span>     | <span data-ttu-id="805a8-127">1-34</span><span class="sxs-lookup"><span data-stu-id="805a8-127">1-34</span></span>        |

<span data-ttu-id="805a8-128">Depenent de la granularitat que voleu per mesurar l'afinitat, podeu utilitzar el nivell d'afinitat o la puntuació.</span><span class="sxs-lookup"><span data-stu-id="805a8-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="805a8-129">La puntuació d'afinitat us proporciona un control més precís.</span><span class="sxs-lookup"><span data-stu-id="805a8-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="805a8-130">Països o regions admesos</span><span class="sxs-lookup"><span data-stu-id="805a8-130">Supported countries/regions</span></span>

<span data-ttu-id="805a8-131">Actualment, admeten a les següents opcions de país o regió: Austràlia, Canadà (anglès), França, Alemanya, Regne Unit o Estats Units (anglès).</span><span class="sxs-lookup"><span data-stu-id="805a8-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="805a8-132">Per seleccionar un país o regió, obriu **Enriquiment de la marca** o **Enriquiment de l'interès** i seleccioneu **Canvia** al costat de **País o regió**.</span><span class="sxs-lookup"><span data-stu-id="805a8-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="805a8-133">A la subfinestra **Configuració de país o regió**, trieu una opció i seleccioneu **Aplica**.</span><span class="sxs-lookup"><span data-stu-id="805a8-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="805a8-134">Implicacions relacionades amb la selecció de països o regions</span><span class="sxs-lookup"><span data-stu-id="805a8-134">Implications related to country selection</span></span>

- <span data-ttu-id="805a8-135">Quan [trieu les vostres pròpies marques](#define-your-brands-or-interests), el sistema ofereix suggeriments basats en el país o regió seleccionat.</span><span class="sxs-lookup"><span data-stu-id="805a8-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="805a8-136">A l'hora de [triar un sector](#define-your-brands-or-interests), obtindreu les marques o els interessos més rellevants en funció del país o regió seleccionat.</span><span class="sxs-lookup"><span data-stu-id="805a8-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="805a8-137">Quan [enriquiu perfils](#refresh-enrichment), millorarem tots els perfils de client per als quals obtenim dades per a les marques i els interessos seleccionats.</span><span class="sxs-lookup"><span data-stu-id="805a8-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="805a8-138">Això inclou els perfils que no es troben al país o regió seleccionats.</span><span class="sxs-lookup"><span data-stu-id="805a8-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="805a8-139">Per exemple, si heu seleccionat Alemanya, enriquirem els perfils ubicats als Estats Units si tenim dades disponibles per a les marques i els interessos seleccionats als EUA.</span><span class="sxs-lookup"><span data-stu-id="805a8-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="805a8-140">Configurar l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="805a8-140">Configure Enrichment</span></span>

<span data-ttu-id="805a8-141">Una experiència guiada us ajuda a través de la configuració dels enriquiments.</span><span class="sxs-lookup"><span data-stu-id="805a8-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="805a8-142">Definir les marques o els interessos</span><span class="sxs-lookup"><span data-stu-id="805a8-142">Define your brands or interests</span></span>

<span data-ttu-id="805a8-143">Trieu fins a cinc marques o interessos utilitzant una opció o totes dues:</span><span class="sxs-lookup"><span data-stu-id="805a8-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="805a8-144">**Sector**: seleccioneu el vostre sector a la llista desplegable i, a continuació, trieu entre les marques principals o els interessos d'aquest sector.</span><span class="sxs-lookup"><span data-stu-id="805a8-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="805a8-145">**Trieu la vostra pròpia**: introduïu una marca o un interès rellevant per a la vostra organització i trieu entre els suggeriments de coincidència.</span><span class="sxs-lookup"><span data-stu-id="805a8-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="805a8-146">Si no enumerem una marca o un interès que cerqueu, envieu-nos els vostres comentaris mitjançant l'enllaç **Suggereix**.</span><span class="sxs-lookup"><span data-stu-id="805a8-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="805a8-147">Revisar les preferències de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="805a8-147">Review enrichment preferences</span></span>

<span data-ttu-id="805a8-148">Reviseu les vostres preferències d'enriquiment per defecte i actualitzeu-les segons calgui.</span><span class="sxs-lookup"><span data-stu-id="805a8-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla de la finestra de preferències d'enriquiment.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="805a8-150">Seleccionar l'entitat que voleu enriquir</span><span class="sxs-lookup"><span data-stu-id="805a8-150">Select entity to enrich</span></span>

<span data-ttu-id="805a8-151">Seleccioneu **Entitat enriquida** i trieu el conjunt de dades que voleu enriquir amb les dades de l'empresa des de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="805a8-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="805a8-152">Podeu seleccionar l'entitat Client per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.</span><span class="sxs-lookup"><span data-stu-id="805a8-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="805a8-153">Assignació dels camps</span><span class="sxs-lookup"><span data-stu-id="805a8-153">Map your fields</span></span>

<span data-ttu-id="805a8-154">Assigneu els camps de l'entitat de client unificada per definir el segment demogràfic que voleu que el sistema utilitzi per enriquir les dades de client.</span><span class="sxs-lookup"><span data-stu-id="805a8-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="805a8-155">Assigneu els atributs País/Regió i, com a mínim, Data de naixement o Gènere.</span><span class="sxs-lookup"><span data-stu-id="805a8-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="805a8-156">A més, heu d'assignar almenys un entre Ciutat (i Província o estat) o Codi postal.</span><span class="sxs-lookup"><span data-stu-id="805a8-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="805a8-157">Seleccioneu **Edita** per definir l'assignació dels camps i seleccioneu **Aplica** quan acabeu.</span><span class="sxs-lookup"><span data-stu-id="805a8-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="805a8-158">Seleccioneu **Desa** per completar l'assignació de camps.</span><span class="sxs-lookup"><span data-stu-id="805a8-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="805a8-159">S'admeten els valors i els formats que es mostren a continuació; els valors no distingeixen entre majúscules i minúscules:</span><span class="sxs-lookup"><span data-stu-id="805a8-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="805a8-160">**Data de naixement**: us recomanem que la data de naixement es converteixi al tipus Data/Hora durant la ingestió de dades.</span><span class="sxs-lookup"><span data-stu-id="805a8-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="805a8-161">Alternativament, pot ser una cadena en format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), com ara "aaaa-MM-dd" o "aaaa-MM-ddTHH:mm: ssZ".</span><span class="sxs-lookup"><span data-stu-id="805a8-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="805a8-162">**Sexe**: masculí, femení, desconegut</span><span class="sxs-lookup"><span data-stu-id="805a8-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="805a8-163">**Codi postal**: codis postals de cinc dígits per als Estats Units, codi postal estàndard a la resta de llocs</span><span class="sxs-lookup"><span data-stu-id="805a8-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="805a8-164">**Ciutat**: nom de la ciutat en anglès</span><span class="sxs-lookup"><span data-stu-id="805a8-164">**City**: City name in English</span></span>
- <span data-ttu-id="805a8-165">**Província o estat**: abreviatura de dues lletres per als Estats Units i Canadà.</span><span class="sxs-lookup"><span data-stu-id="805a8-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="805a8-166">Abreviatura de dues o tres lletres per a Austràlia.</span><span class="sxs-lookup"><span data-stu-id="805a8-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="805a8-167">No s'aplica per a França, Alemanya o el Regne Unit.</span><span class="sxs-lookup"><span data-stu-id="805a8-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="805a8-168">**País o regió**:</span><span class="sxs-lookup"><span data-stu-id="805a8-168">**Country/Region**:</span></span>

  - <span data-ttu-id="805a8-169">US: Estats Units d'Amèrica, Estats Units, EUA</span><span class="sxs-lookup"><span data-stu-id="805a8-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="805a8-170">CA: Canadà, CA</span><span class="sxs-lookup"><span data-stu-id="805a8-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="805a8-171">GB: Regne Unit, UK, Gran Bretanya, GB, Regne Unit de la Gran Bretanya i Irlanda del Nord, Regne Unit de la Gran Bretanya</span><span class="sxs-lookup"><span data-stu-id="805a8-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="805a8-172">AU: Austràlia, AU, Mancomunitat d'Austràlia</span><span class="sxs-lookup"><span data-stu-id="805a8-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="805a8-173">FR: França, FR, República Francesa</span><span class="sxs-lookup"><span data-stu-id="805a8-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="805a8-174">DE: Alemanya, Alemany, Deutschland, Allemagne, DE, República Federal d'Alemanya, República d'Alemanya</span><span class="sxs-lookup"><span data-stu-id="805a8-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="805a8-175">Revisar i donar nom a l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="805a8-175">Review and name the enrichment</span></span>

<span data-ttu-id="805a8-176">Finalment, podeu revisar la informació i proporcionar un nom per a l'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="805a8-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pàgina de revisió i nom.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="805a8-178">Actualitzar l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="805a8-178">Refresh enrichment</span></span>

<span data-ttu-id="805a8-179">Executeu l'enriquiment un cop hàgiu configurat les marques, els interessos i l'assignació de camps de les dades demogràfiques.</span><span class="sxs-lookup"><span data-stu-id="805a8-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="805a8-180">Per iniciar el procés, seleccioneu **Executa** a la pàgina de configuració de l'interès o la marca.</span><span class="sxs-lookup"><span data-stu-id="805a8-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="805a8-181">A més, podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una actualització planificada.</span><span class="sxs-lookup"><span data-stu-id="805a8-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="805a8-182">En funció de la mida de les dades dels clients, l'execució d'enriquiment pot trigar uns quants minuts a completar-se.</span><span class="sxs-lookup"><span data-stu-id="805a8-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="805a8-183">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="805a8-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="805a8-184">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="805a8-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="805a8-185">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="805a8-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="805a8-186">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.</span><span class="sxs-lookup"><span data-stu-id="805a8-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="805a8-187">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="805a8-187">Enrichment results</span></span>

<span data-ttu-id="805a8-188">Després de l'execució del procés d'enriquiment, aneu a **Els meus enriquiments** per revisar el nombre total de clients enriquits i un desglossament de les marques o els interessos dels perfils de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="805a8-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Visualització prèvia dels resultats després d'executar el procés d'enriquiment":::

<span data-ttu-id="805a8-190">Reviseu les dades enriquides seleccionant **Visualitza les dades enriquides** al gràfic.</span><span class="sxs-lookup"><span data-stu-id="805a8-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="805a8-191">Les dades enriquits per a les marques van a l'entitat **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="805a8-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="805a8-192">Les dades d'interès es troben a l'entitat **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="805a8-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="805a8-193">També trobareu aquestes entitats enumerades al grup **Enriquiment** a **Dades** > **Entitats**.</span><span class="sxs-lookup"><span data-stu-id="805a8-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="805a8-194">Veure dades d'enriquiment a la targeta del client</span><span class="sxs-lookup"><span data-stu-id="805a8-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="805a8-195">Les afinitats de marca i d'interès també es poden visualitzar en targetes de clients individuals.</span><span class="sxs-lookup"><span data-stu-id="805a8-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="805a8-196">Aneu a **Clients** i seleccioneu un perfil de client.</span><span class="sxs-lookup"><span data-stu-id="805a8-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="805a8-197">A la targeta del client, trobareu gràfics per a les marques o els interessos per als quals els usuaris del perfil demogràfic del client tenen afinitat.</span><span class="sxs-lookup"><span data-stu-id="805a8-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Targeta del client amb dades enriquides":::

## <a name="next-steps"></a><span data-ttu-id="805a8-199">Passos següents</span><span class="sxs-lookup"><span data-stu-id="805a8-199">Next steps</span></span>

<span data-ttu-id="805a8-200">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="805a8-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="805a8-201">Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="805a8-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
