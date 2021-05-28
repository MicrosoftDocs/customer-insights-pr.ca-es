---
title: Crear i administrar segments
description: Creeu segments de clients per agrupar-los segons diversos atributs.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064925"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="8e75a-103">Crear i administrar segments</span><span class="sxs-lookup"><span data-stu-id="8e75a-103">Create and manage segments</span></span>

<span data-ttu-id="8e75a-104">Definiu filtres complexos per a l'entitat de client unificada i les entitats relacionades.</span><span class="sxs-lookup"><span data-stu-id="8e75a-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="8e75a-105">Cada segment, després del processament, crea un conjunt de registres de client que podeu exportar i on podeu prendre mesures.</span><span class="sxs-lookup"><span data-stu-id="8e75a-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="8e75a-106">Els segments s'administren a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="8e75a-107">A l'exemple següent s'il·lustra l'ús de la capacitat de segmentació.</span><span class="sxs-lookup"><span data-stu-id="8e75a-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="8e75a-108">Hem definit un segment per a clients que han encarregat com a mínim 500 USD de mercaderies en els últims 90 dies *i* que han participat en una trucada al servei d'atenció al client que s'ha derivat.</span><span class="sxs-lookup"><span data-stu-id="8e75a-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captura de pantalla de la IU de creador de segments amb dos grups que especifiquen un segment de client.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="8e75a-110">Crear un segment nou</span><span class="sxs-lookup"><span data-stu-id="8e75a-110">Create a new segment</span></span>

