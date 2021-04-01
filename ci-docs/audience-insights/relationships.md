---
title: Relacions entre entitats i camins d'entitats
description: Creeu i administreu relacions entre entitats procedents de diverses fonts de dades.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595200"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="a8a39-103">Relacions entre entitats</span><span class="sxs-lookup"><span data-stu-id="a8a39-103">Relationships between entities</span></span>

<span data-ttu-id="a8a39-104">Les relacions us ajuden a connectar entitats i generen un gràfic de dades quan les entitats comparteixen un identificador comú (clau externa) al qual es pot fer referència d'una entitat a una altra.</span><span class="sxs-lookup"><span data-stu-id="a8a39-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="a8a39-105">Les entitats connectades us permeten definir segments i mesures segons diverses fonts de dades.</span><span class="sxs-lookup"><span data-stu-id="a8a39-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="a8a39-106">Hi ha dos tipus de relacions.</span><span class="sxs-lookup"><span data-stu-id="a8a39-106">There are two types of relationships.</span></span> <span data-ttu-id="a8a39-107">Relacions del sistema no editables, que es creen automàticament, i relacions personalitzades, creades i configurades pels usuaris.</span><span class="sxs-lookup"><span data-stu-id="a8a39-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="a8a39-108">Durant els processos de coincidència i combinació, les relacions del sistema es creen en segon terme segons coincidències intel·ligents.</span><span class="sxs-lookup"><span data-stu-id="a8a39-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="a8a39-109">Aquestes relacions ajuden a relacionar els registres de perfil del client amb registres d'altres entitats corresponents.</span><span class="sxs-lookup"><span data-stu-id="a8a39-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="a8a39-110">El diagrama següent il·lustra la creació de tres relacions del sistema quan l'entitat de client coincideix amb entitats addicionals per produir l'entitat de perfil del client final.</span><span class="sxs-lookup"><span data-stu-id="a8a39-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a8a39-111">![Creació de relació](media/relationships-entities-merge.png "Creació de relació")</span><span class="sxs-lookup"><span data-stu-id="a8a39-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="a8a39-112">Es crea una **relació *CustomerToContact*** entre l'entitat Client i l'entitat Contacte.</span><span class="sxs-lookup"><span data-stu-id="a8a39-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="a8a39-113">L'entitat Client obté el camp clau **Contact_contactId** relacionar-se amb el camp clau **contactId** de l'entitat Contacte.</span><span class="sxs-lookup"><span data-stu-id="a8a39-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="a8a39-114">Es crea una **relació *CustomerToAccount*** entre l'entitat Client i l'entitat Compte.</span><span class="sxs-lookup"><span data-stu-id="a8a39-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="a8a39-115">L'entitat Client obté el camp clau **Account_contactId** relacionar-se amb el camp clau **accountId** de l'entitat Compte.</span><span class="sxs-lookup"><span data-stu-id="a8a39-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="a8a39-116">Es crea una **relació *CustomerToWebAccount*** entre l'entitat Client i l'entitat WebAccount.</span><span class="sxs-lookup"><span data-stu-id="a8a39-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="a8a39-117">L'entitat Client obté el camp clau **WebAccount_webaccountId** relacionar-se amb el camp clau **webaccountId** de l'entitat WebAccount.</span><span class="sxs-lookup"><span data-stu-id="a8a39-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="a8a39-118">Crear una relació</span><span class="sxs-lookup"><span data-stu-id="a8a39-118">Create a relationship</span></span>

