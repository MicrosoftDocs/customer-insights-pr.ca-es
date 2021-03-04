---
title: Connectar dades del Common Data Model a un compte de l'Azure Data Lake
description: Treballeu amb dades del Common Data Model mitjançant l'Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267848"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="09ef2-103">Connectar-se a una carpeta del Common Data Model amb un compte de l'Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="09ef2-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="09ef2-104">En aquest article es proporciona informació sobre com ingerir dades d'una carpeta del Common Data Model mitjançant el compte Gen2 de l'Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="09ef2-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="09ef2-105">Consideracions importants</span><span class="sxs-lookup"><span data-stu-id="09ef2-105">Important considerations</span></span>

- <span data-ttu-id="09ef2-106">Les dades de l'Azure Data Lake han de seguir l'estàndard Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="09ef2-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="09ef2-107">La resta de formats no s'admeten en aquest moment.</span><span class="sxs-lookup"><span data-stu-id="09ef2-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="09ef2-108">La ingestió de dades només és compatible amb els comptes d'emmagatzematge *Gen2* de l'Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="09ef2-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="09ef2-109">No és possible utilitzar comptes d'emmagatzematge Gen1 de l'Azure Data Lake per ingerir dades.</span><span class="sxs-lookup"><span data-stu-id="09ef2-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="09ef2-110">Per autenticar-vos amb una entitat de servei de l'Azure, assegureu-vos que aquesta s'hagi configurat al vostre inquilí.</span><span class="sxs-lookup"><span data-stu-id="09ef2-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="09ef2-111">Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="09ef2-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="09ef2-112">L'Azure Data Lake amb el que us voleu connectar i del que voleu ingerir dades s'ha de trobar a la mateixa regió de l'Azure que l'entorn de Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="09ef2-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="09ef2-113">No s'admet la connexió a una carpeta del Common Data Model procedent d'un llac de dades d'una regió diferent de l'Azure.</span><span class="sxs-lookup"><span data-stu-id="09ef2-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="09ef2-114">Per conèixer la regió de l'Azure de l'entorn, aneu a **Administració** > **Sistema** > **Quant a** a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="09ef2-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="09ef2-115">Les dades emmagatzemades als serveis en línia es poden emmagatzemar en una ubicació diferent de la ubicació on es processen o s'emmagatzemen al Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="09ef2-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="09ef2-116"> En importar o connectar-vos a les dades emmagatzemades en un servei en línia, accepteu que les dades es poden transferir i emmagatzemar-se amb el Dynamics 365 Customer Insights.  [Més informació al Centre de confiança de Microsoft](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="09ef2-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="09ef2-117">Connecta't a una carpeta del Common Data Model</span><span class="sxs-lookup"><span data-stu-id="09ef2-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="09ef2-118">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="09ef2-119">Seleccioneu **Afegeix una font de dades**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="09ef2-120">Seleccioneu **Connecta't a una carpeta del Common Data Model**, introduïu un **Nom** per a la font de dades i, a continuació, seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="09ef2-121">Directrius del nom:</span><span class="sxs-lookup"><span data-stu-id="09ef2-121">Name guidelines:</span></span> 
   - <span data-ttu-id="09ef2-122">Comenceu per una lletra.</span><span class="sxs-lookup"><span data-stu-id="09ef2-122">Start with a letter.</span></span>
   - <span data-ttu-id="09ef2-123">Utilitzeu només lletres i xifres.</span><span class="sxs-lookup"><span data-stu-id="09ef2-123">Use letters and numbers only.</span></span> <span data-ttu-id="09ef2-124">Els caràcters especials i els espais no estan permesos.</span><span class="sxs-lookup"><span data-stu-id="09ef2-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="09ef2-125">Utilitzeu entre 3 i 64 caràcters.</span><span class="sxs-lookup"><span data-stu-id="09ef2-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="09ef2-126">Per a l'autenticació, podeu triar entre utilitzar una opció basada en recursos i una basada en subscripcions.</span><span class="sxs-lookup"><span data-stu-id="09ef2-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="09ef2-127">Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="09ef2-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="09ef2-128">Introduïu la informació del **Contenidor** i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="09ef2-129">![Quadre de diàleg per introduir nous detalls de connexió a l'Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="09ef2-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="09ef2-130">Necessiteu una de les funcions següents al contenidor o al compte d'emmagatzematge abans descrit per poder connectar-vos i crear una font de dades:</span><span class="sxs-lookup"><span data-stu-id="09ef2-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="09ef2-131">Lector de dades de Blob de l'emmagatzematge</span><span class="sxs-lookup"><span data-stu-id="09ef2-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="09ef2-132">Propietari de dades de Blob de l'emmagatzematge</span><span class="sxs-lookup"><span data-stu-id="09ef2-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="09ef2-133">Col·laborador de dades de Blob d'emmagatzematge</span><span class="sxs-lookup"><span data-stu-id="09ef2-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="09ef2-134">Al diàleg **Seleccioneu una carpeta del Common Data Model**, seleccioneu el fitxer model.json o manifest.json del que voleu importar les dades i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="09ef2-135">Els fitxers model.json o manifest.json associats amb una altra font de dades de l'entorn no es mostraran a la llista.</span><span class="sxs-lookup"><span data-stu-id="09ef2-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="09ef2-136">Obtindreu una llista d'entitats disponibles al fitxer model.json o manifest.json seleccionat.</span><span class="sxs-lookup"><span data-stu-id="09ef2-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="09ef2-137">Podeu revisar i seleccionar a la llista d'entitats disponibles i seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="09ef2-138">Totes les entitats seleccionades s'ingeriran des de la nova font de dades.</span><span class="sxs-lookup"><span data-stu-id="09ef2-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="09ef2-139">![Quadre de diàleg que mostra una llista d'entitats des d'un fitxer model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="09ef2-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="09ef2-140">Indiqueu per a quines entitats de dades voleu habilitar la perfilació de dades i seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="09ef2-141">La generació de perfils de dades habilita les anàlisis i altres capacitats.</span><span class="sxs-lookup"><span data-stu-id="09ef2-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="09ef2-142">Podeu seleccionar tota l'entitat, amb la qual cosa se seleccionen tots els atributs de l'entitat, o bé seleccionar determinats atributs de la vostra elecció.</span><span class="sxs-lookup"><span data-stu-id="09ef2-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="09ef2-143">Per defecte, no s'habilita cap entitat per a la perfilació de dades.</span><span class="sxs-lookup"><span data-stu-id="09ef2-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="09ef2-144">![Quadre de diàleg on es mostra una perfilació de dades](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="09ef2-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="09ef2-145">Després de desar les seleccions, s'obre la pàgina **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="09ef2-146">Ara hauríeu de veure la connexió de la carpeta del Common Data Model com a font de dades.</span><span class="sxs-lookup"><span data-stu-id="09ef2-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="09ef2-147">Un fitxer model.json o manifest.json només pot associar-se amb una font de dades del mateix entorn.</span><span class="sxs-lookup"><span data-stu-id="09ef2-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="09ef2-148">No obstant, un mateix fitxer model.json o manifest.json es pot utilitzar per a fonts de dades de diversos entorns.</span><span class="sxs-lookup"><span data-stu-id="09ef2-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="09ef2-149">Editar la font de dades d'una carpeta del Common Data Model</span><span class="sxs-lookup"><span data-stu-id="09ef2-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="09ef2-150">És possible actualitzar la clau d'accés al compte d'emmagatzematge que conté la carpeta del Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="09ef2-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="09ef2-151">També podeu canviar el fitxer model.json o manifest.json.</span><span class="sxs-lookup"><span data-stu-id="09ef2-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="09ef2-152">Per connectar-vos a un contenidor diferent del vostre compte d'emmagatzematge o canviar el nom de compte, [creeu una connexió de font de dades nova](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="09ef2-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="09ef2-153">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="09ef2-154">Al costat de la font de dades que voleu actualitzar, seleccioneu els punts suspensius.</span><span class="sxs-lookup"><span data-stu-id="09ef2-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="09ef2-155">Seleccioneu l'opció **Edita** de la llista.</span><span class="sxs-lookup"><span data-stu-id="09ef2-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="09ef2-156">Opcionalment, actualitzeu la **Clau d'accés** i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Diàleg per editar i actualitzar una clau d'accés per a una font de dades existent](media/edit-access-key.png)

5. <span data-ttu-id="09ef2-158">Com a alternativa, podeu actualitzar-la des d'una connexió de clau de compte a una connexió basada en recursos o en subscripcions.</span><span class="sxs-lookup"><span data-stu-id="09ef2-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="09ef2-159">Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="09ef2-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="09ef2-160">Quan actualitzeu la connexió, no podreu canviar la informació del **Contenidor**.</span><span class="sxs-lookup"><span data-stu-id="09ef2-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Quadre de diàleg per introduir els detalls de connexió a l'Azure Data Lake a un compte d'emmagatzematge existent](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="09ef2-162">Necessiteu una de les funcions següents al contenidor o al compte d'emmagatzematge abans descrit per poder connectar-vos i crear una font de dades:</span><span class="sxs-lookup"><span data-stu-id="09ef2-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="09ef2-163">Lector de dades de Blob de l'emmagatzematge</span><span class="sxs-lookup"><span data-stu-id="09ef2-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="09ef2-164">Propietari de dades de Blob de l'emmagatzematge</span><span class="sxs-lookup"><span data-stu-id="09ef2-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="09ef2-165">Col·laborador de dades de Blob d'emmagatzematge</span><span class="sxs-lookup"><span data-stu-id="09ef2-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="09ef2-166">Opcionalment, trieu un fitxer model.json o manifest.json diferent amb un conjunt d'entitats diferent del contenidor.</span><span class="sxs-lookup"><span data-stu-id="09ef2-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="09ef2-167">També podeu seleccionar més entitats per ingerir.</span><span class="sxs-lookup"><span data-stu-id="09ef2-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="09ef2-168">També podeu suprimir les entitats que ja estan seleccionades si no hi ha cap dependència.</span><span class="sxs-lookup"><span data-stu-id="09ef2-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="09ef2-169">Si hi ha dependències en el fitxer model.json o manifest.json i el conjunt d'entitats, veureu un missatge d'error i no podreu seleccionar un fitxer model.json o manifest.json diferent.</span><span class="sxs-lookup"><span data-stu-id="09ef2-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="09ef2-170">Suprimiu aquestes dependències abans de canviar el fitxer model.json o manifest.json o creeu una font de dades nou amb el fitxer model.json o manifest.json que voleu utilitzar per evitar la supressió de les dependències.</span><span class="sxs-lookup"><span data-stu-id="09ef2-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="09ef2-171">També podeu seleccionar més atributs o entitats per habilitar-hi la perfilació de dades o inhabilitar els que ja hagueu seleccionat.</span><span class="sxs-lookup"><span data-stu-id="09ef2-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]