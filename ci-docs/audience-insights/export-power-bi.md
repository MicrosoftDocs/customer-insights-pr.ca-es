---
title: Connector del Power BI
description: Apreneu com utilitzar el connector del Dynamics 365 Customer Insights al Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596027"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="469e6-103">Connector del Power BI (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="469e6-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="469e6-104">Creeu visualitzacions per a les dades amb el Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="469e6-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="469e6-105">Genereu informació addicional i creeu informes amb les dades del client unificades.</span><span class="sxs-lookup"><span data-stu-id="469e6-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="469e6-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="469e6-106">Prerequisites</span></span>

- <span data-ttu-id="469e6-107">Teniu perfils de client unificats.</span><span class="sxs-lookup"><span data-stu-id="469e6-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="469e6-108">L'última versió del [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) està instal·lada a l'ordinador.</span><span class="sxs-lookup"><span data-stu-id="469e6-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="469e6-109">[Més informació sobre el Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="469e6-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="469e6-110">Configurar el connector per al Power BI</span><span class="sxs-lookup"><span data-stu-id="469e6-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="469e6-111">Al Power BI Desktop, seleccioneu **Fitxer** > **Obtén dades**.</span><span class="sxs-lookup"><span data-stu-id="469e6-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="469e6-112">Seleccioneu **Mostra'n més** i cerqueu **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="469e6-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="469e6-113">Seleccioneu **Connecta**.</span><span class="sxs-lookup"><span data-stu-id="469e6-113">Select **Connect**.</span></span>

1. <span data-ttu-id="469e6-114">**Inicieu la sessió** amb el mateix compte d'organització que utilitzeu per al Customer Insights i seleccioneu **Connecta**.</span><span class="sxs-lookup"><span data-stu-id="469e6-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="469e6-115">El compte que indiqueu en aquest pas s'utilitza per obtenir dades del Customer Insights i no ha de ser el mateix amb què heu iniciat la sessió al Power BI.</span><span class="sxs-lookup"><span data-stu-id="469e6-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="469e6-116">Per restablir el compte que s'utilitza per a l'obtenció de les dades, obriu el Power BI i aneu a **Fitxer** > **Opcions** > **Configuració** > **Configuració de fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="469e6-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="469e6-117">A la llista de fonts de dades, seleccioneu **Inici de sessió del Dynamics 365 Customer Insights** i seleccioneu **Esborra els permisos**.</span><span class="sxs-lookup"><span data-stu-id="469e6-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="469e6-118">Al quadre de diàleg **Navegador**.</span><span class="sxs-lookup"><span data-stu-id="469e6-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="469e6-119">podeu veure la llista de tots els entorns als quals teniu accés.</span><span class="sxs-lookup"><span data-stu-id="469e6-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="469e6-120">Expandiu un entorn i obriu qualsevol de les carpetes (entitats, mesures, segments i enriquiments).</span><span class="sxs-lookup"><span data-stu-id="469e6-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="469e6-121">Per exemple, obriu la carpeta **Entitats** per veure totes les entitats que podeu importar.</span><span class="sxs-lookup"><span data-stu-id="469e6-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="469e6-122">![Navegador del connector del Power BI](media/power-bi-navigator.png "Navegador del connector del Power BI")</span><span class="sxs-lookup"><span data-stu-id="469e6-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="469e6-123">Activeu les caselles de selecció que hi ha al costat de les entitats que voleu incloure i **Carrega**.</span><span class="sxs-lookup"><span data-stu-id="469e6-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="469e6-124">Podeu seleccionar diverses entitats de diversos entorns.</span><span class="sxs-lookup"><span data-stu-id="469e6-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="469e6-125">Veureu un quadre de diàleg de càrrega mentre les entitats es carreguen.</span><span class="sxs-lookup"><span data-stu-id="469e6-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="469e6-126">Un cop carregades totes les entitats seleccionades, podeu utilitzar les capacitats del Power BI per visualitzar les dades.</span><span class="sxs-lookup"><span data-stu-id="469e6-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="469e6-127">Conjunts de dades grans</span><span class="sxs-lookup"><span data-stu-id="469e6-127">Large data sets</span></span>

<span data-ttu-id="469e6-128">El connector del Customer Insights per al Power BI està dissenyat per funcionar amb els conjunts de dades que contenen fins a 1 milió de perfils de clients.</span><span class="sxs-lookup"><span data-stu-id="469e6-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="469e6-129">La importació de conjunts de dades més grans pot funcionar, però tarda molta estona.</span><span class="sxs-lookup"><span data-stu-id="469e6-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="469e6-130">A més, el procés podria esgotar el temps d'espera a causa de les limitacions del Power BI.</span><span class="sxs-lookup"><span data-stu-id="469e6-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="469e6-131">Per obtenir més informació, vegeu [Power BI: recomanacions per a conjunts de dades grans](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="469e6-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="469e6-132">Treballar amb un subconjunt de dades</span><span class="sxs-lookup"><span data-stu-id="469e6-132">Work with a subset of data</span></span>

<span data-ttu-id="469e6-133">Considereu la possibilitat de treballar amb un subconjunt de les dades.</span><span class="sxs-lookup"><span data-stu-id="469e6-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="469e6-134">Per exemple, podeu crear [segments](segments.md) en comptes d'exportar tots els registres de client al Power BI.</span><span class="sxs-lookup"><span data-stu-id="469e6-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="469e6-135">Solució de problemes</span><span class="sxs-lookup"><span data-stu-id="469e6-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="469e6-136">L'entorn del Customer Insights no es mostra al Power BI</span><span class="sxs-lookup"><span data-stu-id="469e6-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="469e6-137">Els entorns que tenen més d'una [relació](relationships.md) definida entre dues entitats idèntiques a les conclusions del públic no estaran disponible al connector del Power BI.</span><span class="sxs-lookup"><span data-stu-id="469e6-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="469e6-138">Podeu identificar i suprimir les relacions duplicades.</span><span class="sxs-lookup"><span data-stu-id="469e6-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="469e6-139">A les conclusions del públic, aneu a **Dades** > **Relacions** a l'entorn que falta al Power BI.</span><span class="sxs-lookup"><span data-stu-id="469e6-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="469e6-140">Identificar les relacions duplicades:</span><span class="sxs-lookup"><span data-stu-id="469e6-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="469e6-141">Comproveu si hi ha més d'una relació definida entre les mateixes dues entitats.</span><span class="sxs-lookup"><span data-stu-id="469e6-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="469e6-142">Comproveu si s'ha creat una relació entre dues entitats que estan incloses al procés d'unificació.</span><span class="sxs-lookup"><span data-stu-id="469e6-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="469e6-143">Hi ha una relació implícita que es defineix entre totes les entitats incloses al procés d'unificació.</span><span class="sxs-lookup"><span data-stu-id="469e6-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="469e6-144">Suprimiu les relacions duplicades identificades.</span><span class="sxs-lookup"><span data-stu-id="469e6-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="469e6-145">Després de la supressió de les relacions duplicades, proveu de tornar a configurar el connector del Power BI.</span><span class="sxs-lookup"><span data-stu-id="469e6-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="469e6-146">L'entorn hauria d'estar disponible ara.</span><span class="sxs-lookup"><span data-stu-id="469e6-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]