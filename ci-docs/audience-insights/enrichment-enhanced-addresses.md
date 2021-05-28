---
title: Enriquiment per millorar l'adreça
description: Enriquiu i normalitzeu la informació de les adreces dels perfils dels clients amb els models de Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965566"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="403f7-103">Enriquiment de perfils de clients amb adreces millorades</span><span class="sxs-lookup"><span data-stu-id="403f7-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="403f7-104">Les adreces de les dades poden ser desestructurades, incompletes o incorrectes.</span><span class="sxs-lookup"><span data-stu-id="403f7-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="403f7-105">Utilitzeu els models de Microsoft per normalitzar i enriquir les adreces en el [format del model de dades comú](/common-data-model/schema/core/applicationcommon/address) per obtenir una millor precisió i informació.</span><span class="sxs-lookup"><span data-stu-id="403f7-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="403f7-106">Com potenciem les adreces</span><span class="sxs-lookup"><span data-stu-id="403f7-106">How we enhance addresses</span></span>

<span data-ttu-id="403f7-107">El nostre model passa per un procés de dos passos per millorar una adreça.</span><span class="sxs-lookup"><span data-stu-id="403f7-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="403f7-108">En primer lloc, analitza l'adreça per identificar-ne els components i els posa en un format estructurat.</span><span class="sxs-lookup"><span data-stu-id="403f7-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="403f7-109">A continuació, utilitzem la intel·ligència artificial per corregir, completar i estandarditzar els valors de l'adreça.</span><span class="sxs-lookup"><span data-stu-id="403f7-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="403f7-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="403f7-110">Example</span></span>

<span data-ttu-id="403f7-111">La informació de l'adreça pot tenir un format no estàndard i contenir errors ortogràfics.</span><span class="sxs-lookup"><span data-stu-id="403f7-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="403f7-112">El model pot solucionar aquests problemes i crear adreces coherents en perfils de clients unificats.</span><span class="sxs-lookup"><span data-stu-id="403f7-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="403f7-113">Limitacions</span><span class="sxs-lookup"><span data-stu-id="403f7-113">Limitations</span></span>

<span data-ttu-id="403f7-114">Les adreces millorades només funcionen amb els valors que ja existeixen a les dades de l'adreça ingerida.</span><span class="sxs-lookup"><span data-stu-id="403f7-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="403f7-115">El model no:</span><span class="sxs-lookup"><span data-stu-id="403f7-115">The model doesn't:</span></span> 

1. <span data-ttu-id="403f7-116">Verifica si l'adreça és vàlida.</span><span class="sxs-lookup"><span data-stu-id="403f7-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="403f7-117">Verifica si algun dels valors, com ara els codis postals o els noms de carrers, són vàlids.</span><span class="sxs-lookup"><span data-stu-id="403f7-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="403f7-118">Canvia els valors que no reconeix.</span><span class="sxs-lookup"><span data-stu-id="403f7-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="403f7-119">El model utilitza tècniques basades en l'aprenentatge automàtic per millorar les adreces.</span><span class="sxs-lookup"><span data-stu-id="403f7-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="403f7-120">Tot i que apliquem un llindar d'alta confiança per quan el model canvia un valor d'entrada, com en qualsevol model basat en aprenentatge automàtic, no es garanteix la precisió del 100%.</span><span class="sxs-lookup"><span data-stu-id="403f7-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="403f7-121">Països o regions admesos</span><span class="sxs-lookup"><span data-stu-id="403f7-121">Supported countries or regions</span></span>

<span data-ttu-id="403f7-122">Actualment admetem adreces enriquides en aquests països o regions:</span><span class="sxs-lookup"><span data-stu-id="403f7-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="403f7-123">Austràlia</span><span class="sxs-lookup"><span data-stu-id="403f7-123">Australia</span></span>
- <span data-ttu-id="403f7-124">Canadà</span><span class="sxs-lookup"><span data-stu-id="403f7-124">Canada</span></span>
- <span data-ttu-id="403f7-125">Regne Unit</span><span class="sxs-lookup"><span data-stu-id="403f7-125">United Kingdom</span></span>
- <span data-ttu-id="403f7-126">Estats Units</span><span class="sxs-lookup"><span data-stu-id="403f7-126">United States</span></span>

