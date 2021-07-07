---
title: Guia de mostra per a les prediccions de valor de vida dels clients
description: Utilitzeu aquesta guia d'exemple per provar el model de predicció del valor de vida dels clients.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306337"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="b9ca6-103">Guia de mostra per a les prediccions de valor de vida dels clients (CLV)</span><span class="sxs-lookup"><span data-stu-id="b9ca6-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="b9ca6-104">Aquesta guia us explicarà un exemple final de la predicció del valor de vida dels clients (CLV) al Customer Insights mitjançant dades d'exemple.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="b9ca6-105">Escenari</span><span class="sxs-lookup"><span data-stu-id="b9ca6-105">Scenario</span></span>

<span data-ttu-id="b9ca6-106">Contoso és una empresa que produeix cafè i cafeteres d'alta qualitat.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="b9ca6-107">Ven els productes mitjançant el seu lloc web de Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="b9ca6-108">L'empresa vol comprendre el valor (ingressos) que poden generar els seus clients en els propers 12 mesos.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="b9ca6-109">Conèixer el valor esperat dels seus clients durant els propers 12 mesos els ajudarà a dirigir els seus esforços de màrqueting cap als clients d'alt valor.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b9ca6-110">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="b9ca6-110">Prerequisites</span></span>

- <span data-ttu-id="b9ca6-111">Almenys [permisos de contribuïdor](permissions.md) als coneixements del públic.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="b9ca6-112">Us recomanem que implementeu els passos següents [en un entorn nou](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="b9ca6-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="b9ca6-113">Tasca 1 - Ingerir dades</span><span class="sxs-lookup"><span data-stu-id="b9ca6-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="b9ca6-114">Reviseu els articles [sobre la ingestió de dades](data-sources.md) i la [importació de fonts de dades mitjançant els connectors del Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b9ca6-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="b9ca6-115">La informació següent suposa que ja esteu familiaritzat amb el concepte d'ingestió de dades en general.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="b9ca6-116">Ingerir dades de clients procedents de la plataforma de comerç electrònic</span><span class="sxs-lookup"><span data-stu-id="b9ca6-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="b9ca6-117">Creeu una font de dades anomenada **eCommerce**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b9ca6-118">Introduïu l'adreça URL dels contactes d'eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="b9ca6-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="b9ca6-119">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b9ca6-120">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="b9ca6-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b9ca6-121">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="b9ca6-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="b9ca6-122">**CreatedOn**: data/hora/zona</span><span class="sxs-lookup"><span data-stu-id="b9ca6-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeu la data de naixement en data.":::

1. <span data-ttu-id="b9ca6-124">Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="b9ca6-125">**Deseu** la font de dades.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="b9ca6-126">Ingerir dades de compres en línia</span><span class="sxs-lookup"><span data-stu-id="b9ca6-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="b9ca6-127">Afegiu un altre conjunt de dades a la mateixa font de dades **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="b9ca6-128">Torneu a triar el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="b9ca6-129">Introduïu l'adreça URL de les dades de **Compres en línia** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="b9ca6-130">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b9ca6-131">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="b9ca6-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b9ca6-132">**PurchasedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="b9ca6-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="b9ca6-133">**TotalPrice**: moneda</span><span class="sxs-lookup"><span data-stu-id="b9ca6-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="b9ca6-134">Al camp **Nom** de la subfinestra lateral, canvieu el nom de la font de dades **Query** per **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="b9ca6-135">**Deseu** la font de dades.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="b9ca6-136">Ingerir dades de clients procedents de l'esquema de fidelització</span><span class="sxs-lookup"><span data-stu-id="b9ca6-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="b9ca6-137">Creeu una font de dades amb el nom **LoyaltyScheme**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b9ca6-138">Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="b9ca6-139">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b9ca6-140">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="b9ca6-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b9ca6-141">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="b9ca6-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="b9ca6-142">**RewardsPoints**: nombre enter</span><span class="sxs-lookup"><span data-stu-id="b9ca6-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="b9ca6-143">**CreatedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="b9ca6-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="b9ca6-144">Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="b9ca6-145">**Deseu** la font de dades.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="b9ca6-146">Ingerir dades de clients des de ressenyes de llocs web</span><span class="sxs-lookup"><span data-stu-id="b9ca6-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="b9ca6-147">Creeu una font de dades **Website**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b9ca6-148">Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="b9ca6-149">Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b9ca6-150">Actualitzeu el tipus de dades de les columnes següents:</span><span class="sxs-lookup"><span data-stu-id="b9ca6-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="b9ca6-151">**ReviewRating**: nombre decimal</span><span class="sxs-lookup"><span data-stu-id="b9ca6-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="b9ca6-152">**ReviewDate**: data</span><span class="sxs-lookup"><span data-stu-id="b9ca6-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="b9ca6-153">Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades de **Consulta** a **Comentaris**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="b9ca6-154">**Deseu** la font de dades.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="b9ca6-155">Tasca 2 - Unificació de les dades</span><span class="sxs-lookup"><span data-stu-id="b9ca6-155">Task 2 - Data unification</span></span>

<span data-ttu-id="b9ca6-156">Després d'ingerir les dades, comencem el procés d'unificació de dades per crear un perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="b9ca6-157">Per obtenir més informació, vegeu [Unificació de les dades](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="b9ca6-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="b9ca6-158">Assignació</span><span class="sxs-lookup"><span data-stu-id="b9ca6-158">Map</span></span>

1. <span data-ttu-id="b9ca6-159">Un cop ingerides les dades, assigneu contactes de les dades de comerç electrònic i fidelització a tipus de dades comuns.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="b9ca6-160">Aneu a **Dades** > **Unifica** > **Assigna**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="b9ca6-161">Seleccioneu les entitats que representen el perfil del client (**eCommerceContacts** i **loyCustomers**).</span><span class="sxs-lookup"><span data-stu-id="b9ca6-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="b9ca6-162">A continuació, seleccioneu **Aplica**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-162">Then, select **Apply**.</span></span>

   ![unificar les fonts de dades de comerç electrònic i de fidelització.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="b9ca6-164">Seleccioneu **ContactId** com a clau principal per a **eCommerceContacts** i **LoyaltyID** com a clau principal per a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unifiqueu LoyaltyId com a clau principal.](media/unify-loyaltyid.png)

1. <span data-ttu-id="b9ca6-166">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="b9ca6-167">Coincidència</span><span class="sxs-lookup"><span data-stu-id="b9ca6-167">Match</span></span>

1. <span data-ttu-id="b9ca6-168">Aneu a la pestanya **Coincidència** i seleccioneu **Definició d'ordre**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="b9ca6-169">A la llista desplegable **Principal**, trieu **eCommerceContacts: eCommerce** com a font principal i incloeu tots els registres.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="b9ca6-170">A la llista desplegable **Entitat 2**, trieu **loyCustomers: LoyaltyScheme** i incloeu tots els registres.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unifiqueu la coincidència de comerç electrònic i de fidelització.](media/unify-match-order.png)

1. <span data-ttu-id="b9ca6-172">Seleccioneu **Afegeix una regla**</span><span class="sxs-lookup"><span data-stu-id="b9ca6-172">Select **Add rule**</span></span>

1. <span data-ttu-id="b9ca6-173">Afegiu la primera condició amb el FullName.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="b9ca6-174">Per a eCommerceContacts seleccioneu **FullName** al desplegable.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="b9ca6-175">Per a loyCustomers seleccioneu **FullName** al desplegable.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="b9ca6-176">Seleccioneu el desplegable **Normalització** i trieu **Tipus (Telèfon, Nom, Adreça, ...)**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="b9ca6-177">Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="b9ca6-178">Introduïu el nom **Nom complet, correu electrònic** per a la regla nova.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="b9ca6-179">Per afegir una segona condició per a l'adreça electrònica seleccioneu **Afegeix una condició**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="b9ca6-180">Per a l'entitat eCommerceContacts, trieu **EMail** al desplegable.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="b9ca6-181">Per a l'entitat loyCustomers, trieu **EMail** al desplegable.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="b9ca6-182">Deixeu Normalitza en blanc.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="b9ca6-183">Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unifiqueu la regla de coincidència per al nom i el correu electrònic.](media/unify-match-rule.png)

1. <span data-ttu-id="b9ca6-185">Seleccioneu **Fet**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-185">Select **Done**.</span></span>

1. <span data-ttu-id="b9ca6-186">Seleccioneu **Desa** i **Executa**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="b9ca6-187">Combinació</span><span class="sxs-lookup"><span data-stu-id="b9ca6-187">Merge</span></span>

1. <span data-ttu-id="b9ca6-188">Aneu a la pestanya **Combinació**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="b9ca6-189">Al **ContactId** de l'entitat **loyCustomers**, canvieu el nom de visualització per **ContactIdLOYALTY** per diferenciar-lo dels altres identificadors ingerits.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![canvieu el nom de contactid de l'identificador de fidelització.](media/unify-merge-contactid.png)

1. <span data-ttu-id="b9ca6-191">Seleccioneu **Desa** i **Executa la combinació i els processos descendents**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="b9ca6-192">Tasca 3: configurar la predicció del valor de vida dels clients</span><span class="sxs-lookup"><span data-stu-id="b9ca6-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="b9ca6-193">Amb els perfils de client unificats al seu lloc, ara podem executar la predicció del valor de vida dels clients.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="b9ca6-194">Per veure els passos detallats, vegeu [Predicció del valor de vida del client (versió preliminar)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="b9ca6-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="b9ca6-195">Aneu a **Intel·ligència**  > **Prediccions** i seleccioneu el **Model de valor de vida dels clients**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="b9ca6-196">Passeu per la informació de la subfinestra lateral i seleccioneu **Comença**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="b9ca6-197">Poseu un nom al model **Predicció del CLV a OOB eCommerce** i a l'entitat de sortida **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="b9ca6-198">Definiu les preferències del model per al model CLV:</span><span class="sxs-lookup"><span data-stu-id="b9ca6-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="b9ca6-199">**Període de temps de la predicció**: **12 mesos o 1 any**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="b9ca6-200">Aquesta configuració defineix fins a quin punt del futur cal preveure el valor de vida dels clients.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="b9ca6-201">**Clients actius**: especifiqueu què signifiquen els clients actius per a la vostra empresa.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="b9ca6-202">Definiu el període de temps històric en què un client ha d'haver tingut com a mínim una transacció per considerar-lo actiu.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="b9ca6-203">El model només predirà el CLV per als clients actius.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="b9ca6-204">Trieu entre permetre que el model calculi el període de temps segons les dades de transaccions històriques o proporcioneu un període de temps específic.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="b9ca6-205">En aquesta guia d'exemple, **fem que el model calculi l'interval de compra**, que és l'opció per defecte.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="b9ca6-206">**Clients d'alt valor**: definiu els clients d'alt valor com a percentil de clients que més paguen.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="b9ca6-207">El model utilitza aquesta entrada per proporcionar resultats que s'ajustin a la definició empresarial de clients d'alt valor.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="b9ca6-208">Podeu triar que el model defineixi els clients d'alt valor.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="b9ca6-209">Utilitza una regla heurística que deriva el percentil.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="b9ca6-210">També podeu definir els clients d'alt valor com a percentil de clients que més pagaran.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="b9ca6-211">En aquesta guia d'exemple, definim manualment els clients d'alt valor com el **30% superior dels clients actius que paguen** i seleccionem **Següent**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Pas de preferències de l'experiència guiada per al model del CLV.":::

1. <span data-ttu-id="b9ca6-213">Al pas **Dades necessàries**, seleccioneu **Afegeix dades** per proporcionar les dades de l'historial de transaccions.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="b9ca6-214">Afegiu l'entitat **eCommercePurchases: eCommerce** i assigneu els atributs que necessita el model:</span><span class="sxs-lookup"><span data-stu-id="b9ca6-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="b9ca6-215">Identificador de transacció: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="b9ca6-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="b9ca6-216">Data de transacció: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="b9ca6-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="b9ca6-217">Import de les transaccions: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="b9ca6-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="b9ca6-218">ID del producte: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="b9ca6-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="b9ca6-219">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-219">Select **Next**.</span></span>

1. <span data-ttu-id="b9ca6-220">Establiu la relació entre l'entitat **eCommercePurchases: eCommerce** i **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="b9ca6-221">El pas **Dades addicionals (opcional)** us permet afegir més dades d'activitats dels clients.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="b9ca6-222">Aquestes dades poden ajudar a obtenir més informació sobre les interaccions dels clients amb el vostre negoci, la qual cosa pot contribuir al CLV.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="b9ca6-223">Afegir interaccions clau dels clients, com ara registres web, registres del servei d'atenció al client o l'historial del programa de recompenses pot millorar la precisió de les previsions.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="b9ca6-224">Seleccioneu **Afegeix dades** per incloure més dades d'activitat dels clients.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="b9ca6-225">Afegiu l'entitat de l'activitat dels clients i assigneu els noms dels camps als camps corresponents que necessita el model:</span><span class="sxs-lookup"><span data-stu-id="b9ca6-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="b9ca6-226">Entitat d'activitat dels clients: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="b9ca6-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="b9ca6-227">Clau principal: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="b9ca6-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="b9ca6-228">Marca de temps: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="b9ca6-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="b9ca6-229">Incidència (nom de l'activitat): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="b9ca6-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="b9ca6-230">Detalls (import o valor): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="b9ca6-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="b9ca6-231">Seleccioneu **Següent** i configureu l'activitat i la relació entre les dades de transacció i les dades del client:</span><span class="sxs-lookup"><span data-stu-id="b9ca6-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="b9ca6-232">Tipus d'activitat: trieu-ne una d'existent</span><span class="sxs-lookup"><span data-stu-id="b9ca6-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="b9ca6-233">Etiqueta de l'activitat: Review</span><span class="sxs-lookup"><span data-stu-id="b9ca6-233">Activity label: Review</span></span>
   - <span data-ttu-id="b9ca6-234">Etiqueta corresponent: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="b9ca6-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="b9ca6-235">Entitat de client: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="b9ca6-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="b9ca6-236">Relació: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="b9ca6-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="b9ca6-237">Seleccioneu **Següent** per definir la planificació del model.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="b9ca6-238">El model ha d'entrenar-se periòdicament per aprendre nous patrons quan s'ingesten dades noves.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="b9ca6-239">En aquest exemple, trieu **Mensual**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="b9ca6-240">Un cop revisats tots els detalls, seleccioneu **Desa i executa**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="b9ca6-241">Tasca 4 - Revisar els resultats i les explicacions del model</span><span class="sxs-lookup"><span data-stu-id="b9ca6-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="b9ca6-242">Deixeu que el model completi la formació i la puntuació de les dades.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="b9ca6-243">A continuació, podeu revisar els resultats i les explicacions del model del CLV.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="b9ca6-244">Per obtenir més informació, vegeu [Revisar un estat de predicció i els resultats](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="b9ca6-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="b9ca6-245">Tasca 5: crear un segment de clients d'alt valor</span><span class="sxs-lookup"><span data-stu-id="b9ca6-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="b9ca6-246">L'execució del model crea una entitat nova que es mostra a **Dades** > **Entitats**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="b9ca6-247">Podeu crear un segment de client nou basat en l'entitat creada pel model.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="b9ca6-248">Aneu a **Segments**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="b9ca6-249">Seleccioneu **Nou** i trieu **Crea a partir de** > **Intel·ligència**.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Creació d'un segment amb la sortida del model.](media/segment-intelligence.png)

1. <span data-ttu-id="b9ca6-251">Seleccioneu l'entitat **OOBeCommerceCLVPrediction** i definiu el segment:</span><span class="sxs-lookup"><span data-stu-id="b9ca6-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="b9ca6-252">Camp: CLVScore</span><span class="sxs-lookup"><span data-stu-id="b9ca6-252">Field: CLVScore</span></span>
  - <span data-ttu-id="b9ca6-253">Operador: major que</span><span class="sxs-lookup"><span data-stu-id="b9ca6-253">Operator: greater than</span></span>
  - <span data-ttu-id="b9ca6-254">Valor: 1500</span><span class="sxs-lookup"><span data-stu-id="b9ca6-254">Value: 1500</span></span>

1. <span data-ttu-id="b9ca6-255">Seleccioneu **Revisa** i **Deseu** el segment.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="b9ca6-256">Ara teniu un segment que identifica els clients que es preveu que generin més de 1500 USD d'ingressos en els propers 12 mesos.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="b9ca6-257">Aquest segment s'actualitza dinàmicament si s'ingesten més dades.</span><span class="sxs-lookup"><span data-stu-id="b9ca6-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="b9ca6-258">Per a més informació, vegeu [Crear i administrar segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b9ca6-258">For more information, see [Create and manage segments](segments.md).</span></span>
