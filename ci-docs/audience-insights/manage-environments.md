---
title: Crear i administrar entorns
description: Apreneu a registrar-vos al servei i a administrar entorns.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598281"
---
# <a name="manage-environments"></a><span data-ttu-id="1243b-103">Gestionar entorns</span><span class="sxs-lookup"><span data-stu-id="1243b-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1243b-104">En aquest article s'explica com crear una organització nova i com proveir un entorn.</span><span class="sxs-lookup"><span data-stu-id="1243b-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="1243b-105">Registrar-se i crear una organització</span><span class="sxs-lookup"><span data-stu-id="1243b-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="1243b-106">Aneu al lloc web del [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="1243b-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="1243b-107">Seleccioneu **Introducció**.</span><span class="sxs-lookup"><span data-stu-id="1243b-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="1243b-108">Trieu l'escenari preferit de registre i seleccioneu l'enllaç corresponent.</span><span class="sxs-lookup"><span data-stu-id="1243b-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="1243b-109">Accepteu els termes i condicions i seleccioneu **Continua** per començar a crear l'organització.</span><span class="sxs-lookup"><span data-stu-id="1243b-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="1243b-110">Després de crear l'entorn, se us redirigirà al [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="1243b-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="1243b-111">Utilitzeu l'entorn de demostració per explorar l'aplicació o creeu un entorn nou amb els passos de la secció següent.</span><span class="sxs-lookup"><span data-stu-id="1243b-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="1243b-112">Després d'especificar la configuració de l'entorn, seleccioneu **Crea**.</span><span class="sxs-lookup"><span data-stu-id="1243b-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="1243b-113">Un cop creat correctament l'entorn, s'iniciarà la vostra sessió.</span><span class="sxs-lookup"><span data-stu-id="1243b-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="1243b-114">Crear un entorn en una organització existent</span><span class="sxs-lookup"><span data-stu-id="1243b-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="1243b-115">Hi ha dues maneres de crear un nou entorn.</span><span class="sxs-lookup"><span data-stu-id="1243b-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="1243b-116">Podeu especificar una configuració completament nova o bé podeu copiar alguns ajustaments de configuració des d'un entorn existent.</span><span class="sxs-lookup"><span data-stu-id="1243b-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="1243b-117">Per crear un entorn:</span><span class="sxs-lookup"><span data-stu-id="1243b-117">To create an environment:</span></span>

