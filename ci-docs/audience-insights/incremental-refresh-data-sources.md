---
title: Actualització incremental per a fonts de dades basades en Power Query
description: Actualitzeu dades noves i actualitzades per a les fonts de dades grans basades en el Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268536"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="f312d-103">Actualització incremental per a fonts de dades basades en el Power Query</span><span class="sxs-lookup"><span data-stu-id="f312d-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="f312d-104">L'actualització incremental de les fonts de dades proporciona els següents avantatges:</span><span class="sxs-lookup"><span data-stu-id="f312d-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="f312d-105">**Actualitzacions més ràpides**: només s'actualitzen les dades que han canviat.</span><span class="sxs-lookup"><span data-stu-id="f312d-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="f312d-106">Per exemple, pot ser que només actualitzeu els darrers cinc dies d'un conjunt de dades històric.</span><span class="sxs-lookup"><span data-stu-id="f312d-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="f312d-107">**Major fiabilitat**: amb actualitzacions més petites, no cal mantenir connexions al sistemes d'origen volàtils durant tant de temps, la qual cosa redueix el risc de problemes de connexió.</span><span class="sxs-lookup"><span data-stu-id="f312d-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="f312d-108">**Reducció del consum de recursos**: actualitzar només un subconjunt de les dades totals deriva en un ús més eficient dels recursos de computació i redueix l'impacte ambiental.</span><span class="sxs-lookup"><span data-stu-id="f312d-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="f312d-109">Configuració de l'actualització incremental</span><span class="sxs-lookup"><span data-stu-id="f312d-109">Configure incremental refresh</span></span>

<span data-ttu-id="f312d-110">Les conclusions del públic permeten actualitzar de manera incremental fonts de dades importades mitjançant el Power Query que admetin la ingestió incremental.</span><span class="sxs-lookup"><span data-stu-id="f312d-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="f312d-111">Per exemple, les bases de dades de l'Azure SQL amb camps de data i hora, que indiquen quan s'han actualitzat per última vegada els registres de dades.</span><span class="sxs-lookup"><span data-stu-id="f312d-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="f312d-112">[Crear una font de dades nova basada en el Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f312d-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="f312d-113">Proporcioneu un nom per a la font de dades.</span><span class="sxs-lookup"><span data-stu-id="f312d-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="f312d-114">Seleccioneu una font de dades que admeti l'actualització incremental, com ara una base de dades de l'Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="f312d-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="f312d-115">Seleccioneu les entitats o taules que voleu ingerir.</span><span class="sxs-lookup"><span data-stu-id="f312d-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="f312d-116">Completeu els passos de transformació i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="f312d-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="f312d-117">Al quadre de diàleg **Configuració de l'actualització incremental**, seleccioneu **Configura** per obrir la **Configuració de l'actualització incremental**.</span><span class="sxs-lookup"><span data-stu-id="f312d-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="f312d-118">Si seleccioneu **Omet**, la font de dades actualitzarà el conjunt de dades complet.</span><span class="sxs-lookup"><span data-stu-id="f312d-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="f312d-119">També podeu aplicar l'actualització incremental més tard mitjançant l'edició d'una font de dades existent.</span><span class="sxs-lookup"><span data-stu-id="f312d-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="f312d-120">A la **Configuració de l'actualització incremental**, configurareu l'actualització incremental per a totes les entitats que heu seleccionat en crear la font de dades.</span><span class="sxs-lookup"><span data-stu-id="f312d-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f312d-121">![Configurar les entitats en una font de dades per a l'actualització incremental](media/incremental-refresh-settings.png "Configurar les entitats en una font de dades per a l'actualització incremental")</span><span class="sxs-lookup"><span data-stu-id="f312d-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="f312d-122">Seleccioneu una entitat i proporcioneu els detalls següents:</span><span class="sxs-lookup"><span data-stu-id="f312d-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="f312d-123">**Definiu la clau principal**: seleccioneu una clau principal per a l'entitat o la taula.</span><span class="sxs-lookup"><span data-stu-id="f312d-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="f312d-124">**Definiu el camp "darrera actualització"**: aquest camp només mostrarà els atributs del tipus data o hora.</span><span class="sxs-lookup"><span data-stu-id="f312d-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="f312d-125">Seleccioneu un atribut que indiqui quan es van actualitzar per última vegada els registres.</span><span class="sxs-lookup"><span data-stu-id="f312d-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="f312d-126">S'utilitzarà per identificar els registres que es troben dins del període de temps d'actualització incremental.</span><span class="sxs-lookup"><span data-stu-id="f312d-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="f312d-127">**Comprova si hi ha actualitzacions cada**: especifiqueu la freqüència que voleu per al període de temps d'actualització incremental.</span><span class="sxs-lookup"><span data-stu-id="f312d-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="f312d-128">Seleccioneu **Desa** per completar la creació de la font de dades.</span><span class="sxs-lookup"><span data-stu-id="f312d-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="f312d-129">L'actualització inicial de les dades serà una actualització completa.</span><span class="sxs-lookup"><span data-stu-id="f312d-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="f312d-130">Després, es produirà l'actualització de dades incremental com s'ha configurat al pas anterior.</span><span class="sxs-lookup"><span data-stu-id="f312d-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]