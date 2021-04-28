---
title: Exportar dades del Customer Insights a amfitrions d'SFTP
description: Apreneu a configurar la connexió i exportar a una ubicació SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760407"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="2dd1c-103">Exportar llistes de segments i altres dades a SFTP (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="2dd1c-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="2dd1c-104">Utilitzeu les dades de client en aplicacions de tercers exportant-les a una ubicació de Protocol de transferència segura de fitxers (SFTP).</span><span class="sxs-lookup"><span data-stu-id="2dd1c-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="2dd1c-105">Requisits previs per a la connexió</span><span class="sxs-lookup"><span data-stu-id="2dd1c-105">Prerequisites for connection</span></span>

- <span data-ttu-id="2dd1c-106">Disponibilitat d'un amfitrió SFTP i les credencials corresponents.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2dd1c-107">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="2dd1c-107">Known limitations</span></span>

- <span data-ttu-id="2dd1c-108">El temps d'execució d'una exportació depèn del rendiment del sistema.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="2dd1c-109">Us recomanem dos nuclis de CPU i 1 Gb de memòria com a configuració mínima del vostre servidor.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="2dd1c-110">L'exportació d'entitats amb fins a 100 milions de perfils de clients pot tardar 90 minuts quan s'utilitza la configuració mínima recomanada de dos nuclis de CPU i 1 Gb de memòria.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="2dd1c-111">Configuració de la connexió a SFTP</span><span class="sxs-lookup"><span data-stu-id="2dd1c-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="2dd1c-112">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2dd1c-113">Seleccioneu **Afegeix connexió** i trieu **SFTP** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="2dd1c-114">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2dd1c-115">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2dd1c-116">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2dd1c-117">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-117">Choose who can use this connection.</span></span> <span data-ttu-id="2dd1c-118">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2dd1c-119">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2dd1c-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2dd1c-120">Proporcioneu un **Nom d'usuari**, una **Contrasenya**, un **Nom de l'amfitrió** i una **Carpeta d'exportació** per al vostre compte SFTP.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="2dd1c-121">Seleccioneu **Verifica** per provar la connexió.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="2dd1c-122">Trieu si voleu exportar les dades **Comprimides** o **Descomprimides** i el **delimitador de camp** per als fitxers exportats.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="2dd1c-123">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2dd1c-124">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2dd1c-125">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="2dd1c-125">Configure an export</span></span>

<span data-ttu-id="2dd1c-126">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2dd1c-127">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2dd1c-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2dd1c-128">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2dd1c-129">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2dd1c-130">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció SFTP.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="2dd1c-131">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2dd1c-132">Seleccioneu les entitats, per exemple, els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2dd1c-133">Cada entitat seleccionada es divideix en fins a cinc fitxers de sortida en exportar-se.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="2dd1c-134">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-134">Select **Save**.</span></span>

<span data-ttu-id="2dd1c-135">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2dd1c-136">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2dd1c-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2dd1c-137">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2dd1c-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2dd1c-138">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="2dd1c-138">Data privacy and compliance</span></span>

<span data-ttu-id="2dd1c-139">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a través d'SFTP, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2dd1c-140">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que la destinació de l'exportació compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2dd1c-141">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2dd1c-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2dd1c-142">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
