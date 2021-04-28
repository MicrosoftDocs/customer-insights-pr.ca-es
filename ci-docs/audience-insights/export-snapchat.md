---
title: Exportar dades del Customer Insights a Snapchat
description: Apreneu a configurar la connexió i exportar a Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760475"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="a50e7-103">Exportar llistes de segments a Snapchat (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="a50e7-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="a50e7-104">Exporteu segments de perfils de client unificats a Snapchat i utilitzeu-los per a la publicitat.</span><span class="sxs-lookup"><span data-stu-id="a50e7-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a50e7-105">Requisits previs per a una connexió</span><span class="sxs-lookup"><span data-stu-id="a50e7-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a50e7-106">Teniu un [compte d'empresa de Snapchat](https://business.snapchat.com/), un [compte d'anuncis de Snapchat](https://ads.snapchat.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="a50e7-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a50e7-107">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="a50e7-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a50e7-108">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="a50e7-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a50e7-109">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="a50e7-109">Known limitations</span></span>

- <span data-ttu-id="a50e7-110">L'exportació a Snapchat es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="a50e7-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="a50e7-111">L'exportació de fins a 1 milió de perfils a Snapchat pot trigar fins a 15 minuts com a màxim.</span><span class="sxs-lookup"><span data-stu-id="a50e7-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="a50e7-112">Configuració de la connexió a Snapchat</span><span class="sxs-lookup"><span data-stu-id="a50e7-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="a50e7-113">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="a50e7-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a50e7-114">Seleccioneu **Afegeix connexió** i trieu **Snapchat** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="a50e7-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="a50e7-115">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="a50e7-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a50e7-116">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="a50e7-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a50e7-117">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="a50e7-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a50e7-118">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="a50e7-118">Choose who can use this connection.</span></span> <span data-ttu-id="a50e7-119">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="a50e7-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a50e7-120">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a50e7-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a50e7-121">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="a50e7-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a50e7-122">Seleccioneu **Connecta't** per inicialitzar la connexió a Snapchat.</span><span class="sxs-lookup"><span data-stu-id="a50e7-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="a50e7-123">Seleccioneu **Autentica amb Snapchat** i proporcioneu les vostres credencials d'administració per a Snapchat.</span><span class="sxs-lookup"><span data-stu-id="a50e7-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="a50e7-124">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a50e7-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a50e7-125">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="a50e7-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a50e7-126">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="a50e7-126">Configure an export</span></span>

<span data-ttu-id="a50e7-127">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="a50e7-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a50e7-128">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a50e7-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a50e7-129">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="a50e7-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a50e7-130">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="a50e7-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a50e7-131">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Snapchat.</span><span class="sxs-lookup"><span data-stu-id="a50e7-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="a50e7-132">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="a50e7-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a50e7-133">Introduïu l'[**Identificador de públic de Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="a50e7-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="a50e7-134">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="a50e7-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a50e7-135">Cal que exporteu segments a Snapchat.</span><span class="sxs-lookup"><span data-stu-id="a50e7-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="a50e7-136">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="a50e7-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="a50e7-137">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="a50e7-137">Select **Save**.</span></span>

<span data-ttu-id="a50e7-138">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="a50e7-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a50e7-139">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a50e7-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a50e7-140">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a50e7-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a50e7-141">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="a50e7-141">Data privacy and compliance</span></span>

<span data-ttu-id="a50e7-142">Quan permeteu al Dynamics 365 Customer Insights transmetre dades a Snapchat, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals.</span><span class="sxs-lookup"><span data-stu-id="a50e7-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a50e7-143">Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que Snapchat compleixi les obligacions de privadesa o de seguretat que pugueu teniu.</span><span class="sxs-lookup"><span data-stu-id="a50e7-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a50e7-144">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a50e7-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a50e7-145">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="a50e7-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