<span data-ttu-id="8e75a-111">Hi ha diverses maneres de crear un segment nou.</span><span class="sxs-lookup"><span data-stu-id="8e75a-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="8e75a-112">Aquesta secció descriu com es crea un *segment en blanc* des de zero.</span><span class="sxs-lookup"><span data-stu-id="8e75a-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="8e75a-113">També podeu crear un *segment ràpid* basat en entitats existents o utilitzar els models d'aprenentatge automàtic per obtenir *segments suggerits*.</span><span class="sxs-lookup"><span data-stu-id="8e75a-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="8e75a-114">Més informació: [Informació general dels segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8e75a-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="8e75a-115">En crear un segment, podeu desar un esborrany.</span><span class="sxs-lookup"><span data-stu-id="8e75a-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="8e75a-116">Es desarà com un segment inactiu i no es podrà activar fins que s'hagi acabat amb una configuració vàlida.</span><span class="sxs-lookup"><span data-stu-id="8e75a-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="8e75a-117">Aneu a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="8e75a-118">Seleccioneu **Nou** > **Segment en blanc**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="8e75a-119">A la subfinestra **Segment nou**, trieu un tipus de segment:</span><span class="sxs-lookup"><span data-stu-id="8e75a-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="8e75a-120">Els **segments dinàmics** [s'actualitzen](segments.md#refresh-segments) segons una planificació periòdica.</span><span class="sxs-lookup"><span data-stu-id="8e75a-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="8e75a-121">Els **segments estàtics** s'executen un cop es creen.</span><span class="sxs-lookup"><span data-stu-id="8e75a-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="8e75a-122">Proporcioneu un **Nom d'entitat de sortida** per al segment.</span><span class="sxs-lookup"><span data-stu-id="8e75a-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="8e75a-123">Opcionalment, proporcioneu un nom de visualització i una descripció que ajudi a identificar el segment.</span><span class="sxs-lookup"><span data-stu-id="8e75a-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="8e75a-124">Seleccioneu **Següent** per accedir a la pàgina **Creador de segments** on definiu un grup.</span><span class="sxs-lookup"><span data-stu-id="8e75a-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="8e75a-125">Un grup és un conjunt de clients.</span><span class="sxs-lookup"><span data-stu-id="8e75a-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="8e75a-126">Trieu l'entitat que inclou l'atribut pel qual voleu segmentar.</span><span class="sxs-lookup"><span data-stu-id="8e75a-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="8e75a-127">Trieu l'atribut pel qual voleu segmentar.</span><span class="sxs-lookup"><span data-stu-id="8e75a-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="8e75a-128">Aquest atribut pot tenir un de quatre tipus de valors: numèric, cadena, data o booleà.</span><span class="sxs-lookup"><span data-stu-id="8e75a-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="8e75a-129">Trieu un operador i un valor per a l'atribut seleccionat.</span><span class="sxs-lookup"><span data-stu-id="8e75a-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e75a-130">![Filtre de grup personalitzat](media/customer-group-numbers.png "Filtre de grup de client")</span><span class="sxs-lookup"><span data-stu-id="8e75a-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="8e75a-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="8e75a-131">Number</span></span> |<span data-ttu-id="8e75a-132">Definició</span><span class="sxs-lookup"><span data-stu-id="8e75a-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="8e75a-133">1</span><span class="sxs-lookup"><span data-stu-id="8e75a-133">1</span></span>     |<span data-ttu-id="8e75a-134">Entity</span><span class="sxs-lookup"><span data-stu-id="8e75a-134">Entity</span></span>          |
   |<span data-ttu-id="8e75a-135">2</span><span class="sxs-lookup"><span data-stu-id="8e75a-135">2</span></span>     |<span data-ttu-id="8e75a-136">Atribut</span><span class="sxs-lookup"><span data-stu-id="8e75a-136">Attribute</span></span>          |
   |<span data-ttu-id="8e75a-137">3</span><span class="sxs-lookup"><span data-stu-id="8e75a-137">3</span></span>    |<span data-ttu-id="8e75a-138">Operador</span><span class="sxs-lookup"><span data-stu-id="8e75a-138">Operator</span></span>         |
   |<span data-ttu-id="8e75a-139">4</span><span class="sxs-lookup"><span data-stu-id="8e75a-139">4</span></span>    |<span data-ttu-id="8e75a-140">Valor</span><span class="sxs-lookup"><span data-stu-id="8e75a-140">Value</span></span>         |

   1. <span data-ttu-id="8e75a-141">Per afegir més condicions a un grup, podeu utilitzar dos operadors lògics:</span><span class="sxs-lookup"><span data-stu-id="8e75a-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="8e75a-142">Operador **AND**: cal complir ambdues condicions com a part del procés de segmentació.</span><span class="sxs-lookup"><span data-stu-id="8e75a-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="8e75a-143">Aquesta opció és més útil quan definiu les condicions entre diverses entitats diferents.</span><span class="sxs-lookup"><span data-stu-id="8e75a-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="8e75a-144">Operador **OR**: una de les condicions ha de complir-se com a part del procés de segmentació.</span><span class="sxs-lookup"><span data-stu-id="8e75a-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="8e75a-145">Aquesta opció és més útil quan definiu diverses condicions per a la mateixa entitat.</span><span class="sxs-lookup"><span data-stu-id="8e75a-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="8e75a-146">![Operador OR quan s'ha de complir qualsevol condició](media/segmentation-either-condition.png "Operador OR quan s'ha de complir qualsevol condició")</span><span class="sxs-lookup"><span data-stu-id="8e75a-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="8e75a-147">Actualment és possible imbricar un operador **OR** en un operador **AND**, però no a l'inrevés.</span><span class="sxs-lookup"><span data-stu-id="8e75a-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="8e75a-148">Cada grup coincideix amb el conjunt de clients.</span><span class="sxs-lookup"><span data-stu-id="8e75a-148">Each group matches set of customers.</span></span> <span data-ttu-id="8e75a-149">Podeu combinar grups per incloure els clients necessaris per al cas empresarial.</span><span class="sxs-lookup"><span data-stu-id="8e75a-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="8e75a-150">Seleccioneu **Afegeix un grup**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="8e75a-151">![Afegir un grup a un grup de clients](media/customer-group-add-group.png "Afegir un grup a un grup de clients")</span><span class="sxs-lookup"><span data-stu-id="8e75a-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="8e75a-152">Seleccioneu un dels operadors de conjunts: **Union**, **Intersect** o **Except**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e75a-153">![Afegir una unió a un grup de clients](media/customer-group-union.png "Afegir una unió a un grup de clients")</span><span class="sxs-lookup"><span data-stu-id="8e75a-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="8e75a-154">**Unió** uneix els dos grups.</span><span class="sxs-lookup"><span data-stu-id="8e75a-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="8e75a-155">**Intersecció** solapa els dos grups.</span><span class="sxs-lookup"><span data-stu-id="8e75a-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="8e75a-156">Només es conserven al grup unificat les dades *que siguin comunes* a tots dos grups.</span><span class="sxs-lookup"><span data-stu-id="8e75a-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="8e75a-157">**Excepte** combina els dos grups.</span><span class="sxs-lookup"><span data-stu-id="8e75a-157">**Except** combines the two groups.</span></span> <span data-ttu-id="8e75a-158">Només es conserven les dades del grup A que *no siguin comunes* a les dades del grup B.</span><span class="sxs-lookup"><span data-stu-id="8e75a-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="8e75a-159">Si l'entitat està connectada a l'entitat de client unificada per [relacions](relationships.md), heu de definir el camí de la relació per crear un segment vàlid.</span><span class="sxs-lookup"><span data-stu-id="8e75a-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="8e75a-160">Afegiu les entitats del camí de la relació fins que pugueu seleccionar l'entitat **Client: CustomerInsights** del menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="8e75a-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="8e75a-161">A continuació, trieu **Tots els registres** per a cada pas.</span><span class="sxs-lookup"><span data-stu-id="8e75a-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e75a-162">![Camí de la relació durant la creació del segment](media/segments-multiple-relationships.png "Camí de la relació durant la creació del segment")</span><span class="sxs-lookup"><span data-stu-id="8e75a-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="8e75a-163">Per defecte, els segments generen una entitat de sortida que conté tots els atributs dels perfils de client que coincideixen amb els filtres definits.</span><span class="sxs-lookup"><span data-stu-id="8e75a-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="8e75a-164">Si un segment es basa en entitats que no són l'entitat *Client*, podeu afegir més atributs d'aquestes entitats a l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="8e75a-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="8e75a-165">Seleccioneu **Atributs del projecte** per triar els atributs que s'annexaran a l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="8e75a-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="8e75a-166">Exemple: un segment es basa en una entitat que conté dades d'activitat de client relacionades amb l'entitat *Client*.</span><span class="sxs-lookup"><span data-stu-id="8e75a-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="8e75a-167">El segment cerca tots els clients que han trucat al servei d'assistència durant els darrers 60 dies.</span><span class="sxs-lookup"><span data-stu-id="8e75a-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="8e75a-168">Podeu triar si voleu annexar la durada de la trucada i el nombre de trucades a tots els registres de client coincidents de l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="8e75a-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="8e75a-169">Aquesta informació pot ser útil per enviar correus electrònics amb enllaços útils als articles d'ajuda en línia i preguntes freqüents als clients que truquen sovint.</span><span class="sxs-lookup"><span data-stu-id="8e75a-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="8e75a-170">Els atributs previstos només funcionen per a les entitats que tenen una relació d'un a diversos amb l'entitat de client.</span><span class="sxs-lookup"><span data-stu-id="8e75a-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="8e75a-171">Per exemple, un client pot tenir diverses subscripcions.</span><span class="sxs-lookup"><span data-stu-id="8e75a-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="8e75a-172">Només podeu preveure els atributs d'una entitat que s'utilitza a cada grup de consulta de segment que esteu creant.</span><span class="sxs-lookup"><span data-stu-id="8e75a-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="8e75a-173">Els atributs previstos es factoritzen quan s'utilitzen operadors de conjunts.</span><span class="sxs-lookup"><span data-stu-id="8e75a-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="8e75a-174">Seleccioneu **Desa** per desar el segment.</span><span class="sxs-lookup"><span data-stu-id="8e75a-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="8e75a-175">El segment es desa i es processa si es validen tots els requisits.</span><span class="sxs-lookup"><span data-stu-id="8e75a-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="8e75a-176">Altrament, es desarà com a esborrany.</span><span class="sxs-lookup"><span data-stu-id="8e75a-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="8e75a-177">Seleccioneu **Torna als segments** per tornar a la pàgina **Segments**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="8e75a-178">Segments ràpids</span><span class="sxs-lookup"><span data-stu-id="8e75a-178">Quick segments</span></span>

<span data-ttu-id="8e75a-179">Els segments ràpids us permeten crear segments senzills amb un sol operador ràpidament per obtenir informació més ràpida.</span><span class="sxs-lookup"><span data-stu-id="8e75a-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="8e75a-180">A la pàgina **Segments**, seleccioneu **Crea** > **Crea de**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="8e75a-181">Seleccioneu l'opció **Perfils** per crear un segment que es basi en l'entitat de *client unificat*.</span><span class="sxs-lookup"><span data-stu-id="8e75a-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="8e75a-182">Seleccioneu l'opció **Mesures** per crear un segment en les mesures que heu creat anteriorment.</span><span class="sxs-lookup"><span data-stu-id="8e75a-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="8e75a-183">Seleccioneu l'opció **Intel·ligència** per crear un segment sobre una de les entitats de sortida que heu generat mitjançant les funcionalitats **Prediccions** o **Models personalitzats**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="8e75a-184">Al quadre de diàleg **Crea un segment ràpid**, seleccioneu un atribut del desplegable **Camp**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="8e75a-185">El sistema proporcionarà alguna informació addicional que us ajudarà a crear millors segments dels vostres clients.</span><span class="sxs-lookup"><span data-stu-id="8e75a-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="8e75a-186">Per als camps categòrics, mostrarem 10 comptes de clients principals.</span><span class="sxs-lookup"><span data-stu-id="8e75a-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="8e75a-187">Seleccioneu un **Valor** i seleccioneu **Revisa**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="8e75a-188">Per a un atribut numèric, el sistema mostrarà quin valor de l'atribut queda en el percentil de cada client.</span><span class="sxs-lookup"><span data-stu-id="8e75a-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="8e75a-189">Trieu un **Operador** i un **Valor** i, a continuació, seleccioneu **Revisa**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="8e75a-190">El sistema us proporcionarà una **Mida de segment aproximada**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="8e75a-191">Podeu triar si voleu generar el segment que heu definit o, en primer lloc, tornar a examinar-lo per aconseguir una mida diferent del segment.</span><span class="sxs-lookup"><span data-stu-id="8e75a-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8e75a-192">![Nom i estimació per a un segment ràpid](media/quick-segment-name.png "Nom i estimació per a un segment ràpid")</span><span class="sxs-lookup"><span data-stu-id="8e75a-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="8e75a-193">Proporcioneu un **Nom** per al segment.</span><span class="sxs-lookup"><span data-stu-id="8e75a-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="8e75a-194">Opcionalment, proporcioneu un **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="8e75a-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="8e75a-195">Seleccioneu **Desa** per crear el segment.</span><span class="sxs-lookup"><span data-stu-id="8e75a-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="8e75a-196">Quan el segment s'hagi acabat de processar, podeu visualitzar-lo com qualsevol altre segment que hàgiu creat.</span><span class="sxs-lookup"><span data-stu-id="8e75a-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8e75a-197">Passos següents</span><span class="sxs-lookup"><span data-stu-id="8e75a-197">Next steps</span></span>

<span data-ttu-id="8e75a-198">[Exporteu un segment](export-destinations.md) i exploreu la [targeta del client](customer-card-add-in.md) i els [connectors](export-power-bi.md) per obtenir informació al nivell del client.</span><span class="sxs-lookup"><span data-stu-id="8e75a-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
