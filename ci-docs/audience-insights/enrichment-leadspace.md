---
title: Enriquiment de perfils d'empresa amb l'enriquiment de tercers de Leadspace
description: Informació general sobre l'enriquiment de tercers de Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668711"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="c93c2-103">Enriquiment de perfils d'empresa amb el Leadspace (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="c93c2-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="c93c2-104">Leadspace és una empresa de ciència de dades que proporciona una plataforma de dades de clients B2B.</span><span class="sxs-lookup"><span data-stu-id="c93c2-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="c93c2-105">Permet enriquir les dades als clients amb perfils de clients unificats per a les empreses.</span><span class="sxs-lookup"><span data-stu-id="c93c2-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="c93c2-106">Els enriquiments inclouen atributs addicionals com ara la mida de l'empresa, la ubicació, el sector, etc.</span><span class="sxs-lookup"><span data-stu-id="c93c2-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c93c2-107">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="c93c2-107">Prerequisites</span></span>

<span data-ttu-id="c93c2-108">Per configurar el Leadspace, cal complir els requisits previs següents:</span><span class="sxs-lookup"><span data-stu-id="c93c2-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c93c2-109">Teniu una llicència activa de Leadspace i la "clau perpètua" (anomenada **Testimoni del Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="c93c2-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="c93c2-110">Poseu-vos en contacte directament amb [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) per obtenir informació detallada sobre el seu producte.</span><span class="sxs-lookup"><span data-stu-id="c93c2-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="c93c2-111">Teniu permisos d'[Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="c93c2-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="c93c2-112">Tenir [perfils de clients unificats](customer-profiles.md) per a empreses.</span><span class="sxs-lookup"><span data-stu-id="c93c2-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="c93c2-113">Configuració</span><span class="sxs-lookup"><span data-stu-id="c93c2-113">Configuration</span></span>

1. <span data-ttu-id="c93c2-114">A les conclusions del públic, aneu a **Dades** > **Enriquiment**.</span><span class="sxs-lookup"><span data-stu-id="c93c2-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="c93c2-115">Seleccioneu **Enriqueix les meves dades** a la peça de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c93c2-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla de la peça de Leadspace.":::

1. <span data-ttu-id="c93c2-117">Seleccioneu **Comença** i, a continuació, introduïu un **Testimoni del Leadspace** actiu (clau perpètua).</span><span class="sxs-lookup"><span data-stu-id="c93c2-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="c93c2-118">Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**.</span><span class="sxs-lookup"><span data-stu-id="c93c2-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="c93c2-119">Seleccioneu **Connexió al Leadspace** per confirmar totes dues entrades.</span><span class="sxs-lookup"><span data-stu-id="c93c2-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="c93c2-120">Seleccioneu **Assigna les dades** i definiu els camps dels perfils unificats que s'hauran d'utilitzar per cercar les dades coincidents de l'empresa de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c93c2-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="c93c2-121">El camp **Nom de l'empresa** és obligatori.</span><span class="sxs-lookup"><span data-stu-id="c93c2-121">The **Name of company** field is required.</span></span> <span data-ttu-id="c93c2-122">Per augmentar la precisió de la coincidència, es poden afegir fins a dos camps més, **Lloc web de l'empresa** i **Ubicació de l'empresa**.</span><span class="sxs-lookup"><span data-stu-id="c93c2-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Subfinestra d'assignació de camps de Leadspace.":::
   
1. <span data-ttu-id="c93c2-124">Seleccioneu **Aplica** per completar l'assignació de camps.</span><span class="sxs-lookup"><span data-stu-id="c93c2-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="c93c2-125">Seleccioneu **Executa** per enriquir els perfils d'empresa.</span><span class="sxs-lookup"><span data-stu-id="c93c2-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="c93c2-126">La durada de l'enriquiment dependrà del nombre de perfils de client unificats.</span><span class="sxs-lookup"><span data-stu-id="c93c2-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c93c2-127">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="c93c2-127">Enrichment results</span></span>

<span data-ttu-id="c93c2-128">Després d'actualitzar l'enriquiment, podeu revisar les dades d'empresa enriquides recentment a [Els meus enriquiments](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="c93c2-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="c93c2-129">Podeu trobar-hi l'hora de l'última actualització i el nombre de perfils enriquits.</span><span class="sxs-lookup"><span data-stu-id="c93c2-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c93c2-130">Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.</span><span class="sxs-lookup"><span data-stu-id="c93c2-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="c93c2-131">Per obtenir més informació, vegeu [API del Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="c93c2-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c93c2-132">Passos següents</span><span class="sxs-lookup"><span data-stu-id="c93c2-132">Next steps</span></span>

<span data-ttu-id="c93c2-133">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="c93c2-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c93c2-134">Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="c93c2-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c93c2-135">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="c93c2-135">Data privacy and compliance</span></span>

<span data-ttu-id="c93c2-136">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Leadspace, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="c93c2-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c93c2-137">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Leadspace compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="c93c2-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c93c2-138">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c93c2-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c93c2-139">L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="c93c2-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>