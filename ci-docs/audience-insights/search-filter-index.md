---
title: Cercar i filtrar perfils de client
description: Trobeu ràpidament informació sobre els perfils de client unificats i filtreu-los per atributs especificats.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405170"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="5297a-103">Perfils de client: índex de cerca i filtratge</span><span class="sxs-lookup"><span data-stu-id="5297a-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="5297a-104">El resultat d'unificar les dades dels clients és una entitat de perfil de client que proporciona una visualització unificada a la base de clients total.</span><span class="sxs-lookup"><span data-stu-id="5297a-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="5297a-105">Per [cercar ràpidament informació sobre un client o un grup de clients determinat](customer-profiles.md), podeu configurar les funcionalitats **Cerca** i **Filtre** a la pàgina **Clients**.</span><span class="sxs-lookup"><span data-stu-id="5297a-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="5297a-106">Seguiu llegint per obtenir més informació sobre com els administradors poden editar els atributs a la pàgina **Índex de cerca i filtre**, que estan disponibles per als usuaris per cercar i filtrar.</span><span class="sxs-lookup"><span data-stu-id="5297a-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5297a-107">![Filtre de cerca](media/search-filter.png "Filtre de cerca")</span><span class="sxs-lookup"><span data-stu-id="5297a-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="5297a-108">Afegir camps i especificar atributs</span><span class="sxs-lookup"><span data-stu-id="5297a-108">Add fields and specify attributes</span></span>

<span data-ttu-id="5297a-109">Si és la primera vegada que definiu els atributs que es poden cercar com a administrador, primer heu de definir els camps indexats.</span><span class="sxs-lookup"><span data-stu-id="5297a-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="5297a-110">Us suggerim que trieu tots els atributs pels quals els usuaris puguin cercar i filtrar els clients a la pàgina **Clients**.</span><span class="sxs-lookup"><span data-stu-id="5297a-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="5297a-111">Només podeu especificar els atributs que hi ha a l'entitat de perfil de client que heu creat durant el procés d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="5297a-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="5297a-112">Obriu la pàgina **Clients** i seleccioneu **Cerca i filtra l'índex**.</span><span class="sxs-lookup"><span data-stu-id="5297a-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="5297a-113">Creem una configuració d'índex de cerca per defecte als atributs disponibles de l'entitat Client dels tipus semàntics següents tal com es defineix a la pàgina d'assignació.</span><span class="sxs-lookup"><span data-stu-id="5297a-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="5297a-114">Nom, cognom, segon nom, nom complet de la persona</span><span class="sxs-lookup"><span data-stu-id="5297a-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="5297a-115">Nom de l'organització</span><span class="sxs-lookup"><span data-stu-id="5297a-115">Organization Name</span></span>
> - <span data-ttu-id="5297a-116">Adreça electrònica</span><span class="sxs-lookup"><span data-stu-id="5297a-116">Email address</span></span>
> - <span data-ttu-id="5297a-117">Número de telèfon</span><span class="sxs-lookup"><span data-stu-id="5297a-117">Phone number</span></span>
> - <span data-ttu-id="5297a-118">Informació de la ubicació</span><span class="sxs-lookup"><span data-stu-id="5297a-118">Location information</span></span>

2. <span data-ttu-id="5297a-119">Seleccioneu **+ Afegeix** per especificar els camps indexats.</span><span class="sxs-lookup"><span data-stu-id="5297a-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="5297a-120">Seleccioneu els atributs de la llista que voleu afegir com a camps indexats.</span><span class="sxs-lookup"><span data-stu-id="5297a-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="5297a-121">Sempre podeu afegir més atributs seleccionant **Afegeix**.</span><span class="sxs-lookup"><span data-stu-id="5297a-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="5297a-122">Per suprimir els atributs seleccionats, també podeu seleccionar el símbol **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="5297a-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="5297a-123">Explorar la taula de camps de client indexats</span><span class="sxs-lookup"><span data-stu-id="5297a-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="5297a-124">La següent informació es presenta a la taula.</span><span class="sxs-lookup"><span data-stu-id="5297a-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="5297a-125">**Nom**: representa el nom de l'atribut tal com es mostra a l'entitat de perfil del client.</span><span class="sxs-lookup"><span data-stu-id="5297a-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="5297a-126">**Tipus de dades**: especifica si el tipus de dades és una cadena, un número o una data.</span><span class="sxs-lookup"><span data-stu-id="5297a-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="5297a-127">**Inclòs a la cerca**: especifica si aquest atribut es pot utilitzar per cercar clients a la pàgina **Clients** mitjançant el camp **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="5297a-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="5297a-128">**Afegeix un filtre**: control per definir com es pot utilitzar aquest atribut per filtrar a la pàgina **Clients**.</span><span class="sxs-lookup"><span data-stu-id="5297a-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="5297a-129">Editar les opcions de filtratge per a un atribut determinat</span><span class="sxs-lookup"><span data-stu-id="5297a-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="5297a-130">El menú **Filtre** de la pàgina **Clients** pot incloure un nombre variable de nivells d'atribut (per exemple, diferents grups d'edat pels quals filtrar els clients).</span><span class="sxs-lookup"><span data-stu-id="5297a-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="5297a-131">Seleccioneu **Afegeix un filtre** per a un atribut determinat a la pàgina **Índex de cerca i filtre**.</span><span class="sxs-lookup"><span data-stu-id="5297a-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="5297a-132">Podeu definir el nombre de resultats i l'ordre en el qual s'organitzaran.</span><span class="sxs-lookup"><span data-stu-id="5297a-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="5297a-133">En funció del tipus de dades de l'atribut, apareixerà una dels subfinestres següents.</span><span class="sxs-lookup"><span data-stu-id="5297a-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="5297a-134">Atributs de cadena: especifiqueu el nombre de resultats que voleu a la subfinestra **Opcions del filtre de cadena** i la norma d'ordre per la qual s'organitzaran.</span><span class="sxs-lookup"><span data-stu-id="5297a-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="5297a-135">Atributs numèrics: especifiqueu els intervals inclosos a la subfinestra **Opcions del filtre de nombre** i la norma d'ordre per la qual s'organitzaran.</span><span class="sxs-lookup"><span data-stu-id="5297a-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="5297a-136">Atributs de data: especifiqueu els intervals inclosos a la subfinestra **Opcions del filtre de data** i la norma d'ordre per la qual s'organitzaran.</span><span class="sxs-lookup"><span data-stu-id="5297a-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="5297a-137">Seleccioneu **Desa** per aplicar els canvis.</span><span class="sxs-lookup"><span data-stu-id="5297a-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="5297a-138">Seleccioneu **Executa** una vegada que estigueu a punt per aplicar la configuració.</span><span class="sxs-lookup"><span data-stu-id="5297a-138">Select **Run** once you're ready to apply your settings.</span></span>
