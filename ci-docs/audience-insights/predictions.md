---
title: Emplenar dades parcials mitjançant prediccions
description: Utilitzeu prediccions per emplenar les dades incompletes dels clients.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268260"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="7106b-103">Completar les dades parcials amb prediccions</span><span class="sxs-lookup"><span data-stu-id="7106b-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7106b-104">Les prediccions us permeten crear fàcilment valors previstos que poden millorar la comprensió d'un client.</span><span class="sxs-lookup"><span data-stu-id="7106b-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="7106b-105">A la pàgina **Intel·ligència** > **Prediccions**, seleccioneu **Les meves prediccions** per veure les prediccions que heu configurat en altres parts de les conclusions del públic i seguir personalitzant-les.</span><span class="sxs-lookup"><span data-stu-id="7106b-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="7106b-106">No podeu utilitzar aquesta característica si l'entorn utilitza l'emmagatzematge de l'Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="7106b-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="7106b-107">La característica de prediccions utilitza mitjans automatitzats per avaluar dades i fer prediccions a partir d'aquestes dades i, per tant, té la capacitat de ser utilitzada com a mètode de perfilació, com es defineix el terme al Reglament general de protecció de dades ("RGPD").</span><span class="sxs-lookup"><span data-stu-id="7106b-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="7106b-108">L'ús del client d'aquesta característica per processar les dades pot estar subjecte a l'RGPD o altres lleis o regulacions.</span><span class="sxs-lookup"><span data-stu-id="7106b-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="7106b-109">Us responsabilitzeu de garantir que l'ús del Dynamics 365 Customer Insights, incloent-hi prediccions, compleixi totes les lleis i normatives aplicables, incloent-hi la legislació relacionada amb la privadesa, les dades personals, les dades biomètriques, la protecció de dades i la confidencialitat de comunicació.</span><span class="sxs-lookup"><span data-stu-id="7106b-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7106b-110">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="7106b-110">Prerequisites</span></span>

