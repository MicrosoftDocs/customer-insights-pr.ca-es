---
title: Exportar dades del Customer Insights a Mailchimp
description: Apreneu a configurar la connexió a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267161"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="6db9e-103">Connector per a Mailchimp (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="6db9e-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="6db9e-104">Exporteu segments de perfils de client unificats a Mailchimp per crear butlletins i campanyes de correu electrònic.</span><span class="sxs-lookup"><span data-stu-id="6db9e-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6db9e-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="6db9e-105">Prerequisites</span></span>

-   <span data-ttu-id="6db9e-106">Teniu un [compte de Mailchimp](https://mailchimp.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="6db9e-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6db9e-107">Hi ha públics a Mailchimp amb els identificadors corresponents.</span><span class="sxs-lookup"><span data-stu-id="6db9e-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="6db9e-108">Per obtenir més informació, vegeu [Públics de Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="6db9e-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="6db9e-109">Teniu [segments configurats](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6db9e-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="6db9e-110">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="6db9e-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="6db9e-111">Connecta al Mailchimp</span><span class="sxs-lookup"><span data-stu-id="6db9e-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="6db9e-112">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="6db9e-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6db9e-113">A **Mailchimp**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="6db9e-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="6db9e-114">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="6db9e-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6db9e-115">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="6db9e-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6db9e-116">Introduïu el vostre **[Identificador de públic del Mailchimp](https://mailchimp.com/help/find-audience-id/)** i seleccioneu **Connecta't** per inicialitzar la connexió a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="6db9e-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="6db9e-117">Seleccioneu **Autentica amb el Mailchimp** i indiqueu les vostres credencials de Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="6db9e-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="6db9e-118">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6db9e-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Captura de pantalla d'exportació per a la connexió a Mailchimp":::

1. <span data-ttu-id="6db9e-120">Seleccioneu **Següent** per configurar l'exportació.</span><span class="sxs-lookup"><span data-stu-id="6db9e-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6db9e-121">Configurar el connector</span><span class="sxs-lookup"><span data-stu-id="6db9e-121">Configure the connector</span></span>

1. <span data-ttu-id="6db9e-122">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="6db9e-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="6db9e-123">També podeu exportar el **Nom** i el **Cognom** com a camps addicionals per crear missatges de correu electrònic més personalitzats.</span><span class="sxs-lookup"><span data-stu-id="6db9e-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="6db9e-124">Seleccioneu **Afegeix un atribut** per assignar aquests camps.</span><span class="sxs-lookup"><span data-stu-id="6db9e-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="6db9e-125">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="6db9e-125">Select the segments you want to export.</span></span> <span data-ttu-id="6db9e-126">Podeu exportar fins a un total d'un milió de perfils de client a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="6db9e-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Seleccioneu els camps i els segments que voleu exportar a Mailchimp":::

1. <span data-ttu-id="6db9e-128">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="6db9e-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6db9e-129">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="6db9e-129">Export the data</span></span>

<span data-ttu-id="6db9e-130">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6db9e-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6db9e-131">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6db9e-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6db9e-132">A Mailchimp, ara podeu cercar els segments als [públics de Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="6db9e-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6db9e-133">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="6db9e-133">Known limitations</span></span>

- <span data-ttu-id="6db9e-134">Fins a un milió de perfils per exportació a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="6db9e-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="6db9e-135">L'exportació a Mailchimp es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="6db9e-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="6db9e-136">L'exportació de segments amb un total d'un milió de perfils pot durar fins a tres hores a causa de les possibles limitacions del proveïdor.</span><span class="sxs-lookup"><span data-stu-id="6db9e-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="6db9e-137">El nombre de perfils que podeu exportar a Mailchimp és limitat i dependrà del contracte que tingueu amb Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="6db9e-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6db9e-138">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="6db9e-138">Data privacy and compliance</span></span>

<span data-ttu-id="6db9e-139">Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a Mailchimp, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="6db9e-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6db9e-140">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Mailchimp compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="6db9e-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6db9e-141">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6db9e-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6db9e-142">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="6db9e-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]