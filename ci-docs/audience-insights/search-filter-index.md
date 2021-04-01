---
title: Cercar i filtrar perfils de client
description: Trobeu ràpidament informació sobre els perfils de client unificats i filtreu-los per atributs especificats.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597131"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="bdb22-103">Perfils de client: índex de cerca i filtratge</span><span class="sxs-lookup"><span data-stu-id="bdb22-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="bdb22-104">El resultat d'unificar les dades dels clients és una entitat de perfil de client que proporciona una visualització unificada a la base de clients total.</span><span class="sxs-lookup"><span data-stu-id="bdb22-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="bdb22-105">Per [cercar ràpidament informació sobre un client o un grup de clients determinat](customer-profiles.md), podeu configurar les funcionalitats **Cerca** i **Filtre** a la pàgina **Clients**.</span><span class="sxs-lookup"><span data-stu-id="bdb22-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="bdb22-106">Seguiu llegint per obtenir més informació sobre com els administradors poden editar els atributs a la pàgina **Índex de cerca i filtre**, que estan disponibles per als usuaris per cercar i filtrar.</span><span class="sxs-lookup"><span data-stu-id="bdb22-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bdb22-107">![Filtre de cerca](media/search-filter.png "Filtre de cerca")</span><span class="sxs-lookup"><span data-stu-id="bdb22-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="bdb22-108">Afegir camps i especificar atributs</span><span class="sxs-lookup"><span data-stu-id="bdb22-108">Add fields and specify attributes</span></span>

<span data-ttu-id="bdb22-109">Si és la primera vegada que definiu els atributs que es poden cercar com a administrador, primer heu de definir els camps indexats.</span><span class="sxs-lookup"><span data-stu-id="bdb22-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="bdb22-110">Us suggerim que trieu tots els atributs pels quals els usuaris puguin cercar i filtrar els clients a la pàgina **Clients**.</span><span class="sxs-lookup"><span data-stu-id="bdb22-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="bdb22-111">Només podeu especificar els atributs que hi ha a l'entitat de perfil de client que heu creat durant el procés d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="bdb22-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="bdb22-112">Obriu la pàgina **Clients** i seleccioneu **Cerca i filtra l'índex**.</span><span class="sxs-lookup"><span data-stu-id="bdb22-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="bdb22-113">Seleccioneu **+ Afegeix** per especificar els camps indexats.</span><span class="sxs-lookup"><span data-stu-id="bdb22-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="bdb22-114">Seleccioneu els atributs de la llista que voleu afegir com a camps indexats.</span><span class="sxs-lookup"><span data-stu-id="bdb22-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="bdb22-115">Sempre podeu afegir més atributs seleccionant **Afegeix**.</span><span class="sxs-lookup"><span data-stu-id="bdb22-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="bdb22-116">Per suprimir els atributs seleccionats, també podeu seleccionar el símbol **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="bdb22-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="bdb22-117">Explorar la taula de camps de client indexats</span><span class="sxs-lookup"><span data-stu-id="bdb22-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="bdb22-118">La següent informació es presenta a la taula.</span><span class="sxs-lookup"><span data-stu-id="bdb22-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="bdb22-119">**Nom**: representa el nom de l'atribut tal com es mostra a l'entitat de perfil del client.</span><span class="sxs-lookup"><span data-stu-id="bdb22-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="bdb22-120">**Tipus de dades**: especifica si el tipus de dades és una cadena, un número o una data.</span><span class="sxs-lookup"><span data-stu-id="bdb22-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="bdb22-121">**Inclòs a la cerca**: especifica si aquest atribut es pot utilitzar per cercar clients a la pàgina **Clients** mitjançant el camp **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="bdb22-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="bdb22-122">**Afegeix un filtre**: control per definir com es pot utilitzar aquest atribut per filtrar a la pàgina **Clients**.</span><span class="sxs-lookup"><span data-stu-id="bdb22-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="bdb22-123">Editar les opcions de filtratge per a un atribut determinat</span><span class="sxs-lookup"><span data-stu-id="bdb22-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="bdb22-124">El menú **Filtre** de la pàgina **Clients** pot incloure un nombre variable de nivells d'atribut (per exemple, diferents grups d'edat pels quals filtrar els clients).</span><span class="sxs-lookup"><span data-stu-id="bdb22-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="bdb22-125">Seleccioneu **Afegeix un filtre** per a un atribut determinat a la pàgina **Índex de cerca i filtre**.</span><span class="sxs-lookup"><span data-stu-id="bdb22-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="bdb22-126">Podeu definir el nombre de resultats i l'ordre en el qual s'organitzaran.</span><span class="sxs-lookup"><span data-stu-id="bdb22-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="bdb22-127">En funció del tipus de dades de l'atribut, apareixerà una dels subfinestres següents.</span><span class="sxs-lookup"><span data-stu-id="bdb22-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="bdb22-128">Atributs de cadena: especifiqueu el nombre de resultats que voleu a la subfinestra **Opcions del filtre de cadena** i la norma d'ordre per la qual s'organitzaran.</span><span class="sxs-lookup"><span data-stu-id="bdb22-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="bdb22-129">Atributs numèrics: especifiqueu els intervals inclosos a la subfinestra **Opcions del filtre de nombre** i la norma d'ordre per la qual s'organitzaran.</span><span class="sxs-lookup"><span data-stu-id="bdb22-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="bdb22-130">Atributs de data: especifiqueu els intervals inclosos a la subfinestra **Opcions del filtre de data** i la norma d'ordre per la qual s'organitzaran.</span><span class="sxs-lookup"><span data-stu-id="bdb22-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="bdb22-131">Seleccioneu **Desa** per aplicar els canvis.</span><span class="sxs-lookup"><span data-stu-id="bdb22-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="bdb22-132">Seleccioneu **Executa** una vegada que estigueu a punt per aplicar la configuració.</span><span class="sxs-lookup"><span data-stu-id="bdb22-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bdb22-133">Passos següents</span><span class="sxs-lookup"><span data-stu-id="bdb22-133">Next steps</span></span>

<span data-ttu-id="bdb22-134">Aneu a la pàgina **Clients** per cercar perfils de client o utilitzeu els camps indexats per veure un subconjunt de tots els perfils de client.</span><span class="sxs-lookup"><span data-stu-id="bdb22-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]