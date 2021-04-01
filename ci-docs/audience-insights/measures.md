---
title: Crear i administrar mesures
description: Definiu mesures per analitzar i reflectir el rendiment del vostre negoci.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654720"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="27d82-103">Definir i administrar mesures</span><span class="sxs-lookup"><span data-stu-id="27d82-103">Define and manage measures</span></span>

<span data-ttu-id="27d82-104">Les mesures us ajuden a comprendre millor els comportaments dels clients i el rendiment empresarial recuperant valors rellevants dels [perfils unificats](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="27d82-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="27d82-105">Per exemple, una empresa vol veure la *despesa total per client* per comprendre l'historial de compra d'un client concret.</span><span class="sxs-lookup"><span data-stu-id="27d82-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="27d82-106">O mesurar les *vendes totals de l'empresa* per comprendre els ingressos del nivell agregat de tot el negoci.</span><span class="sxs-lookup"><span data-stu-id="27d82-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="27d82-107">Les mesures es creen mitjançant el creador de mesures, una plataforma de consulta de dades amb diversos operadors i opcions d'assignació simples.</span><span class="sxs-lookup"><span data-stu-id="27d82-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="27d82-108">Permet filtrar les dades, agrupar els resultats, detectar [rutes de relació d'entitats](relationships.md) i obtenir una visualització prèvia de la sortida.</span><span class="sxs-lookup"><span data-stu-id="27d82-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="27d82-109">Utilitzeu el creador de mesures per planificar activitats empresarials consultant dades de clients i extreure informació.</span><span class="sxs-lookup"><span data-stu-id="27d82-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="27d82-110">Per exemple, la creació d'una mesura de *despesa total per client* i *retorn total per client* ajuda a identificar un grup de clients amb una despesa alta però amb un retorn alt.</span><span class="sxs-lookup"><span data-stu-id="27d82-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="27d82-111">Podeu [crear un segment](segments.md) per dirigir les pròximes accions recomanades.</span><span class="sxs-lookup"><span data-stu-id="27d82-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="27d82-112">Crear una mesura</span><span class="sxs-lookup"><span data-stu-id="27d82-112">Create a measure</span></span>

<span data-ttu-id="27d82-113">Aquesta secció us guia al llarg de la creació d'una nova mesura des de zero.</span><span class="sxs-lookup"><span data-stu-id="27d82-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="27d82-114">Podeu crear una mesura amb atributs de dades a partir d'entitats de dades que tenen una relació configurada per connectar-se a l'entitat Client.</span><span class="sxs-lookup"><span data-stu-id="27d82-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="27d82-115">A les conclusions del públic, aneu a **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="27d82-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="27d82-116">Seleccioneu **Crea**.</span><span class="sxs-lookup"><span data-stu-id="27d82-116">Select **New**.</span></span>

1. <span data-ttu-id="27d82-117">Seleccioneu **Edita el nom** i proporcioneu un **nom** per a la mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="27d82-118">Si la vostra nova configuració de mesura només té dos camps, per exemple, CustomerID i un càlcul, la sortida s'afegirà com una columna nova a l'entitat generada pel sistema anomenada Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="27d82-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="27d82-119">I podreu veure el valor de la mesura al perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="27d82-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="27d82-120">Altres mesures generaran les seves pròpies entitats.</span><span class="sxs-lookup"><span data-stu-id="27d82-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="27d82-121">A l'àrea de configuració, trieu la funció d'agregació al menú desplegable **Seleccioneu una funció**.</span><span class="sxs-lookup"><span data-stu-id="27d82-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="27d82-122">Les funcions d'agregació inclouen:</span><span class="sxs-lookup"><span data-stu-id="27d82-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="27d82-123">**Suma**</span><span class="sxs-lookup"><span data-stu-id="27d82-123">**Sum**</span></span>
   - <span data-ttu-id="27d82-124">**Mitjana**</span><span class="sxs-lookup"><span data-stu-id="27d82-124">**Average**</span></span>
   - <span data-ttu-id="27d82-125">**Recompte**</span><span class="sxs-lookup"><span data-stu-id="27d82-125">**Count**</span></span>
   - <span data-ttu-id="27d82-126">**Compta únics**</span><span class="sxs-lookup"><span data-stu-id="27d82-126">**Count Unique**</span></span>
   - <span data-ttu-id="27d82-127">**Màx**</span><span class="sxs-lookup"><span data-stu-id="27d82-127">**Max**</span></span>
   - <span data-ttu-id="27d82-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="27d82-128">**Min**</span></span>
   - <span data-ttu-id="27d82-129">**Primer**: pren el primer valor del registre de dades</span><span class="sxs-lookup"><span data-stu-id="27d82-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="27d82-130">**Últim**: pren l'últim valor que s'ha afegit al registre de dades</span><span class="sxs-lookup"><span data-stu-id="27d82-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operadors per a càlculs de mesures.":::

1. <span data-ttu-id="27d82-132">Seleccioneu **Afegeix un atribut** per seleccionar les dades que necessiteu per crear aquesta mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="27d82-133">Seleccioneu la pestanya **Atributs**.</span><span class="sxs-lookup"><span data-stu-id="27d82-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="27d82-134">Entitat de dades: trieu l'entitat que inclou l'atribut que voleu mesurar.</span><span class="sxs-lookup"><span data-stu-id="27d82-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="27d82-135">Atribut de dades: trieu l'atribut que voleu utilitzar a la funció d'agregació per calcular la mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="27d82-136">Només podeu seleccionar un atribut cada vegada.</span><span class="sxs-lookup"><span data-stu-id="27d82-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="27d82-137">Per seleccionar un atribut de dades d'una mesura existent, seleccioneu la pestanya **Mesures**. O bé podeu cercar una entitat o un nom de mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="27d82-138">Seleccioneu **Afegeix** per afegir l'atribut seleccionat a la mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleccioneu un atribut que voleu utilitzar en els càlculs.":::

1. <span data-ttu-id="27d82-140">Per crear mesures més complexes, podeu afegir més atributs o utilitzar operadors matemàtics a la funció de mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Creeu una mesura complexa amb operadors matemàtics.":::

1. <span data-ttu-id="27d82-142">Per afegir filtres, seleccioneu el **Filtre** a l'àrea de configuració.</span><span class="sxs-lookup"><span data-stu-id="27d82-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="27d82-143">A la secció **Afegeix un atribut** de la subfinestra **Filtres**, seleccioneu l'atribut que voleu utilitzar per crear filtres.</span><span class="sxs-lookup"><span data-stu-id="27d82-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="27d82-144">Definiu els operadors de filtre per definir el filtre per a cada atribut seleccionat.</span><span class="sxs-lookup"><span data-stu-id="27d82-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="27d82-145">Seleccioneu **Aplica** per afegir els filtres a la mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="27d82-146">Per afegir dimensions, seleccioneu **Dimensió** a l'àrea de configuració.</span><span class="sxs-lookup"><span data-stu-id="27d82-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="27d82-147">Les dimensions es mostraran com a columnes a l'entitat de sortida de mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="27d82-148">Seleccioneu **Edita les dimensions** per afegir atributs de dades pels quals voleu agrupar els valors de mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="27d82-149">Per exemple, ciutat o gènere.</span><span class="sxs-lookup"><span data-stu-id="27d82-149">For example, city or gender.</span></span> <span data-ttu-id="27d82-150">Per defecte, la dimensió *CustomerID* se selecciona per crear *mesures del nivell del client*.</span><span class="sxs-lookup"><span data-stu-id="27d82-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="27d82-151">Si voleu crear *mesures de nivell de negoci*, podeu suprimir la dimensió per defecte.</span><span class="sxs-lookup"><span data-stu-id="27d82-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="27d82-152">Seleccioneu **Fet** per afegir les dimensions a la mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="27d82-153">Si hi ha diversos rutes entre l'entitat de dades assignada i l'entitat *Client*, heu de triar un dels [camins de relació d'entitat](relationships.md) identificats.</span><span class="sxs-lookup"><span data-stu-id="27d82-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="27d82-154">Els resultats de la mesura poden variar en funció del camí seleccionat.</span><span class="sxs-lookup"><span data-stu-id="27d82-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="27d82-155">Seleccioneu **Preferències de les dades** i trieu el camí de l'entitat que s'utilitzarà per identificar la mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="27d82-156">Si només hi ha un camí a l'entitat *Client*, aquest control no es mostrarà.</span><span class="sxs-lookup"><span data-stu-id="27d82-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="27d82-157">Seleccioneu **Fet** per aplicar la vostra selecció.</span><span class="sxs-lookup"><span data-stu-id="27d82-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleccioneu la ruta d'entitat de la mesura.":::

1. <span data-ttu-id="27d82-159">Per afegir més càlculs per a la mesura, seleccioneu **Càlcul nou**.</span><span class="sxs-lookup"><span data-stu-id="27d82-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="27d82-160">Només podeu utilitzar les entitats al mateix camí d'entitat per als càlculs nous.</span><span class="sxs-lookup"><span data-stu-id="27d82-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="27d82-161">Més càlculs es mostraran com a columnes noves a l'entitat de sortida de mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="27d82-162">Seleccioneu **...** en el càlcul per **duplicar**, **canviar el nom** o **suprimir** un càlcul d'una mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="27d82-163">A l'àrea **Visualització prèvia**, veureu l'esquema de dades de l'entitat de sortida de mesura, incloent-hi els filtres i dimensions.</span><span class="sxs-lookup"><span data-stu-id="27d82-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="27d82-164">La visualització prèvia reacciona dinàmicament als canvis a la configuració.</span><span class="sxs-lookup"><span data-stu-id="27d82-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="27d82-165">Seleccioneu **Executa** per calcular els resultats de la mesura configurada.</span><span class="sxs-lookup"><span data-stu-id="27d82-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="27d82-166">Seleccioneu **Desa i tanca** si voleu mantenir la configuració actual i executar la mesura més endavant.</span><span class="sxs-lookup"><span data-stu-id="27d82-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="27d82-167">Aneu a **Mesures** per veure la mesura que s'ha creat recentment a la llista.</span><span class="sxs-lookup"><span data-stu-id="27d82-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="27d82-168">Administrar les mesures</span><span class="sxs-lookup"><span data-stu-id="27d82-168">Manage your measures</span></span>

<span data-ttu-id="27d82-169">Un cop [creada una mesura](#create-a-measure), apareixerà una llista de mesures a la pàgina **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="27d82-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="27d82-170">Trobareu informació sobre el tipus de mesura, l'autor, la data de creació, l'estat i l'estat.</span><span class="sxs-lookup"><span data-stu-id="27d82-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="27d82-171">Quan seleccioneu una mesura de la llista, podeu obtenir una visualització prèvia de la sortida i baixar un fitxer .CSV.</span><span class="sxs-lookup"><span data-stu-id="27d82-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="27d82-172">Per actualitzar totes les mesures al mateix temps, seleccioneu **Actualitza-ho tot** sense seleccionar una mesura concreta.</span><span class="sxs-lookup"><span data-stu-id="27d82-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="27d82-173">![Accions per administrar mesures individuals](media/measure-actions.png "Accions per administrar mesures individuals")</span><span class="sxs-lookup"><span data-stu-id="27d82-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="27d82-174">Seleccioneu una mesura de la llista per a les opcions següents:</span><span class="sxs-lookup"><span data-stu-id="27d82-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="27d82-175">Seleccioneu el nom de la mesura per veure'n els detalls.</span><span class="sxs-lookup"><span data-stu-id="27d82-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="27d82-176">**Editeu** la configuració de la mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="27d82-177">**Actualitzeu** la mesura segons les dades més recents.</span><span class="sxs-lookup"><span data-stu-id="27d82-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="27d82-178">**Canvieu el nom** de la mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-178">**Rename** the measure.</span></span>
- <span data-ttu-id="27d82-179">**Suprimiu** la mesura.</span><span class="sxs-lookup"><span data-stu-id="27d82-179">**Delete** the measure.</span></span>
- <span data-ttu-id="27d82-180">**Activeu** o **desactiveu-la**.</span><span class="sxs-lookup"><span data-stu-id="27d82-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="27d82-181">Les mesures inactives no s'actualitzaran durant una [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="27d82-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="27d82-182">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="27d82-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="27d82-183">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="27d82-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="27d82-184">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="27d82-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="27d82-185">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.</span><span class="sxs-lookup"><span data-stu-id="27d82-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="27d82-186">Pas següent</span><span class="sxs-lookup"><span data-stu-id="27d82-186">Next step</span></span>

<span data-ttu-id="27d82-187">Podeu utilitzar mesures existents per crear un [segment de client](segments.md).</span><span class="sxs-lookup"><span data-stu-id="27d82-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]