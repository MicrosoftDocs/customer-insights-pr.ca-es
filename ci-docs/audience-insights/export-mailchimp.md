---
title: Exportar dades del Customer Insights a Mailchimp
description: Apreneu a configurar la connexió i exportar a Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976143"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="c2761-103">Exportar llistes de segments a Mailchimp (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="c2761-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="c2761-104">Exporteu segments de perfils de client unificats a Mailchimp per crear butlletins i campanyes de correu electrònic.</span><span class="sxs-lookup"><span data-stu-id="c2761-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="c2761-105">Requisits previs per a la connexió</span><span class="sxs-lookup"><span data-stu-id="c2761-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="c2761-106">Teniu un [compte de Mailchimp](https://mailchimp.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="c2761-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c2761-107">Hi ha públics a Mailchimp amb els identificadors corresponents.</span><span class="sxs-lookup"><span data-stu-id="c2761-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="c2761-108">Per obtenir més informació, vegeu [Públics de Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="c2761-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="c2761-109">Teniu [segments configurats](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c2761-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="c2761-110">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="c2761-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c2761-111">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="c2761-111">Known limitations</span></span>

- <span data-ttu-id="c2761-112">Fins a un milió de perfils per exportació a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c2761-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="c2761-113">L'exportació a Mailchimp es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="c2761-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="c2761-114">L'exportació de segments amb 1 milió de perfils pot trigar fins a tres hores.</span><span class="sxs-lookup"><span data-stu-id="c2761-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="c2761-115">El nombre de perfils que podeu exportar a Mailchimp és limitat i dependrà del contracte que tingueu amb Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c2761-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="c2761-116">Configuració de la connexió a Mailchimp</span><span class="sxs-lookup"><span data-stu-id="c2761-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="c2761-117">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="c2761-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c2761-118">Seleccioneu **Afegeix connexió** i trieu **Autopilot** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="c2761-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="c2761-119">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="c2761-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c2761-120">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="c2761-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c2761-121">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="c2761-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c2761-122">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="c2761-122">Choose who can use this connection.</span></span> <span data-ttu-id="c2761-123">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="c2761-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c2761-124">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c2761-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c2761-125">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="c2761-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c2761-126">Seleccioneu **Connecta't** per inicialitzar la connexió a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c2761-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="c2761-127">Seleccioneu **Autentica amb el Mailchimp** i indiqueu les vostres credencials de Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c2761-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="c2761-128">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c2761-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c2761-129">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="c2761-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="c2761-130">Configurar el connector</span><span class="sxs-lookup"><span data-stu-id="c2761-130">Configure the connector</span></span>

<span data-ttu-id="c2761-131">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="c2761-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c2761-132">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c2761-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c2761-133">Vés a **Dades**> **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="c2761-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="c2761-134">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="c2761-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c2761-135">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c2761-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="c2761-136">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="c2761-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c2761-137">Introduïu l'**[Identificador de públic de Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="c2761-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="c2761-138">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="c2761-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="c2761-139">O bé podeu exportar **Nom** i **Cognom** per crear correus electrònics més personalitzats.</span><span class="sxs-lookup"><span data-stu-id="c2761-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="c2761-140">Seleccioneu **Afegeix un atribut** per assignar aquests camps.</span><span class="sxs-lookup"><span data-stu-id="c2761-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c2761-141">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="c2761-141">Select the segments you want to export.</span></span> <span data-ttu-id="c2761-142">Podeu exportar fins a un total d'un milió de perfils de client a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c2761-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="c2761-143">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="c2761-143">Select **Save**.</span></span>

<span data-ttu-id="c2761-144">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="c2761-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c2761-145">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c2761-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c2761-146">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c2761-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c2761-147">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="c2761-147">Data privacy and compliance</span></span>

<span data-ttu-id="c2761-148">Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a Mailchimp, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="c2761-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c2761-149">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Mailchimp compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="c2761-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c2761-150">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c2761-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c2761-151">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="c2761-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
