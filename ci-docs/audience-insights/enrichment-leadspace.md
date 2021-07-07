---
title: Enriquiment de perfils d'empresa amb l'enriquiment de tercers de Leadspace
description: Informació general sobre l'enriquiment de tercers de Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305190"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="c8cf1-103">Enriquiment de perfils d'empresa amb el Leadspace (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="c8cf1-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="c8cf1-104">Leadspace és una empresa de ciència de dades que proporciona una plataforma de dades de clients B2B.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="c8cf1-105">Permet enriquir les dades als clients amb perfils de clients unificats per a les empreses.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="c8cf1-106">Els enriquiments inclouen més atributs, com ara la mida de l'empresa, la ubicació, el sector, etc.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c8cf1-107">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="c8cf1-107">Prerequisites</span></span>

<span data-ttu-id="c8cf1-108">Per configurar el Leadspace, cal complir els requisits previs següents:</span><span class="sxs-lookup"><span data-stu-id="c8cf1-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c8cf1-109">Teniu una llicència activa del Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="c8cf1-110">Tenir [perfils de clients unificats](customer-profiles.md) per a empreses.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="c8cf1-111">Un administrador ja ha configurat una connexió del Leadspace o teniu permisos d'[administrador](permissions.md#administrator) i la "clau perpètua" (anomenada **testimoni del Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="c8cf1-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="c8cf1-112">Poseu-vos en contacte directament amb [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) per obtenir informació sobre el producte.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="c8cf1-113">Configurar l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="c8cf1-113">Configure the enrichment</span></span>

1. <span data-ttu-id="c8cf1-114">A les conclusions del públic, aneu a **Dades** > **Enriquiment**.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="c8cf1-115">Seleccioneu **Enriqueix les meves dades** a la peça Leadspace i seleccioneu **Comença**.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla de la peça de Leadspace.":::

1. <span data-ttu-id="c8cf1-117">Seleccioneu una [connexió](connections.md) a la llista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="c8cf1-118">Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="c8cf1-119">Si sou administrador, podeu crear una connexió seleccionant **Afegeix una connexió** i triant **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="c8cf1-120">Seleccioneu **Connecta't a Leadspace** per confirmar la selecció de la connexió.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="c8cf1-121">Seleccioneu **Següent** i trieu el **Conjunt de dades de client** que voleu enriquir amb les dades de l'empresa des de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="c8cf1-122">Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. <span data-ttu-id="c8cf1-124">Seleccioneu **Següent** i definiu els tipus de camps dels perfils unificats que s'utilitzen per cercar dades empresarials coincidents de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="c8cf1-125">El camp **Nom de l'empresa** és obligatori.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-125">The **Name of company** field is required.</span></span> <span data-ttu-id="c8cf1-126">Per augmentar la precisió de la coincidència, es poden afegir fins a dos camps més, **Lloc web de l'empresa** i **Ubicació de l'empresa**.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Subfinestra d'assignació de camps de Leadspace.":::

1. <span data-ttu-id="c8cf1-128">Seleccioneu **Següent** per completar l'assignació de camp.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="c8cf1-129">Proporcioneu un nom per a l'enriquiment i seleccioneu **Desa l'enriquiment** després de revisar les vostres opcions.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="c8cf1-130">Configurar la connexió per al Leadspace</span><span class="sxs-lookup"><span data-stu-id="c8cf1-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="c8cf1-131">Heu de ser administrador per configurar les connexions.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c8cf1-132">Seleccioneu **Afegeix una connexió** en configurar un enriquiment *o* aneu a **Administració** > **Connexions** i seleccioneu **Configuració** a la peça Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="c8cf1-133">Seleccioneu **Introducció**.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="c8cf1-134">Introduïu un nom per a la connexió al quadre **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c8cf1-135">Proporcioneu un testimoni vàlid del Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="c8cf1-136">Reviseu i proporcioneu el vostre consentiment per a la **Privadesa de les dades i conformitat** seleccionant **Accepta**.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="c8cf1-137">Seleccioneu **Verifica** per validar la configuració.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c8cf1-138">Després de completar la verificació, seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Pàgina de configuració de la connexió del Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="c8cf1-140">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="c8cf1-140">Enrichment results</span></span>

<span data-ttu-id="c8cf1-141">Després d'actualitzar l'enriquiment, podeu revisar les dades d'empresa enriquides recentment a [Els meus enriquiments](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="c8cf1-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="c8cf1-142">Podeu trobar-hi l'hora de l'última actualització i el nombre de perfils enriquits.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c8cf1-143">Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="c8cf1-144">Per obtenir més informació, vegeu [API del Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="c8cf1-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8cf1-145">Passos següents</span><span class="sxs-lookup"><span data-stu-id="c8cf1-145">Next steps</span></span>

<span data-ttu-id="c8cf1-146">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c8cf1-147">Creeu [segments](segments.md) i [mesures](measures.md) i, fins i tot, [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c8cf1-148">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="c8cf1-148">Data privacy and compliance</span></span>

<span data-ttu-id="c8cf1-149">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Leadspace, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c8cf1-150">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Leadspace compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c8cf1-151">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c8cf1-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c8cf1-152">L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="c8cf1-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
