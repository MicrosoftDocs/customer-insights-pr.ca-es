---
title: Dades del Customer Insights al Microsoft Dataverse
description: Utilitzeu les entitats del Customer Insights com a taules al Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 7157ad930f3cea17c12bd4f95028d291483329d3
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259179"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a><span data-ttu-id="22556-103">Treballar amb dades del Customer Insights al Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="22556-103">Work with Customer Insights data in Microsoft Dataverse</span></span>

<span data-ttu-id="22556-104">El Customer Insights ofereix l'opció de fer que les entitats de sortida estiguin disponibles al [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md).</span><span class="sxs-lookup"><span data-stu-id="22556-104">Customer Insights provides the option to make output entities available in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md).</span></span> <span data-ttu-id="22556-105">Aquesta integració permet l'ús compartit fàcil de dades i el desenvolupament personalitzat mitjançant un mètode de poc codi/sense codi.</span><span class="sxs-lookup"><span data-stu-id="22556-105">This integration enables easy data sharing and custom development through a low code / no code approach.</span></span> <span data-ttu-id="22556-106">Les entitats de sortida estaran disponibles com a taules al Dataverse.</span><span class="sxs-lookup"><span data-stu-id="22556-106">The output entities will be available as tables in Dataverse.</span></span> <span data-ttu-id="22556-107">Aquestes taules permeten escenaris com ara [fluxos de treball automatitzats mitjançant el Power Automate](/power-automate/getting-started), [aplicacions impulsades per models](/powerapps/maker/model-driven-apps/) i [aplicacions de llenç](/powerapps/maker/canvas-apps/) mitjançant el Power Apps.</span><span class="sxs-lookup"><span data-stu-id="22556-107">These tables enable scenarios like [automated workflows through Power Automate](/power-automate/getting-started), [model-driven apps](/powerapps/maker/model-driven-apps/) and [canvas apps](/powerapps/maker/canvas-apps/) through Power Apps.</span></span> <span data-ttu-id="22556-108">Podeu utilitzar les dades de qualsevol altra aplicació basada en taules del Dataverse.</span><span class="sxs-lookup"><span data-stu-id="22556-108">You can use the data for any other application that is based on Dataverse tables.</span></span> <span data-ttu-id="22556-109">La implementació actual admet principalment consultes on es poden obtenir dades de les entitats de coneixements del públic disponibles per a un identificador de client determinat.</span><span class="sxs-lookup"><span data-stu-id="22556-109">The current implementation mainly supports lookups where data from the available audience insights entities can be fetched for a given customer ID.</span></span>

## <a name="attach-a-dataverse-environment-to-customer-insights"></a><span data-ttu-id="22556-110">Adjuntar un entorn del Dataverse al Customer Insights</span><span class="sxs-lookup"><span data-stu-id="22556-110">Attach a Dataverse environment to Customer Insights</span></span>

<span data-ttu-id="22556-111">**Organitzacions amb entorns del Dataverse existents**</span><span class="sxs-lookup"><span data-stu-id="22556-111">**Organizations with existing Dataverse environments**</span></span>

