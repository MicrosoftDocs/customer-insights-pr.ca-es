---
title: Exportar dades del Customer Insights a SendGrid
description: Apreneu a configurar la connexió a SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268720"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="82559-103">Connector per a SendGrid (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="82559-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="82559-104">Exporteu segments de perfils de client unificats a les llistes de contactes de SendGrid i utilitzeu-los per a les campanyes i el màrqueting per correu electrònic a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="82559-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="82559-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="82559-105">Prerequisites</span></span>

-   <span data-ttu-id="82559-106">Teniu un [compte de SendGrid](https://sendgrid.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="82559-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="82559-107">Hi ha llistes de contactes a SendGrid i els identificadors corresponents.</span><span class="sxs-lookup"><span data-stu-id="82559-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="82559-108">Per obtenir més informació, vegeu [SendGrid: administració de contactes](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="82559-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="82559-109">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="82559-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="82559-110">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="82559-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="82559-111">Connectar-se a SendGrid</span><span class="sxs-lookup"><span data-stu-id="82559-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="82559-112">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="82559-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="82559-113">A **SendGrid**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="82559-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="82559-114">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="82559-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Subfinestra de configuració d'exportació a SendGrid.":::

1. <span data-ttu-id="82559-116">Introduïu la **Clau de l'API de SendGrid** [Clau de l'API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="82559-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="82559-117">Introduïu l'**[ID de la llista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="82559-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="82559-118">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="82559-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="82559-119">Seleccioneu **Connecta't** per inicialitzar la connexió a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="82559-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="82559-120">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="82559-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="82559-121">Seleccioneu **Següent** per configurar l'exportació.</span><span class="sxs-lookup"><span data-stu-id="82559-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="82559-122">Configurar el connector</span><span class="sxs-lookup"><span data-stu-id="82559-122">Configure the connector</span></span>

1. <span data-ttu-id="82559-123">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="82559-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="82559-124">Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom**, el **Cognom**, el **País o regió**, l'**Estat**, la **Ciutat** i el **Codi postal**.</span><span class="sxs-lookup"><span data-stu-id="82559-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="82559-125">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="82559-125">Select the segments you want to export.</span></span> <span data-ttu-id="82559-126">Es recomana **no exportar més de 100.000 perfils de clients en total** a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="82559-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="82559-127">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="82559-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="82559-128">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="82559-128">Export the data</span></span>

<span data-ttu-id="82559-129">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="82559-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="82559-130">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="82559-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="82559-131">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="82559-131">Known limitations</span></span>

- <span data-ttu-id="82559-132">Fins a 100.000 perfils en total a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="82559-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="82559-133">L'exportació a SendGrid es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="82559-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="82559-134">L'exportació de fins a 100.000 perfils a SendGrid pot tardar unes hores a completar-se.</span><span class="sxs-lookup"><span data-stu-id="82559-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="82559-135">El nombre de perfils que podeu exportar a SendGrid és limitat i dependrà del contracte que tingueu amb SendGrid.</span><span class="sxs-lookup"><span data-stu-id="82559-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="82559-136">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="82559-136">Data privacy and compliance</span></span>

<span data-ttu-id="82559-137">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a SendGrid, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="82559-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="82559-138">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que SendGrid compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="82559-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="82559-139">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="82559-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="82559-140">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="82559-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]