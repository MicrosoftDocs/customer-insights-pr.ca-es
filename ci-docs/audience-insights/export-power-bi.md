---
title: Connector del Power BI
description: Apreneu com utilitzar el connector del Dynamics 365 Customer Insights al Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405128"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="a5cc7-103">Connector del Power BI (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="a5cc7-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="a5cc7-104">Creeu visualitzacions per a les dades amb el Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="a5cc7-105">Genereu informació addicional i creeu informes amb les dades del client unificades.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a5cc7-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="a5cc7-106">Prerequisites</span></span>

- <span data-ttu-id="a5cc7-107">Teniu perfils de client unificats.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="a5cc7-108">La versió més recent del [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) està instal·lada a l'ordinador.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="a5cc7-109">[Més informació sobre el Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="a5cc7-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="a5cc7-110">Configurar el connector per al Power BI</span><span class="sxs-lookup"><span data-stu-id="a5cc7-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="a5cc7-111">Al Power BI Desktop, seleccioneu **Fitxer** > **Obtén dades**.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="a5cc7-112">Seleccioneu **Mostra'n més** i cerqueu **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="a5cc7-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="a5cc7-113">Seleccioneu el resultat i seleccioneu **Connecta**.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="a5cc7-114">**Inicieu la sessió** amb el mateix compte d'organització que utilitzeu per al Customer Insights i seleccioneu **Connecta**.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a5cc7-115">El compte que indiqueu en aquest pas s'utilitza per obtenir dades del Customer Insights i no ha de ser el mateix amb què heu iniciat la sessió al Power BI.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="a5cc7-116">Per restablir el compte que s'utilitza per a l'obtenció de les dades, obriu el Power BI i aneu a **Fitxer** > **Opcions** > **Configuració** > **Configuració de fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="a5cc7-117">A la llista de fonts de dades, seleccioneu **Inici de sessió del Dynamics 365 Customer Insights** i seleccioneu **Esborra els permisos**.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="a5cc7-118">Al quadre de diàleg **Navegador**.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="a5cc7-119">podeu veure la llista de tots els entorns als quals teniu accés.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="a5cc7-120">Expandiu un entorn i obriu qualsevol de les carpetes (entitats, mesures, segments i enriquiments).</span><span class="sxs-lookup"><span data-stu-id="a5cc7-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="a5cc7-121">Per exemple, obriu la carpeta **Entitats** per veure totes les entitats que podeu importar.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="a5cc7-122">![Navegador del connector del Power BI](media/power-bi-navigator.png "Navegador del connector del Power BI")</span><span class="sxs-lookup"><span data-stu-id="a5cc7-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="a5cc7-123">Activeu les caselles de selecció que hi ha al costat de les entitats que voleu incloure i **Carrega**.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="a5cc7-124">Podeu seleccionar diverses entitats de diversos entorns.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="a5cc7-125">Veureu un quadre de diàleg de càrrega mentre les entitats es carreguen.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="a5cc7-126">Un cop carregades totes les entitats seleccionades, podeu utilitzar les capacitats del Power BI per visualitzar les dades.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="a5cc7-127">Conjunts de dades grans</span><span class="sxs-lookup"><span data-stu-id="a5cc7-127">Large data sets</span></span>

<span data-ttu-id="a5cc7-128">El connector del Customer Insights per al Power BI està dissenyat per funcionar amb els conjunts de dades que contenen fins a 1 milió de perfils de clients.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="a5cc7-129">La importació de conjunts de dades més grans pot funcionar, però tarda molta estona.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="a5cc7-130">A més, el procés podria esgotar el temps d'espera a causa de les limitacions del Power BI.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="a5cc7-131">Per obtenir més informació, vegeu [Power BI: recomanacions per a conjunts de dades grans](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="a5cc7-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="a5cc7-132">Treballar amb un subconjunt de dades</span><span class="sxs-lookup"><span data-stu-id="a5cc7-132">Work with a subset of data</span></span>

<span data-ttu-id="a5cc7-133">Considereu la possibilitat de treballar amb un subconjunt de les dades.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="a5cc7-134">Per exemple, podeu crear [segments](segments.md) en comptes d'exportar tots els registres de client al Power BI.</span><span class="sxs-lookup"><span data-stu-id="a5cc7-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
