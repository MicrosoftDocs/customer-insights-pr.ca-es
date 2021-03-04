---
title: Exportar dades del Customer Insights a Marketo
description: Apreneu a configurar la connexió a Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267069"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="ebb95-103">Connector per a Marketo (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="ebb95-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="ebb95-104">Exporteu segments de perfils de client unificats per generar campanyes, proporcionar màrqueting per correu electrònic i utilitzar grups específics de clients amb Marketo.</span><span class="sxs-lookup"><span data-stu-id="ebb95-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ebb95-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="ebb95-105">Prerequisites</span></span>

-   <span data-ttu-id="ebb95-106">Teniu un [compte de Marketo](https://login.marketo.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="ebb95-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ebb95-107">Hi ha llistes a Marketo amb els identificadors corresponents.</span><span class="sxs-lookup"><span data-stu-id="ebb95-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="ebb95-108">Per obtenir més informació, vegeu [Llistes de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="ebb95-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="ebb95-109">Teniu [segments configurats](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ebb95-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="ebb95-110">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="ebb95-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="ebb95-111">Connectar-se a Marketo</span><span class="sxs-lookup"><span data-stu-id="ebb95-111">Connect to Marketo</span></span>

1. <span data-ttu-id="ebb95-112">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="ebb95-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ebb95-113">A **Marketo**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="ebb95-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="ebb95-114">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="ebb95-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ebb95-115">Introduïu l'**[ID del client, el Secret del client i el Nom de l'amfitrió de l'extrem REST de Marketo](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="ebb95-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="ebb95-116">Introduïu l'**[ID de la llista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="ebb95-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="ebb95-117">Seleccioneu **Accepto** per confirmar el **Compliment i privadesa de les dades** i seleccioneu **Connecta't** per inicialitzar la connexió a Marketo.</span><span class="sxs-lookup"><span data-stu-id="ebb95-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="ebb95-118">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ebb95-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Captura de pantalla d'exportació per a la connexió a Marketo":::

1. <span data-ttu-id="ebb95-120">Seleccioneu **Següent** per configurar l'exportació.</span><span class="sxs-lookup"><span data-stu-id="ebb95-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ebb95-121">Configurar el connector</span><span class="sxs-lookup"><span data-stu-id="ebb95-121">Configure the connector</span></span>

1. <span data-ttu-id="ebb95-122">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="ebb95-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="ebb95-123">També podeu exportar el **Nom**, el **Cognom**, la **Ciutat**, l'**Estat** i el **País/regió** com a camps addicionals per crear missatges de correu electrònic més personalitzats.</span><span class="sxs-lookup"><span data-stu-id="ebb95-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="ebb95-124">Seleccioneu **Afegeix un atribut** per assignar aquests camps.</span><span class="sxs-lookup"><span data-stu-id="ebb95-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ebb95-125">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="ebb95-125">Select the segments you want to export.</span></span> <span data-ttu-id="ebb95-126">Podeu exportar fins a un total d'un milió de perfils de client a Marketo.</span><span class="sxs-lookup"><span data-stu-id="ebb95-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Seleccioneu els camps i els segments que voleu exportar a Marketo":::

1. <span data-ttu-id="ebb95-128">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="ebb95-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ebb95-129">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="ebb95-129">Export the data</span></span>

<span data-ttu-id="ebb95-130">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ebb95-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ebb95-131">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ebb95-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ebb95-132">A Marketo, ara podeu cercar els segments a les [llistes de Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="ebb95-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ebb95-133">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="ebb95-133">Known limitations</span></span>

- <span data-ttu-id="ebb95-134">Fins a un milió de perfils per exportació a Marketo.</span><span class="sxs-lookup"><span data-stu-id="ebb95-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="ebb95-135">L'exportació a Marketo es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="ebb95-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="ebb95-136">L'exportació de segments amb un total d'un milió de perfils pot durar fins a 3 hores.</span><span class="sxs-lookup"><span data-stu-id="ebb95-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="ebb95-137">El nombre de perfils que podeu exportar a Marketo és limitat i dependrà del contracte que tingueu amb Marketo.</span><span class="sxs-lookup"><span data-stu-id="ebb95-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ebb95-138">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="ebb95-138">Data privacy and compliance</span></span>

<span data-ttu-id="ebb95-139">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Marketo, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="ebb95-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ebb95-140">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Marketo compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="ebb95-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ebb95-141">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ebb95-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ebb95-142">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="ebb95-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]