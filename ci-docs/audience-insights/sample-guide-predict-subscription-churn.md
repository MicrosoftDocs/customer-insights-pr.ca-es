---
title: Guia d'exemples de predicció de rotació de subscripcions
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de rotació de subscripcions preparat per a l'ús.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653968"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="1f58e-103">Guia d'exemples de predicció de rotació de subscripcions (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="1f58e-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="1f58e-104">Se us guiarà per un exemple íntegre de predicció de rotació de subscripció mitjançant les dades d'exemple següents.</span><span class="sxs-lookup"><span data-stu-id="1f58e-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="1f58e-105">Escenari</span><span class="sxs-lookup"><span data-stu-id="1f58e-105">Scenario</span></span>

<span data-ttu-id="1f58e-106">Contoso és una empresa que produeix cafè i cafeteres d'alta qualitat, productes que ven a través del seu lloc web de Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="1f58e-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="1f58e-107">Fa poc, van iniciar un negoci de subscripció per als seus clients per rebre cafè de manera periòdica.</span><span class="sxs-lookup"><span data-stu-id="1f58e-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="1f58e-108">El seu objectiu és saber quins dels clients subscrits podrien cancel·lar la seva subscripció en els pròxims mesos.</span><span class="sxs-lookup"><span data-stu-id="1f58e-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="1f58e-109">Sabent quins dels seus clients és **probable que rotin**, pot ajudar l'empresa a estalviar estratègies i mesures de màrqueting centrades en mantenir-los.</span><span class="sxs-lookup"><span data-stu-id="1f58e-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f58e-110">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="1f58e-110">Prerequisites</span></span>

- <span data-ttu-id="1f58e-111">Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1f58e-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1f58e-112">Us recomanem que implementeu els passos següents [en un entorn nou](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="1f58e-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="1f58e-113">Tasca 1 - Ingerir dades</span><span class="sxs-lookup"><span data-stu-id="1f58e-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="1f58e-114">Reviseu els articles [sobre la ingestió de dades](data-sources.md) i, més concretament, [la importació de fonts de dades mitjançant els connectors del Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1f58e-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="1f58e-115">La informació següent suposa que ja esteu familiaritzat amb el concepte d'ingestió de dades en general.</span><span class="sxs-lookup"><span data-stu-id="1f58e-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="1f58e-116">Ingerir dades de clients procedents de la plataforma de comerç electrònic</span><span class="sxs-lookup"><span data-stu-id="1f58e-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="1f58e-117">Creeu una font de dades **eCommerce**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1f58e-118">Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="1f58e-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="1f58e-119">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1f58e-120">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="1f58e-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1f58e-121">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="1f58e-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1f58e-122">**CreatedOn**: data/hora/zona</span><span class="sxs-lookup"><span data-stu-id="1f58e-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="1f58e-123">![Transformar DoB en Data](media/ecommerce-dob-date.PNG "transformar la data de naixement en data")</span><span class="sxs-lookup"><span data-stu-id="1f58e-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="1f58e-124">Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="1f58e-125">Deseu la font de dades.</span><span class="sxs-lookup"><span data-stu-id="1f58e-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="1f58e-126">Ingerir dades de clients procedents de l'esquema de fidelització</span><span class="sxs-lookup"><span data-stu-id="1f58e-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="1f58e-127">Creeu una font de dades amb el nom **LoyaltyScheme**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1f58e-128">Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="1f58e-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="1f58e-129">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1f58e-130">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="1f58e-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1f58e-131">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="1f58e-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1f58e-132">**RewardsPoints**: nombre enter</span><span class="sxs-lookup"><span data-stu-id="1f58e-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="1f58e-133">**CreatedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="1f58e-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="1f58e-134">Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="1f58e-135">Deseu la font de dades.</span><span class="sxs-lookup"><span data-stu-id="1f58e-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="1f58e-136">Ingerir la informació de subscripció</span><span class="sxs-lookup"><span data-stu-id="1f58e-136">Ingest subscription information</span></span>

1. <span data-ttu-id="1f58e-137">Creeu una font de dades **SubscriptionHistory**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1f58e-138">Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="1f58e-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="1f58e-139">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1f58e-140">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="1f58e-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1f58e-141">**SubscriptioID**: nombre enter</span><span class="sxs-lookup"><span data-stu-id="1f58e-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="1f58e-142">**SubscriptionAmount**: moneda</span><span class="sxs-lookup"><span data-stu-id="1f58e-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="1f58e-143">**SubscriptionEndDate**: data/hora</span><span class="sxs-lookup"><span data-stu-id="1f58e-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="1f58e-144">**SubscriptionStartDate**: data/hora</span><span class="sxs-lookup"><span data-stu-id="1f58e-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="1f58e-145">**TransactionDate**: data/hora</span><span class="sxs-lookup"><span data-stu-id="1f58e-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="1f58e-146">**IsRecurring**: vertader/fals</span><span class="sxs-lookup"><span data-stu-id="1f58e-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="1f58e-147">**Is_auto_renew**: vertader/fals</span><span class="sxs-lookup"><span data-stu-id="1f58e-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="1f58e-148">**RecurringFrequencyInMonths**: nombre enter</span><span class="sxs-lookup"><span data-stu-id="1f58e-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="1f58e-149">Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="1f58e-150">Deseu la font de dades.</span><span class="sxs-lookup"><span data-stu-id="1f58e-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="1f58e-151">Ingerir dades de clients des de ressenyes de llocs web</span><span class="sxs-lookup"><span data-stu-id="1f58e-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="1f58e-152">Creeu una font de dades **Website**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1f58e-153">Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="1f58e-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="1f58e-154">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1f58e-155">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="1f58e-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1f58e-156">**ReviewRating**: nombre enter</span><span class="sxs-lookup"><span data-stu-id="1f58e-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="1f58e-157">**ReviewDate**: data</span><span class="sxs-lookup"><span data-stu-id="1f58e-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="1f58e-158">Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="1f58e-159">Tasca 2 - Unificació de les dades</span><span class="sxs-lookup"><span data-stu-id="1f58e-159">Task 2 - Data unification</span></span>

<span data-ttu-id="1f58e-160">Un cop feta la ingestió de les dades, començarem el procés d'**assignació, coincidència i combinació** per tal de crear un perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="1f58e-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="1f58e-161">Per obtenir més informació, vegeu [Unificació de les dades](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1f58e-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="1f58e-162">Assignació</span><span class="sxs-lookup"><span data-stu-id="1f58e-162">Map</span></span>

1. <span data-ttu-id="1f58e-163">Un cop ingerides les dades, assigneu contactes de les dades de comerç electrònic i fidelització a tipus de dades comuns.</span><span class="sxs-lookup"><span data-stu-id="1f58e-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="1f58e-164">Aneu a **Dades** > **Unifica** > **Assigna**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="1f58e-165">Seleccioneu les entitats que representen el perfil del client (**eCommerceContacts** i **loyCustomers**).</span><span class="sxs-lookup"><span data-stu-id="1f58e-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar les fonts de dades de comerç electrònic i de fidelització.":::

1. <span data-ttu-id="1f58e-167">Seleccioneu **ContactId** com a clau principal per a **eCommerceContacts** i **LoyaltyID** com a clau principal per a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifiqueu LoyaltyId com a clau principal.":::

### <a name="match"></a><span data-ttu-id="1f58e-169">Coincidència</span><span class="sxs-lookup"><span data-stu-id="1f58e-169">Match</span></span>

1. <span data-ttu-id="1f58e-170">Aneu a la pestanya **Coincidència** i seleccioneu **Definició d'ordre**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="1f58e-171">A la llista desplegable **Principal**, trieu **eCommerceContacts : eCommerce** com a font principal i incloeu-hi tots els registres.</span><span class="sxs-lookup"><span data-stu-id="1f58e-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="1f58e-172">A la llista desplegable **Entitat 2**, trieu **loyCustomers : LoyaltyScheme** i incloeu-hi tots els registres.</span><span class="sxs-lookup"><span data-stu-id="1f58e-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unifiqueu la coincidència de comerç electrònic i de fidelització.":::

1. <span data-ttu-id="1f58e-174">Seleccioneu **Crea una regla nova**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="1f58e-175">Afegiu la primera condició amb el FullName.</span><span class="sxs-lookup"><span data-stu-id="1f58e-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="1f58e-176">Per a eCommerceContacts, seleccioneu **FullName** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="1f58e-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1f58e-177">Per a loyCustomers, seleccioneu **FullName** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="1f58e-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1f58e-178">Seleccioneu la llista desplegable **Normalitza** i trieu el **Tipus (Telèfon, Nom, Adreça...)**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="1f58e-179">Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="1f58e-180">Introduïu el nom **Nom complet, correu electrònic** per a la regla nova.</span><span class="sxs-lookup"><span data-stu-id="1f58e-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="1f58e-181">Per afegir una segona condició per a l'adreça electrònica seleccioneu **Afegeix una condició**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="1f58e-182">Per a l'entitat eCommerceContacts, trieu **Correu electrònic** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="1f58e-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="1f58e-183">Per a l'entitat loyCustomers, trieu **Correu electrònic** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="1f58e-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="1f58e-184">Deixeu Normalitza en blanc.</span><span class="sxs-lookup"><span data-stu-id="1f58e-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="1f58e-185">Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unifiqueu la regla de coincidència per al nom i el correu electrònic.":::

7. <span data-ttu-id="1f58e-187">Seleccioneu **Desa** i **Executa**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="1f58e-188">Combinació</span><span class="sxs-lookup"><span data-stu-id="1f58e-188">Merge</span></span>

1. <span data-ttu-id="1f58e-189">Aneu a la pestanya **Combinació**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="1f58e-190">Al **ContactId** de l'entitat **loyCustomers**, canvieu el nom de visualització per **ContactIdLOYALTY** per diferenciar-lo dels altres identificadors ingerits.</span><span class="sxs-lookup"><span data-stu-id="1f58e-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="canvieu el nom de contactid de l'identificador de fidelització.":::

1. <span data-ttu-id="1f58e-192">Seleccioneu **Desa** i **Executa** per iniciar el procés de combinació.</span><span class="sxs-lookup"><span data-stu-id="1f58e-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="1f58e-193">Tasca 3 - Configurar la predicció de rotació de subscripcions</span><span class="sxs-lookup"><span data-stu-id="1f58e-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="1f58e-194">Amb els perfils de client unificats i a punt, ja podem executar la predicció de rotació de subscripcions.</span><span class="sxs-lookup"><span data-stu-id="1f58e-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="1f58e-195">Per veure'n els passos detallats, vegeu l'article [Predicció de rotació de subscripcions (versió preliminar)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="1f58e-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="1f58e-196">Aneu a **Intel·ligència** > **Detecta** i seleccioneu l'ús del **Model d'abandonament de clients**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="1f58e-197">Seleccioneu l'opció **Subscripció** i seleccioneu **Comença**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="1f58e-198">Anomeneu el model **Predicció de rotació de subscripcions OOB** i l'entitat de sortida **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="1f58e-199">Definiu dues condicions per al model de rotació:</span><span class="sxs-lookup"><span data-stu-id="1f58e-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="1f58e-200">**Dies des que va finalitzar la subscripció**: **com a mínim 60** dies.</span><span class="sxs-lookup"><span data-stu-id="1f58e-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="1f58e-201">Si un client no renova la subscripció durant aquest temps després d'haver finalitzat la subscripció, se'l considerarà rotació.</span><span class="sxs-lookup"><span data-stu-id="1f58e-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="1f58e-202">**Definició de la cancel·lació**: **com a mínim 93** dies.</span><span class="sxs-lookup"><span data-stu-id="1f58e-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="1f58e-203">La duració durant la qual el model predirà quins clients podrien rotar.</span><span class="sxs-lookup"><span data-stu-id="1f58e-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="1f58e-204">Com més enllà aneu en el futur, menys precisos seran els resultats.</span><span class="sxs-lookup"><span data-stu-id="1f58e-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="seleccioneu les opcions del model Finestra de predicció i Definició de la cancel·lació.":::

1. <span data-ttu-id="1f58e-206">Seleccioneu **Addició de les dades necessàries** i seleccioneu **Afegeix dades** per a l'historial de subscripcions.</span><span class="sxs-lookup"><span data-stu-id="1f58e-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="1f58e-207">Afegiu l'entitat **Subscription : SubscriptionHistory** i assigneu els camps del comerç electrònic als camps corresponents que requereix el model.</span><span class="sxs-lookup"><span data-stu-id="1f58e-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="1f58e-208">Uniu-vos a l'entitat **Subscription : SubscriptionHistory** amb **eCommerceContacts : eCommerce**, i anomeneu la relació **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Uniu entitats de comerç electrònic.":::

1. <span data-ttu-id="1f58e-210">A Activitats del client, afegiu l'entitat **webReviews : Website** i assigneu els camps de webReviews als camps corresponents que requereix el model.</span><span class="sxs-lookup"><span data-stu-id="1f58e-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="1f58e-211">Clau principal: ReviewId</span><span class="sxs-lookup"><span data-stu-id="1f58e-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="1f58e-212">Data i hora: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="1f58e-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="1f58e-213">Esdeveniment: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="1f58e-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="1f58e-214">Configureu una activitat per a ressenyes de llocs web.</span><span class="sxs-lookup"><span data-stu-id="1f58e-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="1f58e-215">Seleccioneu l'activitat **Opinió** i uniu l'entitat **webReviews : Website** amb **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="1f58e-216">Seleccioneu **Següent** per definir la planificació del model.</span><span class="sxs-lookup"><span data-stu-id="1f58e-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="1f58e-217">El model ha formar-se periòdicament per aprendre nous patrons quan hi ha dades noves ingerides.</span><span class="sxs-lookup"><span data-stu-id="1f58e-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="1f58e-218">En aquest exemple, seleccioneu **Mensual**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="1f58e-219">Un cop revisats tots els detalls, seleccioneu **Desa i executa**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="1f58e-220">Tasca 4 - Revisar els resultats i les explicacions del model</span><span class="sxs-lookup"><span data-stu-id="1f58e-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="1f58e-221">Deixeu que el model completi la formació i la puntuació de les dades.</span><span class="sxs-lookup"><span data-stu-id="1f58e-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="1f58e-222">Ara ja podeu revisar les explicacions del model de rotació de subscripcions.</span><span class="sxs-lookup"><span data-stu-id="1f58e-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="1f58e-223">Per obtenir més informació, vegeu [Revisar un estat de predicció i els resultats](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="1f58e-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="1f58e-224">Tasca 5 - Crear un segment de clients amb un alt risc de rotació</span><span class="sxs-lookup"><span data-stu-id="1f58e-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="1f58e-225">En executar el model de producció, es crea una entitat nova, que podreu veure a **Dades** > **Entitats**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="1f58e-226">Podeu crear un segment nou a partir de l'entitat creada pel model.</span><span class="sxs-lookup"><span data-stu-id="1f58e-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="1f58e-227">Aneu a **Segments**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-227">Go to **Segments**.</span></span> <span data-ttu-id="1f58e-228">Seleccioneu **Nou** i trieu **Crea a partir de** > **Intel·ligència**.</span><span class="sxs-lookup"><span data-stu-id="1f58e-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creació d'un segment amb la sortida del model.":::

1. <span data-ttu-id="1f58e-230">Seleccioneu l'extrem **OOBSubscriptionChurnPrediction** i definiu el segment:</span><span class="sxs-lookup"><span data-stu-id="1f58e-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="1f58e-231">Camp: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="1f58e-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="1f58e-232">Operador: major que</span><span class="sxs-lookup"><span data-stu-id="1f58e-232">Operator: greater than</span></span>
   - <span data-ttu-id="1f58e-233">Valor: 0,6</span><span class="sxs-lookup"><span data-stu-id="1f58e-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurar el segment de rotació de la subscripció.":::

<span data-ttu-id="1f58e-235">Ja teniu un segment que s'actualitza dinàmicament i que identifica els clients amb un alt risc de rotació per a aquest negoci de subscripció.</span><span class="sxs-lookup"><span data-stu-id="1f58e-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="1f58e-236">Per a més informació, vegeu [Crear i administrar segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1f58e-236">For more information, see [Create and manage segments](segments.md).</span></span>
