---
title: Exportar dades del Customer Insights a Autopilot
description: Apreneu a configurar la connexió a Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269226"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="0a72d-103">Connector per a Autopilot (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="0a72d-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="0a72d-104">Exporteu segments de perfils de client unificats a Autopilot i utilitzeu-los per al màrqueting per correu electrònic a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0a72d-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0a72d-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="0a72d-105">Prerequisites</span></span>

-   <span data-ttu-id="0a72d-106">Teniu un [compte d'Autopilot](https://www.autopilothq.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="0a72d-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0a72d-107">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="0a72d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0a72d-108">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="0a72d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="0a72d-109">Connectar-se a Autopilot</span><span class="sxs-lookup"><span data-stu-id="0a72d-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="0a72d-110">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="0a72d-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0a72d-111">A **Autopilot**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="0a72d-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="0a72d-112">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="0a72d-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Subfinestra de configuració per a la connexió d'Autopilot.":::

1. <span data-ttu-id="0a72d-114">Introduïu la **Clau de l'API d'Autopilot** [Clau de l'API d'Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="0a72d-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="0a72d-115">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="0a72d-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0a72d-116">Seleccioneu **Connecta't** per inicialitzar la connexió a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0a72d-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="0a72d-117">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0a72d-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0a72d-118">Seleccioneu **Següent** per configurar l'exportació.</span><span class="sxs-lookup"><span data-stu-id="0a72d-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0a72d-119">Configurar el connector</span><span class="sxs-lookup"><span data-stu-id="0a72d-119">Configure the connector</span></span>

1. <span data-ttu-id="0a72d-120">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="0a72d-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0a72d-121">Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom** i el **Cognom**.</span><span class="sxs-lookup"><span data-stu-id="0a72d-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="0a72d-122">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="0a72d-122">Select the segments you want to export.</span></span> <span data-ttu-id="0a72d-123">Es recomana **no exportar més de 100.000 perfils de clients en total** a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0a72d-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="0a72d-124">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="0a72d-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0a72d-125">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="0a72d-125">Export the data</span></span>

<span data-ttu-id="0a72d-126">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0a72d-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0a72d-127">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0a72d-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0a72d-128">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="0a72d-128">Known limitations</span></span>

- <span data-ttu-id="0a72d-129">Podeu exportar fins a un total de 100.000 perfils a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0a72d-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="0a72d-130">L'exportació a Autopilot es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="0a72d-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="0a72d-131">L'exportació de fins a 100.000 perfils a Autopilot pot tardar unes hores a completar-se.</span><span class="sxs-lookup"><span data-stu-id="0a72d-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0a72d-132">El nombre de perfils que podeu exportar a Autopilot és limitat i dependrà del contracte que tingueu amb Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0a72d-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0a72d-133">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="0a72d-133">Data privacy and compliance</span></span>

<span data-ttu-id="0a72d-134">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Autopilot, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="0a72d-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0a72d-135">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Autopilot compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="0a72d-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0a72d-136">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0a72d-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0a72d-137">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="0a72d-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]