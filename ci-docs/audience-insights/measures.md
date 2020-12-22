---
title: Crear i editar mesures
description: Definiu mesures relacionades amb el client per analitzar i reflectir el rendiment de determinades àrees de negoci.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405166"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="4c87d-103">Definir i administrar mesures</span><span class="sxs-lookup"><span data-stu-id="4c87d-103">Define and manage measures</span></span>

<span data-ttu-id="4c87d-104">Les **mesures** representen indicadors clau de rendiment (KPI) que reflecteixen el rendiment i la salut d'àrees de negoci específiques.</span><span class="sxs-lookup"><span data-stu-id="4c87d-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="4c87d-105">Les conclusions del públic proporcionen una experiència intuïtiva per a la creació de diversos tipus de mesures, mitjançant un creador de consultes que no necessita que escriviu cap codi o que valideu les mesures manualment.</span><span class="sxs-lookup"><span data-stu-id="4c87d-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="4c87d-106">Podeu fer el seguiment de les mesures de la vostra empresa a la pàgina **Inici**, veure les mesures per a clients específics a la **Targeta del client** i utilitzar les mesures per definir segments de clients a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="4c87d-107">Crear una mesura</span><span class="sxs-lookup"><span data-stu-id="4c87d-107">Create a measure</span></span>

<span data-ttu-id="4c87d-108">Aquesta secció us guiarà a través de la creació d'una mesura des de zero.</span><span class="sxs-lookup"><span data-stu-id="4c87d-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="4c87d-109">Podeu crear mesures amb dades de diverses fonts de dades connectades a través de l'entitat Client.</span><span class="sxs-lookup"><span data-stu-id="4c87d-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="4c87d-110">S'apliquen [límits de servei](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="4c87d-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="4c87d-111">A les conclusions del públic, aneu a **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="4c87d-112">Seleccioneu **Mesura nova**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-112">Select **New measure**.</span></span>

3. <span data-ttu-id="4c87d-113">Trieu el **tipus** de mesura:</span><span class="sxs-lookup"><span data-stu-id="4c87d-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="4c87d-114">**Atribut de client**: un únic camp per client que reflecteix una puntuació, un valor o un estat per al client.</span><span class="sxs-lookup"><span data-stu-id="4c87d-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="4c87d-115">Els atributs de client es creen com a atributs d'una nova entitat generada pel sistema anomenada **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="4c87d-116">**Mesura del client**: informació sobre el comportament dels clients amb un desglossament per dimensions seleccionades.</span><span class="sxs-lookup"><span data-stu-id="4c87d-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="4c87d-117">Es genera una entitat nova per a cada mesura, potencialment amb diversos registres per client.</span><span class="sxs-lookup"><span data-stu-id="4c87d-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="4c87d-118">**Mesura empresarial**: segueix el rendiment de les empreses i la salut.</span><span class="sxs-lookup"><span data-stu-id="4c87d-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="4c87d-119">Les mesures empresarials poden tenir dues sortides diferents: una sortida numèrica que es mostra a la pàgina **Inici** o a una entitat nova que trobeu a la pàgina **Entitats**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="4c87d-120">Proporcioneu un **Nom** i un **Nom de visualització** opcional i, a continuació, seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="4c87d-121">Per a la secció **Entitats**, seleccioneu la primera entitat de la llista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4c87d-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="4c87d-122">En aquest punt, haureu de decidir si necessitareu entitats addicionals com a part de la definició de la vostra mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c87d-123">![Definició de mesura](media/measure-definition.png "Definició de mesura")</span><span class="sxs-lookup"><span data-stu-id="4c87d-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="4c87d-124">Per afegir més entitats, seleccioneu **Afegeix una entitat** i seleccioneu les entitats que voleu utilitzar per a la mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4c87d-125">Només podeu seleccionar les entitats que tenen relacions amb l'entitat inicial.</span><span class="sxs-lookup"><span data-stu-id="4c87d-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="4c87d-126">Per obtenir més informació sobre la definició de relacions, vegeu [Relacions](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="4c87d-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="4c87d-127">Opcionalment, podeu configurar variables.</span><span class="sxs-lookup"><span data-stu-id="4c87d-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="4c87d-128">A la secció **Variables**, seleccioneu **Variable nova**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="4c87d-129">Les variables són càlculs que es fan a cadascun dels registres seleccionats.</span><span class="sxs-lookup"><span data-stu-id="4c87d-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="4c87d-130">Per exemple, la summa de vendes en punt de venda (POS) i en línia per a cadascun dels registres dels vostres clients.</span><span class="sxs-lookup"><span data-stu-id="4c87d-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="4c87d-131">Proporcioneu un **Nom** per a la variable.</span><span class="sxs-lookup"><span data-stu-id="4c87d-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="4c87d-132">A l'àrea **Expressió**, trieu un camp amb el qual començar el càlcul.</span><span class="sxs-lookup"><span data-stu-id="4c87d-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="4c87d-133">Escriviu una expressió a l'àrea **Expressió** mentre trieu més camps per incloure'ls al càlcul.</span><span class="sxs-lookup"><span data-stu-id="4c87d-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4c87d-134">Actualment, només s'admeten expressions aritmètiques.</span><span class="sxs-lookup"><span data-stu-id="4c87d-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="4c87d-135">A més, el càlcul de variables no està admès per a entitats de diferents [camins d'entitat](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="4c87d-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="4c87d-136">Seleccioneu **Fet**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-136">Select **Done**.</span></span>

