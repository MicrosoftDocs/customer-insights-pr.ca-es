---
title: Connector del LiveRamp
description: Apreneu a configurar la connexió i exportar a LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760315"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="f1d84-103">Exportar segments a LiveRamp&reg; (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="f1d84-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="f1d84-104">Activeu les vostres dades a LiveRamp per connectar-vos amb més de 500 plataformes entre digital, social i televisió.</span><span class="sxs-lookup"><span data-stu-id="f1d84-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="f1d84-105">Treballeu amb les dades de LiveRamp per orientar, suprimir i personalitzar les campanyes publicitàries.</span><span class="sxs-lookup"><span data-stu-id="f1d84-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f1d84-106">Requisits previs per a una connexió</span><span class="sxs-lookup"><span data-stu-id="f1d84-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="f1d84-107">Es necessita una subscripció a LiveRamp per utilitzar aquest connector.</span><span class="sxs-lookup"><span data-stu-id="f1d84-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="f1d84-108">Per obtenir una subscripció, [poseu-vos en contacte amb LiveRamp](https://liveramp.com/contact/) directament.</span><span class="sxs-lookup"><span data-stu-id="f1d84-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="f1d84-109">[Més informació sobre la incorporació a LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="f1d84-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="f1d84-110">Configuració de la connexió a LiveRamp</span><span class="sxs-lookup"><span data-stu-id="f1d84-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="f1d84-111">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="f1d84-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f1d84-112">Seleccioneu **Afegeix connexió** i trieu **LiveRamp** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="f1d84-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="f1d84-113">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="f1d84-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f1d84-114">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="f1d84-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f1d84-115">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="f1d84-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f1d84-116">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="f1d84-116">Choose who can use this connection.</span></span> <span data-ttu-id="f1d84-117">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="f1d84-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f1d84-118">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f1d84-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f1d84-119">Proporcioneu un **nom d'usuari** i una **contrasenya** per al vostre compte de FTP segur (SFTP) de LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f1d84-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="f1d84-120">Aquestes credencials poden ser diferents de les vostres credencials d'incorporació de LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f1d84-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="f1d84-121">Seleccioneu **Verifica** per provar la connexió amb LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f1d84-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="f1d84-122">Després de la verificació correcta, proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**.</span><span class="sxs-lookup"><span data-stu-id="f1d84-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="f1d84-123">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="f1d84-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f1d84-124">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="f1d84-124">Configure an export</span></span>

<span data-ttu-id="f1d84-125">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="f1d84-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f1d84-126">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f1d84-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f1d84-127">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="f1d84-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f1d84-128">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="f1d84-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f1d84-129">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f1d84-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="f1d84-130">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="f1d84-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f1d84-131">Al camp **Trieu el vostre identificador de clau**, seleccioneu el **Correu electrònic**, **Nom i adreça** o **Telèfon** per enviar a LiveRamp per a la resolució de la identitat.</span><span class="sxs-lookup"><span data-stu-id="f1d84-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f1d84-132">![Connector de LiveRamp amb l'assignació d'atributs](media/export-liveramp-segments.png "Connector de LiveRamp amb l'assignació d'atributs")</span><span class="sxs-lookup"><span data-stu-id="f1d84-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="f1d84-133">Assigneu els atributs corresponents de l'entitat del client unificat per a l'identificador de clau seleccionat.</span><span class="sxs-lookup"><span data-stu-id="f1d84-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="f1d84-134">Seleccioneu **Afegeix un atribut** per assignar més atributs per enviar-los a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f1d84-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="f1d84-135">Si envieu més atributs d'identificador clau a LiveRamp, és possible que obtingueu una taxa de concordança més alta.</span><span class="sxs-lookup"><span data-stu-id="f1d84-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="f1d84-136">Seleccioneu els segments que voleu exportar a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f1d84-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="f1d84-137">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="f1d84-137">Select **Save**.</span></span>

<span data-ttu-id="f1d84-138">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="f1d84-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f1d84-139">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f1d84-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f1d84-140">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f1d84-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f1d84-141">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="f1d84-141">Data privacy and compliance</span></span>

<span data-ttu-id="f1d84-142">Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a LiveRamp, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="f1d84-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f1d84-143">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que LiveRamp compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="f1d84-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f1d84-144">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f1d84-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f1d84-145">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="f1d84-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
