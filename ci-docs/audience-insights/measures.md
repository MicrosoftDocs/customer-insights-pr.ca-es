---
title: Crear i administrar mesures
description: Definiu mesures per analitzar i reflectir el rendiment del vostre negoci.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887928"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="ad0ce-103">Definir i administrar mesures</span><span class="sxs-lookup"><span data-stu-id="ad0ce-103">Define and manage measures</span></span>

<span data-ttu-id="ad0ce-104">Les mesures us ajuden a comprendre millor els comportaments dels clients i el rendiment empresarial.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="ad0ce-105">Miren els valors rellevants dels [perfils unificats](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="ad0ce-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="ad0ce-106">Per exemple, una empresa vol veure la *despesa total per client* per comprendre l'historial de compra del client individual o mesurar les *vendes totals de l'empresa* per comprendre els ingressos a nivell agregat de tot el negoci.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="ad0ce-107">Les mesures es creen mitjançant el creador de mesures, una plataforma de consulta de dades amb diversos operadors i opcions d'assignació simples.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="ad0ce-108">Permet filtrar les dades, agrupar els resultats, detectar [rutes de relació d'entitats](relationships.md) i obtenir una visualització prèvia de la sortida.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="ad0ce-109">Utilitzeu el creador de mesures per planificar activitats empresarials consultant dades de clients i extreure informació.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="ad0ce-110">Per exemple, la creació d'una mesura de *despesa total per client* i *retorn total per client* ajuda a identificar un grup de clients amb una despesa alta però amb un retorn alt.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="ad0ce-111">Podeu [crear un segment](segments.md) per dirigir les pròximes accions recomanades.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="ad0ce-112">Crear una mesura pròpia des de zero</span><span class="sxs-lookup"><span data-stu-id="ad0ce-112">Build your own measure from scratch</span></span>

<span data-ttu-id="ad0ce-113">Aquesta secció us guia al llarg de la creació d'una nova mesura des de zero.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="ad0ce-114">Podeu crear una mesura amb atributs de dades a partir d'entitats de dades que tenen una relació configurada per connectar-se a l'entitat Client.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="ad0ce-115">A les conclusions del públic, aneu a **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="ad0ce-116">Seleccioneu **Crea** i trieu **Crea'n una de pròpia**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="ad0ce-117">Seleccioneu **Edita el nom** i proporcioneu un **nom** per a la mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="ad0ce-118">Si la vostra nova configuració de mesura només té dos camps, per exemple, CustomerID i un càlcul, la sortida s'afegirà com una columna nova a l'entitat generada pel sistema anomenada Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="ad0ce-119">I podreu veure el valor de la mesura al perfil de client unificat.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="ad0ce-120">Altres mesures generaran les seves pròpies entitats.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="ad0ce-121">A l'àrea de configuració, trieu la funció d'agregació al menú desplegable **Seleccioneu una funció**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="ad0ce-122">Les funcions d'agregació inclouen:</span><span class="sxs-lookup"><span data-stu-id="ad0ce-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="ad0ce-123">**Suma**</span><span class="sxs-lookup"><span data-stu-id="ad0ce-123">**Sum**</span></span>
   - <span data-ttu-id="ad0ce-124">**Mitjana**</span><span class="sxs-lookup"><span data-stu-id="ad0ce-124">**Average**</span></span>
   - <span data-ttu-id="ad0ce-125">**Recompte**</span><span class="sxs-lookup"><span data-stu-id="ad0ce-125">**Count**</span></span>
   - <span data-ttu-id="ad0ce-126">**Compta únics**</span><span class="sxs-lookup"><span data-stu-id="ad0ce-126">**Count Unique**</span></span>
   - <span data-ttu-id="ad0ce-127">**Màx**</span><span class="sxs-lookup"><span data-stu-id="ad0ce-127">**Max**</span></span>
   - <span data-ttu-id="ad0ce-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="ad0ce-128">**Min**</span></span>
   - <span data-ttu-id="ad0ce-129">**Primer**: pren el primer valor del registre de dades</span><span class="sxs-lookup"><span data-stu-id="ad0ce-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="ad0ce-130">**Últim**: pren l'últim valor que s'ha afegit al registre de dades</span><span class="sxs-lookup"><span data-stu-id="ad0ce-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operadors per a càlculs de mesures.":::

1. <span data-ttu-id="ad0ce-132">Seleccioneu **Afegeix un atribut** per seleccionar les dades que necessiteu per crear aquesta mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="ad0ce-133">Seleccioneu la pestanya **Atributs**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="ad0ce-134">Entitat de dades: trieu l'entitat que inclou l'atribut que voleu mesurar.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="ad0ce-135">Atribut de dades: trieu l'atribut que voleu utilitzar a la funció d'agregació per calcular la mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="ad0ce-136">Només podeu seleccionar un atribut cada vegada.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="ad0ce-137">Per seleccionar un atribut de dades d'una mesura existent, seleccioneu la pestanya **Mesures**. O bé podeu cercar una entitat o un nom de mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="ad0ce-138">Seleccioneu **Afegeix** per afegir l'atribut seleccionat a la mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleccioneu un atribut que voleu utilitzar en els càlculs.":::

1. <span data-ttu-id="ad0ce-140">Per crear mesures més complexes, podeu afegir més atributs o utilitzar operadors matemàtics a la funció de mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Creeu una mesura complexa amb operadors matemàtics.":::

1. <span data-ttu-id="ad0ce-142">Per afegir filtres, seleccioneu el **Filtre** a l'àrea de configuració.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="ad0ce-143">A la secció **Afegeix un atribut** de la subfinestra **Filtres**, seleccioneu l'atribut que voleu utilitzar per crear filtres.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="ad0ce-144">Definiu els operadors de filtre per definir el filtre per a cada atribut seleccionat.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="ad0ce-145">Seleccioneu **Aplica** per afegir els filtres a la mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="ad0ce-146">Per afegir dimensions, seleccioneu **Dimensió** a l'àrea de configuració.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="ad0ce-147">Les dimensions es mostraran com a columnes a l'entitat de sortida de mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="ad0ce-148">Seleccioneu **Edita les dimensions** per afegir atributs de dades pels quals voleu agrupar els valors de mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="ad0ce-149">Per exemple, ciutat o gènere.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-149">For example, city or gender.</span></span> <span data-ttu-id="ad0ce-150">Per defecte, la dimensió *CustomerID* se selecciona per crear *mesures del nivell del client*.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="ad0ce-151">Si voleu crear *mesures de nivell de negoci*, podeu suprimir la dimensió per defecte.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="ad0ce-152">Seleccioneu **Fet** per afegir les dimensions a la mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="ad0ce-153">Si hi ha valors a les dades que heu de substituir per un enter, per exemple, substituir *nul* per *0*, seleccioneu **Regles**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="ad0ce-154">Configureu la regla i assegureu-vos que trieu només els nombres enters com a substituts.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="ad0ce-155">Si hi ha diversos rutes entre l'entitat de dades assignada i l'entitat *Client*, heu de triar un dels [camins de relació d'entitat](relationships.md) identificats.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="ad0ce-156">Els resultats de la mesura poden variar en funció del camí seleccionat.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="ad0ce-157">Seleccioneu **Preferències de les dades** i trieu el camí de l'entitat que s'utilitzarà per identificar la mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="ad0ce-158">Si només hi ha un camí a l'entitat *Client*, aquest control no es mostrarà.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="ad0ce-159">Seleccioneu **Fet** per aplicar la vostra selecció.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleccioneu la ruta d'entitat de la mesura.":::

1. <span data-ttu-id="ad0ce-161">Per afegir més càlculs per a la mesura, seleccioneu **Càlcul nou**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="ad0ce-162">Només podeu utilitzar les entitats al mateix camí d'entitat per als càlculs nous.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="ad0ce-163">Més càlculs es mostraran com a columnes noves a l'entitat de sortida de mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="ad0ce-164">Seleccioneu **...** en el càlcul per **duplicar**, **canviar el nom** o **suprimir** un càlcul d'una mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="ad0ce-165">A l'àrea **Visualització prèvia**, veureu l'esquema de dades de l'entitat de sortida de mesura, incloent-hi els filtres i dimensions.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="ad0ce-166">La visualització prèvia reacciona dinàmicament als canvis a la configuració.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="ad0ce-167">Seleccioneu **Executa** per calcular els resultats de la mesura configurada.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="ad0ce-168">Seleccioneu **Desa i tanca** si voleu mantenir la configuració actual i executar la mesura més endavant.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="ad0ce-169">Aneu a **Mesures** per veure la mesura que s'ha creat recentment a la llista.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="ad0ce-170">Utilitzar una plantilla per crear una mesura</span><span class="sxs-lookup"><span data-stu-id="ad0ce-170">Use a template to build a measure</span></span>

<span data-ttu-id="ad0ce-171">Podeu utilitzar plantilles predefinides de mesures que s'utilitzen habitualment per crear-les.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="ad0ce-172">Les descripcions detallades de les plantilles i una experiència guiada us ajuden a crear una mesura de manera eficient.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="ad0ce-173">Les plantilles es creen a partir de dades assignades de l'entitat *Activitat unificada*.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="ad0ce-174">Per tant, assegureu-vos que heu configurat [activitats de client](activities.md) abans de crear una mesura a partir d'una plantilla.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="ad0ce-175">Plantilles de mesura disponibles:</span><span class="sxs-lookup"><span data-stu-id="ad0ce-175">Available measure templates:</span></span> 
- <span data-ttu-id="ad0ce-176">Valor de transacció mitjà (ATV)</span><span class="sxs-lookup"><span data-stu-id="ad0ce-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="ad0ce-177">Valor total de la transacció</span><span class="sxs-lookup"><span data-stu-id="ad0ce-177">Total transaction value</span></span>
- <span data-ttu-id="ad0ce-178">Mitjana d'ingressos diaris</span><span class="sxs-lookup"><span data-stu-id="ad0ce-178">Average daily revenue</span></span>
- <span data-ttu-id="ad0ce-179">Mitjana d'ingressos anuals</span><span class="sxs-lookup"><span data-stu-id="ad0ce-179">Average yearly revenue</span></span>
- <span data-ttu-id="ad0ce-180">Recompte de transaccions</span><span class="sxs-lookup"><span data-stu-id="ad0ce-180">Transaction count</span></span>
- <span data-ttu-id="ad0ce-181">Punts de fidelitat obtinguts</span><span class="sxs-lookup"><span data-stu-id="ad0ce-181">Loyalty points earned</span></span>
- <span data-ttu-id="ad0ce-182">Punts de fidelitat bescanviats</span><span class="sxs-lookup"><span data-stu-id="ad0ce-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="ad0ce-183">Balanç de punts de fidelitat</span><span class="sxs-lookup"><span data-stu-id="ad0ce-183">Loyalty points balance</span></span>
- <span data-ttu-id="ad0ce-184">Vida del client activa</span><span class="sxs-lookup"><span data-stu-id="ad0ce-184">Active customer lifespan</span></span>
- <span data-ttu-id="ad0ce-185">Duració de la subscripció a la fidelitat</span><span class="sxs-lookup"><span data-stu-id="ad0ce-185">Loyalty membership duration</span></span>
- <span data-ttu-id="ad0ce-186">Temps des de l'última compra</span><span class="sxs-lookup"><span data-stu-id="ad0ce-186">Time since last purchase</span></span>

<span data-ttu-id="ad0ce-187">Al procediment següent es descriuen els passos per crear una mesura nova mitjançant una plantilla.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="ad0ce-188">A les conclusions del públic, aneu a **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="ad0ce-189">Seleccioneu **Crea** i seleccioneu **Tria una plantilla**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de pantalla del menú desplegable quan es crea una mesura nova amb la plantilla destacada.":::

1. <span data-ttu-id="ad0ce-191">Cerqueu la plantilla que s'ajusti a les vostres necessitats i seleccioneu **Tria la plantilla**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="ad0ce-192">Reviseu les dades necessàries i seleccioneu **Introducció** si teniu totes les dades col·locades.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="ad0ce-193">A la subfinestra **Edita el nom**, definiu el nom de la mesura i l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="ad0ce-194">Seleccioneu **Fet**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-194">Select **Done**.</span></span>

1. <span data-ttu-id="ad0ce-195">A la secció **Definiu el període de temps**, definiu el període de temps de les dades que voleu utilitzar.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="ad0ce-196">Trieu si voleu que la mesura nova cobreixi tot el conjunt de dades seleccionant **Tot el temps**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="ad0ce-197">O si voleu que la mesura se centri en un **Període de temps específic**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de pantalla que mostra la secció de període de temps en configurar una mesura a partir d'una plantilla.":::

1. <span data-ttu-id="ad0ce-199">A la secció següent, seleccioneu **Afegeix dades** per triar les activitats i assignar les dades corresponents de l'entitat *Activitat unificada*.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="ad0ce-200">Pas 1 de 2: a **Tipus d'activitat**, trieu el tipus d'entitat que voleu utilitzar.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="ad0ce-201">Per a les **Activitats**, seleccioneu les entitats que voleu assignar.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="ad0ce-202">Pas 2 de 2: trieu l'atribut de l'entitat *Activitat unificada* per al component que requereix la fórmula.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="ad0ce-203">Per exemple, per al valor de Transacció mitjana, és l'atribut que representa el Valor de transacció.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="ad0ce-204">Per a la **Marca horària de l'activitat**, trieu l'atribut de l'entitat Activitat unificada que representi la data i l'hora de l'activitat.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="ad0ce-205">Un cop l'assignació de dades s'ha completat, podeu veure l'estat com a **Completat** i el nom de les activitats i els atributs assignats.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captura de pantalla d'una configuració de plantilla de mesura completada.":::

1. <span data-ttu-id="ad0ce-207">Ara podeu seleccionar **Executa** per calcular els resultats de la mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="ad0ce-208">Per refinar-la més tard, seleccioneu **Desa l'esborrany**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="ad0ce-209">Administrar les mesures</span><span class="sxs-lookup"><span data-stu-id="ad0ce-209">Manage your measures</span></span>

<span data-ttu-id="ad0ce-210">Podeu consultar la llista de mesures a la pàgina **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="ad0ce-211">Trobareu informació sobre el tipus de mesura, l'autor, la data de creació, l'estat i l'estat.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="ad0ce-212">Quan seleccioneu una mesura de la llista, podeu obtenir una visualització prèvia de la sortida i baixar un fitxer .CSV.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="ad0ce-213">Per actualitzar totes les mesures al mateix temps, seleccioneu **Actualitza-ho tot** sense seleccionar una mesura concreta.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ad0ce-214">![Accions per administrar mesures individuals](media/measure-actions.png "Accions per administrar mesures individuals")</span><span class="sxs-lookup"><span data-stu-id="ad0ce-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="ad0ce-215">Seleccioneu una mesura de la llista per a les opcions següents:</span><span class="sxs-lookup"><span data-stu-id="ad0ce-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="ad0ce-216">Seleccioneu el nom de la mesura per veure'n els detalls.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="ad0ce-217">**Editeu** la configuració de la mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="ad0ce-218">**Actualitzeu** la mesura segons les dades més recents.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="ad0ce-219">**Canvieu el nom** de la mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-219">**Rename** the measure.</span></span>
- <span data-ttu-id="ad0ce-220">**Suprimiu** la mesura.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-220">**Delete** the measure.</span></span>
- <span data-ttu-id="ad0ce-221">**Activeu** o **desactiveu-la**.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="ad0ce-222">Les mesures inactives no s'actualitzaran durant una [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ad0ce-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="ad0ce-223">Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ad0ce-224">A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ad0ce-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ad0ce-225">Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ad0ce-226">Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.</span><span class="sxs-lookup"><span data-stu-id="ad0ce-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="ad0ce-227">Pas següent</span><span class="sxs-lookup"><span data-stu-id="ad0ce-227">Next step</span></span>

<span data-ttu-id="ad0ce-228">Podeu utilitzar mesures existents per crear un [segment de client](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ad0ce-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]