1. <span data-ttu-id="1243b-118">Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.</span><span class="sxs-lookup"><span data-stu-id="1243b-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="1243b-119">Seleccioneu **Crea**.</span><span class="sxs-lookup"><span data-stu-id="1243b-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1243b-120">![Configuració de l'entorn](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="1243b-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="1243b-121">En el diàleg **Crea un nou entorn**, seleccioneu **Nou entorn**.</span><span class="sxs-lookup"><span data-stu-id="1243b-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="1243b-122">Si voleu [copiar les dades de l'entorn actual](#additional-considerations-for-copy-configuration-preview), seleccioneu **Copia d'un entorn existent**.</span><span class="sxs-lookup"><span data-stu-id="1243b-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="1243b-123">Veureu una llista de tots els entorns disponibles a l'organització des d'on podeu copiar dades.</span><span class="sxs-lookup"><span data-stu-id="1243b-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="1243b-124">Proporcioneu els següents detalls:</span><span class="sxs-lookup"><span data-stu-id="1243b-124">Provide the following details:</span></span>
   - <span data-ttu-id="1243b-125">**Nom**: el nom de l'entorn en qüestió.</span><span class="sxs-lookup"><span data-stu-id="1243b-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="1243b-126">Aquest camp ja s'emplena si heu copiat des d'un entorn existent, però es pot canviar.</span><span class="sxs-lookup"><span data-stu-id="1243b-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="1243b-127">**Regió**: la regió en la qual s'implementa i s'allotja el servei.</span><span class="sxs-lookup"><span data-stu-id="1243b-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="1243b-128">**Tipus**: seleccioneu si voleu crear un entorn de producció o espai aïllat.</span><span class="sxs-lookup"><span data-stu-id="1243b-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="1243b-129">De manera opcional, podeu seleccionar **Configuració avançada**:</span><span class="sxs-lookup"><span data-stu-id="1243b-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="1243b-130">**Desa totes les dades a**: especifica on voleu emmagatzemar les dades de sortida generades amb el Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1243b-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="1243b-131">Tindreu dues opcions: **Emmagatzematge del Customer Insights** (un Azure Data Lake gestionat per l'equip del Customer Insights) i **Azure Data Lake Storage Gen2** (el vostre propi Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="1243b-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="1243b-132">Per defecte, se selecciona l'opció d'emmagatzematge al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1243b-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1243b-133">En desar les dades a l'Azure Data Lake Storage, accepteu que les dades es transferiran i s'emmagatzemaran a la ubicació geogràfica adequada per al compte d'emmagatzematge de l'Azure, que pot diferir amb la ubicació on s'emmagatzemen les dades al Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1243b-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="1243b-134">Més informació al Centre de confiança de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1243b-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="1243b-135">Actualment, les entitats ingerides sempre s'emmagatzemen al llac de dades gestionat pel Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1243b-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="1243b-136">Només s'admeten comptes d'emmagatzematge Gen2 de l'Azure Data Lake de la mateixa regió de l'Azure que la que vau seleccionar en crear l'entorn.</span><span class="sxs-lookup"><span data-stu-id="1243b-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="1243b-137">Només admetem comptes d'emmagatzematge de l'Azure Data Lake gen2 habilitats per a l'espai de noms jeràrquic (HNS).</span><span class="sxs-lookup"><span data-stu-id="1243b-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="1243b-138">En el caso de l'opció Gen2 de l'Azure Data Lake Storage, podeu triar entre utilitzar una opció basada en recursos i una basada en subscripcions per a l'autenticació.</span><span class="sxs-lookup"><span data-stu-id="1243b-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="1243b-139">Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="1243b-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="1243b-140">El nom del **Contenidor** no es pot canviar i serà "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="1243b-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="1243b-141">Si voleu utilitzar [prediccions](predictions.md) o configurar l'ús compartit de dades amb aplicacions i solucions basades en el Microsoft Dataverse, proporcioneu l'adreça URL de l'entorn del Microsoft Dataverse a **Configurar l'ús compartit de dades amb el Microsoft Dataverse i habilitar característiques addicionals**.</span><span class="sxs-lookup"><span data-stu-id="1243b-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="1243b-142">Seleccioneu **Habilita l'ús compartit de dades** per compartir les dades de sortida del Customer Insights amb el Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="1243b-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="1243b-143">L'ús compartit de dades amb el Microsoft Dataverse Managed Data Lake actualment no s'admet quan deseu totes les dades al vostre propi Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="1243b-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="1243b-144">La [predicció de valors que falten en una entitat](predictions.md) no està actualment admesa quan habiliteu l'ús compartit de dades amb el Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="1243b-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="1243b-145">![Opcions de configuració per habilitar l'ús compartit de dades amb el Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="1243b-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="1243b-146">Quan executeu processos, com ara la ingestió de dades o la creació de segments, les carpetes corresponents es crearan al compte d'emmagatzematge que hagueu especificat anteriorment.</span><span class="sxs-lookup"><span data-stu-id="1243b-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="1243b-147">Els fitxers de dades i els fitxers model.json es crearan i s'afegiran a les respectives subcarpetes en funció del procés que executeu.</span><span class="sxs-lookup"><span data-stu-id="1243b-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="1243b-148">Si creeu diversos entorns del Customer Insights i trieu desar les entitats de sortida d'aquests entorns al vostre compte d'emmagatzematge, es crearan carpetes independents per a cada entorn amb ci_<environmentid> al contenidor.</span><span class="sxs-lookup"><span data-stu-id="1243b-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="1243b-149">Consideracions addicionals per a la configuració de la còpia (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="1243b-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="1243b-150">Es copia la configuració següent:</span><span class="sxs-lookup"><span data-stu-id="1243b-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="1243b-151">Configuracions de característiques</span><span class="sxs-lookup"><span data-stu-id="1243b-151">Feature configurations</span></span>
- <span data-ttu-id="1243b-152">Fonts de dades ingerides/importades</span><span class="sxs-lookup"><span data-stu-id="1243b-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="1243b-153">Configuració d'unificació de dades (assignar, coincidir, combinar)</span><span class="sxs-lookup"><span data-stu-id="1243b-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="1243b-154">Segments</span><span class="sxs-lookup"><span data-stu-id="1243b-154">Segments</span></span>
- <span data-ttu-id="1243b-155">Mesures</span><span class="sxs-lookup"><span data-stu-id="1243b-155">Measures</span></span>
- <span data-ttu-id="1243b-156">Relacions</span><span class="sxs-lookup"><span data-stu-id="1243b-156">Relationships</span></span>
- <span data-ttu-id="1243b-157">Activitats</span><span class="sxs-lookup"><span data-stu-id="1243b-157">Activities</span></span>
- <span data-ttu-id="1243b-158">Cerca i filtra l'índex</span><span class="sxs-lookup"><span data-stu-id="1243b-158">Search & filter Index</span></span>
- <span data-ttu-id="1243b-159">Destinacions d'exportació</span><span class="sxs-lookup"><span data-stu-id="1243b-159">Export destinations</span></span>
- <span data-ttu-id="1243b-160">Actualització planificada</span><span class="sxs-lookup"><span data-stu-id="1243b-160">Scheduled refresh</span></span>
- <span data-ttu-id="1243b-161">Enriquiments</span><span class="sxs-lookup"><span data-stu-id="1243b-161">Enrichments</span></span>
- <span data-ttu-id="1243b-162">Administració de models</span><span class="sxs-lookup"><span data-stu-id="1243b-162">Model management</span></span>
- <span data-ttu-id="1243b-163">Assignacions de funcions</span><span class="sxs-lookup"><span data-stu-id="1243b-163">Role assignments</span></span>

<span data-ttu-id="1243b-164">*No* es copia la configuració següent:</span><span class="sxs-lookup"><span data-stu-id="1243b-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="1243b-165">Perfils de client.</span><span class="sxs-lookup"><span data-stu-id="1243b-165">Customer profiles.</span></span>
- <span data-ttu-id="1243b-166">Credencials de la font de dades.</span><span class="sxs-lookup"><span data-stu-id="1243b-166">Data source credentials.</span></span> <span data-ttu-id="1243b-167">Haureu de proporcionar les credencials de cada font de dades i actualitzar manualment les fonts de dades.</span><span class="sxs-lookup"><span data-stu-id="1243b-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="1243b-168">Fonts de dades de la carpeta del Common Data Model i un llac administrat del Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1243b-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="1243b-169">Haureu de crear aquestes fonts de dades manualment amb el mateix nom que a l'entorn d'origen.</span><span class="sxs-lookup"><span data-stu-id="1243b-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="1243b-170">Quan copieu un entorn, veureu un missatge de confirmació que s'ha creat l'entorn nou.</span><span class="sxs-lookup"><span data-stu-id="1243b-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="1243b-171">Seleccioneu **Ves a les fonts de dades** per veure la llista de fonts de dades.</span><span class="sxs-lookup"><span data-stu-id="1243b-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="1243b-172">Totes les fonts de dades mostraran l'estat **Credencials obligatòries**.</span><span class="sxs-lookup"><span data-stu-id="1243b-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="1243b-173">Editeu les fonts de dades i introduïu les credencials per actualitzar-les.</span><span class="sxs-lookup"><span data-stu-id="1243b-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1243b-174">![Fonts de dades copiades](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="1243b-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="1243b-175">Després d'actualitzar les fonts de dades, aneu a **Dades** > **Unifica**.</span><span class="sxs-lookup"><span data-stu-id="1243b-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="1243b-176">Aquí trobareu la configuració de l'entorn d'origen.</span><span class="sxs-lookup"><span data-stu-id="1243b-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="1243b-177">Editeu-les segons calgui o seleccioneu **Executa** per iniciar el procés d'unificació de dades i crear l'entitat de client unificada.</span><span class="sxs-lookup"><span data-stu-id="1243b-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="1243b-178">Quan la unificació de dades hagi finalitzat, aneu a **Mesures** i **Segments** per actualitzar-los també.</span><span class="sxs-lookup"><span data-stu-id="1243b-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="1243b-179">Editar un entorn existent</span><span class="sxs-lookup"><span data-stu-id="1243b-179">Edit an existing environment</span></span>

<span data-ttu-id="1243b-180">Podeu editar alguns dels detalls dels entorns existents.</span><span class="sxs-lookup"><span data-stu-id="1243b-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="1243b-181">Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.</span><span class="sxs-lookup"><span data-stu-id="1243b-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="1243b-182">Seleccioneu la icona **Edita**.</span><span class="sxs-lookup"><span data-stu-id="1243b-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="1243b-183">Al quadre **Edita l'entorn**, podeu actualitzar el **nom de visualització** de l'entorn, però no podeu canviar la **regió** ni el **tipus**.</span><span class="sxs-lookup"><span data-stu-id="1243b-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="1243b-184">Si es configura un entorn per emmagatzemar dades a l'Azure Data Lake Storage Gen2, podeu actualitzar la **Clau del compte**.</span><span class="sxs-lookup"><span data-stu-id="1243b-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="1243b-185">No obstant això, no podeu canviar el **Nom del compte** ni el del **Contenidor**.</span><span class="sxs-lookup"><span data-stu-id="1243b-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="1243b-186">Com a alternativa, podeu canviar d'una connexió basada en claus de comptes a una connexió basada en recursos o en subscripcions.</span><span class="sxs-lookup"><span data-stu-id="1243b-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="1243b-187">Un cop actualitzada, no podreu tornar a la clau de compte després de l'actualització.</span><span class="sxs-lookup"><span data-stu-id="1243b-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="1243b-188">Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="1243b-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="1243b-189">Quan actualitzeu la connexió, no podreu canviar la informació del **Contenidor**.</span><span class="sxs-lookup"><span data-stu-id="1243b-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="1243b-190">Restablir un entorn existent</span><span class="sxs-lookup"><span data-stu-id="1243b-190">Reset an existing environment</span></span>

<span data-ttu-id="1243b-191">Com a administrador, podeu restablir un entorn en estat buit en el cas que vulgueu suprimir totes les configuracions i eliminar la informació ingerida.</span><span class="sxs-lookup"><span data-stu-id="1243b-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="1243b-192">Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.</span><span class="sxs-lookup"><span data-stu-id="1243b-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="1243b-193">Seleccioneu l'entorn que voleu restablir i seleccioneu els punts suspensius **...**.</span><span class="sxs-lookup"><span data-stu-id="1243b-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="1243b-194">Trieu l'opció **Reinicialitza**.</span><span class="sxs-lookup"><span data-stu-id="1243b-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="1243b-195">Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Restableix**.</span><span class="sxs-lookup"><span data-stu-id="1243b-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="1243b-196">Suprimir un entorn existent (només disponible per a administradors)</span><span class="sxs-lookup"><span data-stu-id="1243b-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="1243b-197">Com a administrador, podeu suprimir un entorn que administreu.</span><span class="sxs-lookup"><span data-stu-id="1243b-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="1243b-198">Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.</span><span class="sxs-lookup"><span data-stu-id="1243b-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="1243b-199">Seleccioneu l'entorn que voleu restablir i seleccioneu els punts suspensius **...**.</span><span class="sxs-lookup"><span data-stu-id="1243b-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="1243b-200">Trieu l'opció **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="1243b-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="1243b-201">Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="1243b-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]