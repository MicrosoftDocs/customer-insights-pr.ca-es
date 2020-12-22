---
title: Destinacions d'exportació
description: Exporteu dades i administreu destinacions d'exportació.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643851"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="c91bc-103">Destinacions d'exportació (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="c91bc-103">Export destinations (preview)</span></span>

<span data-ttu-id="c91bc-104">A la pàgina **Destinacions d'exportació** es mostren totes les ubicacions per a les quals heu configurat l'exportació de dades.</span><span class="sxs-lookup"><span data-stu-id="c91bc-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="c91bc-105">També podeu afegir noves destinacions per a l'exportació.</span><span class="sxs-lookup"><span data-stu-id="c91bc-105">You can also add new destinations for export.</span></span> <span data-ttu-id="c91bc-106">A més, mostra les opcions d'exportació que hi ha disponibles actualment.</span><span class="sxs-lookup"><span data-stu-id="c91bc-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="c91bc-107">Obteniu una descripció general i breu, i esbrineu què podeu fer amb cada opció d'extensibilitat.</span><span class="sxs-lookup"><span data-stu-id="c91bc-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="c91bc-108">Exporteu els perfils unificats, les mesures i els segments a les aplicacions admeses rellevants per a la vostra empresa.</span><span class="sxs-lookup"><span data-stu-id="c91bc-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="c91bc-109">Aneu a **Administració** > **Destinacions d'exportació** per trobar les següents opcions d'extensibilitat:</span><span class="sxs-lookup"><span data-stu-id="c91bc-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="c91bc-110">Complement de targetes de clients del Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c91bc-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="c91bc-111">Connector del Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="c91bc-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="c91bc-112">Connector del Power Automate</span><span class="sxs-lookup"><span data-stu-id="c91bc-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="c91bc-113">Connector del Power Apps</span><span class="sxs-lookup"><span data-stu-id="c91bc-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="c91bc-114">Connector del Power BI</span><span class="sxs-lookup"><span data-stu-id="c91bc-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="c91bc-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="c91bc-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="c91bc-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c91bc-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="c91bc-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="c91bc-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="c91bc-118">Emmagatzematge blob de l’Azure</span><span class="sxs-lookup"><span data-stu-id="c91bc-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="c91bc-119">Connector del LiveRamp&reg;</span><span class="sxs-lookup"><span data-stu-id="c91bc-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="c91bc-120">Bot per al Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c91bc-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="c91bc-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="c91bc-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="c91bc-122">API del Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c91bc-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="c91bc-123">Afegir una destinació d'exportació nova</span><span class="sxs-lookup"><span data-stu-id="c91bc-123">Add a new export destination</span></span>

<span data-ttu-id="c91bc-124">Per afegir destinacions d'exportació, heu de tenir [permisos d'administrador](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c91bc-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="c91bc-125">Si exporteu a serveis de Microsoft, assumim que els dos serveis es troben a la mateixa organització.</span><span class="sxs-lookup"><span data-stu-id="c91bc-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="c91bc-126">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="c91bc-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c91bc-127">Canvieu a la pestanya **Les meves destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="c91bc-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="c91bc-128">Seleccioneu **Afegeix una destinació** per crear una destinació d'exportació nova.</span><span class="sxs-lookup"><span data-stu-id="c91bc-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="c91bc-129">A la subfinestra **Afegeix una destinació**, seleccioneu el **tipus** de destinació d'exportació al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="c91bc-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="c91bc-130">Proporcioneu les dades necessàries i seleccioneu **Següent** per crear la destinació d'exportació.</span><span class="sxs-lookup"><span data-stu-id="c91bc-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="c91bc-131">També podeu seleccionar **Configura** en una peça de la pestanya **Descobreix**.</span><span class="sxs-lookup"><span data-stu-id="c91bc-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="c91bc-132">Visualitzar les destinacions d'exportació</span><span class="sxs-lookup"><span data-stu-id="c91bc-132">View Export destinations</span></span>

<span data-ttu-id="c91bc-133">Després de crear destinacions d'exportació, les trobareu en una taula de la pestanya **Les meves destinacions d'exportació**. Aquesta taula té tres columnes:</span><span class="sxs-lookup"><span data-stu-id="c91bc-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="c91bc-134">**Nom de visualització**: el nom que heu introduït en crear la destinació.</span><span class="sxs-lookup"><span data-stu-id="c91bc-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="c91bc-135">**Tipus**: el tipus de destinació d'exportació que definiu en crear la destinació.</span><span class="sxs-lookup"><span data-stu-id="c91bc-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="c91bc-136">**Data de creació**: la data de creació de la destinació.</span><span class="sxs-lookup"><span data-stu-id="c91bc-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="c91bc-137">Editar una destinació d'exportació</span><span class="sxs-lookup"><span data-stu-id="c91bc-137">Edit an export destination</span></span>

1. <span data-ttu-id="c91bc-138">Seleccioneu els punt suspensius verticals de la destinació d'exportació que voleu editar.</span><span class="sxs-lookup"><span data-stu-id="c91bc-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c91bc-139">![Punts suspensius verticals](media/export-destinations-page-ellipsis.png "Punts suspensius verticals")</span><span class="sxs-lookup"><span data-stu-id="c91bc-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="c91bc-140">Al menú desplegable, seleccioneu **Edita**.</span><span class="sxs-lookup"><span data-stu-id="c91bc-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="c91bc-141">Canvieu els valors que requereixin l'actualització i seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="c91bc-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="c91bc-142">Exportar dades segons demanda</span><span class="sxs-lookup"><span data-stu-id="c91bc-142">Export data on demand</span></span>

<span data-ttu-id="c91bc-143">Després de configurar un connector per a una destinació d'exportació, les exportacions s'executaran amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c91bc-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="c91bc-144">Per exportar les dades sense haver d'esperar una actualització programada, aneu a la pestanya **Les meves destinacions d'exportació** a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="c91bc-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c91bc-145">![Punts suspensius verticals](media/export-destinations-page-ellipsis.png "Punts suspensius verticals")</span><span class="sxs-lookup"><span data-stu-id="c91bc-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="c91bc-146">Seleccioneu **Exporta** sobre de la llista per executar l'exportació a totes les destinacions d'exportació simultàniament.</span><span class="sxs-lookup"><span data-stu-id="c91bc-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="c91bc-147">Seleccioneu els punts suspensius (...) després d'un element de la llista i, a continuació, trieu l'opció **Exporta** per executar l'exportació per a una única destinació d'exportació.</span><span class="sxs-lookup"><span data-stu-id="c91bc-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="c91bc-148">Suprimir una destinació d'exportació</span><span class="sxs-lookup"><span data-stu-id="c91bc-148">Remove an Export destination</span></span>

<span data-ttu-id="c91bc-149">Per suprimir una destinació d'exportació, comenceu des de la pàgina principal **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="c91bc-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="c91bc-150">Seleccioneu els punt suspensius verticals de la destinació d'exportació que voleu suprimir.</span><span class="sxs-lookup"><span data-stu-id="c91bc-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c91bc-151">![Punts suspensius verticals](media/export-destinations-page-ellipsis.png "Punts suspensius verticals")</span><span class="sxs-lookup"><span data-stu-id="c91bc-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="c91bc-152">Seleccioneu **Suprimeix** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="c91bc-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="c91bc-153">Confirmeu la supressió seleccionant **Suprimeix** a la pantalla de confirmació.</span><span class="sxs-lookup"><span data-stu-id="c91bc-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
