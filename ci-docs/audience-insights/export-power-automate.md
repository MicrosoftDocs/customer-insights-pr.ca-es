---
title: Connector del Power Automate | Microsoft Docs
description: Creeu fluxos al Microsoft Power Automate des del Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405123"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="2020a-103">Connector del Power Automate (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="2020a-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="2020a-104">Dispareu esdeveniments específics perquè s'activin automàticament quan canviïn les dades i administreu fluxos més complexos directament al [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="2020a-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="2020a-105">Disparadors del Power Automate</span><span class="sxs-lookup"><span data-stu-id="2020a-105">Power Automate triggers</span></span>

<span data-ttu-id="2020a-106">Podeu utilitzar diversos disparadors que us permeten crear fluxos per automatitzar tasques repetitives, com ara notificacions o accions més avançades.</span><span class="sxs-lookup"><span data-stu-id="2020a-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="2020a-107">Disparador per quan no es pot actualitzar la font de dades.</span><span class="sxs-lookup"><span data-stu-id="2020a-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="2020a-108">Disparador per quan la font de dades s'actualitza correctament.</span><span class="sxs-lookup"><span data-stu-id="2020a-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="2020a-109">Disparador per quan se supera un llindar en un segment.</span><span class="sxs-lookup"><span data-stu-id="2020a-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="2020a-110">El disparador es limita a haver superat el llindar.</span><span class="sxs-lookup"><span data-stu-id="2020a-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="2020a-111">Disparador per quan se supera un llindar en una mesura empresarial.</span><span class="sxs-lookup"><span data-stu-id="2020a-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="2020a-112">El disparador es limita a haver superat el llindar.</span><span class="sxs-lookup"><span data-stu-id="2020a-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="2020a-113">Disparador per quan hagi finalitzat una actualització completa de (fonts de dades, segments, mesures, etc.).</span><span class="sxs-lookup"><span data-stu-id="2020a-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="2020a-114">Es dispara quan s'ha completat una actualització del procés d'unificació (assignació, coincidència i combinació).</span><span class="sxs-lookup"><span data-stu-id="2020a-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="2020a-115">[Configureu els disparadors al Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="2020a-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="2020a-116">Accions del Power Automate</span><span class="sxs-lookup"><span data-stu-id="2020a-116">Power Automate actions</span></span>
<span data-ttu-id="2020a-117">El connector del Power Automate proporciona altres accions que els disparadors disponibles.</span><span class="sxs-lookup"><span data-stu-id="2020a-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="2020a-118">Per obtenir més informació, vegeu la [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="2020a-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="2020a-119">Crear un flux del Power Automate a les conclusions del públic</span><span class="sxs-lookup"><span data-stu-id="2020a-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="2020a-120">A les conclusions del públic, aneu a **Administració** > **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="2020a-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="2020a-121">A la pàgina **Sistema**, seleccioneu la pestanya **Estat**.</span><span class="sxs-lookup"><span data-stu-id="2020a-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="2020a-122">A la secció **Fonts de dades**, seleccioneu **Fluxos** i seleccioneu **Crea un flux** a la llista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2020a-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2020a-123">![Connector del Power Automate que mostra l'acció Crea un flux](media/power-automate-connector-create-flow.png "Connector del Power Automate que mostra l'acció Crea un flux")</span><span class="sxs-lookup"><span data-stu-id="2020a-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="2020a-124">Al Power Automate, seleccioneu un dels disparadors disponibles per crear el vostre flux preferit.</span><span class="sxs-lookup"><span data-stu-id="2020a-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="2020a-125">Si esteu creant el vostre primer flux, haureu d'autenticar-vos primer amb el connector del Power Automate.</span><span class="sxs-lookup"><span data-stu-id="2020a-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
