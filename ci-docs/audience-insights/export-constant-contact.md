---
title: Exportar dades del Customer Insights a Constant Contact
description: Apreneu a configurar la connexió i exportar a Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760476"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="c44d1-103">Exportar llistes de segments a Constant Contact (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="c44d1-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="c44d1-104">Exporteu segments de perfils de client unificats a Constant Contact i utilitzeu-los per a activitats de màrqueting.</span><span class="sxs-lookup"><span data-stu-id="c44d1-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="c44d1-105">Requisits previs per a una connexió</span><span class="sxs-lookup"><span data-stu-id="c44d1-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="c44d1-106">Teniu un [compte de Constant Contact](https://www.constantcontact.com/account-home) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="c44d1-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c44d1-107">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="c44d1-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c44d1-108">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="c44d1-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c44d1-109">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="c44d1-109">Known limitations</span></span>

- <span data-ttu-id="c44d1-110">Podeu exportar fins a 1 milió de perfils per exportació a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c44d1-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="c44d1-111">L'exportació a Constant Contact es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="c44d1-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="c44d1-112">L'exportació de fins a 1 milió de perfils a Constant Contact pot trigar fins a 1 hora com a màxim.</span><span class="sxs-lookup"><span data-stu-id="c44d1-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="c44d1-113">El nombre de perfils que podeu exportar a Constant Contact depèn i està limitat pel contracte amb Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c44d1-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="c44d1-114">Configuració de la connexió a Constant Contact</span><span class="sxs-lookup"><span data-stu-id="c44d1-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="c44d1-115">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="c44d1-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c44d1-116">Seleccioneu **Afegeix una connexió** i trieu **Constant Contact** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="c44d1-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="c44d1-117">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="c44d1-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c44d1-118">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="c44d1-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c44d1-119">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="c44d1-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c44d1-120">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="c44d1-120">Choose who can use this connection.</span></span> <span data-ttu-id="c44d1-121">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="c44d1-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c44d1-122">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c44d1-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c44d1-123">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="c44d1-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c44d1-124">Seleccioneu **Connecta't** per inicialitzar la connexió a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c44d1-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="c44d1-125">Seleccioneu **Autentica amb AdRoll** i proporcioneu les vostres credencials d'administració per a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c44d1-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="c44d1-126">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c44d1-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c44d1-127">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="c44d1-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c44d1-128">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="c44d1-128">Configure an export</span></span>

<span data-ttu-id="c44d1-129">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="c44d1-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c44d1-130">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c44d1-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c44d1-131">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="c44d1-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c44d1-132">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="c44d1-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c44d1-133">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c44d1-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="c44d1-134">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="c44d1-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c44d1-135">Introduïu l'[**ID de llista de Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="c44d1-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="c44d1-136">Obriu una llista a Constant Contact per trobar l'identificador de llista a l'adreça URL.</span><span class="sxs-lookup"><span data-stu-id="c44d1-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="c44d1-137">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="c44d1-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c44d1-138">Cal que exporteu segments a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c44d1-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="c44d1-139">També podeu exportar el Nom i el Cognom com a camps addicionals per crear missatges de correu electrònic més personalitzats.</span><span class="sxs-lookup"><span data-stu-id="c44d1-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="c44d1-140">Seleccioneu **Afegeix un atribut** per assignar aquests camps.</span><span class="sxs-lookup"><span data-stu-id="c44d1-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c44d1-141">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="c44d1-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="c44d1-142">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="c44d1-142">Select **Save**.</span></span>

<span data-ttu-id="c44d1-143">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="c44d1-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c44d1-144">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c44d1-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c44d1-145">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c44d1-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c44d1-146">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="c44d1-146">Data privacy and compliance</span></span>

<span data-ttu-id="c44d1-147">Quan permeteu al Dynamics 365 Customer Insights transmetre dades a Constant Contact, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals.</span><span class="sxs-lookup"><span data-stu-id="c44d1-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c44d1-148">Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que Constant Contact compleixi les obligacions de privadesa o de seguretat que pugueu teniu.</span><span class="sxs-lookup"><span data-stu-id="c44d1-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c44d1-149">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c44d1-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c44d1-150">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="c44d1-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