<span data-ttu-id="a8a39-119">Definiu les relacions personalitzades a la pàgina **Relacions**.</span><span class="sxs-lookup"><span data-stu-id="a8a39-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="a8a39-120">Cada relació es compon d'una entitat d'origen (l'entitat que conté la clau externa) i una entitat de destinació (l'entitat a la qual apunta la clau externa de l'entitat d'origen).</span><span class="sxs-lookup"><span data-stu-id="a8a39-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="a8a39-121">A les conclusions del públic, aneu a **Dades** > **Relacions**.</span><span class="sxs-lookup"><span data-stu-id="a8a39-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="a8a39-122">Seleccioneu **Nova relació**.</span><span class="sxs-lookup"><span data-stu-id="a8a39-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="a8a39-123">A la subfinestra **Afegeix una relació**, proporcioneu la informació següent:</span><span class="sxs-lookup"><span data-stu-id="a8a39-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a8a39-124">![Introduïu els detalls de la relació](media/relationships-add.png "Introduïu els detalls de la relació")</span><span class="sxs-lookup"><span data-stu-id="a8a39-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="a8a39-125">**Nom de la relació**: nom que reflecteix la finalitat de la relació (per exemple, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="a8a39-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="a8a39-126">**Descripció**: descripció de la relació.</span><span class="sxs-lookup"><span data-stu-id="a8a39-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="a8a39-127">**Entitat d'origen**: seleccioneu l'entitat que s'utilitza com a origen a la relació (per exemple, WebLog).</span><span class="sxs-lookup"><span data-stu-id="a8a39-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="a8a39-128">**Cardinalitat**: seleccioneu la cardinalitat dels registres de l'entitat d'origen.</span><span class="sxs-lookup"><span data-stu-id="a8a39-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="a8a39-129">Per exemple, "molts" significa que hi ha diversos registres Weblog relacionats amb un WebAccount.</span><span class="sxs-lookup"><span data-stu-id="a8a39-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="a8a39-130">**Camp de clau d'origen**: representa el camp de clau externa a l'entitat d'origen.</span><span class="sxs-lookup"><span data-stu-id="a8a39-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="a8a39-131">Per exemple, WebLog té el camp de clau externa **accountId**.</span><span class="sxs-lookup"><span data-stu-id="a8a39-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="a8a39-132">**Entitat de destinació**: seleccioneu l'entitat que s'utilitza com a destinació a la relació (per exemple, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="a8a39-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="a8a39-133">**Cardinalitat de destinació**: seleccioneu la cardinalitat dels registres de l'entitat de destinació.</span><span class="sxs-lookup"><span data-stu-id="a8a39-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="a8a39-134">Per exemple, "un" significa que hi ha diversos registres Weblog relacionats amb un WebAccount.</span><span class="sxs-lookup"><span data-stu-id="a8a39-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="a8a39-135">**Camp de clau de destinació**: aquest camp representa el camp de clau de l'entitat de destinació.</span><span class="sxs-lookup"><span data-stu-id="a8a39-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="a8a39-136">Per exemple, WebAccount té el camp de clau **accountId**.</span><span class="sxs-lookup"><span data-stu-id="a8a39-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="a8a39-137">Només s'admeten les relacions de diversos a un i d'un a un.</span><span class="sxs-lookup"><span data-stu-id="a8a39-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="a8a39-138">Es poden crear relacions de diversos a diversos amb dues relacions de diversos a un i una entitat d'enllaç (una entitat que s'utilitza per connectar l'entitat d'origen i l'entitat de destinació).</span><span class="sxs-lookup"><span data-stu-id="a8a39-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="a8a39-139">Suprimir una relació</span><span class="sxs-lookup"><span data-stu-id="a8a39-139">Delete a relationship</span></span>

1. <span data-ttu-id="a8a39-140">A les conclusions del públic, aneu a **Dades** > **Relacions**.</span><span class="sxs-lookup"><span data-stu-id="a8a39-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="a8a39-141">Activeu les caselles de selecció de les relacions que voleu suprimir.</span><span class="sxs-lookup"><span data-stu-id="a8a39-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="a8a39-142">Seleccioneu **Suprimeix** a la part superior de la taula **Relacions**.</span><span class="sxs-lookup"><span data-stu-id="a8a39-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="a8a39-143">Confirmeu la supressió.</span><span class="sxs-lookup"><span data-stu-id="a8a39-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="a8a39-144">Pas següent</span><span class="sxs-lookup"><span data-stu-id="a8a39-144">Next step</span></span>

<span data-ttu-id="a8a39-145">Les relacions de sistema i personalitzades s'utilitzen per crear segments basats en diverses fonts de dades que ja no estan aïllades.</span><span class="sxs-lookup"><span data-stu-id="a8a39-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="a8a39-146">Per obtenir més informació, vegeu [Segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a8a39-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]