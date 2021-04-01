---
title: Guia d'exemples de predicció de rotació de transaccions
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de rotació de transaccions preparat per a l'ús.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 251bc26246cee16952e8e4cb08e2ed7aa4d18488
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595414"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="c3b73-103">Guia d'exemples de predicció de rotació de transaccions (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="c3b73-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="c3b73-104">En aquesta guia, se us guiarà per un exemple íntegre de predicció de rotació de transaccions al Customer Insights mitjançant les dades següents.</span><span class="sxs-lookup"><span data-stu-id="c3b73-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="c3b73-105">Les dades utilitzades en aquesta guia no són dades de clients reals i formen part del conjunt de dades de Contoso que es troba a l'entorn *Demo* de la vostra subscripció al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c3b73-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="c3b73-106">Escenari</span><span class="sxs-lookup"><span data-stu-id="c3b73-106">Scenario</span></span>

<span data-ttu-id="c3b73-107">Contoso és una empresa que produeix cafè i cafeteres d'alta qualitat, productes que ven a través del seu lloc web de Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="c3b73-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="c3b73-108">El seu objectiu és saber quins clients que acostumen a comprar els seus productes de manera periòdica deixaran de ser clients actius en els propers 60 dies.</span><span class="sxs-lookup"><span data-stu-id="c3b73-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="c3b73-109">Sabent quins dels seus clients és **probable que rotin**, pot ajudar l'empresa a estalviar estratègies i mesures de màrqueting centrades en mantenir-los.</span><span class="sxs-lookup"><span data-stu-id="c3b73-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c3b73-110">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="c3b73-110">Prerequisites</span></span>

