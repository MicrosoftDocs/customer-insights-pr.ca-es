---
title: Bot per al Microsoft Teams
description: Cerqueu els perfils de client unificats al Microsoft Teams amb l'ajuda d'un bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405156"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="28bff-103">Bot del Teams per al Dynamics 365 Customer Insights (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="28bff-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="28bff-104">Connecteu amb el Microsoft Teams per permetre que un bot cerqui perfils de client unificats a canals del Teams.</span><span class="sxs-lookup"><span data-stu-id="28bff-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="28bff-105">![Bot del Teams que mostra un registre de client](media/teams-bot.png "Bot del Teams que mostra un registre de client")</span><span class="sxs-lookup"><span data-stu-id="28bff-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28bff-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="28bff-106">Prerequisites</span></span>

<span data-ttu-id="28bff-107">Per configurar i configurar el bot, cal complir els requisits previs següents:</span><span class="sxs-lookup"><span data-stu-id="28bff-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="28bff-108">S'ha afegit com a mínim una [font de dades](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="28bff-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="28bff-109">El [procés d'unificació](data-unification.md) s'ha completat.</span><span class="sxs-lookup"><span data-stu-id="28bff-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="28bff-110">S'han afegit camps a l'[índex de cerca i filtratge](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="28bff-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="28bff-111">El Customer Insights i el Teams es troben a la mateixa organització.</span><span class="sxs-lookup"><span data-stu-id="28bff-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="28bff-112">Configurar el bot</span><span class="sxs-lookup"><span data-stu-id="28bff-112">Configure the bot</span></span>

1. <span data-ttu-id="28bff-113">A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="28bff-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="28bff-114">A la peça del Microsoft Teams, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="28bff-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="28bff-115">Se us redirigirà a l'àrea **Aplicacions** del Teams.</span><span class="sxs-lookup"><span data-stu-id="28bff-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="28bff-116">També podeu obrir el Teams i seleccionar **Aplicacions** a la cantonada inferior esquerra o [obtenir-ho des d'AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directament.</span><span class="sxs-lookup"><span data-stu-id="28bff-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="28bff-117">Cerqueu **Customer Insights** i seleccioneu l'aplicació.</span><span class="sxs-lookup"><span data-stu-id="28bff-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="28bff-118">Seleccioneu **Afegeix**.</span><span class="sxs-lookup"><span data-stu-id="28bff-118">Select **Add**.</span></span>
1. <span data-ttu-id="28bff-119">Després d'iniciar la sessió al Customer Insights al Teams, veureu un missatge de benvinguda i podreu començar.</span><span class="sxs-lookup"><span data-stu-id="28bff-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="28bff-120">Què podeu fer amb el bot</span><span class="sxs-lookup"><span data-stu-id="28bff-120">Things you can do with the bot</span></span>

<span data-ttu-id="28bff-121">El bot proporciona la capacitat de cerca de perfils unificats de client.</span><span class="sxs-lookup"><span data-stu-id="28bff-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="28bff-122">Introduïu **cerca** seguit d'un nom, una adreça de correu electrònic o qualsevol altre camp al perfil del client unificat que s'hagi afegit a l'índex de cerca i de filtratge.</span><span class="sxs-lookup"><span data-stu-id="28bff-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="28bff-123">Obtindreu una targeta amb fins a 15 camps del perfil de client resultant.</span><span class="sxs-lookup"><span data-stu-id="28bff-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="28bff-124">Les coincidències múltiples retornen una llista de resultats on podeu seleccionar un perfil.</span><span class="sxs-lookup"><span data-stu-id="28bff-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="28bff-125">Podeu afegir el terme de cerca entre cometes dobles per cercar una coincidència exacta.</span><span class="sxs-lookup"><span data-stu-id="28bff-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="28bff-126">Si l'organització manté diversos entorns del Customer Insights a la mateixa organització, podeu introduir **switchinstance** per triar a quin entorn voleu connectar el bot.</span><span class="sxs-lookup"><span data-stu-id="28bff-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="28bff-127">Introduïu **ajuda** per veure una llista de les ordres disponibles per al bot.</span><span class="sxs-lookup"><span data-stu-id="28bff-127">Enter **help** to see a list of available commands for the bot.</span></span>  
