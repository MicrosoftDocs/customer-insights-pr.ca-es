---
title: Exportar dades del Customer Insights al Dynamics 365 Sales
description: Més informació sobre com configurar la connexió al Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268996"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="b35f8-103">Connector per al Dynamics 365 Sales (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="b35f8-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b35f8-104">Utilitzeu les dades dels vostres clients per crear llistes de màrqueting, fer un seguiment de fluxos de treball i enviar promocions amb el Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b35f8-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="b35f8-105">Requisit previ</span><span class="sxs-lookup"><span data-stu-id="b35f8-105">Prerequisite</span></span>

1. <span data-ttu-id="b35f8-106">Els registres de contacte han d'estar presents al Dynamics 365 Sales per poder exportar un segment del Customer Insights al Sales.</span><span class="sxs-lookup"><span data-stu-id="b35f8-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="b35f8-107">Llegiu més informació sobre com ingerir contactes al [Dynamics 365 Sales mitjançant el Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b35f8-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="b35f8-108">L'exportació de segments de les conclusions del públic al Sales no crearà registres de contacte nous a les instàncies del Sales.</span><span class="sxs-lookup"><span data-stu-id="b35f8-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="b35f8-109">Els registres de contacte del Sales s'han d'ingerir a les conclusions del públic i s'han d'utilitzar com a font de dades.</span><span class="sxs-lookup"><span data-stu-id="b35f8-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="b35f8-110">També s'han d'incloure a l'entitat Client unificada per assignar els identificadors de client als identificadors de contacte abans d'exportar els segments.</span><span class="sxs-lookup"><span data-stu-id="b35f8-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="b35f8-111">Configurar el connector per al Sales</span><span class="sxs-lookup"><span data-stu-id="b35f8-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="b35f8-112">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="b35f8-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b35f8-113">A **Dynamics 365 Sales**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="b35f8-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="b35f8-114">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="b35f8-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b35f8-115">Introduïu l'adreça URL del Sales de l'organització al camp **Adreça del servidor**.</span><span class="sxs-lookup"><span data-stu-id="b35f8-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b35f8-116">A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b35f8-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="b35f8-117">Assigneu un camp d'ID de client a l'ID de contacte del Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b35f8-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b35f8-118">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="b35f8-118">Select **Next**.</span></span>

1. <span data-ttu-id="b35f8-119">Trieu un o diversos segments.</span><span class="sxs-lookup"><span data-stu-id="b35f8-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="b35f8-120">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="b35f8-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b35f8-121">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="b35f8-121">Export the data</span></span>

<span data-ttu-id="b35f8-122">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b35f8-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b35f8-123">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b35f8-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]