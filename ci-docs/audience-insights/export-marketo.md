---
title: Exportar dades del Customer Insights a Marketo
description: Apreneu a configurar la connexió i exportar a Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759809"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="43375-103">Exportar segments a Marketo (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="43375-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="43375-104">Exporteu segments de perfils de client unificats per generar campanyes, proporcionar màrqueting per correu electrònic i utilitzar grups específics de clients amb Marketo.</span><span class="sxs-lookup"><span data-stu-id="43375-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="43375-105">Requisits previs per a la connexió</span><span class="sxs-lookup"><span data-stu-id="43375-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="43375-106">Teniu un [compte de Marketo](https://login.marketo.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="43375-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="43375-107">Hi ha llistes a Marketo amb els identificadors corresponents.</span><span class="sxs-lookup"><span data-stu-id="43375-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="43375-108">Per obtenir més informació, vegeu [Llistes de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="43375-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="43375-109">Teniu [segments configurats](segments.md).</span><span class="sxs-lookup"><span data-stu-id="43375-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="43375-110">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="43375-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="43375-111">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="43375-111">Known limitations</span></span>

- <span data-ttu-id="43375-112">Fins a un milió de perfils per exportació a Marketo.</span><span class="sxs-lookup"><span data-stu-id="43375-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="43375-113">L'exportació a Marketo es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="43375-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="43375-114">L'exportació de segments amb un total d'un milió de perfils pot durar fins a 3 hores.</span><span class="sxs-lookup"><span data-stu-id="43375-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="43375-115">El nombre de perfils que podeu exportar a Marketo és limitat i dependrà del contracte que tingueu amb Marketo.</span><span class="sxs-lookup"><span data-stu-id="43375-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="43375-116">Configuració de la connexió a Marketo</span><span class="sxs-lookup"><span data-stu-id="43375-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="43375-117">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="43375-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="43375-118">Seleccioneu **Afegeix connexió** i trieu **Marketo** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="43375-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="43375-119">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="43375-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="43375-120">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="43375-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="43375-121">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="43375-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="43375-122">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="43375-122">Choose who can use this connection.</span></span> <span data-ttu-id="43375-123">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="43375-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="43375-124">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="43375-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="43375-125">Introduïu l'**[ID del client, el Secret del client i el Nom de l'amfitrió de l'extrem REST de Marketo](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="43375-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="43375-126">Seleccioneu **Accepto** per confirmar el **Compliment i privadesa de les dades** i seleccioneu **Connecta't** per inicialitzar la connexió a Marketo.</span><span class="sxs-lookup"><span data-stu-id="43375-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="43375-127">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="43375-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="43375-128">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="43375-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="43375-129">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="43375-129">Configure an export</span></span>

<span data-ttu-id="43375-130">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="43375-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="43375-131">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="43375-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="43375-132">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="43375-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="43375-133">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="43375-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="43375-134">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Marketo.</span><span class="sxs-lookup"><span data-stu-id="43375-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="43375-135">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="43375-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="43375-136">Introduïu l'**[ID de la llista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="43375-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="43375-137">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="43375-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="43375-138">O bé podeu exportar **Nom**, **Cognom**, **Ciutat**, **Província** i **País o Regió** per crear correus electrònics més personalitzats.</span><span class="sxs-lookup"><span data-stu-id="43375-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="43375-139">Seleccioneu **Afegeix un atribut** per assignar aquests camps.</span><span class="sxs-lookup"><span data-stu-id="43375-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="43375-140">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="43375-140">Select the segments you want to export.</span></span> <span data-ttu-id="43375-141">Podeu exportar fins a un total d'un milió de perfils de client a Marketo.</span><span class="sxs-lookup"><span data-stu-id="43375-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="43375-142">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="43375-142">Select **Save**.</span></span>

<span data-ttu-id="43375-143">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="43375-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="43375-144">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="43375-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="43375-145">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="43375-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="43375-146">A Marketo, ara podeu cercar els segments a les [llistes de Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="43375-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="43375-147">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="43375-147">Data privacy and compliance</span></span>

<span data-ttu-id="43375-148">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Marketo, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="43375-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="43375-149">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Marketo compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="43375-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="43375-150">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="43375-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="43375-151">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="43375-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]