- <span data-ttu-id="c3b73-111">Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c3b73-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="c3b73-112">Us recomanem que implementeu els passos següents [en un entorn nou](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="c3b73-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="c3b73-113">Tasca 1 - Ingerir dades</span><span class="sxs-lookup"><span data-stu-id="c3b73-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="c3b73-114">Reviseu els articles [sobre la ingestió de dades](data-sources.md) i, més concretament, [la importació de fonts de dades mitjançant els connectors del Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c3b73-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="c3b73-115">La informació següent suposa que ja esteu familiaritzat amb el concepte d'ingestió de dades en general.</span><span class="sxs-lookup"><span data-stu-id="c3b73-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="c3b73-116">Ingerir dades de clients procedents de la plataforma de comerç electrònic</span><span class="sxs-lookup"><span data-stu-id="c3b73-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="c3b73-117">Creeu una font de dades **eCommerce**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c3b73-118">Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="c3b73-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="c3b73-119">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c3b73-120">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="c3b73-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c3b73-121">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="c3b73-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c3b73-122">**CreatedOn**: data/hora/zona</span><span class="sxs-lookup"><span data-stu-id="c3b73-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="c3b73-123">![Transformar DoB en Data](media/ecommerce-dob-date.PNG "transformar la data de naixement en data")</span><span class="sxs-lookup"><span data-stu-id="c3b73-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="c3b73-124">Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="c3b73-125">Deseu la font de dades.</span><span class="sxs-lookup"><span data-stu-id="c3b73-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="c3b73-126">Ingerir dades de compres en línia</span><span class="sxs-lookup"><span data-stu-id="c3b73-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="c3b73-127">Afegiu un altre conjunt de dades a la mateixa font de dades **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="c3b73-128">Torneu a triar el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="c3b73-129">Introduïu l'adreça URL de les dades de **Compres en línia** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="c3b73-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="c3b73-130">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c3b73-131">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="c3b73-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c3b73-132">**PurchasedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="c3b73-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="c3b73-133">**TotalPrice**: moneda</span><span class="sxs-lookup"><span data-stu-id="c3b73-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="c3b73-134">Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="c3b73-135">Deseu la font de dades.</span><span class="sxs-lookup"><span data-stu-id="c3b73-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="c3b73-136">Ingerir dades de clients procedents de l'esquema de fidelització</span><span class="sxs-lookup"><span data-stu-id="c3b73-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="c3b73-137">Creeu una font de dades amb el nom **LoyaltyScheme**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c3b73-138">Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="c3b73-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="c3b73-139">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c3b73-140">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="c3b73-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c3b73-141">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="c3b73-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c3b73-142">**RewardsPoints**: nombre enter</span><span class="sxs-lookup"><span data-stu-id="c3b73-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="c3b73-143">**CreatedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="c3b73-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="c3b73-144">Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="c3b73-145">Deseu la font de dades.</span><span class="sxs-lookup"><span data-stu-id="c3b73-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="c3b73-146">Tasca 2 - Unificació de les dades</span><span class="sxs-lookup"><span data-stu-id="c3b73-146">Task 2 - Data unification</span></span>

<span data-ttu-id="c3b73-147">Un cop feta la ingestió de les dades, començarem el procés d'**assignació, coincidència i combinació** per tal de crear un perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="c3b73-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="c3b73-148">Per obtenir més informació, vegeu [Unificació de les dades](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c3b73-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="c3b73-149">Assignació</span><span class="sxs-lookup"><span data-stu-id="c3b73-149">Map</span></span>

1. <span data-ttu-id="c3b73-150">Un cop ingerides les dades, assigneu contactes de les dades de comerç electrònic i fidelització a tipus de dades comuns.</span><span class="sxs-lookup"><span data-stu-id="c3b73-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="c3b73-151">Aneu a **Dades** > **Unifica** > **Assigna**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="c3b73-152">Seleccioneu les entitats que representen el perfil del client (**eCommerceContacts** i **loyCustomers**).</span><span class="sxs-lookup"><span data-stu-id="c3b73-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar les fonts de dades de comerç electrònic i de fidelització.":::

1. <span data-ttu-id="c3b73-154">Seleccioneu **ContactId** com a clau principal per a **eCommerceContacts** i **LoyaltyID** com a clau principal per a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifiqueu LoyaltyId com a clau principal.":::

### <a name="match"></a><span data-ttu-id="c3b73-156">Coincidència</span><span class="sxs-lookup"><span data-stu-id="c3b73-156">Match</span></span>

1. <span data-ttu-id="c3b73-157">Aneu a la pestanya **Coincidència** i seleccioneu **Definició d'ordre**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="c3b73-158">A la llista desplegable **Principal**, trieu **eCommerceContacts : eCommerce** com a font principal i incloeu-hi tots els registres.</span><span class="sxs-lookup"><span data-stu-id="c3b73-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="c3b73-159">A la llista desplegable **Entitat 2**, trieu **loyCustomers : LoyaltyScheme** i incloeu-hi tots els registres.</span><span class="sxs-lookup"><span data-stu-id="c3b73-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unifiqueu la coincidència de comerç electrònic i de fidelització.":::

1. <span data-ttu-id="c3b73-161">Seleccioneu **Crea una regla nova**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="c3b73-162">Afegiu la primera condició amb el FullName.</span><span class="sxs-lookup"><span data-stu-id="c3b73-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="c3b73-163">Per a eCommerceContacts, seleccioneu **FullName** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="c3b73-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="c3b73-164">Per a loyCustomers, seleccioneu **FullName** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="c3b73-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="c3b73-165">Seleccioneu la llista desplegable **Normalitza** i trieu el **Tipus (Telèfon, Nom, Adreça...)**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="c3b73-166">Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="c3b73-167">Introduïu el nom **Nom complet, correu electrònic** per a la regla nova.</span><span class="sxs-lookup"><span data-stu-id="c3b73-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="c3b73-168">Per afegir una segona condició per a l'adreça electrònica seleccioneu **Afegeix una condició**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="c3b73-169">Per a l'entitat eCommerceContacts, trieu **Correu electrònic** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="c3b73-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="c3b73-170">Per a l'entitat loyCustomers, trieu **Correu electrònic** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="c3b73-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="c3b73-171">Deixeu Normalitza en blanc.</span><span class="sxs-lookup"><span data-stu-id="c3b73-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="c3b73-172">Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unifiqueu la regla de coincidència per al nom i el correu electrònic.":::

7. <span data-ttu-id="c3b73-174">Seleccioneu **Desa** i **Executa**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="c3b73-175">Combinació</span><span class="sxs-lookup"><span data-stu-id="c3b73-175">Merge</span></span>

1. <span data-ttu-id="c3b73-176">Aneu a la pestanya **Combinació**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="c3b73-177">Al **ContactId** de l'entitat **loyCustomers**, canvieu el nom de visualització per **ContactIdLOYALTY** per diferenciar-lo dels altres identificadors ingerits.</span><span class="sxs-lookup"><span data-stu-id="c3b73-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="canvieu el nom de contactid de l'identificador de fidelització.":::

1. <span data-ttu-id="c3b73-179">Seleccioneu **Desa** i **Executa** per iniciar el procés de combinació.</span><span class="sxs-lookup"><span data-stu-id="c3b73-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="c3b73-180">Tasca 3 - Configurar la predicció de rotació de transaccions</span><span class="sxs-lookup"><span data-stu-id="c3b73-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="c3b73-181">Amb els perfils de client unificats i a punt, ja podem executar la predicció de rotació de subscripcions.</span><span class="sxs-lookup"><span data-stu-id="c3b73-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="c3b73-182">Per veure'n els passos detallats, vegeu l'article [Predicció de rotació de subscripcions (versió preliminar)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="c3b73-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="c3b73-183">Aneu a **Intel·ligència** > **Detecta** i seleccioneu l'ús del **Model d'abandonament de clients**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="c3b73-184">Seleccioneu l'opció **Transaccional** i seleccioneu **Comença**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="c3b73-185">Anomeneu el model **Predicció de rotació de transaccions de comerç electrònic OOB** i l'entitat de sortida **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="c3b73-186">Definiu dues condicions per al model de rotació:</span><span class="sxs-lookup"><span data-stu-id="c3b73-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="c3b73-187">**Finestra de predicció**: **com a mínim 60** dies.</span><span class="sxs-lookup"><span data-stu-id="c3b73-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="c3b73-188">Amb aquesta configuració es defineix fins a quin punt en el futur volem predir la rotació de clients.</span><span class="sxs-lookup"><span data-stu-id="c3b73-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="c3b73-189">**Definició de la cancel·lació**: **com a mínim 60** dies.</span><span class="sxs-lookup"><span data-stu-id="c3b73-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="c3b73-190">La duració sense comprar al cap de la qual es considera que un client és rotació.</span><span class="sxs-lookup"><span data-stu-id="c3b73-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="seleccioneu les opcions del model Finestra de predicció i Definició de la cancel·lació.":::

1. <span data-ttu-id="c3b73-192">Seleccioneu **Historial de compres (obligatori)** i seleccioneu **Afegeix dades** per a l'historial de compres.</span><span class="sxs-lookup"><span data-stu-id="c3b73-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="c3b73-193">Afegiu l'entitat **eCommercePurchases : eCommerce** i assigneu els camps del comerç electrònic als camps corresponents que requereix el model.</span><span class="sxs-lookup"><span data-stu-id="c3b73-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="c3b73-194">Uniu l'entitat **eCommercePurchases : eCommerce** amb **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Uniu entitats de comerç electrònic.":::

1. <span data-ttu-id="c3b73-196">Seleccioneu **Següent** per definir la planificació del model.</span><span class="sxs-lookup"><span data-stu-id="c3b73-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="c3b73-197">El model ha formar-se periòdicament per aprendre nous patrons quan hi ha dades noves ingerides.</span><span class="sxs-lookup"><span data-stu-id="c3b73-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="c3b73-198">En aquest exemple, seleccioneu **Mensual**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="c3b73-199">Un cop revisats tots els detalls, seleccioneu **Desa i executa**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="c3b73-200">Tasca 4 - Revisar els resultats i les explicacions del model</span><span class="sxs-lookup"><span data-stu-id="c3b73-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="c3b73-201">Deixeu que el model completi la formació i la puntuació de les dades.</span><span class="sxs-lookup"><span data-stu-id="c3b73-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="c3b73-202">Ara ja podeu revisar les explicacions del model de rotació de subscripcions.</span><span class="sxs-lookup"><span data-stu-id="c3b73-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="c3b73-203">Per obtenir més informació, vegeu [Revisar un estat de predicció i els resultats](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="c3b73-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="c3b73-204">Tasca 5 - Crear un segment de clients amb un alt risc de rotació</span><span class="sxs-lookup"><span data-stu-id="c3b73-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="c3b73-205">En executar el model de producció, es crea una entitat nova, que podreu veure a **Dades** > **Entitats**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="c3b73-206">Podeu crear un segment nou a partir de l'entitat creada pel model.</span><span class="sxs-lookup"><span data-stu-id="c3b73-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="c3b73-207">Aneu a **Segments**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-207">Go to **Segments**.</span></span> <span data-ttu-id="c3b73-208">Seleccioneu **Nou** i trieu **Crea a partir de** > **Intel·ligència**.</span><span class="sxs-lookup"><span data-stu-id="c3b73-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creació d'un segment amb la sortida del model.":::

1. <span data-ttu-id="c3b73-210">Seleccioneu l'extrem **OOBSubscriptionChurnPrediction** i definiu el segment:</span><span class="sxs-lookup"><span data-stu-id="c3b73-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="c3b73-211">Camp: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="c3b73-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="c3b73-212">Operador: major que</span><span class="sxs-lookup"><span data-stu-id="c3b73-212">Operator: greater than</span></span>
   - <span data-ttu-id="c3b73-213">Valor: 0,6</span><span class="sxs-lookup"><span data-stu-id="c3b73-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurar el segment de rotació de la subscripció.":::

<span data-ttu-id="c3b73-215">Ja teniu un segment que s'actualitza dinàmicament i que identifica els clients amb un alt risc de rotació per a aquest negoci de subscripció.</span><span class="sxs-lookup"><span data-stu-id="c3b73-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="c3b73-216">Per a més informació, vegeu [Crear i administrar segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c3b73-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]