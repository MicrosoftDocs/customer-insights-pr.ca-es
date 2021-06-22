---
title: Relacions entre entitats i camins d'entitats
description: Creeu i administreu relacions entre entitats procedents de diverses fonts de dades.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171152"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="1b6ff-103">Relacions entre entitats</span><span class="sxs-lookup"><span data-stu-id="1b6ff-103">Relationships between entities</span></span>

<span data-ttu-id="1b6ff-104">Les relacions connecten entitats i defineixen una gràfica de les dades quan les entitats comparteixen un identificador comú, una externa.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="1b6ff-105">Es pot fer referència a aquesta clau externa d'una entitat a una altra.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="1b6ff-106">Les entitats connectades permeten definir segments i mesures segons diverses fonts de dades.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="1b6ff-107">Hi ha tres tipus de relacions:</span><span class="sxs-lookup"><span data-stu-id="1b6ff-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="1b6ff-108">Relacions del sistema no editables creades pel sistema com a part del procés d'unificació de dades</span><span class="sxs-lookup"><span data-stu-id="1b6ff-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="1b6ff-109">Relacions heretades no editables que es creen automàticament a partir de la ingesta de fonts de dades</span><span class="sxs-lookup"><span data-stu-id="1b6ff-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="1b6ff-110">Relacions personalitzades editables creades i configurades per usuaris</span><span class="sxs-lookup"><span data-stu-id="1b6ff-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="1b6ff-111">Relacions del sistema no editables</span><span class="sxs-lookup"><span data-stu-id="1b6ff-111">Non-editable system relationships</span></span>

<span data-ttu-id="1b6ff-112">Durant la unificació de dades, les relacions del sistema es creen automàticament a partir d'una coincidència intel·ligent.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="1b6ff-113">Aquestes relacions ajuden a relacionar els registres de perfil del client amb registres corresponents.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="1b6ff-114">El diagrama següent il·lustra la creació de tres relacions basades en el sistema.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="1b6ff-115">L'entitat de client es fa coincidir amb altres entitats per produir l'entitat *Client* unificada.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama amb rutes de relació de l'entitat de client amb tres relacions d'1 a n.":::

- <span data-ttu-id="1b6ff-117">Es crea una **relació *CustomerToContact*** entre l'entitat *Client* i l'entitat *Contacte*.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="1b6ff-118">L'entitat *Client* obté el camp clau **Contact_contactID** per relacionar-se amb el camp clau **contactID** de l'entitat *Contacte*.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="1b6ff-119">Es crea una **relació *CustomerToAccount*** entre l'entitat *Client* i l'entitat *Compte*.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="1b6ff-120">L'entitat *Client* obté el camp clau **Account_contactID** per relacionar-se amb el camp clau **accountID** de l'entitat *Compte*.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="1b6ff-121">Es crea una **relació *CustomerToWebAccount*** entre l'entitat *Client* i l'entitat *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="1b6ff-122">L'entitat *Client* obté el camp clau **WebAccount_webaccountID** per relacionar-se amb el camp clau **webaccountID** de l'entitat *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="1b6ff-123">Relacions heretades no editables</span><span class="sxs-lookup"><span data-stu-id="1b6ff-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="1b6ff-124">Durant el procés d'ingestió de dades, el sistema comprova les fonts de dades per si hi ha relacions existents.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="1b6ff-125">Si no hi ha cap relació, el sistema les crea automàticament.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="1b6ff-126">Aquestes relacions s'utilitzen també en processos descendents.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="1b6ff-127">Crear una relació personalitzada</span><span class="sxs-lookup"><span data-stu-id="1b6ff-127">Create a custom relationship</span></span>