<span data-ttu-id="7106b-111">Per tal que la vostra organització pugui utilitzar la característica de prediccions, heu de complir els requisits previs següents:</span><span class="sxs-lookup"><span data-stu-id="7106b-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="7106b-112">La vostra organització té una instància [configurada al Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) i es troba a la mateixa organització que el Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7106b-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="7106b-113">El vostre entorn s'adjunta a la vostra instància del Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7106b-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="7106b-114">Si [creeu un nou entorn](manage-environments.md), configureu-lo al quadre de diàleg **Crea un entorn** i seleccioneu **Avançat**.</span><span class="sxs-lookup"><span data-stu-id="7106b-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="7106b-115">Si ja heu creat un entorn, aneu a la seva configuració i seleccioneu **Avançat**.</span><span class="sxs-lookup"><span data-stu-id="7106b-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="7106b-116">De qualsevol manera, a la secció **Utilitza les prediccions**, introduïu l'adreça URL de la instància del Common Data Service a la qual voleu adjuntar l'entorn.</span><span class="sxs-lookup"><span data-stu-id="7106b-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="7106b-117">Crear una predicció a l'entitat Client</span><span class="sxs-lookup"><span data-stu-id="7106b-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="7106b-118">A les conclusions del públic, aneu a **Dades** > **Entitats**.</span><span class="sxs-lookup"><span data-stu-id="7106b-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="7106b-119">Seleccioneu l'entitat **Client**.</span><span class="sxs-lookup"><span data-stu-id="7106b-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="7106b-120">A l'entitat **Client: CustomerInsights**, seleccioneu la pestanya **Camps**.</span><span class="sxs-lookup"><span data-stu-id="7106b-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="7106b-121">Cerqueu el nom de l'atribut per al qual voleu predir els valors i, a continuació, seleccioneu la icona **Informació general** a la columna **Resum**.</span><span class="sxs-lookup"><span data-stu-id="7106b-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7106b-122">![Icona d'informació general](media/intelligence-overviewicon.png "Icona d'informació general")</span><span class="sxs-lookup"><span data-stu-id="7106b-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="7106b-123">Si hi ha un índex elevat de valors que falten per a l'atribut, seleccioneu **Prediu els valors que falten** per continuar amb la vostra predicció.</span><span class="sxs-lookup"><span data-stu-id="7106b-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7106b-124">![Estat d'informació general amb el botó Prediu els valors que falten](media/intelligence-overviewpredictmissingvalues.png "Estat d'informació general amb el botó Prediu els valors que falten")</span><span class="sxs-lookup"><span data-stu-id="7106b-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="7106b-125">Proporcioneu un **Nom de visualització** i un **Nom d'entitat de sortida** per als resultats de la predicció.</span><span class="sxs-lookup"><span data-stu-id="7106b-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="7106b-126">Una llista d'opcions prèviament emplenada es mostrarà, on podeu assignar els valors a una categoria que s'hagi predit.</span><span class="sxs-lookup"><span data-stu-id="7106b-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="7106b-127">En aquest cas, les úniques opcions de categoria seran 0 o 1, ja que s'assignen a la naturalesa certa/falsa o binària de la predicció.</span><span class="sxs-lookup"><span data-stu-id="7106b-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="7106b-128">Assigneu els valors de camp que voleu que es classifiquin com a "0" a la predicció final a "0" a la columna Categoria i els elements que voleu que es classifiquin com a "1" a la predicció final a "1".</span><span class="sxs-lookup"><span data-stu-id="7106b-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7106b-129">![Exemple que mostra els valors de camp assignats a categories](media/intelligence-categorymapping.png "Exemple que mostra els valors de camp assignats a categories")</span><span class="sxs-lookup"><span data-stu-id="7106b-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="7106b-130">Seleccioneu **Fet** i es processarà la predicció.</span><span class="sxs-lookup"><span data-stu-id="7106b-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="7106b-131">El processament tardarà una estona, en funció de la mida i la complexitat de les dades.</span><span class="sxs-lookup"><span data-stu-id="7106b-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="7106b-132">Els resultats estaran disponibles en una entitat nova basada en el **Nom de l'entitat de sortida** de la predicció que heu creat.</span><span class="sxs-lookup"><span data-stu-id="7106b-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="7106b-133">Crear una predicció durant la creació d'un segment</span><span class="sxs-lookup"><span data-stu-id="7106b-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="7106b-134">La predicció dels valors que falten per a un atribut específic determinat també és possible en crear un segment.</span><span class="sxs-lookup"><span data-stu-id="7106b-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="7106b-135">En concret, quan creeu ràpidament un segment segons la vostra entitat de client unificada o l'entitat Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="7106b-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="7106b-136">Com a part d'aquest flux, trieu un atribut específic en el qual basar el vostre segment com la satisfacció del client o l'import de la compra.</span><span class="sxs-lookup"><span data-stu-id="7106b-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="7106b-137">Quan es crea un segment, el sistema suggerirà un mètode per predir els valors que falten per a aquest atribut.</span><span class="sxs-lookup"><span data-stu-id="7106b-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="7106b-138">A les conclusions del públic, aneu a **Segments** i seleccioneu la peça **Perfils**.</span><span class="sxs-lookup"><span data-stu-id="7106b-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="7106b-139">Trieu un **Camp** del qual crear un segment a i seleccioneu un **Operador** i, a continuació, seleccioneu **Revisa**.</span><span class="sxs-lookup"><span data-stu-id="7106b-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="7106b-140">Proporcioneu un **Nom** i un **Nom de visualització** per al segment.</span><span class="sxs-lookup"><span data-stu-id="7106b-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="7106b-141">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="7106b-141">Select **Save**.</span></span>

5. <span data-ttu-id="7106b-142">Si el segment que heu creat té dades incompletes al camp d'origen, podeu triar predir els valors que falten.</span><span class="sxs-lookup"><span data-stu-id="7106b-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7106b-143">![Botó de predicció](media/segments-predictoption.png "Botó de predicció")</span><span class="sxs-lookup"><span data-stu-id="7106b-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="7106b-144">Proporcioneu un **Nom de visualització** i un **Nom d'entitat de sortida** per als resultats de la predicció.</span><span class="sxs-lookup"><span data-stu-id="7106b-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="7106b-145">Seleccioneu **Fet**.</span><span class="sxs-lookup"><span data-stu-id="7106b-145">Select **Done**.</span></span> <span data-ttu-id="7106b-146">La vostra predicció es generarà en breu en una entitat nova amb el nom que heu indicat per al **Nom de l'entitat de sortida**.</span><span class="sxs-lookup"><span data-stu-id="7106b-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="7106b-147">Visualitzar una predicció</span><span class="sxs-lookup"><span data-stu-id="7106b-147">View a prediction</span></span>