11. <span data-ttu-id="4c87d-137">A la secció **Definició de la mesura**, definireu la manera com s'afegeixen les entitats escollides i de les variables calculades a una nova entitat o atribut de mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="4c87d-138">Seleccioneu **Dimensió nova**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-138">Select **New dimension**.</span></span> <span data-ttu-id="4c87d-139">Podeu pensar en una dimensió com a funció *Agrupa per*.</span><span class="sxs-lookup"><span data-stu-id="4c87d-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="4c87d-140">La sortida de dades de l'entitat o l'atribut de mesura s'agruparà per totes les dimensions definides.</span><span class="sxs-lookup"><span data-stu-id="4c87d-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4c87d-141">![Triar el cicle d'agregació](media/measures-businessreport-measure-definition2.png "Triar el cicle d'agregació")</span><span class="sxs-lookup"><span data-stu-id="4c87d-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="4c87d-142">Seleccioneu o introduïu la informació següent com a part de la definició de la dimensió:</span><span class="sxs-lookup"><span data-stu-id="4c87d-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="4c87d-143">**Entitat**: si definiu una entitat Mesura, hauria d'incloure com a mínim un atribut.</span><span class="sxs-lookup"><span data-stu-id="4c87d-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="4c87d-144">Si definiu un atribut Mesura, només inclourà un atribut per defecte.</span><span class="sxs-lookup"><span data-stu-id="4c87d-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="4c87d-145">Aquesta selecció és l'elecció de l'entitat que inclou aquest atribut.</span><span class="sxs-lookup"><span data-stu-id="4c87d-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="4c87d-146">**Camp**: trieu l'atribut específic que s'ha d'incloure a l'entitat o l'atribut de mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="4c87d-147">**Dipòsit**: trieu si voleu agregar dades diàriament, mensualment o anualment.</span><span class="sxs-lookup"><span data-stu-id="4c87d-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="4c87d-148">Només es tracta d'una selecció obligatòria si heu seleccionat un atribut de tipus de data.</span><span class="sxs-lookup"><span data-stu-id="4c87d-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="4c87d-149">**Com a**: defineix el nom del camp nou.</span><span class="sxs-lookup"><span data-stu-id="4c87d-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="4c87d-150">**Nom de visualització**: defineix el nom de visualització del camp.</span><span class="sxs-lookup"><span data-stu-id="4c87d-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c87d-151">La mesura empresarial es desarà com una entitat de número únic i es mostrarà a la pàgina **Inici**, tret que afegiu més dimensions a la mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="4c87d-152">Després d'afegir més dimensions, la mesura *no* es mostrarà a la pàgina **Inici**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="4c87d-153">Opcionalment, afegiu funcions d'agregació.</span><span class="sxs-lookup"><span data-stu-id="4c87d-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="4c87d-154">Qualsevol agregació que creeu resulta en un valor nou a l'entitat o l'atribut de mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="4c87d-155">Les funcions d'agregació admeses són: **Mínim**, **Màxim**, **Mitjana**, **Mediana**, **Suma**, **Recompte únic**, **Primer** (pren el primer registre d'un valor de dimensió) i **Últim** (pren l'últim registre afegit a un valor de dimensió).</span><span class="sxs-lookup"><span data-stu-id="4c87d-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="4c87d-156">Seleccioneu **Desa** per aplicar els canvis a la mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="4c87d-157">Administrar les mesures</span><span class="sxs-lookup"><span data-stu-id="4c87d-157">Manage your measures</span></span>

<span data-ttu-id="4c87d-158">Un cop creada com a mínim una mesura, apareixerà una llista de mesures a la pàgina **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="4c87d-159">Trobareu informació sobre el tipus de mesura, el creador, la data i l'hora de la creació, la data i l'hora de la darrera edició, l'estat (si la mesura està activa, inactiva o amb errors) i la data i l'hora de la darrera actualització.</span><span class="sxs-lookup"><span data-stu-id="4c87d-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="4c87d-160">Quan seleccioneu una mesura de la llista, podeu veure una visualització prèvia de la seva sortida.</span><span class="sxs-lookup"><span data-stu-id="4c87d-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="4c87d-161">Per actualitzar totes les mesures al mateix temps, seleccioneu **Actualitza-ho tot** sense seleccionar una mesura concreta.</span><span class="sxs-lookup"><span data-stu-id="4c87d-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4c87d-162">![Accions per administrar mesures individuals](media/measure-actions.png "Accions per administrar mesures individuals")</span><span class="sxs-lookup"><span data-stu-id="4c87d-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="4c87d-163">De manera alternativa, seleccioneu una mesura de la llista i feu una de les accions següents:</span><span class="sxs-lookup"><span data-stu-id="4c87d-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="4c87d-164">Seleccioneu el nom de la mesura per veure'n els detalls.</span><span class="sxs-lookup"><span data-stu-id="4c87d-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="4c87d-165">**Editeu** la configuració de la mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="4c87d-166">**Canvieu el nom** de la mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-166">**Rename** the measure.</span></span>
- <span data-ttu-id="4c87d-167">**Suprimiu** la mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-167">**Delete** the measure.</span></span>
- <span data-ttu-id="4c87d-168">Seleccioneu els punts suspensius (...) i, a continuació, **Actualitza** per iniciar el procés d'actualització per a la mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="4c87d-169">Seleccioneu els punts suspensius (...) i després **Baixa** per obtenir un fitxer .CSV de la mesura.</span><span class="sxs-lookup"><span data-stu-id="4c87d-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="4c87d-170">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="4c87d-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="4c87d-171">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="4c87d-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="4c87d-172">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="4c87d-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="4c87d-173">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.</span><span class="sxs-lookup"><span data-stu-id="4c87d-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="4c87d-174">Pas següent</span><span class="sxs-lookup"><span data-stu-id="4c87d-174">Next step</span></span>

<span data-ttu-id="4c87d-175">Podeu utilitzar les mesures existents per crear el primer segment de client a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="4c87d-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="4c87d-176">Per obtenir més informació, vegeu [Segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4c87d-176">For more information, see [Segments](segments.md).</span></span>
