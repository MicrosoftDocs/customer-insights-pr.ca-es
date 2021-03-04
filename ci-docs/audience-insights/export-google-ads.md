---
title: Exportar dades del Customer Insights a Google Ads
description: Apreneu a configurar la connexió a Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268950"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="cb822-103">Connector per a Google Ads (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="cb822-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="cb822-104">Exporteu els segments de perfils de client unificats a la llista de públics de Google Ads i utilitzeu-los per anunciar-vos a la Cerca de Google, Gmail, YouTube i la Xarxa de Display de Google.</span><span class="sxs-lookup"><span data-stu-id="cb822-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="cb822-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="cb822-105">Prerequisites</span></span>

-   <span data-ttu-id="cb822-106">Teniu un [compte de Google Ads](https://ads.google.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="cb822-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cb822-107">Hi ha públics a Google Ads amb els identificadors corresponents.</span><span class="sxs-lookup"><span data-stu-id="cb822-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="cb822-108">Per obtenir més informació, vegeu [Públics de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="cb822-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="cb822-109">Teniu [segments configurats](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cb822-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="cb822-110">Els perfils de client unificats dels segments exportats contenen camps que representen una adreça electrònica, el nom i el cognom.</span><span class="sxs-lookup"><span data-stu-id="cb822-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="cb822-111">Connecta a Google Ads</span><span class="sxs-lookup"><span data-stu-id="cb822-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="cb822-112">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="cb822-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cb822-113">A **Google Ads**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="cb822-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="cb822-114">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="cb822-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="cb822-115">Introduïu el vostre **[ID de client de Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="cb822-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="cb822-116">Introduïu el **[testimoni de desenvolupador autoritzat de Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="cb822-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="cb822-117">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="cb822-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cb822-118">Introduïu el vostre **[Identificador de públic de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i seleccioneu **Connecta't** per inicialitzar la connexió a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cb822-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="cb822-119">Seleccioneu **Autenticació amb el Google Ads** i indiqueu les vostres credencials de Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cb822-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="cb822-120">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cb822-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Captura de pantalla d'exportació per a la connexió a Google Ads":::

1. <span data-ttu-id="cb822-122">Seleccioneu **Següent** per configurar l'exportació.</span><span class="sxs-lookup"><span data-stu-id="cb822-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="cb822-123">Configurar el connector</span><span class="sxs-lookup"><span data-stu-id="cb822-123">Configure the connector</span></span>

1. <span data-ttu-id="cb822-124">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="cb822-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="cb822-125">Repetiu els mateixos passos per als camps **Nom** i **Cognom**.</span><span class="sxs-lookup"><span data-stu-id="cb822-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="cb822-126">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="cb822-126">Select the segments you want to export.</span></span> <span data-ttu-id="cb822-127">Podeu exportar fins a un total d'un milió de perfils de client a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cb822-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="cb822-128">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="cb822-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cb822-129">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="cb822-129">Export the data</span></span>

<span data-ttu-id="cb822-130">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cb822-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cb822-131">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cb822-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cb822-132">A Google Ads, ara podeu cercar els segments als [públics de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="cb822-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cb822-133">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="cb822-133">Known limitations</span></span>

- <span data-ttu-id="cb822-134">Fins a un milió de perfils per exportació a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cb822-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="cb822-135">L'exportació a Google Ads es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="cb822-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="cb822-136">L'exportació de segments amb un total d'un milió de perfils pot durar fins a 5 minuts a causa de les possibles limitacions del proveïdor.</span><span class="sxs-lookup"><span data-stu-id="cb822-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="cb822-137">Les coincidències a Google Ads poden trigar fins a 48 hores.</span><span class="sxs-lookup"><span data-stu-id="cb822-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cb822-138">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="cb822-138">Data privacy and compliance</span></span>

<span data-ttu-id="cb822-139">Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a Google Ads, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="cb822-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cb822-140">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Google Ads compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="cb822-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="cb822-141">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cb822-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cb822-142">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="cb822-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]