---
title: Exportar dades del Customer Insights a RollWorks
description: Apreneu a configurar la connexió i exportar a RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124077"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="d71a4-103">Exportar segments a RollWorks (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="d71a4-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="d71a4-104">Exporteu segments de perfils de client unificats a RollWorks i utilitzeu-los per a la publicitat.</span><span class="sxs-lookup"><span data-stu-id="d71a4-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d71a4-105">Requisits previs per a una connexió</span><span class="sxs-lookup"><span data-stu-id="d71a4-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d71a4-106">Teniu un [compte de RollWorks](https://www.rollworks.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="d71a4-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d71a4-107">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="d71a4-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d71a4-108">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="d71a4-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d71a4-109">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="d71a4-109">Known limitations</span></span>

- <span data-ttu-id="d71a4-110">Podeu exportar fins a 250.000 perfils per exportació al RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d71a4-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="d71a4-111">No podeu exportar segments amb menys de 100 perfils al RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d71a4-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="d71a4-112">L'exportació a RollWorks es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="d71a4-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="d71a4-113">L'exportació de fins a 250.000 perfils a RollWorks pot trigar fins a 10 minuts com a màxim.</span><span class="sxs-lookup"><span data-stu-id="d71a4-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="d71a4-114">El nombre de perfils que podeu exportar a RollWorks depèn i està limitat pel contracte amb RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d71a4-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="d71a4-115">Configuració de la connexió a RollWorks</span><span class="sxs-lookup"><span data-stu-id="d71a4-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="d71a4-116">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="d71a4-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d71a4-117">Seleccioneu **Afegeix connexió** i trieu **RollWorks** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="d71a4-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="d71a4-118">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="d71a4-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d71a4-119">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="d71a4-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d71a4-120">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="d71a4-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d71a4-121">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="d71a4-121">Choose who can use this connection.</span></span> <span data-ttu-id="d71a4-122">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="d71a4-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d71a4-123">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d71a4-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d71a4-124">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="d71a4-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d71a4-125">Seleccioneu **Connecta't** per inicialitzar la connexió a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d71a4-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="d71a4-126">Seleccioneu **Autentica amb RollWorks** i proporcioneu les vostres credencials d'administració per a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d71a4-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="d71a4-127">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d71a4-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d71a4-128">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="d71a4-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d71a4-129">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="d71a4-129">Configure an export</span></span>

<span data-ttu-id="d71a4-130">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="d71a4-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d71a4-131">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d71a4-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d71a4-132">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="d71a4-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d71a4-133">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="d71a4-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d71a4-134">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d71a4-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="d71a4-135">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="d71a4-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d71a4-136">Introduïu l'**Identificador d'anunciant de RollWorks** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="d71a4-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="d71a4-137">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="d71a4-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d71a4-138">Cal que exporteu segments a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d71a4-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="d71a4-139">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="d71a4-139">Select the segments you want to export.</span></span> <span data-ttu-id="d71a4-140">Seleccioneu un segment amb un mínim de 100 membres.</span><span class="sxs-lookup"><span data-stu-id="d71a4-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="d71a4-141">No podeu exportar segments més petits.</span><span class="sxs-lookup"><span data-stu-id="d71a4-141">You can't export smaller segments.</span></span> <span data-ttu-id="d71a4-142">A més, la mida màxima d'un segment que s'ha d'exportar és de 250.000 membres per exportació.</span><span class="sxs-lookup"><span data-stu-id="d71a4-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="d71a4-143">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="d71a4-143">Select **Save**.</span></span>

<span data-ttu-id="d71a4-144">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="d71a4-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d71a4-145">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d71a4-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d71a4-146">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d71a4-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d71a4-147">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="d71a4-147">Data privacy and compliance</span></span>

<span data-ttu-id="d71a4-148">Quan permeteu al Dynamics 365 Customer Insights transmetre dades a RollWorks, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals.</span><span class="sxs-lookup"><span data-stu-id="d71a4-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d71a4-149">Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que RollWorks compleixi les obligacions de privadesa o de seguretat que pugueu teniu.</span><span class="sxs-lookup"><span data-stu-id="d71a4-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d71a4-150">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d71a4-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d71a4-151">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="d71a4-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
