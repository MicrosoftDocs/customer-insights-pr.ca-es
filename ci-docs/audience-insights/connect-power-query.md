---
title: Ingerir dades a través d'un connector del Power Query
description: Connectors per a fonts de dades basades en el Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596901"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="329f3-103">Connectar-se a una font de dades del Power Query</span><span class="sxs-lookup"><span data-stu-id="329f3-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="329f3-104">El Power Query ofereix un ampli conjunt de connectors per ingerir dades.</span><span class="sxs-lookup"><span data-stu-id="329f3-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="329f3-105">La majoria d'aquests connectors estan admesos pel Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="329f3-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="329f3-106">Afegir fonts de dades basades en connectors del Power Query generalment implica els passos indicats a la secció següent.</span><span class="sxs-lookup"><span data-stu-id="329f3-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="329f3-107">Tot i això, en funció del connector que utilitzeu, es requereix informació diferent.</span><span class="sxs-lookup"><span data-stu-id="329f3-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="329f3-108">Per a més informació, vegeu la documentació sobre connectors individuals a la [Referència de connectors del Power Query](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="329f3-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="329f3-109">Crear una font de dades nova</span><span class="sxs-lookup"><span data-stu-id="329f3-109">Create a new data source</span></span>

1. <span data-ttu-id="329f3-110">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="329f3-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="329f3-111">Seleccioneu **Afegeix una font de dades**.</span><span class="sxs-lookup"><span data-stu-id="329f3-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="329f3-112">Trieu el mètode **Importa dades** i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="329f3-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="329f3-113">Proporcioneu un **Nom** per a la font de dades i seleccioneu **Següent** per crear la font de dades.</span><span class="sxs-lookup"><span data-stu-id="329f3-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="329f3-114">Directrius del nom:</span><span class="sxs-lookup"><span data-stu-id="329f3-114">Name guidelines:</span></span> 
   - <span data-ttu-id="329f3-115">Comenceu per una lletra.</span><span class="sxs-lookup"><span data-stu-id="329f3-115">Start with a letter.</span></span>
   - <span data-ttu-id="329f3-116">Utilitzeu només lletres i xifres.</span><span class="sxs-lookup"><span data-stu-id="329f3-116">Use letters and numbers only.</span></span> <span data-ttu-id="329f3-117">Els caràcters especials i els espais no estan permesos.</span><span class="sxs-lookup"><span data-stu-id="329f3-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="329f3-118">Utilitzeu entre 3 i 64 caràcters.</span><span class="sxs-lookup"><span data-stu-id="329f3-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="329f3-119">Seleccioneu un dels [connectors disponibles](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="329f3-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="329f3-120">Per aquest exemple, seleccionem el connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="329f3-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="329f3-121">Introduïu els detalls necessaris a **Configuració de la connexió** per al connector seleccionat i seleccioneu **Següent** per veure una previsualització de les dades.</span><span class="sxs-lookup"><span data-stu-id="329f3-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="329f3-122">Seleccioneu **Transforma les dades**.</span><span class="sxs-lookup"><span data-stu-id="329f3-122">Select **Transform data**.</span></span> <span data-ttu-id="329f3-123">En aquest pas, afegireu entitats a la vostra font de dades.</span><span class="sxs-lookup"><span data-stu-id="329f3-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="329f3-124">Les entitats són conjunts de dades.</span><span class="sxs-lookup"><span data-stu-id="329f3-124">Entities are datasets.</span></span> <span data-ttu-id="329f3-125">Si teniu una base de dades que inclou diversos conjunts de dades, cada conjunt de dades és la seva pròpia entitat.</span><span class="sxs-lookup"><span data-stu-id="329f3-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="329f3-126">El diàleg **Power Query: edita les consultes** permet revisar i refinar les dades.</span><span class="sxs-lookup"><span data-stu-id="329f3-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="329f3-127">Les entitats que els sistemes han identificat a la font de dades seleccionada apareixen a la subfinestra esquerra.</span><span class="sxs-lookup"><span data-stu-id="329f3-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="329f3-128">![Quadre de diàleg Edita les consultes](media/data-manager-configure-edit-queries.png "Quadre de diàleg Edita les consultes")</span><span class="sxs-lookup"><span data-stu-id="329f3-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="329f3-129">També podeu transformar les dades.</span><span class="sxs-lookup"><span data-stu-id="329f3-129">You can also transform your data.</span></span> <span data-ttu-id="329f3-130">Seleccioneu una entitat per editar o transformar.</span><span class="sxs-lookup"><span data-stu-id="329f3-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="329f3-131">Utilitzeu les opcions de la finestra del Power Query per aplicar transformacions.</span><span class="sxs-lookup"><span data-stu-id="329f3-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="329f3-132">Cada transformació apareix a **Passos aplicats**.</span><span class="sxs-lookup"><span data-stu-id="329f3-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="329f3-133">El Power Query proporciona nombroses opcions de transformació incorporades.</span><span class="sxs-lookup"><span data-stu-id="329f3-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="329f3-134">Per a més informació, vegeu [Transformacions del Power Query](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="329f3-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="329f3-135">Per afegir entitats addicionals a la font de dades, seleccioneu **Obtén les dades** al quadre de diàleg **Edita les consultes**.</span><span class="sxs-lookup"><span data-stu-id="329f3-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="329f3-136">Aquestes transformacions són molt recomanables:</span><span class="sxs-lookup"><span data-stu-id="329f3-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="329f3-137">Si esteu ingerint dades d'un fitxer CSV, la primera fila sovint conté capçaleres.</span><span class="sxs-lookup"><span data-stu-id="329f3-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="329f3-138">Aneu a **Transforma la taula** i seleccioneu **Utilitza les capçaleres com a primera fila**.</span><span class="sxs-lookup"><span data-stu-id="329f3-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="329f3-139">Assegureu-vos que el tipus de dades s'ha establert correctament.</span><span class="sxs-lookup"><span data-stu-id="329f3-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="329f3-140">Seleccioneu **Desa** a la part inferior de la finestra de Power Query per desar les transformacions.</span><span class="sxs-lookup"><span data-stu-id="329f3-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="329f3-141">Després de desar-la, trobareu la vostra font de dades a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="329f3-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="329f3-142">A la pàgina **Fonts de dades**, veureu que la nova font de dades té l'estat **S'està actualitzant**.</span><span class="sxs-lookup"><span data-stu-id="329f3-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="329f3-143">Fonts de dades del Power Query disponibles</span><span class="sxs-lookup"><span data-stu-id="329f3-143">Available Power Query data sources</span></span>

<span data-ttu-id="329f3-144">Vegeu la [Referència de connectors del Power Query](/power-query/connectors/) per veure una llista actualitzada de connectors que podeu seleccionar per importar dades al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="329f3-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="329f3-145">Els connectors amb una marca de selecció a la columna **Customer Insights (fluxos de dades)** estan disponibles per crear noves fonts de dades basades en el Power Query.</span><span class="sxs-lookup"><span data-stu-id="329f3-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="329f3-146">Reviseu la documentació d'un connector específic per obtenir més informació sobre els seus prerequisits, limitacions i altres detalls.</span><span class="sxs-lookup"><span data-stu-id="329f3-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="329f3-147">Editar les fonts de dades del Power Query</span><span class="sxs-lookup"><span data-stu-id="329f3-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="329f3-148">Pot ser que no es puguin fer canvis en les fonts de dades que s'estan utilitzant actualment en un dels processos del'aplicació(*segmentació*, *coincidència* o *combinació*, per exemple).</span><span class="sxs-lookup"><span data-stu-id="329f3-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="329f3-149">Mitjançant la pàgina **Configuració**, podeu fer el seguiment del progrés de cadascun dels processos actius.</span><span class="sxs-lookup"><span data-stu-id="329f3-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="329f3-150">Quan es completi un procés, podeu tornar a la pàgina **Fonts de dades** i fer els canvis que vulgueu.</span><span class="sxs-lookup"><span data-stu-id="329f3-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="329f3-151">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="329f3-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="329f3-152">Seleccioneu els punts suspensius vertical que hi ha al costat de la font de dades que voleu canviar i seleccioneu **Edita** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="329f3-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="329f3-153">![Opció Edita](media/edit-option-data-sources.png "Opció Edita")</span><span class="sxs-lookup"><span data-stu-id="329f3-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="329f3-154">Apliqueu els canvis i transformacions al diàleg **Power Query: edita les consultes** tal com es descriu a la secció [Crear una nova font de dades](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="329f3-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="329f3-155">Seleccioneu **Desa** al Power Query després de completar les vostres edicions per desar els canvis.</span><span class="sxs-lookup"><span data-stu-id="329f3-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]