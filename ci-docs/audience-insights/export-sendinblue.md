---
title: Exportar dades del Customer Insights a Sendinblue
description: Més informació sobre com configurar la connexió i l'exportació a Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314580"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="d031f-103">Exportar segments a Sendinblue (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="d031f-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="d031f-104">Exporteu els segments de perfils de client unificats per generar campanyes, proporcionar contingut de màrqueting per correu electrònic i utilitzar grups específics de clients amb Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="d031f-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="d031f-105">Requisits previs per a la connexió</span><span class="sxs-lookup"><span data-stu-id="d031f-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="d031f-106">Teniu un [compte de Sendinblue](https://www.sendinblue.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="d031f-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d031f-107">Hi ha llistes existents a Sendinblue i els ID corresponents.</span><span class="sxs-lookup"><span data-stu-id="d031f-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="d031f-108">Teniu [segments configurats](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d031f-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="d031f-109">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="d031f-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d031f-110">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="d031f-110">Known limitations</span></span>

- <span data-ttu-id="d031f-111">Fins a 1 milió de perfils per exportació a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="d031f-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="d031f-112">L'exportació a Sendinblue es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="d031f-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="d031f-113">L'exportació de segments amb un total d'1 milió de perfils pot tardar fins a 90 minuts.</span><span class="sxs-lookup"><span data-stu-id="d031f-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="d031f-114">El nombre de perfils que podeu exportar a Sendinblue depèn i està limitat pel contracte que tingueu amb Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="d031f-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="d031f-115">Configuració de la connexió a Sendinblue</span><span class="sxs-lookup"><span data-stu-id="d031f-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="d031f-116">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="d031f-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d031f-117">Seleccioneu **Afegeix una connexió** i trieu **Sendinblue** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="d031f-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="d031f-118">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="d031f-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d031f-119">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="d031f-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d031f-120">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="d031f-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d031f-121">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="d031f-121">Choose who can use this connection.</span></span> <span data-ttu-id="d031f-122">Per defecte, només són administradors.</span><span class="sxs-lookup"><span data-stu-id="d031f-122">By default it's only administrators.</span></span> <span data-ttu-id="d031f-123">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d031f-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d031f-124">Introduïu la **[clau de l'API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="d031f-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="d031f-125">Seleccioneu **Accepta** per confirmar la **Privadesa de les dades i conformitat** i seleccioneu **Connecta** per inicialitzar la connexió a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="d031f-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="d031f-126">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d031f-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d031f-127">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="d031f-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d031f-128">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="d031f-128">Configure an export</span></span>

<span data-ttu-id="d031f-129">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="d031f-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d031f-130">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d031f-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d031f-131">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="d031f-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d031f-132">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="d031f-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d031f-133">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="d031f-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="d031f-134">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="d031f-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d031f-135">Introduïu l'**ID de llista de SendinBlue**.</span><span class="sxs-lookup"><span data-stu-id="d031f-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="d031f-136">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="d031f-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="d031f-137">Opcionalment, podeu exportar el **nom**, **cognom** i **telèfon** per crear correus electrònics més personalitzats.</span><span class="sxs-lookup"><span data-stu-id="d031f-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="d031f-138">Seleccioneu **Afegeix un atribut** per assignar aquests camps.</span><span class="sxs-lookup"><span data-stu-id="d031f-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d031f-139">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="d031f-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="d031f-140">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="d031f-140">Select **Save**.</span></span>

<span data-ttu-id="d031f-141">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="d031f-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d031f-142">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d031f-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d031f-143">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d031f-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d031f-144">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="d031f-144">Data privacy and compliance</span></span>

<span data-ttu-id="d031f-145">Quan permeteu que el Dynamics 365 Customer Insights transmeti dades a Sendinblue, permeteu la transferència de dades fora del límit de conformitat per al Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals.</span><span class="sxs-lookup"><span data-stu-id="d031f-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d031f-146">Microsoft transferirà aquestes dades segons la vostra instrucció, però sou responsable d'assegurar que Sendinblue compleixi les obligacions de privadesa o seguretat que tingueu.</span><span class="sxs-lookup"><span data-stu-id="d031f-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d031f-147">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d031f-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d031f-148">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="d031f-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
