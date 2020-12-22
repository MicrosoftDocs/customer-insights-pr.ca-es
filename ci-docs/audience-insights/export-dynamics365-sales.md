---
title: Exportar dades del Customer Insights al Dynamics 365 Sales
description: Més informació sobre com configurar la connexió al Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643806"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="46879-103">Connector per al Dynamics 365 Sales (visualització prèvia)</span><span class="sxs-lookup"><span data-stu-id="46879-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="46879-104">Utilitzeu les dades dels vostres clients per crear llistes de màrqueting, fer un seguiment de fluxos de treball i enviar promocions amb el Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="46879-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="46879-105">Requisit previ</span><span class="sxs-lookup"><span data-stu-id="46879-105">Prerequisite</span></span>

<span data-ttu-id="46879-106">Registres de contactes [del Dynamics 365 Sales ingerits mitjançant el Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="46879-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="46879-107">Configurar el connector per al Sales</span><span class="sxs-lookup"><span data-stu-id="46879-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="46879-108">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="46879-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="46879-109">A **Dynamics 365 Sales**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="46879-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="46879-110">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="46879-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="46879-111">Introduïu l'adreça URL del Sales de l'organització al camp **Adreça del servidor**.</span><span class="sxs-lookup"><span data-stu-id="46879-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="46879-112">A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="46879-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="46879-113">Assigneu un camp d'ID de client a l'ID de contacte del Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="46879-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="46879-114">Seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="46879-114">Select **Next**.</span></span>

1. <span data-ttu-id="46879-115">Trieu un o diversos segments.</span><span class="sxs-lookup"><span data-stu-id="46879-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="46879-116">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="46879-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="46879-117">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="46879-117">Export the data</span></span>

<span data-ttu-id="46879-118">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="46879-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="46879-119">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="46879-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
