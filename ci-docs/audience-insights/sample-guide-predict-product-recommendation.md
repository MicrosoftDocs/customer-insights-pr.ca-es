---
title: Guia d'exemple per a la predicció de recomanacions de productes
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de recomanacions de productes preparat per a l'ús.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270470"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="9dc8a-103">Guia d'exemple per a la predicció de recomanacions de productes (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="9dc8a-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="9dc8a-104">Se us guiarà per un exemple íntegre de predicció de recomanacions de productes mitjançant les dades d'exemple següents.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="9dc8a-105">Escenari</span><span class="sxs-lookup"><span data-stu-id="9dc8a-105">Scenario</span></span>

<span data-ttu-id="9dc8a-106">Contoso és una empresa que produeix cafè i cafeteres d'alta qualitat, productes que ven a través del seu lloc web de Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="9dc8a-107">El seu objectiu és comprendre quins productes han de recomanar als seus clients periòdics.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="9dc8a-108">Conèixer el que és **probable que comprin** els clients els pot ajudar a estalviar esforços de màrqueting centrant-se en articles concrets.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9dc8a-109">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="9dc8a-109">Prerequisites</span></span>

- <span data-ttu-id="9dc8a-110">Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="9dc8a-111">Us recomanem que implementeu els passos següents [en un entorn nou](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="9dc8a-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="9dc8a-112">Tasca 1 - Ingerir dades</span><span class="sxs-lookup"><span data-stu-id="9dc8a-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="9dc8a-113">Reviseu els articles [sobre la ingestió de dades](data-sources.md) i, més concretament, [la importació de fonts de dades mitjançant els connectors del Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9dc8a-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="9dc8a-114">La informació següent suposa que ja esteu familiaritzat amb el concepte d'ingestió de dades en general.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="9dc8a-115">Ingerir dades de clients procedents de la plataforma de comerç electrònic</span><span class="sxs-lookup"><span data-stu-id="9dc8a-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="9dc8a-116">Creeu una font de dades **eCommerce**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9dc8a-117">Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="9dc8a-118">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9dc8a-119">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="9dc8a-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9dc8a-120">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="9dc8a-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9dc8a-121">**CreatedOn**: data/hora/zona</span><span class="sxs-lookup"><span data-stu-id="9dc8a-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeu la data de naixement en data.":::

5. <span data-ttu-id="9dc8a-123">Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="9dc8a-124">**Deseu** la font de dades.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="9dc8a-125">Ingerir dades de compres en línia</span><span class="sxs-lookup"><span data-stu-id="9dc8a-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="9dc8a-126">Afegiu un altre conjunt de dades a la mateixa font de dades **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="9dc8a-127">Torneu a triar el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="9dc8a-128">Introduïu l'adreça URL de les dades de **Compres en línia** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="9dc8a-129">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9dc8a-130">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="9dc8a-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9dc8a-131">**PurchasedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="9dc8a-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="9dc8a-132">**TotalPrice**: moneda</span><span class="sxs-lookup"><span data-stu-id="9dc8a-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="9dc8a-133">Al camp **Nom** de la subfinestra lateral, canvieu el nom de la font de dades **Query** per **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="9dc8a-134">Deseu la font de dades.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="9dc8a-135">Ingerir dades de clients procedents de l'esquema de fidelització</span><span class="sxs-lookup"><span data-stu-id="9dc8a-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="9dc8a-136">Creeu una font de dades amb el nom **LoyaltyScheme**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9dc8a-137">Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="9dc8a-138">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9dc8a-139">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="9dc8a-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9dc8a-140">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="9dc8a-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9dc8a-141">**RewardsPoints**: nombre enter</span><span class="sxs-lookup"><span data-stu-id="9dc8a-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="9dc8a-142">**CreatedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="9dc8a-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="9dc8a-143">Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="9dc8a-144">Deseu la font de dades.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="9dc8a-145">Tasca 2 - Unificació de les dades</span><span class="sxs-lookup"><span data-stu-id="9dc8a-145">Task 2 - Data unification</span></span>

<span data-ttu-id="9dc8a-146">Un cop feta la ingestió de les dades, començarem el procés d'**assignació, coincidència i combinació** per tal de crear un perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="9dc8a-147">Per obtenir més informació, vegeu [Unificació de les dades](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9dc8a-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="9dc8a-148">Assignació</span><span class="sxs-lookup"><span data-stu-id="9dc8a-148">Map</span></span>

1. <span data-ttu-id="9dc8a-149">Un cop ingerides les dades, assigneu contactes de les dades de comerç electrònic i fidelització a tipus de dades comuns.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="9dc8a-150">Aneu a **Dades** > **Unifica** > **Assigna**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="9dc8a-151">Seleccioneu les entitats que representen el perfil del client (**eCommerceContacts** i **loyCustomers**).</span><span class="sxs-lookup"><span data-stu-id="9dc8a-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![unificar les fonts de dades de comerç electrònic i de fidelització.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="9dc8a-153">Seleccioneu **ContactId** com a clau principal per a **eCommerceContacts** i **LoyaltyID** com a clau principal per a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unifiqueu LoyaltyId com a clau principal.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="9dc8a-155">Coincidència</span><span class="sxs-lookup"><span data-stu-id="9dc8a-155">Match</span></span>

1. <span data-ttu-id="9dc8a-156">Aneu a la pestanya **Coincidència** i seleccioneu **Definició d'ordre**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="9dc8a-157">A la llista desplegable **Principal**, trieu **eCommerceContacts : eCommerce** com a font principal i incloeu-hi tots els registres.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="9dc8a-158">A la llista desplegable **Entitat 2**, trieu **loyCustomers : LoyaltyScheme** i incloeu-hi tots els registres.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unifiqueu la coincidència de comerç electrònic i de fidelització.](media/unify-match-order.png)

4. <span data-ttu-id="9dc8a-160">Seleccioneu **Crea una regla nova**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="9dc8a-161">Afegiu la primera condició amb el FullName.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="9dc8a-162">Per a eCommerceContacts, seleccioneu **FullName** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="9dc8a-163">Per a loyCustomers, seleccioneu **FullName** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="9dc8a-164">Seleccioneu la llista desplegable **Normalitza** i trieu el **Tipus (Telèfon, Nom, Adreça...)**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="9dc8a-165">Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="9dc8a-166">Introduïu el nom **Nom complet, correu electrònic** per a la regla nova.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="9dc8a-167">Per afegir una segona condició per a l'adreça electrònica seleccioneu **Afegeix una condició**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="9dc8a-168">Per a l'entitat eCommerceContacts, trieu **Correu electrònic** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="9dc8a-169">Per a l'entitat loyCustomers, trieu **Correu electrònic** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="9dc8a-170">Deixeu Normalitza en blanc.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="9dc8a-171">Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unifiqueu la regla de coincidència per al nom i el correu electrònic.](media/unify-match-rule.png)

7. <span data-ttu-id="9dc8a-173">Seleccioneu **Desa** i **Executa**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="9dc8a-174">Combinació</span><span class="sxs-lookup"><span data-stu-id="9dc8a-174">Merge</span></span>

1. <span data-ttu-id="9dc8a-175">Aneu a la pestanya **Combinació**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="9dc8a-176">Al **ContactId** de l'entitat **loyCustomers**, canvieu el nom de visualització per **ContactIdLOYALTY** per diferenciar-lo dels altres identificadors ingerits.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![canvieu el nom de contactid de l'identificador de fidelització.](media/unify-merge-contactid.png)

1. <span data-ttu-id="9dc8a-178">Seleccioneu **Desa** i **Executa** per iniciar el procés de combinació.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="9dc8a-179">Tasca 3: Configurar la predicció de recomanació de producte</span><span class="sxs-lookup"><span data-stu-id="9dc8a-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="9dc8a-180">Amb els perfils de client unificats i a punt, ja podem executar la predicció de rotació de subscripcions.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="9dc8a-181">Aneu a **Intel·ligència** > **Predicció** i trieu **Recomanació de producte**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="9dc8a-182">Seleccioneu **Introducció**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-182">Select **Get started**.</span></span>

1. <span data-ttu-id="9dc8a-183">Anomeneu el model **Predicció del model de recomanació de productes de fàbrica** i l'entitat de sortida **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="9dc8a-184">Definiu tres condicions per al model:</span><span class="sxs-lookup"><span data-stu-id="9dc8a-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="9dc8a-185">**Nombre de productes**: definiu aquest valor en **5**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="9dc8a-186">Aquesta configuració defineix quants productes voleu recomanar als clients.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="9dc8a-187">**Suggereix productes que han adquirit els clients recentment?**: seleccioneu **Sí** per indicar que voleu incloure productes a la recomanació que els clients ja han adquirit abans.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="9dc8a-188">**Finestra de cerca en el passat**: seleccioneu com a mínim **365 dies**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="9dc8a-189">Aquesta configuració defineix quin temps en el passat consultarà el model a l'activitat del client per utilitzar-la com a entrada de les seves recomanacions.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferències del model per al model de recomanació de producte.":::

1. <span data-ttu-id="9dc8a-191">Seleccioneu **Dades necessàries** i seleccioneu **Afegeix dades** per a l'historial de compres.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="9dc8a-192">Afegiu l'entitat **eCommercePurchases : eCommerce** i assigneu els camps del comerç electrònic als camps corresponents que requereix el model.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="9dc8a-193">Uniu l'entitat **eCommercePurchases : eCommerce** amb **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Uniu entitats de comerç electrònic.](media/model-purchase-join.png)

1. <span data-ttu-id="9dc8a-195">Seleccioneu **Següent** per definir la planificació del model.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="9dc8a-196">El model ha formar-se periòdicament per aprendre nous patrons quan hi ha dades noves ingerides.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="9dc8a-197">En aquest exemple, seleccioneu **Mensual**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="9dc8a-198">Un cop revisats tots els detalls, seleccioneu **Desa i executa**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="9dc8a-199">Tasca 4 - Revisar els resultats i les explicacions del model</span><span class="sxs-lookup"><span data-stu-id="9dc8a-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="9dc8a-200">Deixeu que el model completi la formació i la puntuació de les dades.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="9dc8a-201">Ara ja podeu revisar les explicacions del model de recomanació de productes.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="9dc8a-202">Per obtenir més informació, vegeu [Revisar un estat de predicció i els resultats](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="9dc8a-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="9dc8a-203">Tasca 5: crear un segment de productes molt adquirits</span><span class="sxs-lookup"><span data-stu-id="9dc8a-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="9dc8a-204">En executar el model de producció, es crea una entitat nova, que podreu veure a **Dades** > **Entitats**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="9dc8a-205">Podeu crear un segment nou a partir de l'entitat creada pel model.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="9dc8a-206">Aneu a **Segments**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-206">Go to **Segments**.</span></span> <span data-ttu-id="9dc8a-207">Seleccioneu **Nou** i trieu **Crea a partir de** > **Intel·ligència**.</span><span class="sxs-lookup"><span data-stu-id="9dc8a-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Creació d'un segment amb la sortida del model.](media/segment-intelligence.png)

1. <span data-ttu-id="9dc8a-209">Seleccioneu l'extrem **OOBProductRecommendationModelPrediction** i definiu el segment:</span><span class="sxs-lookup"><span data-stu-id="9dc8a-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="9dc8a-210">Camp: ProductID</span><span class="sxs-lookup"><span data-stu-id="9dc8a-210">Field: ProductID</span></span>
   - <span data-ttu-id="9dc8a-211">Operador: Valor</span><span class="sxs-lookup"><span data-stu-id="9dc8a-211">Operator: Value</span></span>
   - <span data-ttu-id="9dc8a-212">Valor: seleccioneu els tres ID de producte principals</span><span class="sxs-lookup"><span data-stu-id="9dc8a-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Creeu un segment a partir dels resultats del model.":::

<span data-ttu-id="9dc8a-214">Ara teniu un segment que s'actualitza dinàmicament i que identifica els clients que estan més disposats a comprar els tres productes més recomanats</span><span class="sxs-lookup"><span data-stu-id="9dc8a-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="9dc8a-215">Per a més informació, vegeu [Crear i administrar segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9dc8a-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]