<span data-ttu-id="1b6ff-128">La relació consisteix en una *entitat d'origen* que conté la clau externa i una *entitat de destinació* a la qual assenyala la clau externa de l'entitat d'origen.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="1b6ff-129">A les conclusions del públic, aneu a **Dades** > **Relacions**.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="1b6ff-130">Seleccioneu **Nova relació**.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="1b6ff-131">A la subfinestra **Relació nova**, proporcioneu la informació següent:</span><span class="sxs-lookup"><span data-stu-id="1b6ff-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Subfinestra lateral de relació nova amb camps d'entrada buits.":::

   - <span data-ttu-id="1b6ff-133">**Nom de la relació**: nom que reflecteix la finalitat de la relació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="1b6ff-134">Exemple: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="1b6ff-135">**Descripció**: descripció de la relació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="1b6ff-136">**Entitat d'origen**: entitat que s'utilitza com a origen a la relació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="1b6ff-137">Exemple: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="1b6ff-138">**Entitat d'arribada**: entitat que s'utilitza com a arribada de la relació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="1b6ff-139">Exemple: Client.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-139">Example: Customer.</span></span>
   - <span data-ttu-id="1b6ff-140">**Cardinalitat d'origen**: especifiqueu la cardinalitat de l'entitat d'origen.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="1b6ff-141">La cardinalitat descriu el nombre d'elements possibles en un conjunt.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="1b6ff-142">Sempre es relaciona amb la cardinalitat de destinació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="1b6ff-143">Podeu triar entre **Una** i **Diverses**.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="1b6ff-144">Només s'admeten les relacions de diversos a un i d'un a un.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="1b6ff-145">De diversos a un: diversos registres d'origen poden relacionar-se amb un registre de destinació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="1b6ff-146">Exemple: diversos casos de suport d'un únic client.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="1b6ff-147">Un a un: un registre d'origen únic està relacionat amb un registre de destinació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="1b6ff-148">Exemple: un identificador de fidelitat d'un únic client.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1b6ff-149">Les relacions de diversos a diversos es poden crear amb dues relacions de diversos a un i una entitat que enllaça que connecta l'entitat d'origen i l'entitat de destinació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="1b6ff-150">**Cardinalitat de destinació**: seleccioneu la cardinalitat dels registres de l'entitat de destinació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="1b6ff-151">**Camp clau d'origen**: camp clau d'origen de l'entitat d'origen.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="1b6ff-152">Exemple: SupportCase podria utilitzar CaseID com a camp clau extern.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="1b6ff-153">**Camp de clau de destinació**: el camp de clau de l'entitat de destinació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="1b6ff-154">Exemple: Client podria utilitzar el camp clau **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="1b6ff-155">Seleccioneu **Desa** per crear la connexió personalitzada.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="1b6ff-156">Visualitza relacions</span><span class="sxs-lookup"><span data-stu-id="1b6ff-156">View relationships</span></span>

<span data-ttu-id="1b6ff-157">A la pàgina Relacions s'enumeren totes les relacions que s'han creat.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="1b6ff-158">Cada fila representa una relació, que també inclou detalls sobre l'entitat d'origen, l'entitat de destinació i la cardinalitat.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Llista de relacions i opcions de la barra d'accions de la pàgina Relacions.":::

<span data-ttu-id="1b6ff-160">Aquesta pàgina ofereix un conjunt d'opcions per a relacions existents i noves:</span><span class="sxs-lookup"><span data-stu-id="1b6ff-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="1b6ff-161">**Relació nova**: [Crea una relació personalitzada](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="1b6ff-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="1b6ff-162">**Visualitzador**: [Exploreu el visualitzador de relacions](#explore-the-relationship-visualizer) per veure un diagrama de xarxa de les relacions existents i de la seva cardinalitat.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="1b6ff-163">**Filtra per**: trieu el tipus de relacions que es mostraran a la llista.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="1b6ff-164">**Cerca relacions**: utilitzeu una cerca basada en text en les propietats de les relacions.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="1b6ff-165">Explorar el visualitzador de relacions</span><span class="sxs-lookup"><span data-stu-id="1b6ff-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="1b6ff-166">El visualitzador de relacions mostra un diagrama de xarxa de les relacions existents entre les entitats connectades i la seva cardinalitat.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="1b6ff-167">Per personalitzar la visualització, podeu canviar la posició dels quadres arrossegant-los al llenç.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de pantalla del diagrama de xarxa del visualitzador de relacions amb connexions entre entitats relacionades.":::

<span data-ttu-id="1b6ff-169">Opcions disponibles:</span><span class="sxs-lookup"><span data-stu-id="1b6ff-169">Available options:</span></span> 
- <span data-ttu-id="1b6ff-170">**Exporta com a imatge**: deseu la visualització actual com a fitxer d'imatge.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="1b6ff-171">**Canvia a la disposició horitzontal/vertical**: canvieu l'alineació de les entitats i les relacions.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="1b6ff-172">**Edita**: actualitzeu les propietats de les relacions personalitzades a la subfinestra d'edició i deseu els canvis.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="1b6ff-173">Administrar le relacions existents</span><span class="sxs-lookup"><span data-stu-id="1b6ff-173">Manage existing relationships</span></span> 

<span data-ttu-id="1b6ff-174">A la pàgina Relacions, una fila representa cada relació.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="1b6ff-175">Seleccioneu una relació i trieu una de les opcions següents:</span><span class="sxs-lookup"><span data-stu-id="1b6ff-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="1b6ff-176">**Edita**: actualitzeu les propietats de les relacions personalitzades a la subfinestra d'edició i deseu els canvis.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="1b6ff-177">**Suprimeix**: suprimiu relacions personalitzades.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="1b6ff-178">**Visualitza**: visualitzeu relacions creades pel sistema i heretades.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="1b6ff-179">Pas següent</span><span class="sxs-lookup"><span data-stu-id="1b6ff-179">Next step</span></span>

<span data-ttu-id="1b6ff-180">Les relacions de sistema i les personalitzades s'utilitzen per [crear segments](segments.md) basats en diverses fonts de dades que ja no estan aïllades.</span><span class="sxs-lookup"><span data-stu-id="1b6ff-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
