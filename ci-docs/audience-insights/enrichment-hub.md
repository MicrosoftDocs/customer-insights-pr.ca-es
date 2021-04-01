---
title: Enriquir perfils de client unificats
description: Utilitzeu les capacitats disponibles per enriquir les dades dels clients.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597683"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="72361-103">Enriquiment per a perfils de clients (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="72361-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="72361-104">Utilitzeu dades de diverses fonts, com ara Microsoft i altres associats, per enriquir les dades dels clients.</span><span class="sxs-lookup"><span data-stu-id="72361-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pàgina del centre d'enriquiment":::

<span data-ttu-id="72361-106">A les conclusions del públic, aneu a **Dades** > **Enriquiment** per treballar amb les opcions d'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="72361-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="72361-107">Heu de tenir permisos de col·laborador o administrador per crear o editar els enriquiments.</span><span class="sxs-lookup"><span data-stu-id="72361-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="72361-108">Per obtenir més informació, vegeu [Permisos](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="72361-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="72361-109">A la pestanya **Detecta**, trobareu els següents enriquiments:</span><span class="sxs-lookup"><span data-stu-id="72361-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="72361-110">[Marques](enrichment-microsoft-graph.md), proporcionades pel Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="72361-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="72361-111">[Interessos](enrichment-microsoft-graph.md), proporcionats pel Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="72361-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="72361-112">[Dades de l'empresa](enrichment-leadspace.md) proporcionades per Leadspace</span><span class="sxs-lookup"><span data-stu-id="72361-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="72361-113">[Dades demogràfiques](enrichment-experian.md) proporcionades per Experian</span><span class="sxs-lookup"><span data-stu-id="72361-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="72361-114">[Dades d'ubicació](enrichment-here.md) proporcionades per HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="72361-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="72361-115">[Dades personalitzades](enrichment-SFTP-custom-import.md) a través del protocol de transferència segura de fitxers (SFTP)</span><span class="sxs-lookup"><span data-stu-id="72361-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="72361-116">A la pestanya **Els meus enriquiments** podeu veure els enriquiments que heu configurat i editar-ne les propietats.</span><span class="sxs-lookup"><span data-stu-id="72361-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="72361-117">Administrar els enriquiments existents</span><span class="sxs-lookup"><span data-stu-id="72361-117">Manage existing enrichments</span></span>

<span data-ttu-id="72361-118">Aneu a **Els meus enriquiments** per veure tots els enriquiments que heu configurat.</span><span class="sxs-lookup"><span data-stu-id="72361-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="72361-119">Cada enriquiment es representa com una fila que inclou informació addicional sobre l'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="72361-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="72361-120">Seleccioneu un enriquiment per veure les opcions disponibles.</span><span class="sxs-lookup"><span data-stu-id="72361-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="72361-121">Alternativament, podeu seleccionar els punts suspensius (...) en un element de la llista per veure les opcions.</span><span class="sxs-lookup"><span data-stu-id="72361-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcions per administrar els enriquiments a la llista d'enriquiments":::

- <span data-ttu-id="72361-123">**Visualitzeu** els detalls de l'enriquiment amb el nombre de perfils de client enriquits.</span><span class="sxs-lookup"><span data-stu-id="72361-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="72361-124">**Editeu** la configuració d'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="72361-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="72361-125">**Executeu** l'enriquiment per actualitzar els perfils dels clients amb les últimes dades.</span><span class="sxs-lookup"><span data-stu-id="72361-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="72361-126">**Desactiveu** un enriquiment existent per impedir que s'actualitzi de manera automàtica amb cada actualització planificada.</span><span class="sxs-lookup"><span data-stu-id="72361-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="72361-127">Les dades de l'última actualització correcta continuaran estaran disponibles.</span><span class="sxs-lookup"><span data-stu-id="72361-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="72361-128">**Activeu** un enriquiment inactiu per reiniciar l'actualització automàtica amb cada actualització planificada.</span><span class="sxs-lookup"><span data-stu-id="72361-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="72361-129">**Suprimiu** un enriquiment.</span><span class="sxs-lookup"><span data-stu-id="72361-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="72361-130">Podeu executar o desactivar múltiples enriquiments alhora seleccionant-los a la llista.</span><span class="sxs-lookup"><span data-stu-id="72361-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="72361-131">Les opcions de visualització i edició no estan disponibles com a accions massives i només funcionen per a un enriquiment a la vegada.</span><span class="sxs-lookup"><span data-stu-id="72361-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]