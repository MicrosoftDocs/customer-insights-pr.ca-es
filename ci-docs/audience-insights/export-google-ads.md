---
title: Exportar dades del Customer Insights a Google Ads
description: Apreneu a configurar la connexió i exportar a Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759681"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="b2637-103">Exportar segments a Google Ads (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="b2637-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="b2637-104">Exporteu els segments de perfils de client unificats a la llista de públics de Google Ads i utilitzeu-los per anunciar-vos a la Cerca de Google, Gmail, YouTube i la Xarxa de Display de Google.</span><span class="sxs-lookup"><span data-stu-id="b2637-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b2637-105">Requisits previs per a la connexió</span><span class="sxs-lookup"><span data-stu-id="b2637-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="b2637-106">Teniu un [compte de Google Ads](https://ads.google.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="b2637-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b2637-107">Teniu un [testimoni aprovat de Google Ads per a desenvolupadors](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="b2637-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="b2637-108">Compliu els requisits de la [Política de segments de clients](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="b2637-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="b2637-109">Compliu els requisits de les [mides de la llista de remàrqueting](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="b2637-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="b2637-110">Hi ha públics a Google Ads amb els identificadors corresponents.</span><span class="sxs-lookup"><span data-stu-id="b2637-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="b2637-111">Per obtenir més informació, vegeu [Públics de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="b2637-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="b2637-112">Teniu [segments configurats](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b2637-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="b2637-113">Els perfils de client unificats dels segments exportats contenen camps que representen una adreça electrònica, el nom i el cognom.</span><span class="sxs-lookup"><span data-stu-id="b2637-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b2637-114">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="b2637-114">Known limitations</span></span>

- <span data-ttu-id="b2637-115">Fins a un milió de perfils per exportació a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="b2637-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="b2637-116">L'exportació a Google Ads es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="b2637-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="b2637-117">L'exportació de segments amb un total d'un milió de perfils pot durar fins a 5 minuts a causa de les possibles limitacions del proveïdor.</span><span class="sxs-lookup"><span data-stu-id="b2637-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="b2637-118">Les coincidències a Google Ads poden trigar fins a 48 hores.</span><span class="sxs-lookup"><span data-stu-id="b2637-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="b2637-119">Configuració de la connexió a Google Ads</span><span class="sxs-lookup"><span data-stu-id="b2637-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="b2637-120">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="b2637-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b2637-121">Seleccioneu **Afegeix connexió** i trieu **Google Ads** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="b2637-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="b2637-122">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="b2637-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b2637-123">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="b2637-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b2637-124">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="b2637-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b2637-125">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="b2637-125">Choose who can use this connection.</span></span> <span data-ttu-id="b2637-126">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="b2637-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b2637-127">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b2637-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b2637-128">Introduïu el vostre **[ID de client de Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="b2637-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="b2637-129">Introduïu el **[testimoni de desenvolupador autoritzat de Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="b2637-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="b2637-130">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="b2637-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b2637-131">Seleccioneu **Autenticació amb el Google Ads** i indiqueu les vostres credencials de Google Ads.</span><span class="sxs-lookup"><span data-stu-id="b2637-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="b2637-132">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b2637-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b2637-133">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="b2637-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="b2637-134">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="b2637-134">Configure an export</span></span>

<span data-ttu-id="b2637-135">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="b2637-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b2637-136">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b2637-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b2637-137">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="b2637-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b2637-138">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="b2637-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b2637-139">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Google Ads.</span><span class="sxs-lookup"><span data-stu-id="b2637-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="b2637-140">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="b2637-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b2637-141">Introduïu el vostre **[Identificador de públic de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i seleccioneu **Connecta't** per inicialitzar la connexió a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="b2637-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="b2637-142">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="b2637-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b2637-143">Repetiu els mateixos passos per als camps **Nom** i **Cognom**.</span><span class="sxs-lookup"><span data-stu-id="b2637-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="b2637-144">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="b2637-144">Select the segments you want to export.</span></span> <span data-ttu-id="b2637-145">Podeu exportar fins a un total d'un milió de perfils de client a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="b2637-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="b2637-146">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="b2637-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b2637-147">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b2637-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b2637-148">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b2637-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b2637-149">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="b2637-149">Data privacy and compliance</span></span>

<span data-ttu-id="b2637-150">Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a Google Ads, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="b2637-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b2637-151">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Google Ads compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="b2637-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b2637-152">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b2637-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b2637-153">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="b2637-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
