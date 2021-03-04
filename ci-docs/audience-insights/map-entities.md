---
title: Assignar entitats per a la unificació de dades
description: Assigneu dades per crear perfils de client unificats.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267023"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="3489d-103">Assignar entitats i atributs</span><span class="sxs-lookup"><span data-stu-id="3489d-103">Map entities and attributes</span></span>

<span data-ttu-id="3489d-104">L'**assignació** és la primera fase del procés d'unificació de dades de les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="3489d-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="3489d-105">L'assignació consta de tres fases:</span><span class="sxs-lookup"><span data-stu-id="3489d-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="3489d-106">*Selecció d'entitats*: identifiqueu les entitats combinables que condueixen a un conjunt de dades amb informació més completa sobre els clients.</span><span class="sxs-lookup"><span data-stu-id="3489d-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="3489d-107">*Selecció d'atributs*: per a cada entitat, identifiqueu les columnes que voleu combinar i conciliar en les fases de *concordança* i *combinació*.</span><span class="sxs-lookup"><span data-stu-id="3489d-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="3489d-108">Aquestes columnes s'anomenen *Atributs*.</span><span class="sxs-lookup"><span data-stu-id="3489d-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="3489d-109">*Selecció de clau principal i tipus semàntic*: per a cada entitat, identifiqueu un atribut que vulgueu definir com a clau principal per a l'entitat i per a cada atribut, identifiqueu un tipus semàntic que descrigui millor l'atribut.</span><span class="sxs-lookup"><span data-stu-id="3489d-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="3489d-110">Per obtenir més informació sobre el flux general d'unificació de dades, vegeu [Unificar](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="3489d-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="3489d-111">Seleccionar les primeres entitats</span><span class="sxs-lookup"><span data-stu-id="3489d-111">Select the first entities</span></span>

