---
title: Exportar dades del Customer Insights a Campaign Monitor
description: Apreneu a configurar la connexió i exportar a Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124169"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="e181a-103">Exportar segments a Campaign Monitor (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="e181a-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="e181a-104">Exporteu segments de perfils de client unificats a Campaign Monitor i utilitzeu-los per a activitats de màrqueting.</span><span class="sxs-lookup"><span data-stu-id="e181a-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e181a-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="e181a-105">Prerequisites</span></span>

-   <span data-ttu-id="e181a-106">Teniu un [compte de Campaign Monitor](https://www.campaignmonitor.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="e181a-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e181a-107">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="e181a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e181a-108">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="e181a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e181a-109">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="e181a-109">Known limitations</span></span>

- <span data-ttu-id="e181a-110">Podeu exportar fins a 1 milió de perfils per exportació a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e181a-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="e181a-111">L'exportació a Campaign Monitor es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="e181a-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="e181a-112">L'exportació de fins a 1 milió de perfils a Campaign Monitor pot trigar fins a 20 minuts com a màxim.</span><span class="sxs-lookup"><span data-stu-id="e181a-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="e181a-113">El nombre de perfils que podeu exportar a Campaign Monitor depèn i està limitat pel contracte amb Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e181a-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="e181a-114">Configurar la connexió a Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="e181a-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="e181a-115">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="e181a-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e181a-116">Seleccioneu **Afegeix una connexió** i trieu **Campaign Monitor** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="e181a-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="e181a-117">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="e181a-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e181a-118">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="e181a-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e181a-119">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="e181a-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e181a-120">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="e181a-120">Choose who can use this connection.</span></span> <span data-ttu-id="e181a-121">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="e181a-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e181a-122">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e181a-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e181a-123">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="e181a-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e181a-124">Seleccioneu **Connecta't** per inicialitzar la connexió a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e181a-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="e181a-125">Seleccioneu **Autentica amb Campaign Monitor** i proporcioneu les vostres credencials d'administració per a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e181a-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="e181a-126">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e181a-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e181a-127">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="e181a-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e181a-128">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="e181a-128">Configure an export</span></span>

<span data-ttu-id="e181a-129">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="e181a-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e181a-130">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e181a-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e181a-131">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="e181a-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e181a-132">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="e181a-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e181a-133">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e181a-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="e181a-134">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="e181a-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e181a-135">Introduïu l'[**ID de llista de Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="e181a-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="e181a-136">[Genereu la clau de l'API](https://www.campaignmonitor.com/api/getting-started/) des de **Configuració del compte** a Campaign Monitor per visualitzar primer l'ID de la llista de l'API.</span><span class="sxs-lookup"><span data-stu-id="e181a-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="e181a-137">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="e181a-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e181a-138">Cal que exporteu segments a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="e181a-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="e181a-139">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="e181a-139">Select **Save**.</span></span>

<span data-ttu-id="e181a-140">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="e181a-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e181a-141">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e181a-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e181a-142">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e181a-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e181a-143">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="e181a-143">Data privacy and compliance</span></span>

<span data-ttu-id="e181a-144">Quan permeteu al Dynamics 365 Customer Insights transmetre dades a Campaign Monitor, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals.</span><span class="sxs-lookup"><span data-stu-id="e181a-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e181a-145">Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que Campaign Monitor compleixi les obligacions de privadesa o de seguretat que pugueu teniu.</span><span class="sxs-lookup"><span data-stu-id="e181a-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e181a-146">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e181a-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e181a-147">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="e181a-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
