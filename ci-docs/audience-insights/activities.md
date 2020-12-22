---
title: Activitats del client
description: Definiu activitats de client i visualitzeu-les a la cronologia del client.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667217"
---
# <a name="customer-activities"></a><span data-ttu-id="11842-103">Activitats del client</span><span class="sxs-lookup"><span data-stu-id="11842-103">Customer activities</span></span>

<span data-ttu-id="11842-104">Combineu les activitats del client procedents de [diverses fonts](data-sources.md) al Dynamics 365 Customer Insights per crear una cronologia del client que enumeri les activitats en ordre cronològic.</span><span class="sxs-lookup"><span data-stu-id="11842-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="11842-105">Podeu incloure la cronologia a les aplicacions d'interacció amb els clients del Dynamics 365 mitjançant el [complement Targeta del client](customer-card-add-in.md) o en un escriptori digital del Power BI.</span><span class="sxs-lookup"><span data-stu-id="11842-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="11842-106">Definir una activitat</span><span class="sxs-lookup"><span data-stu-id="11842-106">Define an activity</span></span>

<span data-ttu-id="11842-107">Les fonts de dades inclouen entitats amb dades transaccionals i d'activitats procedents de diverses fonts de dades.</span><span class="sxs-lookup"><span data-stu-id="11842-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="11842-108">Identifiqueu aquestes entitats i seleccioneu les activitats que voleu visualitzar a la cronologia del client.</span><span class="sxs-lookup"><span data-stu-id="11842-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="11842-109">Trieu l'entitat que inclogui l'activitat o les activitats de destinació.</span><span class="sxs-lookup"><span data-stu-id="11842-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="11842-110">A les conclusions del públic, aneu a **Dades** > **Activitats**.</span><span class="sxs-lookup"><span data-stu-id="11842-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="11842-111">Seleccioneu **Afegeix una activitat**.</span><span class="sxs-lookup"><span data-stu-id="11842-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="11842-112">Una entitat ha de tenir com a mínim un atribut del tipus **Data** per ser inclosa en una cronologia de client i no es poden afegir entitats sense camps **Data**.</span><span class="sxs-lookup"><span data-stu-id="11842-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="11842-113">El control **Afegeix una activitat** està inhabilitat si no es troba cap entitat.</span><span class="sxs-lookup"><span data-stu-id="11842-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="11842-114">A la subfinestra **Afegeix una activitat**, definiu els valors per als camps següents:</span><span class="sxs-lookup"><span data-stu-id="11842-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="11842-115">**Entitat**: seleccioneu una entitat que inclogui dades transaccionals o d'activitat.</span><span class="sxs-lookup"><span data-stu-id="11842-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="11842-116">**Clau principal**: seleccioneu el camp que identifica de manera única un registre.</span><span class="sxs-lookup"><span data-stu-id="11842-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="11842-117">No hauria de contenir cap valor duplicat, valors buits o valors que faltin.</span><span class="sxs-lookup"><span data-stu-id="11842-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="11842-118">**Marca de temps**: seleccioneu el camp que representa l'hora d'inici de l'activitat.</span><span class="sxs-lookup"><span data-stu-id="11842-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="11842-119">**Esdeveniment**: seleccioneu el camp que és l'esdeveniment de l'activitat.</span><span class="sxs-lookup"><span data-stu-id="11842-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="11842-120">**Adreça web**: seleccioneu el camp que representa una adreça URL en la qual es proporciona informació addicional sobre aquesta activitat.</span><span class="sxs-lookup"><span data-stu-id="11842-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="11842-121">Per exemple, el sistema transaccional que és l'origen d'aquesta activitat.</span><span class="sxs-lookup"><span data-stu-id="11842-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="11842-122">Aquesta adreça URL pot ser qualsevol camp de la font de dades; o bé, es pot crear com a camp nou mitjançant una transformació del Power Query.</span><span class="sxs-lookup"><span data-stu-id="11842-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="11842-123">Aquestes dades d'URL s'emmagatzemaran a l'entitat Activitat unificada, que pot consumir-se de manera descendent amb API.</span><span class="sxs-lookup"><span data-stu-id="11842-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="11842-124">**Detalls**: opcionalment, seleccioneu el camp que s'afegeix per als detalls addicionals.</span><span class="sxs-lookup"><span data-stu-id="11842-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="11842-125">**Icona**: opcionalment, seleccioneu la icona que representa aquesta activitat.</span><span class="sxs-lookup"><span data-stu-id="11842-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="11842-126">**Tipus d'activitat**: definiu la referència del tipus d'activitat al Common Data Model que descriu millor la definició semàntica de l'activitat.</span><span class="sxs-lookup"><span data-stu-id="11842-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="11842-127">A la secció **Configura la relació**, configureu els detalls per connectar les dades d'activitat al client corresponent.</span><span class="sxs-lookup"><span data-stu-id="11842-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11842-128">![Definir la relació d'entitat](media/activities-entities-define.png "Definir la relació d'entitat")</span><span class="sxs-lookup"><span data-stu-id="11842-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="11842-129">**Camp d'entitat d'activitat**: seleccioneu el camp a la vostra entitat d'activitat que s'utilitzarà per establir una relació amb una altra entitat.</span><span class="sxs-lookup"><span data-stu-id="11842-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="11842-130">**Entitat de client**: seleccioneu l'entitat de client d'origen corresponent amb la qual l'entitat activitat tindrà una relació.</span><span class="sxs-lookup"><span data-stu-id="11842-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="11842-131">Només podeu relacionar-vos amb les entitats de client d'origen que s'utilitzen al procés d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="11842-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="11842-132">**Camp d'entitat de client**: aquest camp mostra la clau principal de l'entitat de client d'origen com a seleccionada al procés d'assignació.</span><span class="sxs-lookup"><span data-stu-id="11842-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="11842-133">Aquest camp de clau principal a l'entitat de client d'origen s'utilitza per establir una relació amb l'entitat d'activitat.</span><span class="sxs-lookup"><span data-stu-id="11842-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="11842-134">**Nom**: si ja hi ha una relació entre aquesta entitat d'activitat i l'entitat de client d'origen seleccionada, el nom de la relació serà només de lectura.</span><span class="sxs-lookup"><span data-stu-id="11842-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="11842-135">Si no existeix aquesta relació, es crearà una relació nova amb el nom que es proporciona aquí.</span><span class="sxs-lookup"><span data-stu-id="11842-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="11842-136">Seleccioneu **Desa** per aplicar els canvis.</span><span class="sxs-lookup"><span data-stu-id="11842-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="11842-137">A la pàgina **Activitats**, seleccioneu **Executa**.</span><span class="sxs-lookup"><span data-stu-id="11842-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="11842-138">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="11842-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="11842-139">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="11842-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="11842-140">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="11842-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="11842-141">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.</span><span class="sxs-lookup"><span data-stu-id="11842-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="11842-142">Editar una activitat</span><span class="sxs-lookup"><span data-stu-id="11842-142">Edit an activity</span></span>

1. <span data-ttu-id="11842-143">A les conclusions del públic, aneu a **Dades** > **Activitats**.</span><span class="sxs-lookup"><span data-stu-id="11842-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="11842-144">Seleccioneu l'entitat d'activitat que voleu editar i seleccioneu **Edita**.</span><span class="sxs-lookup"><span data-stu-id="11842-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="11842-145">O bé, podeu passar el cursor per sobre de la fila d'entitat i seleccionar la icona **Edita**.</span><span class="sxs-lookup"><span data-stu-id="11842-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="11842-146">Feu clic a a la icona **Edita**.</span><span class="sxs-lookup"><span data-stu-id="11842-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="11842-147">A la subfinestra **Edita l'activitat**, actualitzeu els valors i seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="11842-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="11842-148">A la pàgina **Activitats**, seleccioneu **Executa**.</span><span class="sxs-lookup"><span data-stu-id="11842-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="11842-149">Suprimir una activitat</span><span class="sxs-lookup"><span data-stu-id="11842-149">Delete an activity</span></span>

1. <span data-ttu-id="11842-150">A les conclusions del públic, aneu a **Dades** > **Activitats**.</span><span class="sxs-lookup"><span data-stu-id="11842-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="11842-151">Seleccioneu l'entitat d'activitat que voleu suprimir i seleccioneu **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="11842-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="11842-152">O bé, podeu passar el cursor per sobre de la fila d'entitat i seleccionar la icona **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="11842-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="11842-153">A més, podeu seleccionar diverses entitats d'activitat per suprimir-les alhora.</span><span class="sxs-lookup"><span data-stu-id="11842-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11842-154">![Editar o suprimir la relació d'entitats](media/activities-entities-edit-delete.png "Editar o suprimir la relació d'entitats")</span><span class="sxs-lookup"><span data-stu-id="11842-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="11842-155">Seleccioneu a la icona **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="11842-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="11842-156">Confirmeu la supressió.</span><span class="sxs-lookup"><span data-stu-id="11842-156">Confirm your deletion.</span></span>