1. <span data-ttu-id="3489d-112">A les conclusions del públic, aneu a **Dades** > **Unifica** > **Assignació**.</span><span class="sxs-lookup"><span data-stu-id="3489d-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="3489d-113">Per iniciar la fase d'assignació, seleccioneu **Selecciona entitats**.</span><span class="sxs-lookup"><span data-stu-id="3489d-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="3489d-114">Seleccioneu les entitats i els atributs que voleu utilitzar a les fases de *coincidència* i *combinació*.</span><span class="sxs-lookup"><span data-stu-id="3489d-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="3489d-115">Podeu seleccionar els atributs necessaris individualment d'una entitat o incloure tots els atributs d'una entitat seleccionant la casella de selecció **Inclou tots els camps** del nivell d'entitat.</span><span class="sxs-lookup"><span data-stu-id="3489d-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="3489d-116">Es recomana seleccionar com a mínim dues entitats per beneficiar-se del procés d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="3489d-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3489d-117">![Exemple d'addició d'entitats](media/data-manager-configure-map-add-entities-example.png "Exemple d'addició d'entitats")</span><span class="sxs-lookup"><span data-stu-id="3489d-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="3489d-118">En aquest exemple, estem afegint les entitats **eCommerceContacts** i **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3489d-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="3489d-119">En triar aquestes entitats, podeu derivar informació sobre els client de quina empresa en línia són membres del programa de fidelització.</span><span class="sxs-lookup"><span data-stu-id="3489d-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="3489d-120">Podeu fer cerques per paraules clau a tots els atributs i les entitats per seleccionar els atributs necessaris que voleu assignar.</span><span class="sxs-lookup"><span data-stu-id="3489d-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3489d-121">![Exemple de camps de cerca](media/data-manager-configure-map-search-fields-example.png "Exemple de camps de cerca")</span><span class="sxs-lookup"><span data-stu-id="3489d-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="3489d-122">Seleccioneu **Aplica** per confirmar les seleccions.</span><span class="sxs-lookup"><span data-stu-id="3489d-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="3489d-123">Seleccioneu la clau principal i el tipus semàntic per als atributs</span><span class="sxs-lookup"><span data-stu-id="3489d-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="3489d-124">Després de seleccionar les entitats, la pàgina **Assignació** enumera les entitats seleccionades per a la revisió.</span><span class="sxs-lookup"><span data-stu-id="3489d-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="3489d-125">Definiu la clau principal per a una entitat i identifiqueu el tipus semàntic per a un atribut a l'entitat.</span><span class="sxs-lookup"><span data-stu-id="3489d-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="3489d-126">**Clau principal**: seleccioneu un atribut com a clau principal per a cadascuna de les entitats.</span><span class="sxs-lookup"><span data-stu-id="3489d-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="3489d-127">Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls.</span><span class="sxs-lookup"><span data-stu-id="3489d-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="3489d-128">Els atributs del tipus de dades de cadena, enter i GUID s'admeten com a claus principals i es mostraran en un camp perquè els seleccioneu.</span><span class="sxs-lookup"><span data-stu-id="3489d-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="3489d-129">**Tipus semàntic d'atribut**: categories dels atributs, com ara l'adreça electrònica o el nom.</span><span class="sxs-lookup"><span data-stu-id="3489d-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="3489d-130">Per utilitzar models d'IA per a la predicció intel·ligent de la semàntica, estalviar temps i millorar la precisió, establiu **Assignació intel·ligent** a **Activada**.</span><span class="sxs-lookup"><span data-stu-id="3489d-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="3489d-131">L'assignació intel·ligent destaca la recomanació semàntica basada en IA en el camp **Tipus**.</span><span class="sxs-lookup"><span data-stu-id="3489d-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="3489d-132">Si la establiu a **Desactivada**, veureu les nostres recomanacions normals d'assignació.</span><span class="sxs-lookup"><span data-stu-id="3489d-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="3489d-133">Podeu seleccionar qualsevol tipus semàntic de la llista d'opcions disponibles i substituir la selecció suggerida.</span><span class="sxs-lookup"><span data-stu-id="3489d-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3489d-134">![Tipus d'atribut i predicció semàntica](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipus d'atribut i predicció semàntica")</span><span class="sxs-lookup"><span data-stu-id="3489d-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="3489d-135">L'addició d'un tipus semàntic d'entitat personalitzat també és possible.</span><span class="sxs-lookup"><span data-stu-id="3489d-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="3489d-136">Seleccioneu el camp de tipus per a un atribut i escriviu el nom del tipus semàntic de l'atribut personalitzat.</span><span class="sxs-lookup"><span data-stu-id="3489d-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="3489d-137">D'aquesta manera, també podeu canviar els tipus d'atribut que s'han identificat pel sistema.</span><span class="sxs-lookup"><span data-stu-id="3489d-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="3489d-138">Tots els atributs per als quals s'identifica automàticament un tipus semàntic es classifiquen a la secció **Revisió dels camps assignats**.</span><span class="sxs-lookup"><span data-stu-id="3489d-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="3489d-139">Reviseu aquests atributs i els seus tipus semàntics perquè s'utilitzaran per combinar les entitats al pas de combinació d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="3489d-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="3489d-140">Els atributs que no estan assignats automàticament a un tipus semàntic s'agrupen a la secció **Definiu les dades als camps no assignats**.</span><span class="sxs-lookup"><span data-stu-id="3489d-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="3489d-141">Seleccioneu el camp tipus semàntic per als atributs no assignats o introduïu el nom del tipus d'atribut personalitzat.</span><span class="sxs-lookup"><span data-stu-id="3489d-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3489d-142">![Clau principal i tipus d'atribut](media/data-manager-configure-map-add-attributes.png "Clau principal i tipus d'atribut")</span><span class="sxs-lookup"><span data-stu-id="3489d-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="3489d-143">Un camp hauria d'assignar-se a l'usuari de tipus semàntic Person.FullName per emplenar el nom del client a la targeta del client.</span><span class="sxs-lookup"><span data-stu-id="3489d-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="3489d-144">Altrament, les targetes del client apareixeran sense nom.</span><span class="sxs-lookup"><span data-stu-id="3489d-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="3489d-145">Afegir i suprimir atributs i entitats</span><span class="sxs-lookup"><span data-stu-id="3489d-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="3489d-146">A **Unifica** > **Assigna**, seleccioneu **Edita els camps**.</span><span class="sxs-lookup"><span data-stu-id="3489d-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="3489d-147">A la subfinestra **Edita els camps**, afegiu o suprimiu els atributs i les entitats.</span><span class="sxs-lookup"><span data-stu-id="3489d-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="3489d-148">Utilitzeu la cerca o desplaçament per cercar i seleccionar els atributs i les entitats d'interès.</span><span class="sxs-lookup"><span data-stu-id="3489d-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="3489d-149">No podeu suprimir un atribut ni una entitat si ja s'han assignat.</span><span class="sxs-lookup"><span data-stu-id="3489d-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3489d-150">![Afegir o suprimir atributs](media/configure-data-map-edit.png "Afegir o suprimir atributs")</span><span class="sxs-lookup"><span data-stu-id="3489d-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="3489d-151">Seleccioneu **Aplica**.</span><span class="sxs-lookup"><span data-stu-id="3489d-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="3489d-152">Afegir imatges als perfils</span><span class="sxs-lookup"><span data-stu-id="3489d-152">Add images to profiles</span></span>

<span data-ttu-id="3489d-153">Si una entitat conté URL d'imatges de perfil o logotips disponibles públicament, podeu afegir-los al perfil del client unificat.</span><span class="sxs-lookup"><span data-stu-id="3489d-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="3489d-154">Seleccioneu l'entitat i cerqueu el camp que conté l'adreça URL a la imatge de perfil.</span><span class="sxs-lookup"><span data-stu-id="3489d-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="3489d-155">Al camp d'entrada **Tipus** introduïu manualment el valor següent:</span><span class="sxs-lookup"><span data-stu-id="3489d-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="3489d-156">Per a una persona: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="3489d-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="3489d-157">Per a una organització: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="3489d-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="3489d-158">Continueu amb els passos d'unificació i assegureu-vos que l'atribut que conté l'adreça URL de la imatge també s'afegeixi al pas [Combinació](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="3489d-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="3489d-159">Definir els atributs per a organitzacions</span><span class="sxs-lookup"><span data-stu-id="3489d-159">Set attributes for organizations</span></span>

<span data-ttu-id="3489d-160">Per a les organitzacions (versió preliminar), cal que el tipus d'atribut s'assigni a "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="3489d-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="3489d-161">![Clau principal i tipus d'atribut B2B](media/configure-data-map-edit-b2b.png "Clau principal i tipus d'atribut B2B")</span><span class="sxs-lookup"><span data-stu-id="3489d-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="3489d-162">Pas següent</span><span class="sxs-lookup"><span data-stu-id="3489d-162">Next step</span></span>

<span data-ttu-id="3489d-163">Com a part del procés d'unificació de dades, aneu a la pàgina **Coincidència**.</span><span class="sxs-lookup"><span data-stu-id="3489d-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="3489d-164">Visiteu [**Coincidència**](match-entities.md) per obtenir més informació sobre aquesta fase.</span><span class="sxs-lookup"><span data-stu-id="3489d-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="3489d-165">Consulteu el vídeo següent: [Introducció: crear un perfil de client unificat](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="3489d-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]