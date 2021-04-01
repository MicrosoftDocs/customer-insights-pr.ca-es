---
title: Connector del LiveRamp
description: Apreneu a exportar dades a LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597545"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="7d35f-103">Connector de LiveRamp&reg; (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="7d35f-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="7d35f-104">Activeu les dades a LiveRamp per connectar-vos amb més de 500 plataformes en ecosistemes digitals, socials i de TV.</span><span class="sxs-lookup"><span data-stu-id="7d35f-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="7d35f-105">Treballeu amb les dades de LiveRamp per orientar, suprimir i personalitzar les campanyes publicitàries.</span><span class="sxs-lookup"><span data-stu-id="7d35f-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d35f-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="7d35f-106">Prerequisites</span></span>

- <span data-ttu-id="7d35f-107">Es necessita una subscripció a LiveRamp per utilitzar aquest connector.</span><span class="sxs-lookup"><span data-stu-id="7d35f-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="7d35f-108">Per obtenir una subscripció, [poseu-vos en contacte amb LiveRamp](https://liveramp.com/contact/) directament.</span><span class="sxs-lookup"><span data-stu-id="7d35f-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="7d35f-109">[Més informació sobre la incorporació a LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="7d35f-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="7d35f-110">Connectar-se a LiveRamp</span><span class="sxs-lookup"><span data-stu-id="7d35f-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="7d35f-111">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="7d35f-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7d35f-112">A la peça de **LiveRamp**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="7d35f-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="7d35f-113">Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="7d35f-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7d35f-114">Proporcioneu un **nom d'usuari** i una **contrasenya** per al vostre compte de FTP segur (SFTP) de LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7d35f-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="7d35f-115">Aquestes credencials poden ser diferents de les vostres credencials d'incorporació de LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7d35f-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="7d35f-116">Seleccioneu **Verifica** per provar la connexió amb LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7d35f-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="7d35f-117">Després de la verificació correcta, proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**.</span><span class="sxs-lookup"><span data-stu-id="7d35f-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="7d35f-118">Seleccioneu **Següent** per configurar el connector de LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7d35f-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="7d35f-119">Configurar el connector</span><span class="sxs-lookup"><span data-stu-id="7d35f-119">Configure the connector</span></span>

1. <span data-ttu-id="7d35f-120">Al camp **Trieu el vostre identificador de clau**, seleccioneu el **Correu electrònic**, **Nom i adreça** o **Telèfon** per enviar a LiveRamp per a la resolució de la identitat.</span><span class="sxs-lookup"><span data-stu-id="7d35f-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="7d35f-121">Assigneu els atributs corresponents de l'entitat del client unificat per a l'identificador de clau seleccionat.</span><span class="sxs-lookup"><span data-stu-id="7d35f-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="7d35f-122">Seleccioneu **Afegeix un atribut** per assignar atributs addicionals per enviar a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7d35f-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="7d35f-123">Si envieu més atributs d'identificador clau a LiveRamp, és possible que obtingueu una taxa de concordança més alta.</span><span class="sxs-lookup"><span data-stu-id="7d35f-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="7d35f-124">Seleccioneu els segments que voleu exportar a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7d35f-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="7d35f-125">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="7d35f-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7d35f-126">![Connector de LiveRamp amb l'assignació d'atributs](media/export-liveramp-segments.png "Connector de LiveRamp amb l'assignació d'atributs")</span><span class="sxs-lookup"><span data-stu-id="7d35f-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7d35f-127">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="7d35f-127">Export the data</span></span>

<span data-ttu-id="7d35f-128">L'exportació començarà en breu si tots els requisits previs per a l'exportació s'han completat.</span><span class="sxs-lookup"><span data-stu-id="7d35f-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="7d35f-129">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7d35f-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="7d35f-130">Una vegada que l'exportació s'hagi completat correctament, podeu iniciar la sessió a la incorporació de LiveRamp per activar i distribuir les dades.</span><span class="sxs-lookup"><span data-stu-id="7d35f-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7d35f-131">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="7d35f-131">Data privacy and compliance</span></span>

<span data-ttu-id="7d35f-132">Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a LiveRamp, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="7d35f-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7d35f-133">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que LiveRamp compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="7d35f-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7d35f-134">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7d35f-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7d35f-135">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="7d35f-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]