<span data-ttu-id="22556-112">Les organitzacions que ja utilitzen el Dataverse poden [utilitzar un dels entorns del Dataverse existents](manage-environments.md#create-an-environment-in-an-existing-organization) quan un administrador configura conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="22556-112">Organizations that already use Dataverse can [use one of their existing Dataverse environments](manage-environments.md#create-an-environment-in-an-existing-organization) when an administrator sets up audience insights.</span></span> <span data-ttu-id="22556-113">En proporcionar l'adreça URL a l'entorn del Dataverse, s'adjunta a l'entorn nou de les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="22556-113">By providing the URL to the Dataverse environment, it's attaching to their new audience insights environment.</span></span> <span data-ttu-id="22556-114">Per garantir el millor rendiment possible, els entorns del Customer Insights i del Dataverse s'han d'allotjar a la mateixa regió.</span><span class="sxs-lookup"><span data-stu-id="22556-114">To ensure the best possible performance, Customer Insights and Dataverse environments must be hosted in the same region.</span></span>

<span data-ttu-id="22556-115">Per adjuntar un entorn del Dataverse, expandiu la **Configuració avançada** en crear l'entorn de les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="22556-115">To attach a Dataverse environment, expand the **Advanced settings** when creating the audience insights environment.</span></span> <span data-ttu-id="22556-116">Proporcioneu l'**adreça URL de l'entorn del Microsoft Dataverse** i activeu la casella de selecció per **Habilitar l'ús compartit de dades**.</span><span class="sxs-lookup"><span data-stu-id="22556-116">Provide the **Microsoft Dataverse environment URL** and select the checkbox to **Enable data sharing**.</span></span>

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt":::

<span data-ttu-id="22556-118">**Organització nova**</span><span class="sxs-lookup"><span data-stu-id="22556-118">**New organization**</span></span>

<span data-ttu-id="22556-119">Si creeu una organització nova en configurar el Customer Insights, obtindreu automàticament un entorn del Dataverse nou.</span><span class="sxs-lookup"><span data-stu-id="22556-119">If you create a new organization when setting up Customer Insights, you'll automatically get a new Dataverse environment.</span></span>

> [!NOTE]
> <span data-ttu-id="22556-120">Si les organitzacions ja utilitzen el Dataverse al seu inquilí, és important recordar que [la creació de l'entorn del Dataverse està controlada per un administrador](/power-platform/admin/control-environment-creation.md). Per exemple, si configureu un entorn nou de conclusions del públic amb el vostre compte de l'organització i l'administrador ha inhabilitat la creació d'entorns de prova del Dataverse per a tots els usuaris, tret dels administradors, no podreu crear cap entorn de prova nou.</span><span class="sxs-lookup"><span data-stu-id="22556-120">If your organizations already uses Dataverse in their tenant, it’s important to remember that [Dataverse environment creation is controlled by an admin](/power-platform/admin/control-environment-creation.md). For example, if a you're setting up a new audience insights environment with your organizational account and the admin has disabled the creation of Dataverse trial environments for everyone except admins, you can't create a new trial environment.</span></span>
> 
> <span data-ttu-id="22556-121">Els entorns de prova del Dataverse creats al Customer Insights tenen 3 GB d'emmagatzematge que no es compten per a la capacitat global de l'inquilí.</span><span class="sxs-lookup"><span data-stu-id="22556-121">The Dataverse trial environments created in Customer Insights have 3 GB of storage which won't count towards the overall capacity entitled to the tenant.</span></span> <span data-ttu-id="22556-122">Les subscripcions pagades tenen dret de 15 GB al Dataverse per a la base de dades i 20 GB per a l'emmagatzematge de fitxers.</span><span class="sxs-lookup"><span data-stu-id="22556-122">Paid subscriptions get Dataverse entitlement of 15 GB for database and 20 GB for file storage.</span></span>

## <a name="output-entities"></a><span data-ttu-id="22556-123">Entitats de sortida</span><span class="sxs-lookup"><span data-stu-id="22556-123">Output entities</span></span>

<span data-ttu-id="22556-124">Algunes entitats de sortida dels coneixements del públic estan disponibles com a taules al Dataverse.</span><span class="sxs-lookup"><span data-stu-id="22556-124">Some output entities from audience insights are available as tables in Dataverse.</span></span> <span data-ttu-id="22556-125">Les seccions següents descriuen l'esquema esperat d'aquestes taules.</span><span class="sxs-lookup"><span data-stu-id="22556-125">The sections below describe the expected schema of these tables.</span></span>

- [<span data-ttu-id="22556-126">CustomerProfile</span><span class="sxs-lookup"><span data-stu-id="22556-126">CustomerProfile</span></span>](#customerprofile)
- [<span data-ttu-id="22556-127">AlternateKey</span><span class="sxs-lookup"><span data-stu-id="22556-127">AlternateKey</span></span>](#alternatekey)
- [<span data-ttu-id="22556-128">UnifiedActivity</span><span class="sxs-lookup"><span data-stu-id="22556-128">UnifiedActivity</span></span>](#unifiedactivity)
- [<span data-ttu-id="22556-129">CustomerMeasure</span><span class="sxs-lookup"><span data-stu-id="22556-129">CustomerMeasure</span></span>](#customermeasure)
- [<span data-ttu-id="22556-130">Enriquiment</span><span class="sxs-lookup"><span data-stu-id="22556-130">Enrichment</span></span>](#enrichment)
- [<span data-ttu-id="22556-131">Predicció</span><span class="sxs-lookup"><span data-stu-id="22556-131">Prediction</span></span>](#prediction)


### <a name="customerprofile"></a><span data-ttu-id="22556-132">CustomerProfile</span><span class="sxs-lookup"><span data-stu-id="22556-132">CustomerProfile</span></span>

<span data-ttu-id="22556-133">Aquesta taula conté el perfil de client unificat del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="22556-133">This table contains the unified customer profile from Customer Insights.</span></span> <span data-ttu-id="22556-134">L'esquema d'un perfil de client unificat depèn de les entitats i els atributs utilitzats en el procés de combinació.</span><span class="sxs-lookup"><span data-stu-id="22556-134">The schema for a unified customer profile depends on the entities and attributes used in the merge process.</span></span> <span data-ttu-id="22556-135">Un esquema de perfil de client sol contenir un subconjunt dels atributs de la [definició del model de dades comú del CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).</span><span class="sxs-lookup"><span data-stu-id="22556-135">A customer profile schema usually contains a subset of the attributes from the [Common Data Model definition of CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).</span></span>

### <a name="alternatekey"></a><span data-ttu-id="22556-136">AlternateKey</span><span class="sxs-lookup"><span data-stu-id="22556-136">AlternateKey</span></span>

<span data-ttu-id="22556-137">La taula AlternativeKey conté les claus de les entitats que han participat en el procés d'unificació.</span><span class="sxs-lookup"><span data-stu-id="22556-137">The AlternateKey table contains keys of the entities, which participated in the unify process.</span></span>

|<span data-ttu-id="22556-138">Column</span><span class="sxs-lookup"><span data-stu-id="22556-138">Column</span></span>  |<span data-ttu-id="22556-139">Type</span><span class="sxs-lookup"><span data-stu-id="22556-139">Type</span></span>  |<span data-ttu-id="22556-140">Descripció</span><span class="sxs-lookup"><span data-stu-id="22556-140">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="22556-141">DataSourceName</span><span class="sxs-lookup"><span data-stu-id="22556-141">DataSourceName</span></span>    |<span data-ttu-id="22556-142">String</span><span class="sxs-lookup"><span data-stu-id="22556-142">String</span></span>         | <span data-ttu-id="22556-143">Nom de la font de dades.</span><span class="sxs-lookup"><span data-stu-id="22556-143">Name of the data source.</span></span> <span data-ttu-id="22556-144">Per exemple: `datasource5`</span><span class="sxs-lookup"><span data-stu-id="22556-144">For example: `datasource5`</span></span>        |
|<span data-ttu-id="22556-145">EntityName</span><span class="sxs-lookup"><span data-stu-id="22556-145">EntityName</span></span>        | <span data-ttu-id="22556-146">String</span><span class="sxs-lookup"><span data-stu-id="22556-146">String</span></span>        | <span data-ttu-id="22556-147">Nom de l'entitat als coneixements del públic.</span><span class="sxs-lookup"><span data-stu-id="22556-147">Name of the entity in audience insights.</span></span> <span data-ttu-id="22556-148">Per exemple: `contact1`</span><span class="sxs-lookup"><span data-stu-id="22556-148">For example: `contact1`</span></span>        |
|<span data-ttu-id="22556-149">AlternateValue</span><span class="sxs-lookup"><span data-stu-id="22556-149">AlternateValue</span></span>    |<span data-ttu-id="22556-150">String</span><span class="sxs-lookup"><span data-stu-id="22556-150">String</span></span>         |<span data-ttu-id="22556-151">Identificador alternatiu assignat a l'identificador de client.</span><span class="sxs-lookup"><span data-stu-id="22556-151">Alternative ID that is mapped to the customer ID.</span></span> <span data-ttu-id="22556-152">Exemple: `cntid_1078`</span><span class="sxs-lookup"><span data-stu-id="22556-152">Example: `cntid_1078`</span></span>         |
|<span data-ttu-id="22556-153">KeyRing</span><span class="sxs-lookup"><span data-stu-id="22556-153">KeyRing</span></span>           | <span data-ttu-id="22556-154">Text de diverses línies</span><span class="sxs-lookup"><span data-stu-id="22556-154">Multiline text</span></span>        | <span data-ttu-id="22556-155">Valor JSON</span><span class="sxs-lookup"><span data-stu-id="22556-155">JSON value</span></span>  </br> <span data-ttu-id="22556-156">Exemple: [{"dataSourceName":" datasource5 ",</span><span class="sxs-lookup"><span data-stu-id="22556-156">Sample: [{"dataSourceName":" datasource5 ",</span></span></br><span data-ttu-id="22556-157">"entityName":" contact1",</span><span class="sxs-lookup"><span data-stu-id="22556-157">"entityName":" contact1",</span></span></br><span data-ttu-id="22556-158">"preferredKey":" cntid_1078",</span><span class="sxs-lookup"><span data-stu-id="22556-158">"preferredKey":" cntid_1078",</span></span></br><span data-ttu-id="22556-159">"keys":[" cntid_1078"]}]</span><span class="sxs-lookup"><span data-stu-id="22556-159">"keys":[" cntid_1078"]}]</span></span>       |
|<span data-ttu-id="22556-160">CustomerId</span><span class="sxs-lookup"><span data-stu-id="22556-160">CustomerId</span></span>         | <span data-ttu-id="22556-161">String</span><span class="sxs-lookup"><span data-stu-id="22556-161">String</span></span>        | <span data-ttu-id="22556-162">Identificador del perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="22556-162">ID of the unified customer profile.</span></span>         |
|<span data-ttu-id="22556-163">AlternateKeyId</span><span class="sxs-lookup"><span data-stu-id="22556-163">AlternateKeyId</span></span>     | <span data-ttu-id="22556-164">GUID</span><span class="sxs-lookup"><span data-stu-id="22556-164">GUID</span></span>         |  <span data-ttu-id="22556-165">GUID determinista d'AlternateKey basat en msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="22556-165">AlternateKey deterministic GUID based on msdynci_identifier</span></span>       |
|<span data-ttu-id="22556-166">msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="22556-166">msdynci_identifier</span></span> |   <span data-ttu-id="22556-167">String</span><span class="sxs-lookup"><span data-stu-id="22556-167">String</span></span>      |   `DataSourceName|EntityName|AlternateValue`  </br> <span data-ttu-id="22556-168">Exemple: `testdatasource|contact1|cntid_1078`</span><span class="sxs-lookup"><span data-stu-id="22556-168">Sample: `testdatasource|contact1|cntid_1078`</span></span>    |

### <a name="unifiedactivity"></a><span data-ttu-id="22556-169">UnifiedActivity</span><span class="sxs-lookup"><span data-stu-id="22556-169">UnifiedActivity</span></span>

<span data-ttu-id="22556-170">Aquesta taula conté activitats dels usuaris que estan disponibles al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="22556-170">This table contains activities by users that are available in Customer Insights.</span></span>

| <span data-ttu-id="22556-171">Column</span><span class="sxs-lookup"><span data-stu-id="22556-171">Column</span></span>            | <span data-ttu-id="22556-172">Type</span><span class="sxs-lookup"><span data-stu-id="22556-172">Type</span></span>        | <span data-ttu-id="22556-173">Descripció</span><span class="sxs-lookup"><span data-stu-id="22556-173">Description</span></span>                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| <span data-ttu-id="22556-174">CustomerId</span><span class="sxs-lookup"><span data-stu-id="22556-174">CustomerId</span></span>        | <span data-ttu-id="22556-175">String</span><span class="sxs-lookup"><span data-stu-id="22556-175">String</span></span>      | <span data-ttu-id="22556-176">Identificador del perfil del client</span><span class="sxs-lookup"><span data-stu-id="22556-176">Customer Profile ID</span></span>                                                                      |
| <span data-ttu-id="22556-177">ActivityId</span><span class="sxs-lookup"><span data-stu-id="22556-177">ActivityId</span></span>        | <span data-ttu-id="22556-178">String</span><span class="sxs-lookup"><span data-stu-id="22556-178">String</span></span>      | <span data-ttu-id="22556-179">Identificador intern de l'activitat de client (clau principal)</span><span class="sxs-lookup"><span data-stu-id="22556-179">Internal ID of the customer activity (primary key)</span></span>                                       |
| <span data-ttu-id="22556-180">SourceEntityName</span><span class="sxs-lookup"><span data-stu-id="22556-180">SourceEntityName</span></span>  | <span data-ttu-id="22556-181">String</span><span class="sxs-lookup"><span data-stu-id="22556-181">String</span></span>      | <span data-ttu-id="22556-182">Nom de l'entitat d'origen</span><span class="sxs-lookup"><span data-stu-id="22556-182">Name of the source entity</span></span>                                                                |
| <span data-ttu-id="22556-183">SourceActivityId</span><span class="sxs-lookup"><span data-stu-id="22556-183">SourceActivityId</span></span>  | <span data-ttu-id="22556-184">String</span><span class="sxs-lookup"><span data-stu-id="22556-184">String</span></span>      | <span data-ttu-id="22556-185">Clau principal de l'entitat d'origen</span><span class="sxs-lookup"><span data-stu-id="22556-185">Primary key from the source entity</span></span>                                                       |
| <span data-ttu-id="22556-186">ActivityType</span><span class="sxs-lookup"><span data-stu-id="22556-186">ActivityType</span></span>      | <span data-ttu-id="22556-187">String</span><span class="sxs-lookup"><span data-stu-id="22556-187">String</span></span>      | <span data-ttu-id="22556-188">Tipus d'activitat administrada o nom de l'activitat personalitzada</span><span class="sxs-lookup"><span data-stu-id="22556-188">Semantic activity type or name of custom activity</span></span>                                        |
| <span data-ttu-id="22556-189">ActivityTimeStamp</span><span class="sxs-lookup"><span data-stu-id="22556-189">ActivityTimeStamp</span></span> | <span data-ttu-id="22556-190">DATETIME</span><span class="sxs-lookup"><span data-stu-id="22556-190">DATETIME</span></span>    | <span data-ttu-id="22556-191">Marca de temps de l'activitat</span><span class="sxs-lookup"><span data-stu-id="22556-191">Activity Time stamp</span></span>                                                                      |
| <span data-ttu-id="22556-192">Càrrec</span><span class="sxs-lookup"><span data-stu-id="22556-192">Title</span></span>             | <span data-ttu-id="22556-193">String</span><span class="sxs-lookup"><span data-stu-id="22556-193">String</span></span>      | <span data-ttu-id="22556-194">Títol o nom de l'activitat</span><span class="sxs-lookup"><span data-stu-id="22556-194">Title or name of the activity</span></span>                                                               |
| <span data-ttu-id="22556-195">Descripció</span><span class="sxs-lookup"><span data-stu-id="22556-195">Description</span></span>       | <span data-ttu-id="22556-196">String</span><span class="sxs-lookup"><span data-stu-id="22556-196">String</span></span>      | <span data-ttu-id="22556-197">Descripció d'activitat</span><span class="sxs-lookup"><span data-stu-id="22556-197">Activity description</span></span>                                                                     |
| <span data-ttu-id="22556-198">Adreça URL</span><span class="sxs-lookup"><span data-stu-id="22556-198">URL</span></span>               | <span data-ttu-id="22556-199">String</span><span class="sxs-lookup"><span data-stu-id="22556-199">String</span></span>      | <span data-ttu-id="22556-200">Enllaçar amb una adreça URL externa específica de l'activitat</span><span class="sxs-lookup"><span data-stu-id="22556-200">Link to an external URL specific to the activity</span></span>                                         |
| <span data-ttu-id="22556-201">SemanticData</span><span class="sxs-lookup"><span data-stu-id="22556-201">SemanticData</span></span>      | <span data-ttu-id="22556-202">Cadena JSON</span><span class="sxs-lookup"><span data-stu-id="22556-202">JSON String</span></span> | <span data-ttu-id="22556-203">Inclou una llista de parelles de valors clau per als camps d'assignació semàntica específics del tipus d'activitat</span><span class="sxs-lookup"><span data-stu-id="22556-203">Includes a list of key value pairs for semantic mapping fields specific to the type of activity</span></span> |
| <span data-ttu-id="22556-204">RangeIndex</span><span class="sxs-lookup"><span data-stu-id="22556-204">RangeIndex</span></span>        | <span data-ttu-id="22556-205">String</span><span class="sxs-lookup"><span data-stu-id="22556-205">String</span></span>      | <span data-ttu-id="22556-206">Marca de temps unix utilitzada per ordenar la cronologia de l'activitat i les consultes d'interval eficaces</span><span class="sxs-lookup"><span data-stu-id="22556-206">Unix timestamp used for sorting activity timeline and effective range queries</span></span> |
| <span data-ttu-id="22556-207">mydynci_unifiedactivityid</span><span class="sxs-lookup"><span data-stu-id="22556-207">mydynci_unifiedactivityid</span></span>   | <span data-ttu-id="22556-208">GUID</span><span class="sxs-lookup"><span data-stu-id="22556-208">GUID</span></span> | <span data-ttu-id="22556-209">Identificador intern de l'activitat de client (ActivityId)</span><span class="sxs-lookup"><span data-stu-id="22556-209">Internal ID of the customer activity (ActivityId)</span></span> |

### <a name="customermeasure"></a><span data-ttu-id="22556-210">CustomerMeasure</span><span class="sxs-lookup"><span data-stu-id="22556-210">CustomerMeasure</span></span>

<span data-ttu-id="22556-211">Aquesta taula conté les dades de sortida de les mesures basades en atributs del client.</span><span class="sxs-lookup"><span data-stu-id="22556-211">This table contains the output data of customer attribute-based measures.</span></span>

| <span data-ttu-id="22556-212">Column</span><span class="sxs-lookup"><span data-stu-id="22556-212">Column</span></span>             | <span data-ttu-id="22556-213">Type</span><span class="sxs-lookup"><span data-stu-id="22556-213">Type</span></span>             | <span data-ttu-id="22556-214">Descripció</span><span class="sxs-lookup"><span data-stu-id="22556-214">Description</span></span>                 |
|--------------------|------------------|-----------------------------|
| <span data-ttu-id="22556-215">CustomerId</span><span class="sxs-lookup"><span data-stu-id="22556-215">CustomerId</span></span>         | <span data-ttu-id="22556-216">String</span><span class="sxs-lookup"><span data-stu-id="22556-216">String</span></span>           | <span data-ttu-id="22556-217">Identificador del perfil del client</span><span class="sxs-lookup"><span data-stu-id="22556-217">Customer profile ID</span></span>        |
| <span data-ttu-id="22556-218">Mesures</span><span class="sxs-lookup"><span data-stu-id="22556-218">Measures</span></span>           | <span data-ttu-id="22556-219">Cadena JSON</span><span class="sxs-lookup"><span data-stu-id="22556-219">JSON String</span></span>      | <span data-ttu-id="22556-220">Inclou una llista de parelles de valors clau per al nom de mesura i els valors del client determinat</span><span class="sxs-lookup"><span data-stu-id="22556-220">Includes a list of key value pairs for measure name and values for the given customer</span></span> | 
| <span data-ttu-id="22556-221">msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="22556-221">msdynci_identifier</span></span> | <span data-ttu-id="22556-222">String</span><span class="sxs-lookup"><span data-stu-id="22556-222">String</span></span>           | `Customer_Measure|CustomerId` |
| <span data-ttu-id="22556-223">msdynci_customermeasureid</span><span class="sxs-lookup"><span data-stu-id="22556-223">msdynci_customermeasureid</span></span> | <span data-ttu-id="22556-224">GUID</span><span class="sxs-lookup"><span data-stu-id="22556-224">GUID</span></span>      | <span data-ttu-id="22556-225">Identificador del perfil del client</span><span class="sxs-lookup"><span data-stu-id="22556-225">Customer profile ID</span></span> |


### <a name="enrichment"></a><span data-ttu-id="22556-226">Enriquiment</span><span class="sxs-lookup"><span data-stu-id="22556-226">Enrichment</span></span>

<span data-ttu-id="22556-227">Aquesta taula conté la sortida del procés d'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="22556-227">This table contains the output of the enrichment process.</span></span>

| <span data-ttu-id="22556-228">Column</span><span class="sxs-lookup"><span data-stu-id="22556-228">Column</span></span>               | <span data-ttu-id="22556-229">Type</span><span class="sxs-lookup"><span data-stu-id="22556-229">Type</span></span>             |  <span data-ttu-id="22556-230">Descripció</span><span class="sxs-lookup"><span data-stu-id="22556-230">Description</span></span>                                          |
|----------------------|------------------|------------------------------------------------------|
| <span data-ttu-id="22556-231">CustomerId</span><span class="sxs-lookup"><span data-stu-id="22556-231">CustomerId</span></span>           | <span data-ttu-id="22556-232">String</span><span class="sxs-lookup"><span data-stu-id="22556-232">String</span></span>           | <span data-ttu-id="22556-233">Identificador del perfil del client</span><span class="sxs-lookup"><span data-stu-id="22556-233">Customer profile ID</span></span>                                 |
| <span data-ttu-id="22556-234">EnrichmentProvider</span><span class="sxs-lookup"><span data-stu-id="22556-234">EnrichmentProvider</span></span>   | <span data-ttu-id="22556-235">String</span><span class="sxs-lookup"><span data-stu-id="22556-235">String</span></span>           | <span data-ttu-id="22556-236">Nom del proveïdor de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="22556-236">Name of the provider for the enrichment</span></span>                                  |
| <span data-ttu-id="22556-237">EnrichmentType</span><span class="sxs-lookup"><span data-stu-id="22556-237">EnrichmentType</span></span>       | <span data-ttu-id="22556-238">String</span><span class="sxs-lookup"><span data-stu-id="22556-238">String</span></span>           | <span data-ttu-id="22556-239">Tipus d'enriquiment</span><span class="sxs-lookup"><span data-stu-id="22556-239">Type of enrichment</span></span>                                      |
| <span data-ttu-id="22556-240">Valors</span><span class="sxs-lookup"><span data-stu-id="22556-240">Values</span></span>               | <span data-ttu-id="22556-241">Cadena JSON</span><span class="sxs-lookup"><span data-stu-id="22556-241">JSON String</span></span>      | <span data-ttu-id="22556-242">Llista d'atributs produïts pel procés d'enriquiment</span><span class="sxs-lookup"><span data-stu-id="22556-242">List of attributes produced by the enrichment process</span></span> |
| <span data-ttu-id="22556-243">msdynci_enrichmentid</span><span class="sxs-lookup"><span data-stu-id="22556-243">msdynci_enrichmentid</span></span> | <span data-ttu-id="22556-244">GUID</span><span class="sxs-lookup"><span data-stu-id="22556-244">GUID</span></span>             | <span data-ttu-id="22556-245">GUID determinista generat a partir de msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="22556-245">Deterministic GUID generated from msdynci_identifier</span></span> |
| <span data-ttu-id="22556-246">msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="22556-246">msdynci_identifier</span></span>   | <span data-ttu-id="22556-247">String</span><span class="sxs-lookup"><span data-stu-id="22556-247">String</span></span>           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a><span data-ttu-id="22556-248">Predicció</span><span class="sxs-lookup"><span data-stu-id="22556-248">Prediction</span></span>

<span data-ttu-id="22556-249">Aquesta taula conté la sortida de les prediccions de models.</span><span class="sxs-lookup"><span data-stu-id="22556-249">This table contains the output of the model predictions.</span></span>

| <span data-ttu-id="22556-250">Column</span><span class="sxs-lookup"><span data-stu-id="22556-250">Column</span></span>               | <span data-ttu-id="22556-251">Type</span><span class="sxs-lookup"><span data-stu-id="22556-251">Type</span></span>        | <span data-ttu-id="22556-252">Descripció</span><span class="sxs-lookup"><span data-stu-id="22556-252">Description</span></span>                                          |
|----------------------|-------------|------------------------------------------------------|
| <span data-ttu-id="22556-253">CustomerId</span><span class="sxs-lookup"><span data-stu-id="22556-253">CustomerId</span></span>           | <span data-ttu-id="22556-254">String</span><span class="sxs-lookup"><span data-stu-id="22556-254">String</span></span>      | <span data-ttu-id="22556-255">Identificador del perfil del client</span><span class="sxs-lookup"><span data-stu-id="22556-255">Customer Profile ID</span></span>                                  |
| <span data-ttu-id="22556-256">ModelProvider</span><span class="sxs-lookup"><span data-stu-id="22556-256">ModelProvider</span></span>        | <span data-ttu-id="22556-257">String</span><span class="sxs-lookup"><span data-stu-id="22556-257">String</span></span>      | <span data-ttu-id="22556-258">Nom del proveïdor del model</span><span class="sxs-lookup"><span data-stu-id="22556-258">Name of the provider of the model</span></span>                                      |
| <span data-ttu-id="22556-259">Model</span><span class="sxs-lookup"><span data-stu-id="22556-259">Model</span></span>                | <span data-ttu-id="22556-260">String</span><span class="sxs-lookup"><span data-stu-id="22556-260">String</span></span>      | <span data-ttu-id="22556-261">Nom del model</span><span class="sxs-lookup"><span data-stu-id="22556-261">Model name</span></span>                                                |
| <span data-ttu-id="22556-262">Valors</span><span class="sxs-lookup"><span data-stu-id="22556-262">Values</span></span>               | <span data-ttu-id="22556-263">Cadena JSON</span><span class="sxs-lookup"><span data-stu-id="22556-263">JSON String</span></span> | <span data-ttu-id="22556-264">Llista d'atributs produïts pel model</span><span class="sxs-lookup"><span data-stu-id="22556-264">List of attributes produced by the model</span></span> |
| <span data-ttu-id="22556-265">msdynci_predictionid</span><span class="sxs-lookup"><span data-stu-id="22556-265">msdynci_predictionid</span></span> | <span data-ttu-id="22556-266">GUID</span><span class="sxs-lookup"><span data-stu-id="22556-266">GUID</span></span>        | <span data-ttu-id="22556-267">GUID determinista generat a partir de msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="22556-267">Deterministic GUID generated from msdynci_identifier</span></span> | 
| <span data-ttu-id="22556-268">msdynci_identifier</span><span class="sxs-lookup"><span data-stu-id="22556-268">msdynci_identifier</span></span>   | <span data-ttu-id="22556-269">String</span><span class="sxs-lookup"><span data-stu-id="22556-269">String</span></span>      |  `Model|ModelProvider|CustomerId`                      |