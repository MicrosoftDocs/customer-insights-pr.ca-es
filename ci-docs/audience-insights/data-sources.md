---
title: Utilitzar fonts de dades per ingerir dades
description: Més informació sobre com importar dades de diverses fonts.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643941"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="615e4-103">Informació general de les fonts de dades</span><span class="sxs-lookup"><span data-stu-id="615e4-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="615e4-104">La capacitat de conclusions del públic del Dynamics 365 Customer Insights connecta amb les dades d'un ampli conjunt de fonts.</span><span class="sxs-lookup"><span data-stu-id="615e4-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="615e4-105">La connexió a una font de dades sovint es coneix com el procés d'*ingesta de dades*.</span><span class="sxs-lookup"><span data-stu-id="615e4-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="615e4-106">Després d'ingerir les dades, les podeu [unificar](data-unification.md) i treballar-hi.</span><span class="sxs-lookup"><span data-stu-id="615e4-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="615e4-107">Afegeix un origen de dades</span><span class="sxs-lookup"><span data-stu-id="615e4-107">Add a data source</span></span>

<span data-ttu-id="615e4-108">Consulteu els articles detallats sobre com afegir una font de dades, en funció de l'opció que trieu.</span><span class="sxs-lookup"><span data-stu-id="615e4-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="615e4-109">Podeu afegir una font de dades de tres maneres principals:</span><span class="sxs-lookup"><span data-stu-id="615e4-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="615e4-110">Mitjançant desenes de connectors del Power Query</span><span class="sxs-lookup"><span data-stu-id="615e4-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="615e4-111">Des d'una carpeta del Common Data Model</span><span class="sxs-lookup"><span data-stu-id="615e4-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="615e4-112">Des del vostre propi llac del Common Data Service</span><span class="sxs-lookup"><span data-stu-id="615e4-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="615e4-113">Encara no podeu afegir dades de les fonts de dades locals.</span><span class="sxs-lookup"><span data-stu-id="615e4-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="615e4-114">Revisar les dades ingerides</span><span class="sxs-lookup"><span data-stu-id="615e4-114">Review ingested data</span></span>

<span data-ttu-id="615e4-115">Veureu el nom de cada font de dades ingerida, el seu estat i l'última vegada que les dades s'han actualitzat per a aquesta font.</span><span class="sxs-lookup"><span data-stu-id="615e4-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="615e4-116">Podeu ordenar la llista de fonts de dades per cada columna.</span><span class="sxs-lookup"><span data-stu-id="615e4-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="615e4-117">![Font de dades afegida](media/configure-data-datasource-added.png "Font de dades afegida")</span><span class="sxs-lookup"><span data-stu-id="615e4-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="615e4-118">Estat</span><span class="sxs-lookup"><span data-stu-id="615e4-118">Status</span></span>  |<span data-ttu-id="615e4-119">Descripció</span><span class="sxs-lookup"><span data-stu-id="615e4-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="615e4-120">Correcte</span><span class="sxs-lookup"><span data-stu-id="615e4-120">Successful</span></span>   |<span data-ttu-id="615e4-121">La font de dades s'ha ingerit correctament si es mostra una hora a la columna **Actualitzat**.</span><span class="sxs-lookup"><span data-stu-id="615e4-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="615e4-122">No s'ha iniciat</span><span class="sxs-lookup"><span data-stu-id="615e4-122">Not started</span></span>   |<span data-ttu-id="615e4-123">La font de dades no té encara dades ingerides o encara es troben en mode d'esborrany.</span><span class="sxs-lookup"><span data-stu-id="615e4-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="615e4-124">S'està actualitzant</span><span class="sxs-lookup"><span data-stu-id="615e4-124">Refreshing</span></span>    |<span data-ttu-id="615e4-125">La ingestió de dades està en curs.</span><span class="sxs-lookup"><span data-stu-id="615e4-125">Data ingestion is in progress.</span></span> <span data-ttu-id="615e4-126">Per cancel·lar aquesta operació, seleccioneu **Deixa d'actualitzar** a la columna **Accions**.</span><span class="sxs-lookup"><span data-stu-id="615e4-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="615e4-127">Si atureu l'actualització d'una font de dades, es revertirà a l'últim estat d'actualització.</span><span class="sxs-lookup"><span data-stu-id="615e4-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="615e4-128">Erroni</span><span class="sxs-lookup"><span data-stu-id="615e4-128">Failed</span></span>     |<span data-ttu-id="615e4-129">L'ingestió de dades ha trobat errors.</span><span class="sxs-lookup"><span data-stu-id="615e4-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="615e4-130">Seleccioneu **Actualitza l'estat** per revisar més detalls sobre l'estat d'actualització, incloent-hi els detalls dels errors i les actualitzacions dels processos derivats.</span><span class="sxs-lookup"><span data-stu-id="615e4-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="615e4-131">La càrrega de dades pot tardar una estona.</span><span class="sxs-lookup"><span data-stu-id="615e4-131">Loading data can take some time.</span></span> <span data-ttu-id="615e4-132">Després d'una actualització correcta, les dades d'ingerides es poden revisar des de la pàgina **Entitats**.</span><span class="sxs-lookup"><span data-stu-id="615e4-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="615e4-133">Per obtenir més informació, vegeu [Entitats](entities.md).</span><span class="sxs-lookup"><span data-stu-id="615e4-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="615e4-134">Actualitzar una font de dades</span><span class="sxs-lookup"><span data-stu-id="615e4-134">Refresh a data source</span></span>

<span data-ttu-id="615e4-135">Les fonts de dades es poden actualitzar seguint una planificació automàtica o bé manualment segons demanda.</span><span class="sxs-lookup"><span data-stu-id="615e4-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="615e4-136">Per configurar les actualitzacions planificades de totes les fonts de dades ingerides, aneu a **Administració** > **Sistema** > [**Planificació**](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="615e4-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="615e4-137">Per actualitzar una font de dades segons demanda, seguiu aquests passos:</span><span class="sxs-lookup"><span data-stu-id="615e4-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="615e4-138">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="615e4-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="615e4-139">Seleccioneu els punts suspensius verticals que hi ha al costat de la font de dades que voleu actualitzar i seleccioneu **Actualitza** a la llista desplegable.</span><span class="sxs-lookup"><span data-stu-id="615e4-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="615e4-140">S'inicia l'actualització manual de la font de dades en qüestió.</span><span class="sxs-lookup"><span data-stu-id="615e4-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="615e4-141">En actualitzar una font de dades, s'actualitza tant l'esquema de l'entitat com les dades de totes les entitats especificades a la font de dades.</span><span class="sxs-lookup"><span data-stu-id="615e4-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="615e4-142">Seleccioneu **Para d'actualitzar** si voleu cancel·lar una actualització existent; la font de dades tornarà a l'últim estat d'actualització.</span><span class="sxs-lookup"><span data-stu-id="615e4-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="615e4-143">Suprimir una font de dades</span><span class="sxs-lookup"><span data-stu-id="615e4-143">Delete a data source</span></span>

1. <span data-ttu-id="615e4-144">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="615e4-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="615e4-145">Seleccioneu els punts suspensius vertical que hi ha al costat de la font de dades que voleu suprimir i seleccioneu **Suprimeix** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="615e4-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="615e4-146">Confirmeu la supressió.</span><span class="sxs-lookup"><span data-stu-id="615e4-146">Confirm your deletion.</span></span>
