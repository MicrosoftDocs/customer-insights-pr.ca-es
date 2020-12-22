---
title: Exportar dades del Customer Insights al Dynamics 365 Marketing
description: Més informació sobre com configurar la connexió al Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643761"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="a5401-103">Connector per al Dynamics 365 Marketing (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="a5401-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a5401-104">Utilitzeu [segments](segments.md) per generar campanyes i posar-vos en contacte amb grups específics de clients amb el Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a5401-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a5401-105">Per obtenir més informació, vegeu [Utilitzar segments del Dynamics 365 Customer Insights amb el Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="a5401-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a5401-106">Requisit previ</span><span class="sxs-lookup"><span data-stu-id="a5401-106">Prerequisite</span></span>

<span data-ttu-id="a5401-107">Registres de contactes [del Dynamics 365 Marketing ingerits mitjançant el Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a5401-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="a5401-108">Configurar el connector per al Marketing</span><span class="sxs-lookup"><span data-stu-id="a5401-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="a5401-109">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="a5401-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a5401-110">A **Dynamics 365 Marketing**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="a5401-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="a5401-111">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="a5401-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a5401-112">Introduïu l'adreça URL del Marketing de l'organització al camp **Adreça del servidor**.</span><span class="sxs-lookup"><span data-stu-id="a5401-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a5401-113">A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a5401-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a5401-114">Assigneu un camp d'ID de client a l'ID de contacte del Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a5401-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a5401-115">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="a5401-115">Select **Next**.</span></span>

1. <span data-ttu-id="a5401-116">Trieu un o diversos segments.</span><span class="sxs-lookup"><span data-stu-id="a5401-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="a5401-117">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="a5401-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a5401-118">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="a5401-118">Export the data</span></span>

<span data-ttu-id="a5401-119">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a5401-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a5401-120">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a5401-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
