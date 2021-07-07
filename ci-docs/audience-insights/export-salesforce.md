---
title: Exportar dades del Customer Insights a Salesforce Marketing Cloud
description: Més informació sobre com configurar la connexió i l'exportació a Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314579"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="847cb-103">Exportar segments i altres dades a Salesforce Marketing Cloud (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="847cb-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="847cb-104">Utilitzeu les dades de clients a Salesforce Marketing Cloud exportant-les a través d'una ubicació del protocol Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="847cb-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="847cb-105">Requisits previs per a la connexió</span><span class="sxs-lookup"><span data-stu-id="847cb-105">Prerequisites for connection</span></span>

- <span data-ttu-id="847cb-106">Disponibilitat d'un amfitrió SFTP i les credencials d'administració corresponents.</span><span class="sxs-lookup"><span data-stu-id="847cb-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="847cb-107">Com configurar ubicacions SFTP per a Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="847cb-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="847cb-108">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="847cb-108">Known limitations</span></span>

- <span data-ttu-id="847cb-109">El temps d'execució d'una exportació depèn del rendiment del sistema.</span><span class="sxs-lookup"><span data-stu-id="847cb-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="847cb-110">Us recomanem dos nuclis de CPU i 1 Gb de memòria com a configuració mínima del vostre servidor.</span><span class="sxs-lookup"><span data-stu-id="847cb-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="847cb-111">L'exportació d'entitats amb fins a 100 milions de perfils de client pot tardar 90 minuts quan s'utilitza la configuració mínima recomanada.</span><span class="sxs-lookup"><span data-stu-id="847cb-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="847cb-112">Configurar la connexió a Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="847cb-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="847cb-113">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="847cb-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="847cb-114">Seleccioneu **Afegeix una connexió** i trieu **Salesforce Marketing Cloud** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="847cb-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="847cb-115">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="847cb-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="847cb-116">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="847cb-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="847cb-117">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="847cb-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="847cb-118">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="847cb-118">Choose who can use this connection.</span></span> <span data-ttu-id="847cb-119">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="847cb-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="847cb-120">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="847cb-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="847cb-121">Proporcioneu un **Nom d'usuari**, una **Contrasenya**, un **Nom de l'amfitrió** i una **Carpeta d'exportació** per al vostre compte SFTP.</span><span class="sxs-lookup"><span data-stu-id="847cb-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="847cb-122">Seleccioneu **Verifica** per provar la connexió.</span><span class="sxs-lookup"><span data-stu-id="847cb-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="847cb-123">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="847cb-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="847cb-124">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="847cb-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="847cb-125">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="847cb-125">Configure an export</span></span>

<span data-ttu-id="847cb-126">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="847cb-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="847cb-127">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="847cb-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="847cb-128">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="847cb-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="847cb-129">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="847cb-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="847cb-130">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció SFTP.</span><span class="sxs-lookup"><span data-stu-id="847cb-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="847cb-131">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="847cb-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="847cb-132">Trieu si voleu exportar les dades **Comprimides** o **Descomprimides** i el **delimitador de camp** per als fitxers exportats.</span><span class="sxs-lookup"><span data-stu-id="847cb-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="847cb-133">Seleccioneu les entitats, per exemple, els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="847cb-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="847cb-134">Cada entitat seleccionada es divideix en fins a cinc fitxers de sortida en exportar-se.</span><span class="sxs-lookup"><span data-stu-id="847cb-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="847cb-135">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="847cb-135">Select **Save**.</span></span>

<span data-ttu-id="847cb-136">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="847cb-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="847cb-137">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="847cb-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="847cb-138">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="847cb-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="847cb-139">Importar dades del Customer Insights de la ubicació SFTP a Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="847cb-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="847cb-140">Creeu [extensions de dades a Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) per importar el fitxer de dades del Customer Insights des de la ubicació SFTP.</span><span class="sxs-lookup"><span data-stu-id="847cb-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="847cb-141">[Importeu les dades de la ubicació SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) a l'extensió de dades de Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="847cb-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="847cb-142">Configureu l'automatització per importar les dades a les extensions de dades.</span><span class="sxs-lookup"><span data-stu-id="847cb-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="847cb-143">Més informació sobre les [automatitzacions de supressió de fitxers i les automatitzacions planificades](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="847cb-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="847cb-144">Definiu una [automatització de supressió de fitxers](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) o una [automatització planificada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="847cb-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="847cb-145">Aquí teniu un exemple d'una [automatització amb SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="847cb-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="847cb-146">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="847cb-146">Data privacy and compliance</span></span>

<span data-ttu-id="847cb-147">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a través d'SFTP, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="847cb-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="847cb-148">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que la destinació de l'exportació compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="847cb-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="847cb-149">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="847cb-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="847cb-150">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="847cb-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
