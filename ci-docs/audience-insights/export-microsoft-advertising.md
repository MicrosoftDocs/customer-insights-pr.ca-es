---
title: Exportar dades del Customer Insights al Microsoft Advertising
description: Apreneu a configurar la connexió i exportar al Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124456"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="16a1b-103">Exportar segments al Microsoft Advertising (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="16a1b-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="16a1b-104">Exporteu els segments del Customer Insights al Microsoft Advertising per crear públics del Customer Match.</span><span class="sxs-lookup"><span data-stu-id="16a1b-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="16a1b-105">Utilitzeu aquests públics per a les campanyes publicitàries.</span><span class="sxs-lookup"><span data-stu-id="16a1b-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="16a1b-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="16a1b-106">Prerequisites</span></span>

-   <span data-ttu-id="16a1b-107">Un [compte del Microsoft Advertising](https://ads.microsoft.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="16a1b-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="16a1b-108">Heu acceptat les condicions d'ús del Customer Match.</span><span class="sxs-lookup"><span data-stu-id="16a1b-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="16a1b-109">[Segments configurats](segments.md) als coneixements del públic.</span><span class="sxs-lookup"><span data-stu-id="16a1b-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="16a1b-110">Els perfils de client unificats als segments exportats contenen un camp amb una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="16a1b-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="16a1b-111">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="16a1b-111">Known limitations</span></span>

- <span data-ttu-id="16a1b-112">Podeu exportar fins a 500 000 perfils per exportació al Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="16a1b-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="16a1b-113">L'exportació al Microsoft Advertising es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="16a1b-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="16a1b-114">L'exportació de fins a 500 000 perfils al Microsoft Advertising pot trigar fins a 10 minuts com a màxim.</span><span class="sxs-lookup"><span data-stu-id="16a1b-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="16a1b-115">Configurar la connexió amb el Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="16a1b-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="16a1b-116">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="16a1b-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="16a1b-117">Seleccioneu **Afegeix una connexió** i trieu **Microsoft Advertising** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="16a1b-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="16a1b-118">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="16a1b-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="16a1b-119">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="16a1b-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="16a1b-120">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="16a1b-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="16a1b-121">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="16a1b-121">Choose who can use this connection.</span></span> <span data-ttu-id="16a1b-122">Per defecte són els administradors.</span><span class="sxs-lookup"><span data-stu-id="16a1b-122">The default is administrators.</span></span> <span data-ttu-id="16a1b-123">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="16a1b-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="16a1b-124">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="16a1b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="16a1b-125">Seleccioneu **Connecta't** per inicialitzar la connexió al Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="16a1b-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="16a1b-126">Seleccioneu **Autentica amb el Microsoft Advertising** i proporcioneu les vostres credencials d'administració per al Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="16a1b-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="16a1b-127">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="16a1b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="16a1b-128">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="16a1b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="16a1b-129">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="16a1b-129">Configure an export</span></span>

<span data-ttu-id="16a1b-130">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="16a1b-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="16a1b-131">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="16a1b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="16a1b-132">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="16a1b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="16a1b-133">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="16a1b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="16a1b-134">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció del Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="16a1b-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="16a1b-135">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="16a1b-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="16a1b-136">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="16a1b-136">Select the segments to export.</span></span> <span data-ttu-id="16a1b-137">Els públics del Customer Match al Microsoft Advertising es creen automàticament amb el nom dels segments seleccionats per a l'exportació.</span><span class="sxs-lookup"><span data-stu-id="16a1b-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="16a1b-138">Cada segment serà un públic diferent al Customer Match.</span><span class="sxs-lookup"><span data-stu-id="16a1b-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="16a1b-139">Introduïu **l'identificador de client i l'identificador de compte de Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="16a1b-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="16a1b-140">Podeu trobar l'identificador de client (`cid`) i l'identificador de compte (`aid`) als paràmetres de l'adreça URL quan inicieu la sessió al Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="16a1b-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="16a1b-141">A la secció **Coincidències de dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat amb l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="16a1b-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="16a1b-142">Cal que exporteu segments al Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="16a1b-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="16a1b-143">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="16a1b-143">Select **Save**.</span></span>

<span data-ttu-id="16a1b-144">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="16a1b-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="16a1b-145">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="16a1b-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="16a1b-146">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="16a1b-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="16a1b-147">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="16a1b-147">Data privacy and compliance</span></span>

<span data-ttu-id="16a1b-148">Quan permeteu al Dynamics 365 Customer Insights transmetre dades al Microsoft Advertising, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals.</span><span class="sxs-lookup"><span data-stu-id="16a1b-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="16a1b-149">Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que el Microsoft Advertising compleixi les obligacions de privadesa o de seguretat que pugueu teniu.</span><span class="sxs-lookup"><span data-stu-id="16a1b-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="16a1b-150">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="16a1b-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="16a1b-151">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per aturar l'ús d'aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="16a1b-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
