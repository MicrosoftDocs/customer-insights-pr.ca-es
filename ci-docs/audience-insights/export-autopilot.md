---
title: Exportar dades del Customer Insights a Autopilot
description: Apreneu a configurar la connexió i exportar a Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760131"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="1e9e6-103">Exportar segments a Autopilot (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="1e9e6-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="1e9e6-104">Exporteu segments de perfils de client unificats a Autopilot i utilitzeu-los per al màrqueting per correu electrònic a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="1e9e6-105">Requisits previs per a una connexió</span><span class="sxs-lookup"><span data-stu-id="1e9e6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="1e9e6-106">Teniu un [compte d'Autopilot](https://www.autopilothq.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1e9e6-107">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1e9e6-108">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1e9e6-109">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="1e9e6-109">Known limitations</span></span>

- <span data-ttu-id="1e9e6-110">Podeu exportar fins a un total de 100.000 perfils a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="1e9e6-111">L'exportació a Autopilot es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="1e9e6-112">L'exportació de fins a 100.000 perfils a Autopilot pot tardar unes hores a completar-se.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="1e9e6-113">El nombre de perfils que podeu exportar a Autopilot és limitat i dependrà del contracte que tingueu amb Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="1e9e6-114">Configuració de la connexió a Autopilot</span><span class="sxs-lookup"><span data-stu-id="1e9e6-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="1e9e6-115">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1e9e6-116">Seleccioneu **Afegeix connexió** i trieu **Autopilot** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="1e9e6-117">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1e9e6-118">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1e9e6-119">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1e9e6-120">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-120">Choose who can use this connection.</span></span> <span data-ttu-id="1e9e6-121">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1e9e6-122">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1e9e6-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="1e9e6-123">Introduïu la [clau de l'API d'Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="1e9e6-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="1e9e6-124">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1e9e6-125">Seleccioneu **Connecta't** per inicialitzar la connexió a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="1e9e6-126">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1e9e6-127">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1e9e6-128">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="1e9e6-128">Configure an export</span></span>

<span data-ttu-id="1e9e6-129">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1e9e6-130">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1e9e6-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1e9e6-131">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1e9e6-132">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1e9e6-133">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="1e9e6-134">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="1e9e6-135">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1e9e6-136">Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom** i el **Cognom**.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="1e9e6-137">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-137">Select the segments you want to export.</span></span> <span data-ttu-id="1e9e6-138">Es recomana **no exportar més de 100.000 perfils de clients en total** a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="1e9e6-139">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-139">Select **Save**.</span></span>

<span data-ttu-id="1e9e6-140">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1e9e6-141">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1e9e6-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1e9e6-142">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1e9e6-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1e9e6-143">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="1e9e6-143">Data privacy and compliance</span></span>

<span data-ttu-id="1e9e6-144">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Autopilot, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1e9e6-145">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Autopilot compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1e9e6-146">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1e9e6-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1e9e6-147">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="1e9e6-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