1. <span data-ttu-id="7106b-148">A les conclusions del públic, aneu a **Intel·ligència** > **Prediccions** > **Les meves prediccions**.</span><span class="sxs-lookup"><span data-stu-id="7106b-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="7106b-149">Seleccioneu la predicció que voleu revisar.</span><span class="sxs-lookup"><span data-stu-id="7106b-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="7106b-150">Seleccioneu els punts suspensius de la columna **Accions** i trieu **Visualitza**.</span><span class="sxs-lookup"><span data-stu-id="7106b-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="7106b-151">Veureu un nombre de punts de dades a la visualització de la vostra predicció.</span><span class="sxs-lookup"><span data-stu-id="7106b-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7106b-152">![Pàgina Prediccions](media/intelligence-predictionsviewpage.png "Pàgina Prediccions")</span><span class="sxs-lookup"><span data-stu-id="7106b-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="7106b-153">**Valors previstos** mostra l'assignació que heu creat durant la fase d'assignació de valor de camp a categoria.</span><span class="sxs-lookup"><span data-stu-id="7106b-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="7106b-154">Hi ha valors del conjunt de dades que s'han assignat a una categoria concreta.</span><span class="sxs-lookup"><span data-stu-id="7106b-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="7106b-155">-Els **influenciadors principals** són els factors del conjunt de dades que tenen més probabilitats d'influir en la confiança de la predicció del valor del camp assignat a una categoria concreta.</span><span class="sxs-lookup"><span data-stu-id="7106b-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="7106b-156">El **rendiment** indica la manera com estan les prediccions.</span><span class="sxs-lookup"><span data-stu-id="7106b-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="7106b-157">Seleccioneu l'enllaç per obtenir més informació.</span><span class="sxs-lookup"><span data-stu-id="7106b-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="7106b-158">**Visualització prèvia** mostra mostres del conjunt de dades de sortida de la predicció i la probabilitat, o la confiança, del valor previst, on 0 és incert i 1 és segur.</span><span class="sxs-lookup"><span data-stu-id="7106b-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="7106b-159">Actualitzar una predicció</span><span class="sxs-lookup"><span data-stu-id="7106b-159">Update a prediction</span></span>

1. <span data-ttu-id="7106b-160">A les conclusions del públic, aneu a **Intel·ligència** > **Prediccions** > **Les meves prediccions**.</span><span class="sxs-lookup"><span data-stu-id="7106b-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="7106b-161">Seleccioneu la predicció que voleu actualitzar i seleccioneu la icona **Actualitza**.</span><span class="sxs-lookup"><span data-stu-id="7106b-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="7106b-162">La predicció es planificarà per processar-la.</span><span class="sxs-lookup"><span data-stu-id="7106b-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="7106b-163">Podeu veure l'hora que s'ha actualitzat per última vegada a la columna **Darrera actualització** de la pàgina **Prediccions**.</span><span class="sxs-lookup"><span data-stu-id="7106b-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="7106b-164">Editar una predicció</span><span class="sxs-lookup"><span data-stu-id="7106b-164">Edit a prediction</span></span>

