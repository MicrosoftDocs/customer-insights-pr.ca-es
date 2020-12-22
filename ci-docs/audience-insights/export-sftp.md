---
title: Exportar dades del Customer Insights a amfitrions d'SFTP
description: Més informació sobre com configurar la connexió a un amfitrió SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643491"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="3ebbd-103">Connector per a SFTP (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="3ebbd-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="3ebbd-104">Per utilitzar les dades dels vostres clients en aplicacions de tercers, exporteu-les a un amfitrió del protocol de transferència segura de fitxers (SFTP).</span><span class="sxs-lookup"><span data-stu-id="3ebbd-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ebbd-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="3ebbd-105">Prerequisites</span></span>

- <span data-ttu-id="3ebbd-106">Disponibilitat d'un amfitrió SFTP i de les credencials corresponents.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="3ebbd-107">Connectar-se a SFTP</span><span class="sxs-lookup"><span data-stu-id="3ebbd-107">Connect to SFTP</span></span>

1. <span data-ttu-id="3ebbd-108">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3ebbd-109">A **SFTP**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="3ebbd-110">Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3ebbd-111">Proporcioneu un **Nom d'usuari**, una **Contrasenya** i un **Nom de l'amfitrió** per al vostre compte d'SFTP.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="3ebbd-112">Exemple: Si la carpeta arrel del servidor d'SFTP és /root/folder, i voleu que les dades s'exportin a /root/folder/ci_export_destination_folder, l'amfitrió haurà de ser sftp://<adreça_del_servidor>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="3ebbd-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="3ebbd-113">Seleccioneu **Verifica** per provar la connexió.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="3ebbd-114">Després de la verificació correcta, trieu si voleu exportar les dades **Comprimides** o **Descomprimides** i seleccioneu el **delimitador de camp** per als fitxers exportats.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="3ebbd-115">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3ebbd-116">Seleccioneu **Següent** per començar a configurar l'exportació.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="3ebbd-117">Configurar la connexió</span><span class="sxs-lookup"><span data-stu-id="3ebbd-117">Configure the connection</span></span>

1. <span data-ttu-id="3ebbd-118">Seleccioneu els **atributs del client** que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="3ebbd-119">Podeu exportar un o diversos atributs.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="3ebbd-120">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-120">Select **Next**.</span></span>

1. <span data-ttu-id="3ebbd-121">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="3ebbd-122">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3ebbd-123">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="3ebbd-123">Export the data</span></span>

<span data-ttu-id="3ebbd-124">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3ebbd-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3ebbd-125">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3ebbd-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3ebbd-126">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="3ebbd-126">Data privacy and compliance</span></span>

<span data-ttu-id="3ebbd-127">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a través d'SFTP, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3ebbd-128">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que la destinació de l'exportació compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3ebbd-129">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3ebbd-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3ebbd-130">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="3ebbd-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
