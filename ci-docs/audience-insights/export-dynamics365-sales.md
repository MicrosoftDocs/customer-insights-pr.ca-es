---
title: Exportar dades del Customer Insights al Dynamics 365 Sales
description: Apreneu a configurar la connexió i exportar a Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976214"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="32af9-103">Ús de segments al Dynamics 365 Sales (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="32af9-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="32af9-104">Utilitzeu les dades dels vostres clients per crear llistes de màrqueting, fer un seguiment de fluxos de treball i enviar promocions amb el Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="32af9-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="32af9-105">Requisit previ per a la connexió</span><span class="sxs-lookup"><span data-stu-id="32af9-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="32af9-106">Els registres de contacte han d'estar presents al Dynamics 365 Sales per poder exportar un segment del Customer Insights al Sales.</span><span class="sxs-lookup"><span data-stu-id="32af9-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="32af9-107">Llegiu més informació sobre com ingerir contactes al [Dynamics 365 Sales mitjançant el Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="32af9-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="32af9-108">L'exportació de segments de les conclusions del públic al Sales no crearà registres de contacte nous a les instàncies del Sales.</span><span class="sxs-lookup"><span data-stu-id="32af9-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="32af9-109">Els registres de contacte del Sales s'han d'ingerir a les conclusions del públic i s'han d'utilitzar com a font de dades.</span><span class="sxs-lookup"><span data-stu-id="32af9-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="32af9-110">També s'han d'incloure a l'entitat Client unificada per assignar els identificadors de client als identificadors de contacte abans d'exportar els segments.</span><span class="sxs-lookup"><span data-stu-id="32af9-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="32af9-111">Configuració de la connexió a Sales</span><span class="sxs-lookup"><span data-stu-id="32af9-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="32af9-112">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="32af9-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="32af9-113">Seleccioneu **Afegeix connexió** i trieu **Dynamics 365 Sales** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="32af9-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="32af9-114">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="32af9-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="32af9-115">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="32af9-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="32af9-116">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="32af9-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="32af9-117">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="32af9-117">Choose who can use this connection.</span></span> <span data-ttu-id="32af9-118">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="32af9-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="32af9-119">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="32af9-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="32af9-120">Introduïu l'adreça URL del Sales de l'organització al camp **Adreça del servidor**.</span><span class="sxs-lookup"><span data-stu-id="32af9-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="32af9-121">A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="32af9-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="32af9-122">Assigneu un camp d'ID de client a l'ID de contacte del Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="32af9-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="32af9-123">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="32af9-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="32af9-124">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="32af9-124">Configure an export</span></span>

<span data-ttu-id="32af9-125">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="32af9-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="32af9-126">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="32af9-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="32af9-127">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="32af9-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="32af9-128">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="32af9-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="32af9-129">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="32af9-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="32af9-130">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="32af9-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="32af9-131">Trieu un o diversos segments.</span><span class="sxs-lookup"><span data-stu-id="32af9-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="32af9-132">Seleccioneu **Desa**</span><span class="sxs-lookup"><span data-stu-id="32af9-132">Select **Save**</span></span>

<span data-ttu-id="32af9-133">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="32af9-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="32af9-134">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="32af9-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="32af9-135">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="32af9-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
