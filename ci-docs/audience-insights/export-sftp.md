---
title: Exportar dades del Customer Insights a amfitrions d'SFTP
description: Més informació sobre com configurar la connexió a un amfitrió SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267986"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="ca619-103">Connector per a SFTP (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="ca619-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="ca619-104">Per utilitzar les dades dels vostres clients en aplicacions de tercers, exporteu-les a un amfitrió del protocol de transferència segura de fitxers (SFTP).</span><span class="sxs-lookup"><span data-stu-id="ca619-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca619-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="ca619-105">Prerequisites</span></span>

- <span data-ttu-id="ca619-106">Disponibilitat d'un amfitrió SFTP i les credencials corresponents.</span><span class="sxs-lookup"><span data-stu-id="ca619-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="ca619-107">Connecta a SFTP</span><span class="sxs-lookup"><span data-stu-id="ca619-107">Connect to SFTP</span></span>

1. <span data-ttu-id="ca619-108">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="ca619-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ca619-109">A **SFTP**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="ca619-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="ca619-110">Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="ca619-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ca619-111">Proporcioneu un **Nom d'usuari**, una **Contrasenya**, un **Nom de l'amfitrió** i una **Carpeta d'exportació** per al vostre compte SFTP.</span><span class="sxs-lookup"><span data-stu-id="ca619-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="ca619-112">Seleccioneu **Verifica** per provar la connexió.</span><span class="sxs-lookup"><span data-stu-id="ca619-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="ca619-113">Després d'haver realitzat una verificació correcta, trieu si voleu exportar les dades **Comprimides** o **Sense comprimir** i seleccioneu el **delimitador de camp** per als fitxers exportats.</span><span class="sxs-lookup"><span data-stu-id="ca619-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="ca619-114">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="ca619-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ca619-115">Seleccioneu **Següent** per començar a configurar l'exportació.</span><span class="sxs-lookup"><span data-stu-id="ca619-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="ca619-116">Configurar l'exportació</span><span class="sxs-lookup"><span data-stu-id="ca619-116">Configure the export</span></span>

1. <span data-ttu-id="ca619-117">Seleccioneu les entitats, per exemple, els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="ca619-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ca619-118">Cada entitat seleccionada tindrà fins a cinc fitxers de sortida en exportar-se.</span><span class="sxs-lookup"><span data-stu-id="ca619-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="ca619-119">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="ca619-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ca619-120">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="ca619-120">Export the data</span></span>

<span data-ttu-id="ca619-121">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ca619-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ca619-122">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ca619-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ca619-123">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="ca619-123">Known limitations</span></span>

- <span data-ttu-id="ca619-124">El temps d'execució d'una exportació depèn del rendiment del sistema.</span><span class="sxs-lookup"><span data-stu-id="ca619-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="ca619-125">Us recomanem dos nuclis de CPU i 1 Gb de memòria com a configuració mínima del vostre servidor.</span><span class="sxs-lookup"><span data-stu-id="ca619-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="ca619-126">L'exportació d'entitats amb fins a 100 milions de perfils de clients pot tardar 90 minuts quan s'utilitza la configuració mínima recomanada de dos nuclis de CPU i 1 Gb de memòria.</span><span class="sxs-lookup"><span data-stu-id="ca619-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ca619-127">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="ca619-127">Data privacy and compliance</span></span>

<span data-ttu-id="ca619-128">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a través d'SFTP, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="ca619-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ca619-129">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que la destinació de l'exportació compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="ca619-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ca619-130">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ca619-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ca619-131">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="ca619-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]