---
title: Exportar dades del Customer Insights al Dynamics 365 Marketing
description: Apreneu a configurar la connexió i exportar a Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976788"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="6a66e-103">Ús de segments al Dynamics 365 Marketing (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="6a66e-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6a66e-104">Utilitzeu [segments](segments.md) per generar campanyes i posar-vos en contacte amb grups específics de clients amb el Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="6a66e-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="6a66e-105">Per obtenir més informació, vegeu [Utilitzar segments del Dynamics 365 Customer Insights amb el Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="6a66e-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="6a66e-106">Requisit previ per a la connexió</span><span class="sxs-lookup"><span data-stu-id="6a66e-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="6a66e-107">Els registres de contacte han d'estar presents al Dynamics 365 Marketing per poder exportar un segment del Customer Insights al Marketing.</span><span class="sxs-lookup"><span data-stu-id="6a66e-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="6a66e-108">Llegiu més informació sobre com ingerir contactes al [Dynamics 365 Marketing mitjançant el Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="6a66e-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="6a66e-109">L'exportació de segments de les conclusions del públic al Marketing no crearà registres de contacte nous a les instàncies del Marketing.</span><span class="sxs-lookup"><span data-stu-id="6a66e-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="6a66e-110">Els registres de contacte del Marketing s'han d'ingerir a les conclusions del públic i s'han d'utilitzar com a font de dades.</span><span class="sxs-lookup"><span data-stu-id="6a66e-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="6a66e-111">També s'han d'incloure a l'entitat Client unificada per assignar els identificadors de client als identificadors de contacte abans d'exportar els segments.</span><span class="sxs-lookup"><span data-stu-id="6a66e-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="6a66e-112">Configuració de la connexió a Marketing</span><span class="sxs-lookup"><span data-stu-id="6a66e-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="6a66e-113">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6a66e-114">Seleccioneu **Afegeix connexió** i trieu **Dynamics 365 Marketing** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="6a66e-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="6a66e-115">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6a66e-116">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="6a66e-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6a66e-117">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="6a66e-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6a66e-118">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="6a66e-118">Choose who can use this connection.</span></span> <span data-ttu-id="6a66e-119">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="6a66e-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6a66e-120">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6a66e-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6a66e-121">Introduïu l'adreça URL del Marketing de l'organització al camp **Adreça del servidor**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="6a66e-122">A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="6a66e-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="6a66e-123">Assigneu un camp d'ID de client a l'ID de contacte del Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6a66e-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="6a66e-124">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="6a66e-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="6a66e-125">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="6a66e-125">Configure an export</span></span>

<span data-ttu-id="6a66e-126">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="6a66e-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6a66e-127">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6a66e-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6a66e-128">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6a66e-129">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6a66e-130">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="6a66e-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="6a66e-131">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="6a66e-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6a66e-132">Trieu un o diversos segments.</span><span class="sxs-lookup"><span data-stu-id="6a66e-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="6a66e-133">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="6a66e-133">Select **Save**.</span></span>

<span data-ttu-id="6a66e-134">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="6a66e-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6a66e-135">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6a66e-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6a66e-136">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6a66e-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
