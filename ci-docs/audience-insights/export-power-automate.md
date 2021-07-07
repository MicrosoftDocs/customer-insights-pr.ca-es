---
title: Connector del Power Automate | Microsoft Docs
description: Creeu fluxos al Microsoft Power Automate des del Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305052"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="32680-103">Connector del Power Automate (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="32680-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="32680-104">Dispareu esdeveniments específics perquè s'activin automàticament quan canviïn les dades i administreu fluxos més complexos directament al [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="32680-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="32680-105">Disparadors del Power Automate</span><span class="sxs-lookup"><span data-stu-id="32680-105">Power Automate triggers</span></span>

<span data-ttu-id="32680-106">Utilitzeu disparadors per crear fluxos de núvol i automatitzar tasques repetitives, com ara notificacions o accions més avançades.</span><span class="sxs-lookup"><span data-stu-id="32680-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="32680-107">Disparador per quan no es pot actualitzar la font de dades.</span><span class="sxs-lookup"><span data-stu-id="32680-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="32680-108">Disparador per quan la font de dades s'actualitza correctament.</span><span class="sxs-lookup"><span data-stu-id="32680-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="32680-109">Disparador per quan se supera un llindar en un segment.</span><span class="sxs-lookup"><span data-stu-id="32680-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="32680-110">El disparador es limita a haver superat el llindar.</span><span class="sxs-lookup"><span data-stu-id="32680-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="32680-111">Disparador per quan se supera un llindar en una mesura empresarial.</span><span class="sxs-lookup"><span data-stu-id="32680-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="32680-112">Només són compatibles les mesures empresarials sense cap dimensió.</span><span class="sxs-lookup"><span data-stu-id="32680-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="32680-113">El disparador es limita a haver superat el llindar.</span><span class="sxs-lookup"><span data-stu-id="32680-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="32680-114">Disparador per quan hagi finalitzat una actualització completa de (fonts de dades, segments, mesures, etc.).</span><span class="sxs-lookup"><span data-stu-id="32680-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="32680-115">Es dispara quan s'ha completat una actualització del procés d'unificació (assignació, coincidència i combinació).</span><span class="sxs-lookup"><span data-stu-id="32680-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="32680-116">Configureu els disparadors al Power Automate.</span><span class="sxs-lookup"><span data-stu-id="32680-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="32680-117">Accions del Power Automate</span><span class="sxs-lookup"><span data-stu-id="32680-117">Power Automate actions</span></span>

<span data-ttu-id="32680-118">El connector del Power Automate proporciona altres accions que els disparadors disponibles.</span><span class="sxs-lookup"><span data-stu-id="32680-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="32680-119">Per obtenir més informació, vegeu la [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="32680-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="32680-120">Crear un flux del Power Automate</span><span class="sxs-lookup"><span data-stu-id="32680-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="32680-121">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="32680-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="32680-122">A la peça del **Power Automate**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="32680-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="32680-123">El connector del Customer Insights (versió preliminar) al Power Automate s'obre.</span><span class="sxs-lookup"><span data-stu-id="32680-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="32680-124">**Inicieu la sessió** al Power Automate.</span><span class="sxs-lookup"><span data-stu-id="32680-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="32680-125">Trieu un dels disparadors disponibles i afegiu més passos al flux nou.</span><span class="sxs-lookup"><span data-stu-id="32680-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="32680-126">Per obtenir més informació, vegeu [Crear un flux de núvol al Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="32680-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="32680-127">Exemples de com utilitzar els fluxos:</span><span class="sxs-lookup"><span data-stu-id="32680-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="32680-128">Publicar un missatge a un canal del Microsoft Teams si es produeix un error en actualitzar la font de dades.</span><span class="sxs-lookup"><span data-stu-id="32680-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="32680-129">Enviar un correu electrònic als propietaris de les dades quan se superi un llindar en un segment.</span><span class="sxs-lookup"><span data-stu-id="32680-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
