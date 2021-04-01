---
title: Exportar dades del Customer Insights al Dynamics 365 Marketing
description: Més informació sobre com configurar la connexió al Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597591"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="88976-103">Connector per al Dynamics 365 Marketing (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="88976-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="88976-104">Utilitzeu [segments](segments.md) per generar campanyes i posar-vos en contacte amb grups específics de clients amb el Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="88976-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="88976-105">Per obtenir més informació, vegeu [Utilitzar segments del Dynamics 365 Customer Insights amb el Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="88976-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="88976-106">Requisit previ</span><span class="sxs-lookup"><span data-stu-id="88976-106">Prerequisite</span></span>

- <span data-ttu-id="88976-107">Els registres de contacte han d'estar presents al Dynamics 365 Marketing per poder exportar un segment del Customer Insights al Marketing.</span><span class="sxs-lookup"><span data-stu-id="88976-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="88976-108">Llegiu més informació sobre com ingerir contactes al [Dynamics 365 Marketing mitjançant el Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="88976-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="88976-109">L'exportació de segments de les conclusions del públic al Marketing no crearà registres de contacte nous a les instàncies del Marketing.</span><span class="sxs-lookup"><span data-stu-id="88976-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="88976-110">Els registres de contacte del Marketing s'han d'ingerir a les conclusions del públic i s'han d'utilitzar com a font de dades.</span><span class="sxs-lookup"><span data-stu-id="88976-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="88976-111">També s'han d'incloure a l'entitat Client unificada per assignar els identificadors de client als identificadors de contacte abans d'exportar els segments.</span><span class="sxs-lookup"><span data-stu-id="88976-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="88976-112">Configurar el connector per al Marketing</span><span class="sxs-lookup"><span data-stu-id="88976-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="88976-113">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="88976-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="88976-114">A **Dynamics 365 Marketing**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="88976-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="88976-115">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="88976-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="88976-116">Introduïu l'adreça URL del Marketing de l'organització al camp **Adreça del servidor**.</span><span class="sxs-lookup"><span data-stu-id="88976-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="88976-117">A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="88976-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="88976-118">Assigneu un camp d'ID de client a l'ID de contacte del Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="88976-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="88976-119">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="88976-119">Select **Next**.</span></span>

1. <span data-ttu-id="88976-120">Trieu un o diversos segments.</span><span class="sxs-lookup"><span data-stu-id="88976-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="88976-121">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="88976-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="88976-122">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="88976-122">Export the data</span></span>

<span data-ttu-id="88976-123">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="88976-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="88976-124">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="88976-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]