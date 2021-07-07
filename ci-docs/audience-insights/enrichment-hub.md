---
title: Enriquir perfils de client unificats
description: Utilitzeu les capacitats disponibles per enriquir les dades dels clients.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305236"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="bdb66-103">Enriquiment per a perfils de clients (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="bdb66-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="bdb66-104">Utilitzeu dades de diverses fonts, com ara Microsoft i altres associats, per enriquir les dades dels clients.</span><span class="sxs-lookup"><span data-stu-id="bdb66-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pàgina del centre d'enriquiment":::

<span data-ttu-id="bdb66-106">A les conclusions del públic, aneu a **Dades** > **Enriquiment** per treballar amb les opcions d'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="bdb66-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="bdb66-107">Heu de tenir permisos de col·laborador o administrador per crear o editar els enriquiments.</span><span class="sxs-lookup"><span data-stu-id="bdb66-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="bdb66-108">Per obtenir més informació, vegeu [Permisos](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="bdb66-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="bdb66-109">A la pestanya **Detecta**, trobareu els següents enriquiments:</span><span class="sxs-lookup"><span data-stu-id="bdb66-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="bdb66-110">[Marques](enrichment-microsoft.md) proporcionades per Microsoft</span><span class="sxs-lookup"><span data-stu-id="bdb66-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="bdb66-111">[Interessos](enrichment-microsoft.md) proporcionats per Microsoft</span><span class="sxs-lookup"><span data-stu-id="bdb66-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="bdb66-112">[Adreces millorades](enrichment-enhanced-addresses.md) proporcionades per Microsoft</span><span class="sxs-lookup"><span data-stu-id="bdb66-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="bdb66-113">[Dades de l'empresa](enrichment-leadspace.md) proporcionades per Leadspace</span><span class="sxs-lookup"><span data-stu-id="bdb66-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="bdb66-114">[Dades demogràfiques](enrichment-experian.md) proporcionades per Experian</span><span class="sxs-lookup"><span data-stu-id="bdb66-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="bdb66-115">[Dades d'ubicació](enrichment-here.md) proporcionades per HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="bdb66-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="bdb66-116">[Dades personalitzades](enrichment-SFTP-custom-import.md) a través del protocol de transferència segura de fitxers (SFTP)</span><span class="sxs-lookup"><span data-stu-id="bdb66-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="bdb66-117">A la pestanya **Els meus enriquiments** podeu veure els enriquiments que heu configurat i editar-ne les propietats.</span><span class="sxs-lookup"><span data-stu-id="bdb66-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="bdb66-118">Administrar els enriquiments existents</span><span class="sxs-lookup"><span data-stu-id="bdb66-118">Manage existing enrichments</span></span>

<span data-ttu-id="bdb66-119">Aneu a la pestanya **Els meus enriquiments** per veure tots els enriquiments configurats.</span><span class="sxs-lookup"><span data-stu-id="bdb66-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="bdb66-120">Cada enriquiment es representa com una fila que inclou informació addicional sobre l'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="bdb66-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="bdb66-121">Seleccioneu un enriquiment per veure les opcions disponibles.</span><span class="sxs-lookup"><span data-stu-id="bdb66-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="bdb66-122">També podeu seleccionar els punts suspensius (...) en un element de llista per veure les opcions.</span><span class="sxs-lookup"><span data-stu-id="bdb66-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcions per administrar els enriquiments a la llista d'enriquiments":::

- <span data-ttu-id="bdb66-124">**Visualitzeu** els detalls de l'enriquiment amb el nombre de perfils de client enriquits.</span><span class="sxs-lookup"><span data-stu-id="bdb66-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="bdb66-125">**Editeu** la configuració d'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="bdb66-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="bdb66-126">**Executeu** l'enriquiment per actualitzar els perfils dels clients amb les últimes dades.</span><span class="sxs-lookup"><span data-stu-id="bdb66-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="bdb66-127">**Desactiveu** un enriquiment existent per impedir que s'actualitzi de manera automàtica amb cada actualització planificada.</span><span class="sxs-lookup"><span data-stu-id="bdb66-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="bdb66-128">Les dades de l'última actualització correcta continuaran estaran disponibles.</span><span class="sxs-lookup"><span data-stu-id="bdb66-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="bdb66-129">**Activeu** un enriquiment inactiu per reiniciar l'actualització automàtica amb cada actualització planificada.</span><span class="sxs-lookup"><span data-stu-id="bdb66-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="bdb66-130">**Suprimiu** un enriquiment.</span><span class="sxs-lookup"><span data-stu-id="bdb66-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="bdb66-131">Podeu executar o desactivar múltiples enriquiments alhora seleccionant-los a la llista.</span><span class="sxs-lookup"><span data-stu-id="bdb66-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="bdb66-132">Les opcions de visualització i edició no estan disponibles com a accions massives i només funcionen per a un enriquiment a la vegada.</span><span class="sxs-lookup"><span data-stu-id="bdb66-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="bdb66-133">Enriquiments i connexions</span><span class="sxs-lookup"><span data-stu-id="bdb66-133">Enrichments and connections</span></span>

<span data-ttu-id="bdb66-134">Les millores de tercers es configuren mitjançant [connexions](connections.md), que un administrador configura amb credencials i proporciona el consentiment per a les transferències de dades.</span><span class="sxs-lookup"><span data-stu-id="bdb66-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="bdb66-135">Els administradors i els col·laboradors poden utilitzar la connexió per configurar enriquiments.</span><span class="sxs-lookup"><span data-stu-id="bdb66-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="bdb66-136">Múltiples enriquiments del mateix tipus</span><span class="sxs-lookup"><span data-stu-id="bdb66-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="bdb66-137">L'entitat que s'ha d'enriquir s'especifica durant la configuració de l'enriquiment, la qual cosa us permet enriquir només un subconjunt dels vostres perfils.</span><span class="sxs-lookup"><span data-stu-id="bdb66-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="bdb66-138">Per exemple, podeu enriquir només les dades d'un segment concret.</span><span class="sxs-lookup"><span data-stu-id="bdb66-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="bdb66-139">Podeu configurar diversos enriquiments del mateix tipus i reutilitzar la mateixa connexió.</span><span class="sxs-lookup"><span data-stu-id="bdb66-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="bdb66-140">Alguns enriquiments tindran límits pel que fa al nombre d'enriquiments del mateix tipus que es poden crear.</span><span class="sxs-lookup"><span data-stu-id="bdb66-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="bdb66-141">Els límits i l'ús actual es poden veure a la pàgina **Enriquiment**.</span><span class="sxs-lookup"><span data-stu-id="bdb66-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
