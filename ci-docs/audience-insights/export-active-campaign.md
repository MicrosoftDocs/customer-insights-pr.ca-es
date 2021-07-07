---
title: Exportar dades del Customer Insights a ActiveCampaign
description: Més informació sobre com configurar la connexió i l'exportació a ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314581"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="ccacc-103">Exportar segments a ActiveCampaign (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="ccacc-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="ccacc-104">Exporteu segments de perfils de client unificats a ActiveCampaign i utilitzeu-los per a activitats de màrqueting.</span><span class="sxs-lookup"><span data-stu-id="ccacc-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ccacc-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="ccacc-105">Prerequisites</span></span>

-   <span data-ttu-id="ccacc-106">Teniu un [compte d'ActiveCampaign](https://www.activecampaign.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="ccacc-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ccacc-107">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="ccacc-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ccacc-108">Els perfils de client unificats als segments exportats contenen un camp amb una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="ccacc-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ccacc-109">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="ccacc-109">Known limitations</span></span>

- <span data-ttu-id="ccacc-110">Podeu exportar fins a 1 milió de perfils per exportació a ActiveCampaign i pot tardar fins a 90 minuts com a màxim.</span><span class="sxs-lookup"><span data-stu-id="ccacc-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="ccacc-111">L'exportació a ActiveCampaign es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="ccacc-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="ccacc-112">El nombre de perfils que podeu exportar a ActiveCampaign depèn del contracte que tingueu amb ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ccacc-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="ccacc-113">Configuració de la connexió a ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="ccacc-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="ccacc-114">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="ccacc-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ccacc-115">Seleccioneu **Afegeix una connexió** i trieu **ActiveCampaign** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="ccacc-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="ccacc-116">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="ccacc-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ccacc-117">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="ccacc-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ccacc-118">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="ccacc-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ccacc-119">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="ccacc-119">Choose who can use this connection.</span></span> <span data-ttu-id="ccacc-120">Per defecte, només són administradors.</span><span class="sxs-lookup"><span data-stu-id="ccacc-120">By default, it's only administrators.</span></span> <span data-ttu-id="ccacc-121">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ccacc-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ccacc-122">Introduïu la [clau de l'API d'ActiveCampaign i el nom d'amfitrió de l'extrem REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="ccacc-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="ccacc-123">El nom d'amfitrió de l'extrem REST és només el nom d'amfitrió, sense https://.</span><span class="sxs-lookup"><span data-stu-id="ccacc-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="ccacc-124">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="ccacc-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ccacc-125">Seleccioneu **Connecta** per inicialitzar la connexió a ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ccacc-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="ccacc-126">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ccacc-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ccacc-127">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="ccacc-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ccacc-128">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="ccacc-128">Configure an export</span></span>

<span data-ttu-id="ccacc-129">Podeu configurar una exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="ccacc-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="ccacc-130">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ccacc-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ccacc-131">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="ccacc-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ccacc-132">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="ccacc-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ccacc-133">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ccacc-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="ccacc-134">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="ccacc-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ccacc-135">Introduïu l'[**ID de llista d'ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="ccacc-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="ccacc-136">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="ccacc-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ccacc-137">És necessària per exportar segments a ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ccacc-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="ccacc-138">Opcionalment, podeu exportar el nom, cognom i telèfon per crear correus electrònics més personalitzats.</span><span class="sxs-lookup"><span data-stu-id="ccacc-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="ccacc-139">Seleccioneu Afegeix un atribut per assignar aquests camps.</span><span class="sxs-lookup"><span data-stu-id="ccacc-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="ccacc-140">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="ccacc-140">Select **Save**.</span></span>

<span data-ttu-id="ccacc-141">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="ccacc-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ccacc-142">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ccacc-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ccacc-143">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ccacc-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ccacc-144">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="ccacc-144">Data privacy and compliance</span></span>

<span data-ttu-id="ccacc-145">Quan permeteu que el Dynamics 365 Customer Insights transmeti dades a ActiveCampaign, permeteu la transferència de dades fora del límit de conformitat per al Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals.</span><span class="sxs-lookup"><span data-stu-id="ccacc-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ccacc-146">Microsoft transferirà aquestes dades segons la vostra instrucció, però sou responsable d'assegurar que ActiveCampaign compleixi les obligacions de privadesa o seguretat que tingueu.</span><span class="sxs-lookup"><span data-stu-id="ccacc-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ccacc-147">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ccacc-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ccacc-148">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="ccacc-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
