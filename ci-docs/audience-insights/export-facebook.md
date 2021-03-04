---
title: Exportar dades del Customer Insights a l'Administrador d'anuncis del Facebook
description: Més informació sobre com configurar la connexió al Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269962"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="283c2-103">Connector per al Facebook Ads Manager (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="283c2-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="283c2-104">Exporteu els segments de perfils unificats de client al Facebook Ads Manager per crear campanyes a Facebook i a Instagram.</span><span class="sxs-lookup"><span data-stu-id="283c2-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="283c2-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="283c2-105">Prerequisites</span></span>

- <span data-ttu-id="283c2-106">Heu de tenir un [**compte publicitari de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclogui un [**compte empresarial de Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="283c2-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="283c2-107">Heu de ser un administrador del [**compte publicitari de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="283c2-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="283c2-108">Connectar-se al Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="283c2-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="283c2-109">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="283c2-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="283c2-110">A **Facebook Ads Manager**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="283c2-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="283c2-111">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="283c2-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="283c2-112">Seleccioneu **Continua amb Facebook** per iniciar la sessió al vostre compte publicitari de Facebook.</span><span class="sxs-lookup"><span data-stu-id="283c2-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="283c2-113">Activeu el permís **ads_management** un cop us hagueu autenticat amb el Facebook.</span><span class="sxs-lookup"><span data-stu-id="283c2-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="283c2-114">Seleccioneu el **compte publicitari de Facebook** que voleu fer servir.</span><span class="sxs-lookup"><span data-stu-id="283c2-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="283c2-115">Seleccioneu un **Públic personalitzat existent** de la llista desplegable o creeu un **Nou públic personalitzat**.</span><span class="sxs-lookup"><span data-stu-id="283c2-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="283c2-116">Per obtenir més informació, vegeu [**Públics al Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="283c2-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="283c2-117">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="283c2-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="283c2-118">Seleccioneu **Següent** per configurar l'exportació.</span><span class="sxs-lookup"><span data-stu-id="283c2-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="283c2-119">Configurar el connector</span><span class="sxs-lookup"><span data-stu-id="283c2-119">Configure the connector</span></span>

1. <span data-ttu-id="283c2-120">Al camp **Trieu el vostre identificador de clau**, seleccioneu **Correu electrònic**, **Nom i adreça** o **Telèfon** per enviar al Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="283c2-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="283c2-121">Assigneu els atributs corresponents de l'entitat del client unificat per a l'identificador de clau seleccionat.</span><span class="sxs-lookup"><span data-stu-id="283c2-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="283c2-122">[CONSELL] Les millors oportunitats perquè hi hagi una coincidència es produeixen si seleccioneu **Correu electrònic** com a identificador de clau.</span><span class="sxs-lookup"><span data-stu-id="283c2-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="283c2-123">L'addició d'identificadors addicionals podria millorar la coincidència.</span><span class="sxs-lookup"><span data-stu-id="283c2-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="283c2-124">Seleccioneu **Afegeix un atribut** per assignar atributs addicionals per enviar al Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="283c2-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="283c2-125">Els atributs del Facebook Ads Manager s'assignen als noms amigables següents: **FN** = **Nom**, **LN** = **Cognom**, **FI** = **Primera inicial**, **PHONE** = **Telèfon**, **GEN** = **Gènere**, **DOB** = **Data de naixement**, **ST** = **Estat**, **CT** = **Ciutat**, **ZIP** = **Codi postal**, **COUNTRY** = **País/regió**</span><span class="sxs-lookup"><span data-stu-id="283c2-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="283c2-126">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="283c2-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="283c2-127">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="283c2-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="283c2-128">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="283c2-128">Export the data</span></span>

<span data-ttu-id="283c2-129">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="283c2-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="283c2-130">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="283c2-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="283c2-131">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="283c2-131">Known limitations</span></span>

- <span data-ttu-id="283c2-132">Fins a 10 milions de perfils de client per exportació a l'Administrador d'anuncis de Facebook</span><span class="sxs-lookup"><span data-stu-id="283c2-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="283c2-133">L'exportació a l'Administrador d'anuncis de Facebook es limita als segments</span><span class="sxs-lookup"><span data-stu-id="283c2-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="283c2-134">L'exportació de segments amb un total de 10 milions de perfils pot tardar fins a 90 minuts a completar-se</span><span class="sxs-lookup"><span data-stu-id="283c2-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="283c2-135">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="283c2-135">Data privacy and compliance</span></span>

<span data-ttu-id="283c2-136">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a l'Administrador d'anuncis del Facebook, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="283c2-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="283c2-137">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Facebook Ads compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="283c2-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="283c2-138">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="283c2-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="283c2-139">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="283c2-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]