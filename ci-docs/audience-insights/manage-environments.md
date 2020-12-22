---
title: Crear i administrar entorns
description: Apreneu a registrar-vos al servei i a administrar entorns.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644121"
---
# <a name="manage-environments"></a><span data-ttu-id="3ca31-103">Gestionar entorns</span><span class="sxs-lookup"><span data-stu-id="3ca31-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3ca31-104">En aquest article s'explica com crear una organització nova i com proveir un entorn.</span><span class="sxs-lookup"><span data-stu-id="3ca31-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="3ca31-105">Registrar-se i crear una organització</span><span class="sxs-lookup"><span data-stu-id="3ca31-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="3ca31-106">Aneu al lloc web del [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="3ca31-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="3ca31-107">Seleccioneu **Introducció**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="3ca31-108">Trieu l'escenari preferit de registre i seleccioneu l'enllaç corresponent.</span><span class="sxs-lookup"><span data-stu-id="3ca31-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="3ca31-109">Accepteu els termes i condicions i seleccioneu **Continua** per començar a crear l'organització.</span><span class="sxs-lookup"><span data-stu-id="3ca31-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="3ca31-110">Després de crear l'entorn, se us redirigirà al [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="3ca31-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="3ca31-111">Utilitzeu l'entorn de demostració per explorar l'aplicació o creeu un entorn nou amb els passos de la secció següent.</span><span class="sxs-lookup"><span data-stu-id="3ca31-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="3ca31-112">Després d'especificar la configuració de l'entorn, seleccioneu **Crea**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="3ca31-113">Un cop creat correctament l'entorn, s'iniciarà la vostra sessió.</span><span class="sxs-lookup"><span data-stu-id="3ca31-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="3ca31-114">Crear un entorn en una organització existent</span><span class="sxs-lookup"><span data-stu-id="3ca31-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="3ca31-115">Hi ha dues maneres de crear un nou entorn.</span><span class="sxs-lookup"><span data-stu-id="3ca31-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="3ca31-116">Podeu especificar una configuració completament nova o bé podeu copiar alguns ajustaments de configuració des d'un entorn existent.</span><span class="sxs-lookup"><span data-stu-id="3ca31-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="3ca31-117">Per crear un entorn:</span><span class="sxs-lookup"><span data-stu-id="3ca31-117">To create an environment:</span></span>

