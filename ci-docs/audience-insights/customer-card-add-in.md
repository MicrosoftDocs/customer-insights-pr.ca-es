---
title: Instal·lar i configurar el Complement de targeta del client
description: Instal·leu i configureu el complement de targeta del client per al Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644031"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="127dd-103">Complement de targeta del client (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="127dd-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="127dd-104">Obtingueu una visió integral dels clients directament a les aplicacions del Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="127dd-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="127dd-105">Visualitzeu dades demogràfiques, estadístiques i cronologies d'activitats amb el complement de targeta del client.</span><span class="sxs-lookup"><span data-stu-id="127dd-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="127dd-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="127dd-106">Prerequisites</span></span>

- <span data-ttu-id="127dd-107">Aplicació Dynamics 365 (com ara el Centre de vendes o el Centre del Customer Service), versió 9.0 o posterior amb la Interfície unificada habilitada.</span><span class="sxs-lookup"><span data-stu-id="127dd-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="127dd-108">Perfils de client [ingerits des de l'aplicació Dynamics 365 mitjançant el Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="127dd-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="127dd-109">Els usuaris del Complement de targeta del client s'han d'[afegir com a usuaris](permissions.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="127dd-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="127dd-110">[Capacitats de cerca i filtratge configurades](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="127dd-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="127dd-111">Control demogràfic: Els camps demogràfics, com l'edat o el sexe, estan disponibles al perfil unificat del client.</span><span class="sxs-lookup"><span data-stu-id="127dd-111">Demographic control: Demographic fields, such as age or gender are available in the unified customer profile.</span></span>
- <span data-ttu-id="127dd-112">Control Enriquiment: requereix [enriquiments](enrichment-hub.md) actius aplicats als perfils del client.</span><span class="sxs-lookup"><span data-stu-id="127dd-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="127dd-113">Control d'intel·ligència: Necessita dades generades mitjançant l'aprenentatge automàtic de l'Azure ([prediccions](predictions.md) o [models personalitzats](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="127dd-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="127dd-114">Control de mesures: Requereix [mesures configurades](measures.md).</span><span class="sxs-lookup"><span data-stu-id="127dd-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="127dd-115">Control de la cronologia: Requereix [activitats configurades](activities.md).</span><span class="sxs-lookup"><span data-stu-id="127dd-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="127dd-116">Instal·lar el complement de targeta del client</span><span class="sxs-lookup"><span data-stu-id="127dd-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="127dd-117">El complement de la targeta del client és una solució per a les aplicacions d'interacció amb els clients al Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="127dd-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="127dd-118">Per instal·lar la solució, aneu a AppSource i cerqueu **Targeta del client del Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="127dd-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="127dd-119">Seleccioneu el [Complement de targeta del client a AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i seleccioneu **Obtén ara**.</span><span class="sxs-lookup"><span data-stu-id="127dd-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="127dd-120">Potser heu d'iniciar la sessió amb les credencials d'administrador de l'aplicació Dynamics 365 per instal·lar la solució.</span><span class="sxs-lookup"><span data-stu-id="127dd-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="127dd-121">Pot ser que la solució tardi una estona en instal·lar-se al vostre entorn.</span><span class="sxs-lookup"><span data-stu-id="127dd-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="127dd-122">Configurar el complement de targeta del client</span><span class="sxs-lookup"><span data-stu-id="127dd-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="127dd-123">Com a administrador, aneu a la secció **Configuració** al Dynamics 365 i seleccioneu **Solucions**.</span><span class="sxs-lookup"><span data-stu-id="127dd-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="127dd-124">Seleccioneu l'enllaç **Nom de visualització** per a la solució del **Complement de targeta de client del Dynamics 365 Customer Insights (visualització prèvia)**.</span><span class="sxs-lookup"><span data-stu-id="127dd-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="127dd-125">![Seleccionar el nom de visualització](media/select-display-name.png "Seleccionar el nom de visualització")</span><span class="sxs-lookup"><span data-stu-id="127dd-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="127dd-126">Seleccioneu **Inicia la sessió** i introduïu les credencials del compte d'administrador que utilitzeu per configurar el Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="127dd-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="127dd-127">Comproveu que el bloquejador d'elements emergents del navegador no bloquegi la finestra d'autenticació en seleccionar el botó **Inicia la sessió**.</span><span class="sxs-lookup"><span data-stu-id="127dd-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="127dd-128">Seleccioneu l'entorn des del qual voleu obtenir dades.</span><span class="sxs-lookup"><span data-stu-id="127dd-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="127dd-129">Definiu l'assignació de camps a registres a l'aplicació Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="127dd-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="127dd-130">Per dur a terme l'assignació a un contacte, seleccioneu el camp de l'entitat de client que coincideixi amb l'identificador de l'entitat del contacte.</span><span class="sxs-lookup"><span data-stu-id="127dd-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="127dd-131">Per dur a terme l'assignació a un compte, seleccioneu el camp de l'entitat de client que coincideixi amb l'identificador de l'entitat del compte.</span><span class="sxs-lookup"><span data-stu-id="127dd-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="127dd-132">![Camp Identificador de contacte](media/contact-id-field.png "Camp Identificador de contacte")</span><span class="sxs-lookup"><span data-stu-id="127dd-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="127dd-133">Seleccioneu **Desa la configuració** per desar la configuració.</span><span class="sxs-lookup"><span data-stu-id="127dd-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="127dd-134">A continuació, heu d'assignar funcions de seguretat al Dynamics 365 per tal que els usuaris puguin personalitzar i veure la targeta del client.</span><span class="sxs-lookup"><span data-stu-id="127dd-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="127dd-135">Al Dynamics 365, aneu a **Configuració** > **Seguretat** > **Usuaris**.</span><span class="sxs-lookup"><span data-stu-id="127dd-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="127dd-136">Seleccioneu els usuaris per editar funcions d'usuari i seleccioneu **Administra les funcions**.</span><span class="sxs-lookup"><span data-stu-id="127dd-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="127dd-137">Assigneu la funció **Personalitzador de targetes del Customer Insights** a usuaris que personalitzaran el contingut que es mostra a la targeta per a tota l'organització.</span><span class="sxs-lookup"><span data-stu-id="127dd-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="127dd-138">Afegir controls de la targeta de client a formularis</span><span class="sxs-lookup"><span data-stu-id="127dd-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="127dd-139">Per afegir els controls de la targeta del client al formulari de contacte, aneu a **Configuració** > **Personalitzacions** al Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="127dd-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="127dd-140">Seleccioneu **Personalitza el sistema**.</span><span class="sxs-lookup"><span data-stu-id="127dd-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="127dd-141">Navegueu a l'entitat **Contacte**, expandiu-la i seleccioneu **Formularis**.</span><span class="sxs-lookup"><span data-stu-id="127dd-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="127dd-142">Seleccioneu el formulari de contacte al qual voleu afegir els controls de la targeta del client.</span><span class="sxs-lookup"><span data-stu-id="127dd-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="127dd-143">![Seleccioneu el formulari de contacte](media/contact-active-forms.png "Seleccioneu el formulari de contacte")</span><span class="sxs-lookup"><span data-stu-id="127dd-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="127dd-144">Per afegir un control, a l'editor de formularis, arrossegueu qualsevol camp de l'**Explorador de camps** a on voleu que aparegui el control.</span><span class="sxs-lookup"><span data-stu-id="127dd-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="127dd-145">Seleccioneu el camp al formulari que acabeu d'afegir i seleccioneu **Canvia les propietats**.</span><span class="sxs-lookup"><span data-stu-id="127dd-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="127dd-146">Aneu a la pestanya **Controls** i seleccioneu **Afegeix un control**.</span><span class="sxs-lookup"><span data-stu-id="127dd-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="127dd-147">Trieu un dels controls personalitzats disponibles i seleccioneu **Afegeix**.</span><span class="sxs-lookup"><span data-stu-id="127dd-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="127dd-148">Al quadre de diàleg **Propietats del camp**, desactiveu la casella de selecció **Mostra l'etiqueta al formulari**.</span><span class="sxs-lookup"><span data-stu-id="127dd-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="127dd-149">Seleccioneu l'opció **Web** per al control.</span><span class="sxs-lookup"><span data-stu-id="127dd-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="127dd-150">Per al control Enriquiment, seleccioneu el tipus d'enriquiment que voleu mostrar configurant el camp **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="127dd-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="127dd-151">Heu d'afegir un control d'enriquiment diferent per a cada tipus d'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="127dd-151">You need to add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="127dd-152">Seleccioneu **Desa** i **Publica** per publicar el formulari de contacte actualitzat.</span><span class="sxs-lookup"><span data-stu-id="127dd-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="127dd-153">Aneu al formulari de contacte publicat.</span><span class="sxs-lookup"><span data-stu-id="127dd-153">Go to the published contact form.</span></span> <span data-ttu-id="127dd-154">Es mostra el control acabat d'afegir.</span><span class="sxs-lookup"><span data-stu-id="127dd-154">You'll see the newly added control.</span></span> <span data-ttu-id="127dd-155">Pot ser que hàgiu d'iniciar la sessió la primera vegada que l'utilitzeu.</span><span class="sxs-lookup"><span data-stu-id="127dd-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="127dd-156">Per personalitzar el que voleu que es mostri en el control personalitzat, seleccioneu el botó Edita a la cantonada superior dreta.</span><span class="sxs-lookup"><span data-stu-id="127dd-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>
