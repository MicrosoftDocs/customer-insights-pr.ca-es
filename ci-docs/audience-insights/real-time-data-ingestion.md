---
title: Ingestió de dades en temps real i limitacions
description: Informació general sobre les capacitats en temps real de les conclusions del públic.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598557"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="7be71-103">Ingestió de dades en temps real (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="7be71-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="7be71-104">La funcionalitat gairebé en temps real us permet veure, en qüestió de segons, les darreres interaccions que els clients han fet amb els vostres productes o serveis.</span><span class="sxs-lookup"><span data-stu-id="7be71-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="7be71-105">Les [actualitzacions planificades](system.md#schedule-tab) inclouen grans quantitats de registres i diverses operacions complexes.</span><span class="sxs-lookup"><span data-stu-id="7be71-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="7be71-106">En primer lloc, les dades s'extreuen de la font de dades.</span><span class="sxs-lookup"><span data-stu-id="7be71-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="7be71-107">A continuació, les dades s'unifiquen i enriqueixen amb informació addicional.</span><span class="sxs-lookup"><span data-stu-id="7be71-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="7be71-108">Cada execució d'aquest procés pot tardar de minuts a hores.</span><span class="sxs-lookup"><span data-stu-id="7be71-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="7be71-109">Aquesta funcionalitat en temps real proporciona dades immediatament per al consum fins que la següent actualització planificada extreu aquestes dades de la font de dades.</span><span class="sxs-lookup"><span data-stu-id="7be71-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="7be71-110">Les actualitzacions en temps real tenen un temps de venciment després del qual ja no poden substituir el valor de la font de dades:</span><span class="sxs-lookup"><span data-stu-id="7be71-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="7be71-111">Les actualitzacions de perfil es conservaran durant 4 hores</span><span class="sxs-lookup"><span data-stu-id="7be71-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="7be71-112">Les activitats es conservaran durant 30 dies</span><span class="sxs-lookup"><span data-stu-id="7be71-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="7be71-113">Aquests valors són paràmetres de trucada de l'API que podeu canviar.</span><span class="sxs-lookup"><span data-stu-id="7be71-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="7be71-114">Pretenen assegurar--se que les dades d'origen segueixen sent el vostre origen en la veritat.</span><span class="sxs-lookup"><span data-stu-id="7be71-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="7be71-115">Si voleu que les actualitzacions en temps real s'incloguin durant més temps, heu d'afegir-les a una font de dades perquè es puguin extreure durant la propera actualització planificada.</span><span class="sxs-lookup"><span data-stu-id="7be71-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="7be71-116">Actualització en temps real dels camps del perfil del client unificat</span><span class="sxs-lookup"><span data-stu-id="7be71-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="7be71-117">Els perfils actualitzats es mostraran al cap d'uns pocs segons a la visualització de la targeta del client o a qualsevol altra visualització.</span><span class="sxs-lookup"><span data-stu-id="7be71-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="7be71-118">Com que les operacions en temps real tenen lloc després que s'hagi produït la unificació de dades, només s'apliquen als perfils de client unificats.</span><span class="sxs-lookup"><span data-stu-id="7be71-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="7be71-119">En conseqüència, els canvis de perfil en temps real no actualitzaran les mesures, la pertinença a segments o els enriquiments.</span><span class="sxs-lookup"><span data-stu-id="7be71-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="7be71-120">Limitacions</span><span class="sxs-lookup"><span data-stu-id="7be71-120">Limitations</span></span>

- <span data-ttu-id="7be71-121">Els perfils de client es poden actualitzar, però no crear o suprimir.</span><span class="sxs-lookup"><span data-stu-id="7be71-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="7be71-122">L'exportació d'actualitzacions en temps real per a sistemes externs, com el Power BI, no és possible en aquest moment.</span><span class="sxs-lookup"><span data-stu-id="7be71-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="7be71-123">Creació d'activitats en temps real</span><span class="sxs-lookup"><span data-stu-id="7be71-123">Real-time creation of activities</span></span>

