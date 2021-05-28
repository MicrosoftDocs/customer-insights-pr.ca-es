---
title: Utilitzar fonts de dades per ingerir dades
description: Més informació sobre com importar dades de diverses fonts.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085518"
---
# <a name="data-sources-overview"></a><span data-ttu-id="bf1f9-103">Informació general de les fonts de dades</span><span class="sxs-lookup"><span data-stu-id="bf1f9-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bf1f9-104">La capacitat de conclusions del públic del Dynamics 365 Customer Insights connecta amb les dades d'un ampli conjunt de fonts.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="bf1f9-105">La connexió a una font de dades sovint es coneix com el procés d'*ingesta de dades*.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="bf1f9-106">Després d'ingerir les dades, les podeu [unificar](data-unification.md) i treballar-hi.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="bf1f9-107">Afegeix un origen de dades</span><span class="sxs-lookup"><span data-stu-id="bf1f9-107">Add a data source</span></span>

<span data-ttu-id="bf1f9-108">Consulteu els articles detallats sobre com afegir una font de dades, en funció de l'opció que trieu.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="bf1f9-109">Podeu afegir una font de dades de tres maneres principals:</span><span class="sxs-lookup"><span data-stu-id="bf1f9-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="bf1f9-110">Mitjançant desenes de connectors del Power Query</span><span class="sxs-lookup"><span data-stu-id="bf1f9-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="bf1f9-111">Des d'una carpeta del Common Data Model</span><span class="sxs-lookup"><span data-stu-id="bf1f9-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="bf1f9-112">Des del vostre propi llac del Common Data Service</span><span class="sxs-lookup"><span data-stu-id="bf1f9-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="bf1f9-113">Afegir dades des de fonts de dades locals</span><span class="sxs-lookup"><span data-stu-id="bf1f9-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="bf1f9-114">La ingesta de dades de fonts de dades locals a l'Audience Insights està admesa als fluxos de dades del Power Platform.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="bf1f9-115">Els fluxos de dades es poden habilitar al Customer Insights [proporcionant l'adreça URL de l'entorn del Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) en configurar l'entorn.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="bf1f9-116">Les fonts de dades que es creen després d'associar un entorn del Dataverse amb el Customer Insights utilitzaran [fluxos de dades del Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) per defecte.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="bf1f9-117">Els fluxos de dades admeten la connectivitat local mitjançant l'ús de la passarel·la de dades.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="bf1f9-118">Suprimiu i torneu a crear fonts de dades que hi havia abans a l'entorn del Dataverse que estava associat a [utilitzar les passarel·les de dades locals](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="bf1f9-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="bf1f9-119">Les passarel·les de dades d'un entorn existent del Power BI o el Power Apps seran visibles i es poden reutilitzar al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="bf1f9-120">La pàgina de fonts de dades mostra enllaços per anar a l'entorn del Power Platform on podeu visualitzar i configurar passarel·les de dades locals.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="bf1f9-121">Revisar les dades ingerides</span><span class="sxs-lookup"><span data-stu-id="bf1f9-121">Review ingested data</span></span>

<span data-ttu-id="bf1f9-122">Veureu el nom de cada font de dades ingerida, el seu estat i l'última vegada que les dades s'han actualitzat per a aquesta font.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="bf1f9-123">Podeu ordenar la llista de fonts de dades per cada columna.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bf1f9-124">![Font de dades afegida](media/configure-data-datasource-added.png "Font de dades afegida")</span><span class="sxs-lookup"><span data-stu-id="bf1f9-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="bf1f9-125">Estat</span><span class="sxs-lookup"><span data-stu-id="bf1f9-125">Status</span></span>  |<span data-ttu-id="bf1f9-126">Descripció</span><span class="sxs-lookup"><span data-stu-id="bf1f9-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="bf1f9-127">Correcte</span><span class="sxs-lookup"><span data-stu-id="bf1f9-127">Successful</span></span>   |<span data-ttu-id="bf1f9-128">La font de dades s'ha ingerit correctament si es mostra una hora a la columna **Actualitzat**.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="bf1f9-129">No s'ha iniciat</span><span class="sxs-lookup"><span data-stu-id="bf1f9-129">Not started</span></span>   |<span data-ttu-id="bf1f9-130">La font de dades no té encara dades ingerides o encara es troben en mode d'esborrany.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="bf1f9-131">S'està actualitzant</span><span class="sxs-lookup"><span data-stu-id="bf1f9-131">Refreshing</span></span>    |<span data-ttu-id="bf1f9-132">La ingestió de dades està en curs.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-132">Data ingestion is in progress.</span></span> <span data-ttu-id="bf1f9-133">Per cancel·lar aquesta operació, seleccioneu **Deixa d'actualitzar** a la columna **Accions**.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="bf1f9-134">Si atureu l'actualització d'una font de dades, es revertirà a l'últim estat d'actualització.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="bf1f9-135">Erroni</span><span class="sxs-lookup"><span data-stu-id="bf1f9-135">Failed</span></span>     |<span data-ttu-id="bf1f9-136">L'ingestió de dades ha trobat errors.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="bf1f9-137">Seleccioneu el valor de la columna **Estat** de qualsevol font de dades per revisar més detalls.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="bf1f9-138">A la subfinestra **Detalls del progrés**, expandiu **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="bf1f9-139">Seleccioneu **Visualitza els detalls** per a més informació sobre l'estat d'actualització, incloent-hi els detalls dels errors i les actualitzacions dels processos derivats.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="bf1f9-140">La càrrega de dades pot tardar una estona.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-140">Loading data can take some time.</span></span> <span data-ttu-id="bf1f9-141">Després d'una actualització correcta, les dades d'ingerides es poden revisar des de la pàgina **Entitats**.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="bf1f9-142">Per obtenir més informació, vegeu [Entitats](entities.md).</span><span class="sxs-lookup"><span data-stu-id="bf1f9-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="bf1f9-143">Actualitzar una font de dades</span><span class="sxs-lookup"><span data-stu-id="bf1f9-143">Refresh a data source</span></span>

<span data-ttu-id="bf1f9-144">Les fonts de dades es poden actualitzar seguint una planificació automàtica o bé manualment segons demanda.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="bf1f9-145">Per configurar les actualitzacions planificades de totes les fonts de dades ingerides, aneu a **Administració** > **Sistema** > [**Planificació**](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bf1f9-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="bf1f9-146">Per actualitzar una font de dades segons demanda, seguiu aquests passos:</span><span class="sxs-lookup"><span data-stu-id="bf1f9-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="bf1f9-147">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="bf1f9-148">Seleccioneu els punts suspensius verticals que hi ha al costat de la font de dades que voleu actualitzar i seleccioneu **Actualitza** a la llista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="bf1f9-149">S'inicia l'actualització manual de la font de dades en qüestió.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="bf1f9-150">En actualitzar una font de dades s'actualitza tan l'esquema d'entitat com les dades de totes les entitats especificades a la font de dades.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="bf1f9-151">Seleccioneu **Para d'actualitzar** si voleu cancel·lar una actualització existent; la font de dades tornarà a l'últim estat d'actualització.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="bf1f9-152">Suprimir una font de dades</span><span class="sxs-lookup"><span data-stu-id="bf1f9-152">Delete a data source</span></span>

1. <span data-ttu-id="bf1f9-153">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="bf1f9-154">Seleccioneu els punts suspensius vertical que hi ha al costat de la font de dades que voleu suprimir i seleccioneu **Suprimeix** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="bf1f9-155">Confirmeu la supressió.</span><span class="sxs-lookup"><span data-stu-id="bf1f9-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
