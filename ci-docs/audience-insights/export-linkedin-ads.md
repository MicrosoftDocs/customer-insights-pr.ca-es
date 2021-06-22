---
title: Exportar dades del Customer Insights a LinkedIn Ads
description: Apreneu a configurar la connexió i exportar a LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124458"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="42a29-103">Exportar segments a LinkedIn Ads (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="42a29-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="42a29-104">Exporteu segments de perfils de client unificats a LinkedIn Ads per crear públics coincidents.</span><span class="sxs-lookup"><span data-stu-id="42a29-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="42a29-105">Utilitzeu els públics coincidents per a la destinació de l'empresa i la destinació de contactes.</span><span class="sxs-lookup"><span data-stu-id="42a29-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="42a29-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="42a29-106">Prerequisites</span></span>

-   <span data-ttu-id="42a29-107">Teniu un [compte de LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="42a29-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="42a29-108">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="42a29-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="42a29-109">Els perfils de client als segments exportats contenen un camp amb una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="42a29-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="42a29-110">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="42a29-110">Known limitations</span></span>

- <span data-ttu-id="42a29-111">Podeu exportar fins a 100 000 perfils per exportació a LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="42a29-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="42a29-112">L'exportació a LinkedIn Ads es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="42a29-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="42a29-113">L'exportació de fins a 100 000 perfils a LinkedIn Ads pot trigar fins a 10 minuts com a màxim.</span><span class="sxs-lookup"><span data-stu-id="42a29-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="42a29-114">Configurar la connexió a LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="42a29-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="42a29-115">A les conclusions del públic, aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="42a29-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="42a29-116">Seleccioneu **Afegeix connexió** i trieu **LinkedIn Ads** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="42a29-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="42a29-117">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="42a29-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="42a29-118">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="42a29-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="42a29-119">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="42a29-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="42a29-120">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="42a29-120">Choose who can use this connection.</span></span> <span data-ttu-id="42a29-121">Si no feu cap acció, el valor per defecte és administradors.</span><span class="sxs-lookup"><span data-stu-id="42a29-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="42a29-122">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="42a29-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="42a29-123">Proporcioneu [l'identificador de compte del LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="42a29-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="42a29-124">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="42a29-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="42a29-125">Seleccioneu **Connecta't** per inicialitzar la connexió a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="42a29-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="42a29-126">Seleccioneu **Autentica amb LinkedIn** i proporcioneu les vostres credencials d'administrador per a LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="42a29-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="42a29-127">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="42a29-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="42a29-128">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="42a29-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="42a29-129">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="42a29-129">Configure an export</span></span>

<span data-ttu-id="42a29-130">Podeu configurar una exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="42a29-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="42a29-131">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="42a29-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="42a29-132">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="42a29-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="42a29-133">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="42a29-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="42a29-134">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="42a29-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="42a29-135">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="42a29-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="42a29-136">Trieu si voleu exportar les dades per fer [segmentació de contactes](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [segmentació d'empreses](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) a LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="42a29-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="42a29-137">A la secció **Coincidències de dades**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="42a29-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="42a29-138">Cal que exporteu segments a LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="42a29-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="42a29-139">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="42a29-139">Select the segments you want to export.</span></span> <span data-ttu-id="42a29-140">Els públics coincidents al LinkedIn Campaign Manager es crearan automàticament amb el nom dels segments que heu seleccionat per exportar.</span><span class="sxs-lookup"><span data-stu-id="42a29-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="42a29-141">Cada segment serà un públic coincident diferent.</span><span class="sxs-lookup"><span data-stu-id="42a29-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="42a29-142">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="42a29-142">Select **Save**.</span></span>

<span data-ttu-id="42a29-143">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="42a29-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="42a29-144">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="42a29-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="42a29-145">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="42a29-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="42a29-146">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="42a29-146">Data privacy and compliance</span></span>

<span data-ttu-id="42a29-147">Quan permeteu al Dynamics 365 Customer Insights transmetre dades a LinkedIn Ads, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals.</span><span class="sxs-lookup"><span data-stu-id="42a29-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="42a29-148">Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que LinkedIn Ads compleixi les obligacions de privadesa o de seguretat que pugueu teniu.</span><span class="sxs-lookup"><span data-stu-id="42a29-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="42a29-149">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="42a29-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="42a29-150">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per aturar l'ús d'aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="42a29-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