1. <span data-ttu-id="3ca31-118">Seleccioneu el símbol **Configuració** a la capçalera de l'aplicació.</span><span class="sxs-lookup"><span data-stu-id="3ca31-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="3ca31-119">Seleccioneu **Nou entorn**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3ca31-120">![Configuració de l'entorn](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="3ca31-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="3ca31-121">En el diàleg **Crea un nou entorn**, seleccioneu **Nou entorn**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="3ca31-122">Si voleu [copiar les dades de l'entorn actual](#additional-considerations-for-copy-configuration-preview), seleccioneu **Copia d'un entorn existent**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="3ca31-123">Veureu una llista de tots els entorns disponibles a l'organització des d'on podeu copiar dades.</span><span class="sxs-lookup"><span data-stu-id="3ca31-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="3ca31-124">Proporcioneu els següents detalls:</span><span class="sxs-lookup"><span data-stu-id="3ca31-124">Provide the following details:</span></span>
   - <span data-ttu-id="3ca31-125">**Nom**: el nom de l'entorn en qüestió.</span><span class="sxs-lookup"><span data-stu-id="3ca31-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="3ca31-126">Aquest camp ja s'emplena si heu copiat des d'un entorn existent, però es pot canviar.</span><span class="sxs-lookup"><span data-stu-id="3ca31-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="3ca31-127">**Regió**: la regió en la qual s'implementa i s'allotja el servei.</span><span class="sxs-lookup"><span data-stu-id="3ca31-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="3ca31-128">**Tipus**: seleccioneu si voleu crear un entorn de producció o espai aïllat.</span><span class="sxs-lookup"><span data-stu-id="3ca31-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="3ca31-129">De manera opcional, podeu seleccionar **Configuració avançada**:</span><span class="sxs-lookup"><span data-stu-id="3ca31-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="3ca31-130">**Desa totes les dades a**: especifica on voleu emmagatzemar les dades de sortida generades amb el Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3ca31-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="3ca31-131">Tindreu dues opcions: **Emmagatzematge del Customer Insights** (un Azure Data Lake gestionat per l'equip del Customer Insights) i **Azure Data Lake Storage Gen2** (el vostre propi Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="3ca31-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="3ca31-132">Per defecte, se selecciona l'opció d'emmagatzematge al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3ca31-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3ca31-133">En desar les dades a l'Azure Data Lake Storage, accepteu que les dades es transferiran i s'emmagatzemaran a la ubicació geogràfica adequada per al compte d'emmagatzematge de l'Azure, que pot diferir amb la ubicació on s'emmagatzemen les dades al Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3ca31-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="3ca31-134">Més informació al Centre de confiança de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ca31-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="3ca31-135">Actualment, les entitats ingerides sempre s'emmagatzemen al llac de dades gestionat pel Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3ca31-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="3ca31-136">Només s'admeten comptes d'emmagatzematge Gen2 de l'Azure Data Lake de la mateixa regió de l'Azure que la que vau seleccionar en crear l'entorn.</span><span class="sxs-lookup"><span data-stu-id="3ca31-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="3ca31-137">Només admetem comptes d'emmagatzematge de l'Azure Data Lake gen2 habilitats per a l'espai de noms jeràrquic (HNS).</span><span class="sxs-lookup"><span data-stu-id="3ca31-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="3ca31-138">En el caso de l'opció Gen2 de l'Azure Data Lake Storage, podeu triar entre utilitzar una opció basada en recursos i una basada en subscripcions per a l'autenticació.</span><span class="sxs-lookup"><span data-stu-id="3ca31-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="3ca31-139">Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="3ca31-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="3ca31-140">El nom del **Contenidor** no es pot canviar i serà "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="3ca31-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="3ca31-141">Si voleu utilitzar [prediccions](predictions.md), introduïu l'adreça URL de la instància del Common Data Service al camp **Adreça del servidor** a **Utilitza les prediccions**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="3ca31-142">Quan executeu processos, com ara la ingestió de dades o la creació de segments, les carpetes corresponents es crearan al compte d'emmagatzematge que hagueu especificat anteriorment.</span><span class="sxs-lookup"><span data-stu-id="3ca31-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="3ca31-143">Els fitxers de dades i els fitxers model.json es crearan i s'afegiran a les respectives subcarpetes en funció del procés que executeu.</span><span class="sxs-lookup"><span data-stu-id="3ca31-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="3ca31-144">Si creeu diversos entorns del Customer Insights i trieu desar les entitats de sortida d'aquests entorns al vostre compte d'emmagatzematge, es crearan carpetes independents per a cada entorn amb ci_<environmentid> al contenidor.</span><span class="sxs-lookup"><span data-stu-id="3ca31-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="3ca31-145">Consideracions addicionals per a la configuració de la còpia (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="3ca31-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="3ca31-146">Es copia la configuració següent:</span><span class="sxs-lookup"><span data-stu-id="3ca31-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="3ca31-147">Configuracions de característiques</span><span class="sxs-lookup"><span data-stu-id="3ca31-147">Feature configurations</span></span>
- <span data-ttu-id="3ca31-148">Fonts de dades importades o ingerides</span><span class="sxs-lookup"><span data-stu-id="3ca31-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="3ca31-149">Configuració d'unificació de dades (assignar, coincidir, combinar)</span><span class="sxs-lookup"><span data-stu-id="3ca31-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="3ca31-150">Segments</span><span class="sxs-lookup"><span data-stu-id="3ca31-150">Segments</span></span>
- <span data-ttu-id="3ca31-151">Mesures</span><span class="sxs-lookup"><span data-stu-id="3ca31-151">Measures</span></span>
- <span data-ttu-id="3ca31-152">Relacions</span><span class="sxs-lookup"><span data-stu-id="3ca31-152">Relationships</span></span>
- <span data-ttu-id="3ca31-153">Activitats</span><span class="sxs-lookup"><span data-stu-id="3ca31-153">Activities</span></span>
- <span data-ttu-id="3ca31-154">Cerca i filtra l'índex</span><span class="sxs-lookup"><span data-stu-id="3ca31-154">Search & filter Index</span></span>
- <span data-ttu-id="3ca31-155">Destinacions d'exportació</span><span class="sxs-lookup"><span data-stu-id="3ca31-155">Export destinations</span></span>
- <span data-ttu-id="3ca31-156">Actualització planificada</span><span class="sxs-lookup"><span data-stu-id="3ca31-156">Scheduled refresh</span></span>
- <span data-ttu-id="3ca31-157">Enriquiments</span><span class="sxs-lookup"><span data-stu-id="3ca31-157">Enrichments</span></span>
- <span data-ttu-id="3ca31-158">Administració de models</span><span class="sxs-lookup"><span data-stu-id="3ca31-158">Model management</span></span>
- <span data-ttu-id="3ca31-159">Assignacions de funcions</span><span class="sxs-lookup"><span data-stu-id="3ca31-159">Role assignments</span></span>

<span data-ttu-id="3ca31-160">*No* es copia la configuració següent:</span><span class="sxs-lookup"><span data-stu-id="3ca31-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="3ca31-161">Perfils de client.</span><span class="sxs-lookup"><span data-stu-id="3ca31-161">Customer profiles.</span></span>
- <span data-ttu-id="3ca31-162">Credencials de la font de dades.</span><span class="sxs-lookup"><span data-stu-id="3ca31-162">Data source credentials.</span></span> <span data-ttu-id="3ca31-163">Haureu de proporcionar les credencials de cada font de dades i actualitzar manualment les fonts de dades.</span><span class="sxs-lookup"><span data-stu-id="3ca31-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="3ca31-164">Fonts de dades de la carpeta del Common Data Model i un llac administrat del Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3ca31-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="3ca31-165">Haureu de crear aquestes fonts de dades manualment amb el mateix nom que a l'entorn d'origen.</span><span class="sxs-lookup"><span data-stu-id="3ca31-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="3ca31-166">Quan copieu un entorn, veureu un missatge de confirmació que s'ha creat l'entorn nou.</span><span class="sxs-lookup"><span data-stu-id="3ca31-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="3ca31-167">Seleccioneu **Ves a les fonts de dades** per veure la llista de fonts de dades.</span><span class="sxs-lookup"><span data-stu-id="3ca31-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="3ca31-168">Totes les fonts de dades mostraran l'estat **Credencials obligatòries**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="3ca31-169">Editeu les fonts de dades i introduïu les credencials per actualitzar-les.</span><span class="sxs-lookup"><span data-stu-id="3ca31-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3ca31-170">![Fonts de dades copiades](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="3ca31-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="3ca31-171">Després d'actualitzar les fonts de dades, aneu a **Dades** > **Unifica**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="3ca31-172">Aquí trobareu la configuració de l'entorn d'origen.</span><span class="sxs-lookup"><span data-stu-id="3ca31-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="3ca31-173">Editeu-les segons calgui o seleccioneu **Executa** per iniciar el procés d'unificació de dades i crear l'entitat de client unificada.</span><span class="sxs-lookup"><span data-stu-id="3ca31-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="3ca31-174">Quan la unificació de dades hagi finalitzat, aneu a **Mesures** i **Segments** per actualitzar-los també.</span><span class="sxs-lookup"><span data-stu-id="3ca31-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="3ca31-175">Editar un entorn existent</span><span class="sxs-lookup"><span data-stu-id="3ca31-175">Edit an existing environment</span></span>

<span data-ttu-id="3ca31-176">Podeu editar alguns dels detalls dels entorns existents.</span><span class="sxs-lookup"><span data-stu-id="3ca31-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="3ca31-177">Aneu a **Administració** > **Sistema** > **Quant a**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="3ca31-178">Seleccioneu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-178">Select **Edit**.</span></span>

3. <span data-ttu-id="3ca31-179">Podeu actualitzar el **Nom de visualització** de l'entorn, però no podeu canviar la **Regió** ni el **Tipus**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="3ca31-180">Si es configura un entorn per emmagatzemar dades a l'Azure Data Lake Storage Gen2, podeu actualitzar la **Clau del compte**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="3ca31-181">No obstant això, no podeu canviar el **Nom del compte** ni el del **Contenidor**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="3ca31-182">Com a alternativa, podeu canviar d'una connexió basada en claus de comptes a una connexió basada en recursos o en subscripcions.</span><span class="sxs-lookup"><span data-stu-id="3ca31-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="3ca31-183">Un cop actualitzada, no podreu tornar a la clau de compte després de l'actualització.</span><span class="sxs-lookup"><span data-stu-id="3ca31-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="3ca31-184">Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="3ca31-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="3ca31-185">Quan actualitzeu la connexió, no podreu canviar la informació del **Contenidor**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="3ca31-186">Restablir un entorn existent</span><span class="sxs-lookup"><span data-stu-id="3ca31-186">Reset an existing environment</span></span>

<span data-ttu-id="3ca31-187">Podeu restablir un entorn en estat buit en el cas que vulgueu suprimir totes les configuracions i eliminar la informació ingerida.</span><span class="sxs-lookup"><span data-stu-id="3ca31-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="3ca31-188">Aneu a **Administració** > **Sistema** > **Quant a**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="3ca31-189">Seleccioneu **Restableix**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="3ca31-190">Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Restableix**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="3ca31-191">Suprimir un entorn existent</span><span class="sxs-lookup"><span data-stu-id="3ca31-191">Delete an existing environment</span></span>

1. <span data-ttu-id="3ca31-192">Aneu a **Administració** > **Sistema** > **Quant a**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="3ca31-193">Seleccioneu **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-193">Select **Delete**.</span></span>

1. <span data-ttu-id="3ca31-194">Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="3ca31-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
