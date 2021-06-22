---
title: Exportar dades del Customer Insights a AdRoll
description: Apreneu a configurar la connexió i exportar a AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124353"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="92db8-103">Exportar segments a AdRoll (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="92db8-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="92db8-104">Exporteu segments de perfils de client unificats a AdRoll i utilitzeu-los per a la publicitat.</span><span class="sxs-lookup"><span data-stu-id="92db8-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="92db8-105">Requisits previs per a una connexió</span><span class="sxs-lookup"><span data-stu-id="92db8-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="92db8-106">Teniu un [compte d'AdRoll](https://www.adroll.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="92db8-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="92db8-107">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="92db8-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="92db8-108">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="92db8-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="92db8-109">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="92db8-109">Known limitations</span></span>

- <span data-ttu-id="92db8-110">Podeu exportar fins a un total de 100.000 perfils per exportació a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="92db8-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="92db8-111">No podeu exportar segments amb menys de 100 perfils a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="92db8-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="92db8-112">L'exportació a AdRoll es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="92db8-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="92db8-113">L'exportació de fins a 250.000 perfils a AdRoll pot trigar fins a 10 minuts com a completar-se.</span><span class="sxs-lookup"><span data-stu-id="92db8-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="92db8-114">El nombre de perfils que podeu exportar a AdRoll és limitat i dependrà del contracte que tingueu amb AdRoll.</span><span class="sxs-lookup"><span data-stu-id="92db8-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="92db8-115">Configuració de la connexió a AdRoll</span><span class="sxs-lookup"><span data-stu-id="92db8-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="92db8-116">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="92db8-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="92db8-117">Seleccioneu **Afegeix connexió** i trieu **AdRoll** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="92db8-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="92db8-118">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="92db8-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="92db8-119">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="92db8-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="92db8-120">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="92db8-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="92db8-121">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="92db8-121">Choose who can use this connection.</span></span> <span data-ttu-id="92db8-122">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="92db8-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="92db8-123">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="92db8-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="92db8-124">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="92db8-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="92db8-125">Seleccioneu **Connecta't** per inicialitzar la connexió a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="92db8-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="92db8-126">Seleccioneu **Autenticació amb AdRoll** i indiqueu les vostres credencials d'administrador d'AdRoll.</span><span class="sxs-lookup"><span data-stu-id="92db8-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="92db8-127">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="92db8-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="92db8-128">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="92db8-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="92db8-129">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="92db8-129">Configure an export</span></span>

<span data-ttu-id="92db8-130">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="92db8-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="92db8-131">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="92db8-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="92db8-132">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="92db8-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="92db8-133">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="92db8-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="92db8-134">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció AdRoll.</span><span class="sxs-lookup"><span data-stu-id="92db8-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="92db8-135">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="92db8-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="92db8-136">Introduïu l'**Identificador de l'anunciant d'AdRoll** Per obtenir més informació, vegeu [Perfils d'anunciant d'AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="92db8-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="92db8-137">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="92db8-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="92db8-138">Cal que exporteu segments a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="92db8-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="92db8-139">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="92db8-139">Select the segments you want to export.</span></span> <span data-ttu-id="92db8-140">Seleccioneu un segment amb un mínim de 100 membres.</span><span class="sxs-lookup"><span data-stu-id="92db8-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="92db8-141">No podeu exportar segments més petits.</span><span class="sxs-lookup"><span data-stu-id="92db8-141">You can't export smaller segments.</span></span> <span data-ttu-id="92db8-142">A més, la mida màxima d'un segment que s'ha d'exportar és de 250.000 membres per exportació.</span><span class="sxs-lookup"><span data-stu-id="92db8-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="92db8-143">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="92db8-143">Select **Save**.</span></span>

<span data-ttu-id="92db8-144">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="92db8-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="92db8-145">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="92db8-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="92db8-146">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="92db8-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="92db8-147">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="92db8-147">Data privacy and compliance</span></span>

<span data-ttu-id="92db8-148">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a AdRoll, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="92db8-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="92db8-149">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que AdRoll compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="92db8-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="92db8-150">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="92db8-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="92db8-151">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="92db8-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
