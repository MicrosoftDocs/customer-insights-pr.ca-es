---
title: Exportar dades del Customer Insights a Omnisend
description: Apreneu a configurar la connexió i exportar a Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124457"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="de223-103">Exportar segments a Omnisend (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="de223-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="de223-104">Exporteu segments de perfils de client unificats a Omnisend i utilitzeu-los per a activitats de màrqueting.</span><span class="sxs-lookup"><span data-stu-id="de223-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="de223-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="de223-105">Prerequisites</span></span>

-   <span data-ttu-id="de223-106">Teniu un [compte d'Omnisend](https://www.omnisend.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="de223-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="de223-107">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="de223-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="de223-108">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="de223-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="de223-109">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="de223-109">Known limitations</span></span>

- <span data-ttu-id="de223-110">Podeu exportar fins a 1 milió de perfils per exportació a Omnisend i pot trigar fins a 4 hores a completar-se.</span><span class="sxs-lookup"><span data-stu-id="de223-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="de223-111">L'exportació a Omnisend es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="de223-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="de223-112">El nombre de perfils que podeu exportar a Omnisend depèn del vostre contracte amb Omnisend.</span><span class="sxs-lookup"><span data-stu-id="de223-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="de223-113">Configuració de la connexió a Omnisend</span><span class="sxs-lookup"><span data-stu-id="de223-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="de223-114">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="de223-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="de223-115">Seleccioneu **Afegeix connexió** i trieu **Omnisend** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="de223-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="de223-116">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="de223-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="de223-117">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="de223-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="de223-118">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="de223-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="de223-119">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="de223-119">Choose who can use this connection.</span></span> <span data-ttu-id="de223-120">Per defecte, només són administradors.</span><span class="sxs-lookup"><span data-stu-id="de223-120">By default it's only administrators.</span></span> <span data-ttu-id="de223-121">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="de223-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="de223-122">Introduïu la [clau de l'API d'Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="de223-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="de223-123">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="de223-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="de223-124">Seleccioneu **Connecta't** per inicialitzar la connexió a Omnisend.</span><span class="sxs-lookup"><span data-stu-id="de223-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="de223-125">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="de223-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="de223-126">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="de223-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="de223-127">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="de223-127">Configure an export</span></span>

<span data-ttu-id="de223-128">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="de223-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="de223-129">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="de223-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="de223-130">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="de223-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="de223-131">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="de223-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="de223-132">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Omnisend.</span><span class="sxs-lookup"><span data-stu-id="de223-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="de223-133">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="de223-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="de223-134">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="de223-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="de223-135">Cal que exporteu segments a Omnisend.</span><span class="sxs-lookup"><span data-stu-id="de223-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="de223-136">O bé podeu exportar Nom, Cognom, Adreça, País o Regió, Província, Ciutat i Codi postal per crear correus electrònics més personalitzats.</span><span class="sxs-lookup"><span data-stu-id="de223-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="de223-137">Seleccioneu **Afegeix un atribut** per assignar aquests camps.</span><span class="sxs-lookup"><span data-stu-id="de223-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="de223-138">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="de223-138">Select **Save**.</span></span>

<span data-ttu-id="de223-139">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="de223-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="de223-140">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="de223-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="de223-141">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="de223-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="de223-142">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="de223-142">Data privacy and compliance</span></span>

<span data-ttu-id="de223-143">Quan permeteu al Dynamics 365 Customer Insights transmetre dades a Omnisend, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals.</span><span class="sxs-lookup"><span data-stu-id="de223-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="de223-144">Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que Omnisend compleixi les obligacions de privadesa o de seguretat que pugueu teniu.</span><span class="sxs-lookup"><span data-stu-id="de223-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="de223-145">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="de223-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="de223-146">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="de223-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
