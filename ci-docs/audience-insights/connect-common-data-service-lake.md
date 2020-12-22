---
title: Connectar amb entitats del llac administrat del Common Data Service
description: Importeu dades d'un llac de dades administrat del Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643386"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="f4705-103">Connectar-se a dades d'un llac de dades administrat del Common Data Service</span><span class="sxs-lookup"><span data-stu-id="f4705-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f4705-104">Aquest article proporciona informació sobre com els clients del Dynamics 365 existents es poden connectar ràpidament a les seves entitats analítiques en el llac administrat del Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f4705-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="f4705-105">Heu de ser administrador de l'organització del Common Data Service per continuar i veure la llista d'entitats disponibles al llac administrat.</span><span class="sxs-lookup"><span data-stu-id="f4705-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="f4705-106">Consideracions importants</span><span class="sxs-lookup"><span data-stu-id="f4705-106">Important considerations</span></span>

<span data-ttu-id="f4705-107">Les dades emmagatzemades en un servei en línia, com ara el Azure Data Lake Storage, es poden emmagatzemar en una ubicació diferent d'on es processen o s'emmagatzemen les dades al Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f4705-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="f4705-108"> En importar o connectar-vos a les dades emmagatzemades en un servei en línia, accepteu que les dades es poden transferir i emmagatzemar-se amb el Dynamics 365 Customer Insights.  [Més informació al Centre de confiança de Microsoft](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="f4705-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="f4705-109">Connectar-se a un llac administrat del Common Data Service</span><span class="sxs-lookup"><span data-stu-id="f4705-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="f4705-110">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="f4705-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f4705-111">Seleccioneu **Afegeix una font de dades**.</span><span class="sxs-lookup"><span data-stu-id="f4705-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="f4705-112">Seleccioneu **Connecta't al Common Data Service** i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="f4705-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="f4705-113">Introduïu un **Nom** per a la font de dades i seleccioneu **Següent**.</span><span class="sxs-lookup"><span data-stu-id="f4705-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="f4705-114">Proporcioneu l'**adreça del servidor** de l'organització del Common Data Service i, a continuació, seleccioneu **inicia la sessió**.</span><span class="sxs-lookup"><span data-stu-id="f4705-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4705-115">![Quadre de diàleg per introduir l'adreça del servidor del Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="f4705-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="f4705-116">Seleccioneu les entitats que voleu ingerir a la llista disponible.</span><span class="sxs-lookup"><span data-stu-id="f4705-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="f4705-117">Si algunes entitats ja estan seleccionades, pot ser que s'utilitzin en altres aplicacions del Dynamics 365 (com ara el Dynamics 365 Sales Insights o el Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="f4705-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="f4705-118">Aquesta selecció no es pot canviar.</span><span class="sxs-lookup"><span data-stu-id="f4705-118">You can't change the selection.</span></span> <span data-ttu-id="f4705-119">Aquestes entitats estaran disponibles quan es creï la font de dades.</span><span class="sxs-lookup"><span data-stu-id="f4705-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4705-120">![Quadre de diàleg que mostra una llista d'entitats de l'organització del Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="f4705-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="f4705-121">Deseu la selecció per iniciar la sincronització de les entitats seleccionades al llac gestionat del Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f4705-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="f4705-122">Trobareu la connexió afegida recentment a la pàgina **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="f4705-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="f4705-123">Es posarà en cua per actualitzar-se i mostrarà el recompte d'entitats com a 0 fins que totes les entitats se sincronitzin.</span><span class="sxs-lookup"><span data-stu-id="f4705-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="f4705-124">Només una font de dades d'un entorn podrà utilitzar simultàniament el mateix llac administrat del Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f4705-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="f4705-125">Editar una font de dades d'un llac gestionat del Common Data Service</span><span class="sxs-lookup"><span data-stu-id="f4705-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="f4705-126">Només editeu la selecció d'entitats després de crear la font de dades.</span><span class="sxs-lookup"><span data-stu-id="f4705-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="f4705-127">Per exemple, si s'han afegit entitats addicionals al Common Data Service i també voleu importar-les.</span><span class="sxs-lookup"><span data-stu-id="f4705-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="f4705-128">Per connectar-vos a un Common Data Service diferent, [creeu una nova font de dades](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="f4705-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="f4705-129">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="f4705-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f4705-130">Al costat de la font de dades que voleu actualitzar, seleccioneu els punts suspensius.</span><span class="sxs-lookup"><span data-stu-id="f4705-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="f4705-131">Seleccioneu l'opció **Edita** de la llista.</span><span class="sxs-lookup"><span data-stu-id="f4705-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="f4705-132">Seleccioneu les entitats addicionals a la llista disponible d'entitats i seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="f4705-132">Select additional entities from the available list of entities and select **Save**.</span></span>