<span data-ttu-id="7106b-165">Després d'haver creat una predicció, podeu personalitzar el model de l'AI Builder per augmentar l'eficàcia del model.</span><span class="sxs-lookup"><span data-stu-id="7106b-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="7106b-166">A les conclusions del públic, aneu a **Intel·ligència** > **Prediccions** > **Les meves prediccions**.</span><span class="sxs-lookup"><span data-stu-id="7106b-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="7106b-167">Seleccioneu la predicció que voleu editar.</span><span class="sxs-lookup"><span data-stu-id="7106b-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="7106b-168">Seleccioneu els punts suspensius de la columna **Accions** i trieu **Visualitza**.</span><span class="sxs-lookup"><span data-stu-id="7106b-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="7106b-169">Seleccioneu **Personalitza a l'AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="7106b-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="7106b-170">Actualitzeu el model a l'AI Builder.</span><span class="sxs-lookup"><span data-stu-id="7106b-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="7106b-171">[Més informació sobre la gestió de models a l'AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="7106b-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="7106b-172">A la següent execució de la vostra predicció s'utilitzarà el model actualitzat que hàgiu creat.</span><span class="sxs-lookup"><span data-stu-id="7106b-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="7106b-173">Els models nous creats a l'AI Builder no es mostraran a les conclusions del públic si no s'ha creat el model a partir de les experiències enumerades anteriorment.</span><span class="sxs-lookup"><span data-stu-id="7106b-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="7106b-174">Suprimir una predicció</span><span class="sxs-lookup"><span data-stu-id="7106b-174">Remove a prediction</span></span>

1. <span data-ttu-id="7106b-175">A les conclusions del públic, aneu a **Intel·ligència** > **Prediccions** > **Les meves prediccions**.</span><span class="sxs-lookup"><span data-stu-id="7106b-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="7106b-176">Seleccioneu la predicció que voleu suprimir.</span><span class="sxs-lookup"><span data-stu-id="7106b-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="7106b-177">Seleccioneu els punts suspensius de la columna **Accions** i trieu **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="7106b-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="7106b-178">Confirmar la supressió.</span><span class="sxs-lookup"><span data-stu-id="7106b-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7106b-179">Detecció d'errors</span><span class="sxs-lookup"><span data-stu-id="7106b-179">Troubleshooting</span></span>

<span data-ttu-id="7106b-180">Si no podeu completar el procés d'adjunció del Common Data Service a causa d'un error, podeu provar d'acabar el procés manualment.</span><span class="sxs-lookup"><span data-stu-id="7106b-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="7106b-181">Hi ha dos problemes coneguts que es poden produir en el procés d'adjunció:</span><span class="sxs-lookup"><span data-stu-id="7106b-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="7106b-182">La solució de complement de targeta de client no està instal·lada.</span><span class="sxs-lookup"><span data-stu-id="7106b-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="7106b-183">Completeu les instruccions per [instal·lar i configurar la solució](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="7106b-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="7106b-184">No s'han concedit permisos de l'aplicació.</span><span class="sxs-lookup"><span data-stu-id="7106b-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="7106b-185">Aneu al [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7106b-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="7106b-186">Seleccioneu **Entorns**.</span><span class="sxs-lookup"><span data-stu-id="7106b-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="7106b-187">Seleccioneu els punts suspensius que hi ha al costat de l'entorn on voleu afegir el permís i seleccioneu **Configuració**.</span><span class="sxs-lookup"><span data-stu-id="7106b-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="7106b-188">Expandiu **Usuaris i permisos** i seleccioneu **Usuaris**.</span><span class="sxs-lookup"><span data-stu-id="7106b-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="7106b-189">Seleccioneu **+Nou** i seleccioneu **Usuari**.</span><span class="sxs-lookup"><span data-stu-id="7106b-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="7106b-190">Seleccioneu **Usuari de l'aplicació** si ja no està seleccionat i introduïu la següent informació:</span><span class="sxs-lookup"><span data-stu-id="7106b-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="7106b-191">**Nom d'usuari:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7106b-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="7106b-192">**Identificador d'aplicació:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="7106b-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="7106b-193">**Nom:** Customer</span><span class="sxs-lookup"><span data-stu-id="7106b-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="7106b-194">**Cognoms:** Insights</span><span class="sxs-lookup"><span data-stu-id="7106b-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="7106b-195">**Correu electrònic principal:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7106b-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="7106b-196">Seleccioneu **Desa i tanca**.</span><span class="sxs-lookup"><span data-stu-id="7106b-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="7106b-197">Seleccioneu l'usuari que acabeu de crear.</span><span class="sxs-lookup"><span data-stu-id="7106b-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="7106b-198">Seleccioneu **Administra les funcions** a la barra de menú superior.</span><span class="sxs-lookup"><span data-stu-id="7106b-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="7106b-199">Seleccioneu **Administrador del sistema** i, a continuació, seleccioneu **D'acord**.</span><span class="sxs-lookup"><span data-stu-id="7106b-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]