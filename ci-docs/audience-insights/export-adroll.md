---
title: Exportar dades del Customer Insights a AdRoll
description: Apreneu a configurar la connexió a AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697062"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="70af1-103">Connector per a AdRoll (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="70af1-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="70af1-104">Exporteu segments de perfils de client unificats a AdRoll i utilitzeu-los per a la publicitat.</span><span class="sxs-lookup"><span data-stu-id="70af1-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="70af1-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="70af1-105">Prerequisites</span></span>

-   <span data-ttu-id="70af1-106">Teniu un [compte d'AdRoll](https://www.adroll.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="70af1-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="70af1-107">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="70af1-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="70af1-108">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="70af1-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="70af1-109">Connecta a AdRoll</span><span class="sxs-lookup"><span data-stu-id="70af1-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="70af1-110">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="70af1-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="70af1-111">A **AdRoll**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="70af1-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="70af1-112">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="70af1-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Subfinestra de configuració per a la connexió d'AdRoll.":::

1. <span data-ttu-id="70af1-114">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="70af1-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="70af1-115">Seleccioneu **Connecta't** per inicialitzar la connexió a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="70af1-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="70af1-116">Seleccioneu **Autenticació amb AdRoll** i indiqueu les vostres credencials d'administrador d'AdRoll.</span><span class="sxs-lookup"><span data-stu-id="70af1-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="70af1-117">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="70af1-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="70af1-118">Introduïu l'**Identificador de l'anunciant d'AdRoll** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="70af1-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="70af1-119">Seleccioneu **Següent** per configurar l'exportació.</span><span class="sxs-lookup"><span data-stu-id="70af1-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="70af1-120">Configurar el connector</span><span class="sxs-lookup"><span data-stu-id="70af1-120">Configure the connector</span></span>

1. <span data-ttu-id="70af1-121">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="70af1-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="70af1-122">Cal que exporteu segments a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="70af1-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="70af1-123">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="70af1-123">Select the segments you want to export.</span></span> <span data-ttu-id="70af1-124">Seleccioneu un segment amb un mínim de 100 membres.</span><span class="sxs-lookup"><span data-stu-id="70af1-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="70af1-125">No podeu exportar segments més petits.</span><span class="sxs-lookup"><span data-stu-id="70af1-125">You can't export smaller segments.</span></span> <span data-ttu-id="70af1-126">A més, la mida màxima d'un segment que s'ha d'exportar és de 250.000 membres per exportació.</span><span class="sxs-lookup"><span data-stu-id="70af1-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="70af1-127">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="70af1-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="70af1-128">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="70af1-128">Export the data</span></span>

<span data-ttu-id="70af1-129">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="70af1-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="70af1-130">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="70af1-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="70af1-131">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="70af1-131">Known limitations</span></span>

- <span data-ttu-id="70af1-132">Podeu exportar fins a un total de 100.000 perfils per exportació a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="70af1-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="70af1-133">No podeu exportar segments amb menys de 100 perfils a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="70af1-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="70af1-134">L'exportació a AdRoll es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="70af1-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="70af1-135">L'exportació de fins a 250.000 perfils a AdRoll pot trigar fins a 10 minuts com a completar-se.</span><span class="sxs-lookup"><span data-stu-id="70af1-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="70af1-136">El nombre de perfils que podeu exportar a AdRoll és limitat i dependrà del contracte que tingueu amb AdRoll.</span><span class="sxs-lookup"><span data-stu-id="70af1-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="70af1-137">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="70af1-137">Data privacy and compliance</span></span>

<span data-ttu-id="70af1-138">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a AdRoll, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="70af1-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="70af1-139">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que AdRoll compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="70af1-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="70af1-140">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="70af1-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="70af1-141">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="70af1-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
