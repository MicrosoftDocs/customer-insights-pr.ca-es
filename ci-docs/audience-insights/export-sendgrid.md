---
title: Exportar dades del Customer Insights a SendGrid
description: Apreneu a configurar la connexió i exportar a SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759753"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="91547-103">Exportar segments a SendGrid (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="91547-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="91547-104">Exporteu segments de perfils de client unificats a les llistes de contactes de SendGrid i utilitzeu-los per a les campanyes i el màrqueting per correu electrònic a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="91547-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="91547-105">Requisits previs per a una connexió</span><span class="sxs-lookup"><span data-stu-id="91547-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="91547-106">Teniu un [compte de SendGrid](https://sendgrid.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="91547-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="91547-107">Hi ha llistes de contactes a SendGrid i els identificadors corresponents.</span><span class="sxs-lookup"><span data-stu-id="91547-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="91547-108">Per obtenir més informació, vegeu [SendGrid: administració de contactes](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="91547-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="91547-109">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="91547-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="91547-110">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="91547-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="91547-111">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="91547-111">Known limitations</span></span>

- <span data-ttu-id="91547-112">Fins a 100.000 perfils en total a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="91547-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="91547-113">L'exportació a SendGrid es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="91547-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="91547-114">L'exportació de fins a 100.000 perfils a SendGrid pot tardar unes hores a completar-se.</span><span class="sxs-lookup"><span data-stu-id="91547-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="91547-115">El nombre de perfils que podeu exportar a SendGrid és limitat i dependrà del contracte que tingueu amb SendGrid.</span><span class="sxs-lookup"><span data-stu-id="91547-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="91547-116">Configuració de la connexió a SendGrid</span><span class="sxs-lookup"><span data-stu-id="91547-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="91547-117">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="91547-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="91547-118">Seleccioneu **Afegeix connexió** i trieu **SendGrid** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="91547-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="91547-119">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="91547-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="91547-120">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="91547-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="91547-121">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="91547-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="91547-122">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="91547-122">Choose who can use this connection.</span></span> <span data-ttu-id="91547-123">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="91547-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="91547-124">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="91547-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="91547-125">Introduïu la **Clau de l'API de SendGrid** [Clau de l'API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="91547-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="91547-126">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="91547-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="91547-127">Seleccioneu **Connecta't** per inicialitzar la connexió a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="91547-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="91547-128">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="91547-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="91547-129">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="91547-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="91547-130">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="91547-130">Configure an export</span></span>

<span data-ttu-id="91547-131">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="91547-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="91547-132">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="91547-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="91547-133">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="91547-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="91547-134">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="91547-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="91547-135">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció SendGrid.</span><span class="sxs-lookup"><span data-stu-id="91547-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="91547-136">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="91547-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="91547-137">Introduïu l'**[ID de la llista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="91547-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="91547-138">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="91547-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="91547-139">Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom**, el **Cognom**, el **País o regió**, l'**Estat**, la **Ciutat** i el **Codi postal**.</span><span class="sxs-lookup"><span data-stu-id="91547-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="91547-140">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="91547-140">Select the segments you want to export.</span></span> <span data-ttu-id="91547-141">Es recomana **no exportar més de 100.000 perfils de clients en total** a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="91547-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="91547-142">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="91547-142">Select **Save**.</span></span>

<span data-ttu-id="91547-143">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="91547-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="91547-144">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="91547-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="91547-145">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="91547-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="91547-146">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="91547-146">Data privacy and compliance</span></span>

<span data-ttu-id="91547-147">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a SendGrid, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="91547-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="91547-148">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que SendGrid compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="91547-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="91547-149">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="91547-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="91547-150">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="91547-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]