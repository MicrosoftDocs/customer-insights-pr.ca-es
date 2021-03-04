---
title: Connectar-se a un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei
description: Utilitzeu una entitat de servei de l'Azure per a les conclusions del públic per connectar-vos al vostre llac de dades propi quan l'adjunteu a les conclusions del públic.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267710"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="cdaf7-103">Connectar-se a un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure per a les conclusions del públic</span><span class="sxs-lookup"><span data-stu-id="cdaf7-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="cdaf7-104">Les eines automatitzades que utilitzen serveis de l'Azure sempre hauran de tenir permisos restringits.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="cdaf7-105">En comptes d'iniciar la sessió a les aplicacions com a usuari amb tots els privilegis, l'Azure ofereix entitats de servei.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="cdaf7-106">Seguiu llegint per obtenir més informació sobre com connectar les conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage mitjançant una entitat de servei de l'Azure en comptes de les claus de compte d'emmagatzematge.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="cdaf7-107">Podeu utilitzar l'entitat de servei per [afegir o editar de manera segura una carpeta de Common Data Model com a font de dades](connect-common-data-model.md) o [crear un entorn nou o actualitzar-ne un d'existent](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="cdaf7-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="cdaf7-108">El compte d'emmagatzematge de l'Azure Data Lake Storage Gen2 que té com a objectiu utilitzar l'entitat de servei ha de tenir habilitat l'[Espai jeràrquic de noms (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="cdaf7-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="cdaf7-109">Per poder crear l'entitat de servei, heu de tenir permisos d'administrador per a la vostra subscripció a l'Azure.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="cdaf7-110">Crear l'entitat de servei de l'Azure per a les conclusions del públic</span><span class="sxs-lookup"><span data-stu-id="cdaf7-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="cdaf7-111">Abans de crear una nova entitat de servei per a les conclusions del públic, comproveu si aquesta ja existeix a l'organització.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="cdaf7-112">Cercar una entitat de servei existent</span><span class="sxs-lookup"><span data-stu-id="cdaf7-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="cdaf7-113">Aneu al [portal d'administració de l'Azure](https://portal.azure.com) i inicieu-hi la sessió a la vostra organització.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="cdaf7-114">Seleccioneu **Azure Active Directory** als serveis de l'Azure.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="cdaf7-115">A **Administra**, seleccioneu **Aplicacions empresarials**.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="cdaf7-116">Cerqueu l'identificador de l'aplicació principal de les conclusions del públic `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` o el nom `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="cdaf7-117">Si trobeu un registre coincident, vol dir que l'entitat de servei per a les conclusions del públic existeix.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="cdaf7-118">No cal que la torneu a crear.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla con es mostra l'entitat de servei existent.":::
   
6. <span data-ttu-id="cdaf7-120">Si no es retorna cap resultat, creeu una nova entitat de servei.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="cdaf7-121">Crear una nova entitat de servei</span><span class="sxs-lookup"><span data-stu-id="cdaf7-121">Create a new service principal</span></span>

1. <span data-ttu-id="cdaf7-122">Instal·leu la versió més recent del **PowerShell de l'Azure Active Directory per al Graph**.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="cdaf7-123">Per obtenir més informació, vegeu [Instal·lar el PowerShell de l'Azure Active Directory per al Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="cdaf7-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="cdaf7-124">Al PC, seleccioneu la tecla de Windows al teclat, cerqueu **Windows PowerShell** i seleccioneu **Executa com un administrador**.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="cdaf7-125">A la finestra del PowerShell que s'obre, introduïu `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="cdaf7-126">Creeu l'entitat de servei per a les conclusions del públic amb el mòdul del PowerShell de l'Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="cdaf7-127">A la finestra del PowerShell introduïu `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="cdaf7-128">Substituïu "l'identificador d'inquilí" per l'identificador real del vostre inquilí on voleu crear l'entitat de servei.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="cdaf7-129">El paràmetre del nom de l'entorn `AzureEnvironmentName` és opcional.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="cdaf7-130">Introduïu `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="cdaf7-131">Amb aquesta ordre es crea l'entitat de servei per a les conclusions del públic a l'inquilí seleccionat.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="cdaf7-132">Concedir permisos a l'entitat de servei per accedir al compte d'emmagatzematge</span><span class="sxs-lookup"><span data-stu-id="cdaf7-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="cdaf7-133">Aneu al portal de l'Azure per concedir permisos a l'entitat de servei del compte d'emmagatzematge que voleu utilitzar a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="cdaf7-134">Aneu al [portal d'administració de l'Azure](https://portal.azure.com) i inicieu-hi la sessió a la vostra organització.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="cdaf7-135">Obriu el compte d'emmagatzematge al qual voleu que tingui accés l'entitat de servei per a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="cdaf7-136">Seleccioneu **Control d'accés (IAM)** a la subfinestra de navegació i seleccioneu **Afegeix** > **Afegeix l'assignació de funcions**.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla on es mostra el portal de l'Azure mentre s'afegeix una assignació de funcions.":::
   
1. <span data-ttu-id="cdaf7-138">A la subfinestra **Afegeix l'assignació de funcions**, definiu les propietats següents:</span><span class="sxs-lookup"><span data-stu-id="cdaf7-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="cdaf7-139">Funció: *Col·laborador de dades de Blob d'emmagatzematge*</span><span class="sxs-lookup"><span data-stu-id="cdaf7-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="cdaf7-140">Assignació d'accés a: *Usuari, grup o entitat de servei*</span><span class="sxs-lookup"><span data-stu-id="cdaf7-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="cdaf7-141">Seleccionar: *Dynamics 365 AI per a Customer Insights* (l'[entitat de servei que heu creat](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="cdaf7-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="cdaf7-142">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-142">Select **Save**.</span></span>

<span data-ttu-id="cdaf7-143">La propagació dels canvis pot trigar fins a 15 minuts.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="cdaf7-144">Introduïu l'identificador de recurs de l'Azure o els detalls de subscripció de l'Azure al fitxer adjunt del compte d'emmagatzematge de les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="cdaf7-145">Adjunteu un compte d'emmagatzematge de l'Azure Data Lake a les conclusions del públic per [emmagatzemar dades de sortida](manage-environments.md) o [utilitzar-les com a font de dades](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="cdaf7-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="cdaf7-146">Si trieu l'opció de l'Azure Data Lake, podreu triar entre un mètode basat en recursos o un basat en subscripcions.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="cdaf7-147">Seguiu els passos que es descriuen a continuació per proporcionar la informació necessària sobre el mètode seleccionat.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="cdaf7-148">Connexió al compte d'emmagatzematge basat en recursos</span><span class="sxs-lookup"><span data-stu-id="cdaf7-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="cdaf7-149">Aneu al [portal d'administració de l'Azure](https://portal.azure.com), inicieu-hi la sessió a la vostra subscripció i obriu el compte d'emmagatzematge.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="cdaf7-150">Aneu a **Configuració** > **Propietats** a la subfinestra de navegació.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="cdaf7-151">Copieu el valor de l'identificador de recurs del compte d'emmagatzematge.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copieu l'identificador de recurs del compte d'emmagatzematge.":::

1. <span data-ttu-id="cdaf7-153">A les conclusions del públic, inseriu l'identificador de recurs al camp de recurs que es mostra a la pantalla de connexió del compte d'emmagatzematge.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduïu la informació de l'identificador de recurs del compte d'emmagatzematge.":::   
   
1. <span data-ttu-id="cdaf7-155">Continueu amb els passos restants a les conclusions del públic per adjuntar el compte d'emmagatzematge.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="cdaf7-156">Connexió al compte d'emmagatzematge basat en subscripcions</span><span class="sxs-lookup"><span data-stu-id="cdaf7-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="cdaf7-157">Aneu al [portal d'administració de l'Azure](https://portal.azure.com), inicieu-hi la sessió a la vostra subscripció i obriu el compte d'emmagatzematge.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="cdaf7-158">Aneu a **Configuració** > **Propietats** a la subfinestra de navegació.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="cdaf7-159">Reviseu la **Subscripció**, el **Grup de recursos** i el **Nom** del compte d'emmagatzematge per assegurar-vos de seleccionar els valors adequats a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="cdaf7-160">A les conclusions del públic, trieu els valors o els camps corresponents quan adjunteu el compte d'emmagatzematge.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="cdaf7-161">Continueu amb els passos restants a les conclusions del públic per adjuntar el compte d'emmagatzematge.</span><span class="sxs-lookup"><span data-stu-id="cdaf7-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]