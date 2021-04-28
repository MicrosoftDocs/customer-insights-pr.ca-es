---
title: Connexions amb altres serveis des del Customer Insights.
description: Compartiu dades amb altres serveis.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896085"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="87f21-103">Informació general sobre les connexions (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="87f21-103">Connections (preview) overview</span></span>

<span data-ttu-id="87f21-104">Les connexions són la clau per permetre l'ús compartit de dades al i des del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="87f21-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="87f21-105">Cada connexió estableix l'ús compartit de dades amb un servei específic.</span><span class="sxs-lookup"><span data-stu-id="87f21-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="87f21-106">Les connexions són la base per [configurar millores de tercers](enrichment-hub.md) i [configurar les exportacions](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="87f21-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="87f21-107">La mateixa connexió es pot utilitzar diverses vegades.</span><span class="sxs-lookup"><span data-stu-id="87f21-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="87f21-108">Per exemple, una connexió al Dynamics 365 Marketing funciona per a diverses exportacions i es pot utilitzar una connexió de Leadspace per a diverses millores.</span><span class="sxs-lookup"><span data-stu-id="87f21-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="87f21-109">Aneu a **Administració** > **Connexions** per crear i visualitzar connexions.</span><span class="sxs-lookup"><span data-stu-id="87f21-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="87f21-110">La pestanya **Connexions** mostra totes les connexions actives.</span><span class="sxs-lookup"><span data-stu-id="87f21-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="87f21-111">La llista mostra una fila per a cada connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="87f21-112">Podeu obtenir una descripció general ràpida, una descripció i saber què podeu fer amb cada opció d'extensibilitat a la pestanya **Descobriu**.</span><span class="sxs-lookup"><span data-stu-id="87f21-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="87f21-113">Exportacions</span><span class="sxs-lookup"><span data-stu-id="87f21-113">Exports</span></span>

<span data-ttu-id="87f21-114">Només els administradors poden configurar noves connexions, però poden atorgar accés als col·laboradors perquè utilitzin connexions existents.</span><span class="sxs-lookup"><span data-stu-id="87f21-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="87f21-115">Els administradors controlen on poden anar les dades, els col·laboradors defineixen la càrrega i la freqüència que s'ajusten a les seves necessitats.</span><span class="sxs-lookup"><span data-stu-id="87f21-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="87f21-116">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="87f21-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="87f21-117">Enriquiments</span><span class="sxs-lookup"><span data-stu-id="87f21-117">Enrichments</span></span>

<span data-ttu-id="87f21-118">Només els administradors poden configurar noves connexions, però les connexions creades sempre estan disponibles per als administradors i per als col·laboradors.</span><span class="sxs-lookup"><span data-stu-id="87f21-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="87f21-119">Els administradors administren les credencials i donen el consentiment per a les transferències de dades.</span><span class="sxs-lookup"><span data-stu-id="87f21-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="87f21-120">A continuació, les connexions es poden utilitzar per a enriquiments dels administradors i els col·laboradors.</span><span class="sxs-lookup"><span data-stu-id="87f21-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="87f21-121">Afegir una connexió nova</span><span class="sxs-lookup"><span data-stu-id="87f21-121">Add a new connection</span></span>

