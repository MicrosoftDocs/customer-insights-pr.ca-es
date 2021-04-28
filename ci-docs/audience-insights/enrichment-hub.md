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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895993"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="17465-103">Enriquiment per a perfils de clients (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="17465-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="17465-104">Utilitzeu dades de diverses fonts, com ara Microsoft i altres associats, per enriquir les dades dels clients.</span><span class="sxs-lookup"><span data-stu-id="17465-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pàgina del centre d'enriquiment":::

<span data-ttu-id="17465-106">A les conclusions del públic, aneu a **Dades** > **Enriquiment** per treballar amb les opcions d'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="17465-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="17465-107">Heu de tenir permisos de col·laborador o administrador per crear o editar els enriquiments.</span><span class="sxs-lookup"><span data-stu-id="17465-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="17465-108">Per obtenir més informació, vegeu [Permisos](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="17465-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="17465-109">A la pestanya **Detecta**, trobareu els següents enriquiments:</span><span class="sxs-lookup"><span data-stu-id="17465-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="17465-110">[Marques](enrichment-microsoft.md) proporcionades per Microsoft</span><span class="sxs-lookup"><span data-stu-id="17465-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="17465-111">[Interessos](enrichment-microsoft.md) proporcionats per Microsoft</span><span class="sxs-lookup"><span data-stu-id="17465-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="17465-112">[Dades de l'empresa](enrichment-leadspace.md) proporcionades per Leadspace</span><span class="sxs-lookup"><span data-stu-id="17465-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="17465-113">[Dades demogràfiques](enrichment-experian.md) proporcionades per Experian</span><span class="sxs-lookup"><span data-stu-id="17465-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="17465-114">[Dades d'ubicació](enrichment-here.md) proporcionades per HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="17465-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="17465-115">[Dades personalitzades](enrichment-SFTP-custom-import.md) a través del protocol de transferència segura de fitxers (SFTP)</span><span class="sxs-lookup"><span data-stu-id="17465-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="17465-116">A la pestanya **Els meus enriquiments** podeu veure els enriquiments que heu configurat i editar-ne les propietats.</span><span class="sxs-lookup"><span data-stu-id="17465-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="17465-117">Administrar els enriquiments existents</span><span class="sxs-lookup"><span data-stu-id="17465-117">Manage existing enrichments</span></span>

<span data-ttu-id="17465-118">Aneu a **Els meus enriquiments** per veure tots els enriquiments que heu configurat.</span><span class="sxs-lookup"><span data-stu-id="17465-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="17465-119">Cada enriquiment es representa com una fila que inclou informació addicional sobre l'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="17465-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="17465-120">Seleccioneu un enriquiment per veure les opcions disponibles.</span><span class="sxs-lookup"><span data-stu-id="17465-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="17465-121">També podeu seleccionar els punts suspensius (...) en un element de llista per veure les opcions.</span><span class="sxs-lookup"><span data-stu-id="17465-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcions per administrar els enriquiments a la llista d'enriquiments":::

- <span data-ttu-id="17465-123">**Visualitzeu** els detalls de l'enriquiment amb el nombre de perfils de client enriquits.</span><span class="sxs-lookup"><span data-stu-id="17465-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="17465-124">**Editeu** la configuració d'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="17465-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="17465-125">**Executeu** l'enriquiment per actualitzar els perfils dels clients amb les últimes dades.</span><span class="sxs-lookup"><span data-stu-id="17465-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="17465-126">**Desactiveu** un enriquiment existent per impedir que s'actualitzi de manera automàtica amb cada actualització planificada.</span><span class="sxs-lookup"><span data-stu-id="17465-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="17465-127">Les dades de l'última actualització correcta continuaran estaran disponibles.</span><span class="sxs-lookup"><span data-stu-id="17465-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="17465-128">**Activeu** un enriquiment inactiu per reiniciar l'actualització automàtica amb cada actualització planificada.</span><span class="sxs-lookup"><span data-stu-id="17465-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="17465-129">**Suprimiu** un enriquiment.</span><span class="sxs-lookup"><span data-stu-id="17465-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="17465-130">Podeu executar o desactivar múltiples enriquiments alhora seleccionant-los a la llista.</span><span class="sxs-lookup"><span data-stu-id="17465-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="17465-131">Les opcions de visualització i edició no estan disponibles com a accions massives i només funcionen per a un enriquiment a la vegada.</span><span class="sxs-lookup"><span data-stu-id="17465-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="17465-132">Enriquiments i connexions</span><span class="sxs-lookup"><span data-stu-id="17465-132">Enrichments and connections</span></span>

<span data-ttu-id="17465-133">Les millores de tercers es configuren mitjançant [connexions](connections.md), que un administrador configura amb credencials i proporciona el consentiment per a les transferències de dades.</span><span class="sxs-lookup"><span data-stu-id="17465-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="17465-134">Els administradors i els col·laboradors poden utilitzar la connexió per configurar enriquiments.</span><span class="sxs-lookup"><span data-stu-id="17465-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="17465-135">Múltiples enriquiments del mateix tipus</span><span class="sxs-lookup"><span data-stu-id="17465-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="17465-136">L'entitat que s'ha d'enriquir s'especifica durant la configuració de l'enriquiment, la qual cosa us permet enriquir només un subconjunt dels vostres perfils.</span><span class="sxs-lookup"><span data-stu-id="17465-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="17465-137">Per exemple, enriquiu només les dades d'un segment concret.</span><span class="sxs-lookup"><span data-stu-id="17465-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="17465-138">Podeu configurar diversos enriquiments del mateix tipus i reutilitzar la mateixa connexió.</span><span class="sxs-lookup"><span data-stu-id="17465-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="17465-139">Alguns enriquiments tindran límits pel que fa al nombre d'enriquiments del mateix tipus que es poden crear.</span><span class="sxs-lookup"><span data-stu-id="17465-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="17465-140">Els límits i l'ús actual es poden veure a la pàgina **Enriquiment**.</span><span class="sxs-lookup"><span data-stu-id="17465-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
