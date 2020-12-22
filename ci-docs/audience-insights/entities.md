---
title: Entitats i conjunts de dades
description: Visualitzeu dades de la pàgina Entitats.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405134"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="519ac-103">Entitats a les conclusions del públic</span><span class="sxs-lookup"><span data-stu-id="519ac-103">Entities in audience insights</span></span>

<span data-ttu-id="519ac-104">Després de [configurar les fonts de dades](data-sources.md), aneu a la pàgina **Entitats** per avaluar la qualitat de les dades que heu ingerit.</span><span class="sxs-lookup"><span data-stu-id="519ac-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="519ac-105">Les entitats es consideren conjunts de dades.</span><span class="sxs-lookup"><span data-stu-id="519ac-105">Entities are considered datasets.</span></span> <span data-ttu-id="519ac-106">Diverses capacitats del Dynamics 365 Customer Insights es construeixen al voltant d'aquestes entitats.</span><span class="sxs-lookup"><span data-stu-id="519ac-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="519ac-107">Revisar-les amb atenció us pot ajudar a validar la sortida d'aquestes funcions.</span><span class="sxs-lookup"><span data-stu-id="519ac-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="519ac-108">A la pàgina **Entitats** s'enumeren entitats i inclou diverses columnes:</span><span class="sxs-lookup"><span data-stu-id="519ac-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="519ac-109">**Nom**: nom de l'entitat de dades.</span><span class="sxs-lookup"><span data-stu-id="519ac-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="519ac-110">Si veieu un símbol d'advertiment al costat del nom d'una entitat, vol dir que les dades de l'entitat no s'han carregat correctament.</span><span class="sxs-lookup"><span data-stu-id="519ac-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="519ac-111">**Font**: tipus de font de dades que ha ingerit l'entitat</span><span class="sxs-lookup"><span data-stu-id="519ac-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="519ac-112">**Creat per**: nom de la persona que ha creat l'entitat</span><span class="sxs-lookup"><span data-stu-id="519ac-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="519ac-113">**Data de creació**: data i hora de creació de l'entitat</span><span class="sxs-lookup"><span data-stu-id="519ac-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="519ac-114">**Actualitzat per**: nom de la persona que ha actualitzat l'entitat</span><span class="sxs-lookup"><span data-stu-id="519ac-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="519ac-115">**Última actualització**: data i hora de l'última vegada que es va actualitzar l'entitat</span><span class="sxs-lookup"><span data-stu-id="519ac-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="519ac-116">**Darrera actualització**: data i hora de l'última actualització de les dades</span><span class="sxs-lookup"><span data-stu-id="519ac-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="519ac-117">Explorar les dades d'una entitat concreta</span><span class="sxs-lookup"><span data-stu-id="519ac-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="519ac-118">Seleccioneu una entitat per explorar els diferents camps i registres inclosos dins d'aquesta entitat.</span><span class="sxs-lookup"><span data-stu-id="519ac-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="519ac-119">![Seleccioneu una entitat](media/data-manager-entities-data.png "Seleccioneu una entitat")</span><span class="sxs-lookup"><span data-stu-id="519ac-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="519ac-120">La pestanya **Dades** està seleccionada per defecte i mostra una taula amb detalls sobre els registres individuals de l'entitat.</span><span class="sxs-lookup"><span data-stu-id="519ac-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="519ac-121">![Taula de camps](media/data-manager-entities-fields.PNG "Taula de camps")</span><span class="sxs-lookup"><span data-stu-id="519ac-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="519ac-122">A la pestanya **Camps** es mostra una taula per revisar els detalls de l'entitat seleccionada, com ara els noms de camp, els tipus de dades i els tipus.</span><span class="sxs-lookup"><span data-stu-id="519ac-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="519ac-123">A la columna **Tipus** es mostren els tipus associats del Common Data Model, els quals són identificats automàticament pel sistema o [assignats manualment](map-entities.md) pels usuaris.</span><span class="sxs-lookup"><span data-stu-id="519ac-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="519ac-124">Són tipus semàntics que poden diferir dels tipus de dades dels atributs; per exemple, el camp *Correu electrònic* següent té un tipus de dades *Text*, però el seu tipus del Common Data Model (semàntic) comú pot ser *Email* o *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="519ac-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="519ac-125">Ambdues taules mostren només una mostra de les dades de l'entitat.</span><span class="sxs-lookup"><span data-stu-id="519ac-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="519ac-126">Per visualitzar el conjunt de dades complet, aneu a la pàgina **Fonts de dades**, seleccioneu una entitat, seleccioneu **Edita** i, a continuació, visualitzeu les dades d'aquesta entitat amb l'editor del Power Query com s'explica a [Fonts de dades](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="519ac-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="519ac-127">Per obtenir més informació sobre les dades que s'ingereixen a l'entitat, la columna **Resum** us ofereix algunes característiques importants de les dades, com ara valors inexistents, valor que falten, valors únics, recomptes i distribucions, segons s'apliqui a les vostres dades.</span><span class="sxs-lookup"><span data-stu-id="519ac-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="519ac-128">Seleccioneu la icona del gràfic per veure el resum de les dades.</span><span class="sxs-lookup"><span data-stu-id="519ac-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="519ac-129">![Símbol de resum](media/data-manager-entities-summary.png "Taula de resum de dades")</span><span class="sxs-lookup"><span data-stu-id="519ac-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="519ac-130">Pas següent</span><span class="sxs-lookup"><span data-stu-id="519ac-130">Next step</span></span>

<span data-ttu-id="519ac-131">Vegeu el tema [Unificar](data-unification.md) per obtenir més informació sobrecom podeu *assignar*, *combinar* i *fusionar* les dades ingerides.</span><span class="sxs-lookup"><span data-stu-id="519ac-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>