<span data-ttu-id="87f21-122">Per afegir connexions, heu de tenir [permisos d'administrador](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="87f21-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="87f21-123">Si us connecteu amb altres serveis de Microsoft, suposem que ambdós serveis són a la mateixa organització.</span><span class="sxs-lookup"><span data-stu-id="87f21-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="87f21-124">Aneu a **Administració** > **Connexions (versió preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="87f21-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="87f21-125">Aneu a la pestanya **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="87f21-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="87f21-126">Seleccioneu **Afegeix una connexió** per crear una connexió nova.</span><span class="sxs-lookup"><span data-stu-id="87f21-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="87f21-127">Trieu al menú desplegable quin tipus de connexió voleu crear.</span><span class="sxs-lookup"><span data-stu-id="87f21-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="87f21-128">A la subfinestra **Configuració de la connexió**, proporcioneu els detalls necessaris.</span><span class="sxs-lookup"><span data-stu-id="87f21-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="87f21-129">El **Nom de visualització** i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="87f21-130">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="87f21-131">Els camps exactes depenen del servei amb què us connecteu.</span><span class="sxs-lookup"><span data-stu-id="87f21-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="87f21-132">Podeu obtenir informació sobre els detalls d'un tipus de connexió específic a l'article sobre el servei de destinació.</span><span class="sxs-lookup"><span data-stu-id="87f21-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="87f21-133">Per crear la connexió, seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="87f21-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="87f21-134">També podeu seleccionar **Configura** en una peça de la pestanya **Descobreix**.</span><span class="sxs-lookup"><span data-stu-id="87f21-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="87f21-135">Permetre que els col·laboradors utilitzin una connexió per a les exportacions</span><span class="sxs-lookup"><span data-stu-id="87f21-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="87f21-136">Quan configureu o editeu una connexió d'exportació, trieu quins usuaris poden utilitzar aquesta connexió específica per definir les [exportacions](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="87f21-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="87f21-137">Per defecte, hi ha disponible una connexió per als usuaris que tenen una funció d'administrador.</span><span class="sxs-lookup"><span data-stu-id="87f21-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="87f21-138">Podeu canviar aquesta opció a **Trieu qui pot utilitzar aquesta connexió** i permetre als usuaris que tenen la funció de col·laborador utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="87f21-139">Els col·laboradors no podran visualitzar ni editar la connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="87f21-140">Només veuran el nom de visualització i el tipus en crear una exportació.</span><span class="sxs-lookup"><span data-stu-id="87f21-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="87f21-141">Mitjançant l'ús compartit d'una connexió, permeteu que els col·laboradors utilitzin una connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="87f21-142">Els col·laboradors veuran les connexions compartides quan configurin exportacions.</span><span class="sxs-lookup"><span data-stu-id="87f21-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="87f21-143">Poden administrar totes les exportacions que utilitzin aquesta connexió específica.</span><span class="sxs-lookup"><span data-stu-id="87f21-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="87f21-144">Podeu canviar aquesta configuració mantenint les exportacions que ja han estat definides pels col·laboradors.</span><span class="sxs-lookup"><span data-stu-id="87f21-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="87f21-145">Editar una connexió</span><span class="sxs-lookup"><span data-stu-id="87f21-145">Edit a connection</span></span>

1. <span data-ttu-id="87f21-146">Aneu a **Administració** > **Connexions (versió preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="87f21-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="87f21-147">Aneu a la pestanya **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="87f21-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="87f21-148">Seleccioneu els punts suspensius verticals de la connexió que voleu editar.</span><span class="sxs-lookup"><span data-stu-id="87f21-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="87f21-149">Seleccioneu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="87f21-149">Select **Edit**.</span></span>

1. <span data-ttu-id="87f21-150">Canvieu els valors que voleu actualitzar i seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="87f21-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="87f21-151">Suprimir una connexió</span><span class="sxs-lookup"><span data-stu-id="87f21-151">Remove a connection</span></span>

<span data-ttu-id="87f21-152">Si la connexió que suprimiu s'utilitza amb enriquiments o exportacions, primer les heu de desvincular o suprimir.</span><span class="sxs-lookup"><span data-stu-id="87f21-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="87f21-153">El quadre de diàleg de supressió us guiarà als enriquiments o exportacions rellevants.</span><span class="sxs-lookup"><span data-stu-id="87f21-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="87f21-154">Els enriquiments i les exportacions desvinculats esdevenen inactius.</span><span class="sxs-lookup"><span data-stu-id="87f21-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="87f21-155">Els reactiveu afegint-hi una altra connexió a la pàgina [Enriquiments](enrichment-hub.md) o [Exportacions](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="87f21-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="87f21-156">Aneu a **Administració** > **Connexions (versió preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="87f21-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="87f21-157">Aneu a la pestanya **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="87f21-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="87f21-158">Seleccioneu els punts suspensius verticals de la connexió que voleu eliminar.</span><span class="sxs-lookup"><span data-stu-id="87f21-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="87f21-159">Seleccioneu **Suprimeix** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="87f21-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="87f21-160">Apareix un quadre de diàleg de confirmació.</span><span class="sxs-lookup"><span data-stu-id="87f21-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="87f21-161">Si hi ha enriquiments o exportacions que utilitzen aquesta connexió, seleccioneu el botó per veure què utilitza la connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="87f21-162">**Exportacions:** podeu triar si voleu suprimir o desconnectar les exportacions per poder suprimir la connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="87f21-163">Per desconnectar una exportació, els administradors poden utilitzar l'acció **Desconnecta**.</span><span class="sxs-lookup"><span data-stu-id="87f21-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="87f21-164">Aquesta acció està disponible per a exportacions individuals i múltiples exportacions seleccionades.</span><span class="sxs-lookup"><span data-stu-id="87f21-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="87f21-165">En desconnectar-les, conserveu la configuració de l'exportació, però no s'executarà fins que s'hi afegeixi una altra connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="87f21-166">**Enriquiments**: podeu triar si voleu suprimir o desactivar els enriquiments per poder suprimir la connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="87f21-167">Quan la connexió no té més dependències, torneu a **Administració** > **Connexions** i torneu a provar de suprimir la connexió.</span><span class="sxs-lookup"><span data-stu-id="87f21-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="87f21-168">Per confirmar la supressió, seleccioneu **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="87f21-168">To confirm the deletion select **Remove**.</span></span>