<span data-ttu-id="403f7-127">Les adreces han de contenir un valor de país o de regió.</span><span class="sxs-lookup"><span data-stu-id="403f7-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="403f7-128">No processem adreces per a països o regions que no són compatibles i adreces que no tenen cap país o regió proporcionat.</span><span class="sxs-lookup"><span data-stu-id="403f7-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="403f7-129">Configurar l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="403f7-129">Configure the enrichment</span></span>

1. <span data-ttu-id="403f7-130">Aneu a **Dades** > **Enriquiment**.</span><span class="sxs-lookup"><span data-stu-id="403f7-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="403f7-131">Seleccioneu **Enriqueix les meves dades** a la peça **Adreces millorades**.</span><span class="sxs-lookup"><span data-stu-id="403f7-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de pantalla de la peça Adreces millorades.":::

1. <span data-ttu-id="403f7-133">Seleccioneu el **Conjunt de dades de client** i trieu l'entitat que conté les adreces que voleu enriquir.</span><span class="sxs-lookup"><span data-stu-id="403f7-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="403f7-134">Podeu seleccionar l'entitat *Client* per enriquir les adreces de tots els perfils de client o seleccionar una entitat de segment per enriquir les adreces només als perfils de client que conté aquest segment.</span><span class="sxs-lookup"><span data-stu-id="403f7-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="403f7-135">Seleccioneu com es formaten les adreces al conjunt de dades.</span><span class="sxs-lookup"><span data-stu-id="403f7-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="403f7-136">Trieu **Adreça d'un sol atribut** si les adreces de les dades utilitzen un únic camp.</span><span class="sxs-lookup"><span data-stu-id="403f7-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="403f7-137">Trieu **Adreça de diversos atributs** si les adreces de les dades utilitzen més d'un camp de dades.</span><span class="sxs-lookup"><span data-stu-id="403f7-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="403f7-138">El país o la regió és obligatori tant a l'adreça d'un sol atribut com a l'adreça de diversos atributs.</span><span class="sxs-lookup"><span data-stu-id="403f7-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="403f7-139">Les adreces que no continguin valors de país o regió vàlids o admesos no s'enriquiran</span><span class="sxs-lookup"><span data-stu-id="403f7-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="403f7-140">Assigneu els camps d'adreça de l'entitat de client unificada.</span><span class="sxs-lookup"><span data-stu-id="403f7-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Pàgina d'assignació de camp d'adreça millorada.":::

1. <span data-ttu-id="403f7-142">Seleccioneu **Següent** per completar l'assignació de camp.</span><span class="sxs-lookup"><span data-stu-id="403f7-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="403f7-143">Proporcioneu un nom per a l'enriquiment i per a l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="403f7-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="403f7-144">Seleccioneu **Desa l'enriquiment** després de revisar les opcions.</span><span class="sxs-lookup"><span data-stu-id="403f7-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="403f7-145">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="403f7-145">Enrichment results</span></span>

<span data-ttu-id="403f7-146">Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="403f7-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="403f7-147">També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="403f7-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="403f7-148">El temps de processament depèn de la mida de les dades dels clients.</span><span class="sxs-lookup"><span data-stu-id="403f7-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="403f7-149">Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**.</span><span class="sxs-lookup"><span data-stu-id="403f7-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="403f7-150">A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.</span><span class="sxs-lookup"><span data-stu-id="403f7-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="403f7-151">Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.</span><span class="sxs-lookup"><span data-stu-id="403f7-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="403f7-152">Passos següents</span><span class="sxs-lookup"><span data-stu-id="403f7-152">Next steps</span></span>

<span data-ttu-id="403f7-153">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="403f7-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="403f7-154">Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="403f7-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