<span data-ttu-id="7be71-124">L'API en temps real us permet publicar una activitat nova des del sistema d'origen (registre d'origen individual) en un perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="7be71-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="7be71-125">L'activitat nova estarà disponible com a activitat unificada a la cronologia unificada del perfil del client en segons.</span><span class="sxs-lookup"><span data-stu-id="7be71-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="7be71-126">Podeu veure la cronologia a la visualització de targeta del client o qualsevol altra integració de cronologia que hagueu configurat.</span><span class="sxs-lookup"><span data-stu-id="7be71-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7be71-127">Les activitats són immutables.</span><span class="sxs-lookup"><span data-stu-id="7be71-127">Activities are immutable.</span></span> <span data-ttu-id="7be71-128">No canvien una vegada creades.</span><span class="sxs-lookup"><span data-stu-id="7be71-128">They don't change once created.</span></span>
> - <span data-ttu-id="7be71-129">Actualment, els segments i les mesures no es mostraran en funció de la nova activitat.</span><span class="sxs-lookup"><span data-stu-id="7be71-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="7be71-130">Les activitats afegides només a través de l'API en temps real no formen part d'exportacions i no es mostraran al PowerBI.</span><span class="sxs-lookup"><span data-stu-id="7be71-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="7be71-131">Hi ha dues maneres de connectar-se a l'API en temps real:</span><span class="sxs-lookup"><span data-stu-id="7be71-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="7be71-132">[indirectament](#connect-via-the-dynamics-365-customer-insights-connector), mitjançant el [connector del Dynamics 365 Customer Insights](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="7be71-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="7be71-133">[directament](#connect-directly-to-the-real-time-api), amb el codi</span><span class="sxs-lookup"><span data-stu-id="7be71-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="7be71-134">Ambdues maneres comparteixen els requisits previs següents:</span><span class="sxs-lookup"><span data-stu-id="7be71-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="7be71-135">Un entorn del Customer Insights</span><span class="sxs-lookup"><span data-stu-id="7be71-135">A Customer Insights environment</span></span>
- <span data-ttu-id="7be71-136">Perfils de client unificats</span><span class="sxs-lookup"><span data-stu-id="7be71-136">Unified customer profiles</span></span>
- <span data-ttu-id="7be71-137">Activitats configurades i en execució</span><span class="sxs-lookup"><span data-stu-id="7be71-137">Activities configured and run</span></span>
- <span data-ttu-id="7be71-138">Permisos de col·laborador o d'administrador per autenticar el compte</span><span class="sxs-lookup"><span data-stu-id="7be71-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="7be71-139">Connectar-se amb el connector del Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="7be71-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="7be71-140">L'API en temps real pot ingerir dades d'un connector del Power Platform dedicat, el [connector del Dynamics 365 Customer Insights](/connectors/customerinsights/), sense haver d'escriure ni implementar cap codi.</span><span class="sxs-lookup"><span data-stu-id="7be71-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="7be71-141">El connector pot fer les mateixes accions en temps real que l'API.</span><span class="sxs-lookup"><span data-stu-id="7be71-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="7be71-142">Necessiteu una llicència vàlida per als connectors prèmium.</span><span class="sxs-lookup"><span data-stu-id="7be71-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="7be71-143">Per obtenir més informació, vegeu [Preguntes freqüents de llicències del Power Apps i el Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="7be71-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="7be71-144">Power Platform [Power Apps i/o Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="7be71-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="7be71-145">[Aplicacions lògiques](/azure/connectors/apis-list) de l'Azure</span><span class="sxs-lookup"><span data-stu-id="7be71-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="7be71-146">Per obtenir informació detallada sobre la creació de fluxos, vegeu la [documentació del Power Automate](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="7be71-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="7be71-147">Connectar-se directament a l'API en temps real</span><span class="sxs-lookup"><span data-stu-id="7be71-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="7be71-148">Per utilitzar les capacitats en temps real, creeu el vostre propi pipeline i connecteu-vos directament a l'API en temps real.</span><span class="sxs-lookup"><span data-stu-id="7be71-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="7be71-149">Podeu publicar una activitat en el format del vostre sistema d'origen o en el format UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="7be71-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="7be71-150">Obtenir el format fent una trucada de l'API a /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="7be71-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="7be71-151">Els detalls d'aquesta API, incloent-hi els paràmetres i les respostes, es troben a la secció **EntityData** de la [referència de les API del Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="7be71-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="7be71-152">Per obtenir més informació, vegeu [Treballar amb les API del Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="7be71-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="7be71-153">Comprendre l'ús en temps real amb la telemetria</span><span class="sxs-lookup"><span data-stu-id="7be71-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="7be71-154">Obtingueu una visió general del volum de sol·licituds realitzades a l'API en temps real i la informació sobre els problemes que pot trobar el sistema.</span><span class="sxs-lookup"><span data-stu-id="7be71-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="7be71-155">Podeu [accedir a la telemetria en temps real](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="7be71-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]