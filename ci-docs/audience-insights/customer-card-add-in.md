---
title: Complement de la targeta del client de les aplicacions del Dynamics 365
description: Mostra dades dels coneixements del públic a les aplicacions del Dynamics 365 amb aquest complement.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059576"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="79bc9-103">Complement de targeta del client (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="79bc9-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="79bc9-104">Obtingueu una visió integral dels clients directament a les aplicacions del Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="79bc9-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="79bc9-105">Amb el complement de la targeta del client instal·lat a una aplicació compatible amb el Dynamics 365, podeu triar entre visualitzar la demografia, els coneixements i la cronologia d'activitats.</span><span class="sxs-lookup"><span data-stu-id="79bc9-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="79bc9-106">El complement recuperarà les dades del Customer Insights sense que afectin les dades de l'aplicació del Dynamics 365 connectada.</span><span class="sxs-lookup"><span data-stu-id="79bc9-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="79bc9-107">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="79bc9-107">Prerequisites</span></span>

- <span data-ttu-id="79bc9-108">El complement només funciona amb les aplicacions controlades per models del Dynamics 365, com ara Vendes o Servei d'atenció al client, versió 9.0 i posteriors.</span><span class="sxs-lookup"><span data-stu-id="79bc9-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="79bc9-109">Perquè les dades del Dynamics 365 s'assignin als perfils de client dels coneixements del públic, han de ser [ingerides des de l'aplicació del Dynamics 365 utilitzant el connector del Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="79bc9-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="79bc9-110">Tots els usuaris del Dynamics 365 del complement de la targeta del client s'han d'[afegir com a usuaris](permissions.md) als coneixements del públic per veure les dades.</span><span class="sxs-lookup"><span data-stu-id="79bc9-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="79bc9-111">[Les capacitats de cerca i filtre configurades](search-filter-index.md) als coneixements del públic són necessàries per cercar dades per treballar.</span><span class="sxs-lookup"><span data-stu-id="79bc9-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="79bc9-112">Cada complement es basa en dades específiques dels coneixements del públic:</span><span class="sxs-lookup"><span data-stu-id="79bc9-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="79bc9-113">Control de mesures: Requereix [mesures configurades](measures.md).</span><span class="sxs-lookup"><span data-stu-id="79bc9-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="79bc9-114">Control d'intel·ligència: requereix dades generades mitjançant [prediccions](predictions.md) o [models personalitzats](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="79bc9-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="79bc9-115">Control demogràfic: Els camps demogràfics, com l'edat o el gènere, estan disponibles al perfil unificat del client.</span><span class="sxs-lookup"><span data-stu-id="79bc9-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="79bc9-116">Control Enriquiment: requereix [enriquiments](enrichment-hub.md) actius aplicats als perfils del client.</span><span class="sxs-lookup"><span data-stu-id="79bc9-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="79bc9-117">Control de la cronologia: Requereix [activitats configurades](activities.md).</span><span class="sxs-lookup"><span data-stu-id="79bc9-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="79bc9-118">Instal·lar el complement de targeta del client</span><span class="sxs-lookup"><span data-stu-id="79bc9-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="79bc9-119">El complement de la targeta del client és una solució per a les aplicacions d'interacció amb els clients al Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="79bc9-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="79bc9-120">Per instal·lar la solució, aneu a AppSource i cerqueu **Targeta del client del Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="79bc9-121">Seleccioneu el [Complement de targeta del client a AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i seleccioneu **Obtén ara**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="79bc9-122">Potser heu d'iniciar la sessió amb les credencials d'administrador de l'aplicació Dynamics 365 per instal·lar la solució.</span><span class="sxs-lookup"><span data-stu-id="79bc9-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="79bc9-123">Pot ser que la solució tardi una estona en instal·lar-se al vostre entorn.</span><span class="sxs-lookup"><span data-stu-id="79bc9-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="79bc9-124">Configurar el complement de targeta del client</span><span class="sxs-lookup"><span data-stu-id="79bc9-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="79bc9-125">Com a administrador, aneu a la secció **Configuració** al Dynamics 365 i seleccioneu **Solucions**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="79bc9-126">Seleccioneu l'enllaç **Nom de visualització** per a la solució del **Complement de targeta de client del Dynamics 365 Customer Insights (visualització prèvia)**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79bc9-127">![Seleccionar el nom de visualització](media/select-display-name.png "Seleccionar el nom de visualització")</span><span class="sxs-lookup"><span data-stu-id="79bc9-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="79bc9-128">Seleccioneu **Inicia la sessió** i introduïu les credencials del compte d'administrador que utilitzeu per configurar el Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="79bc9-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="79bc9-129">Comproveu que el bloquejador d'elements emergents del navegador no bloquegi la finestra d'autenticació en seleccionar el botó **Inicia la sessió**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="79bc9-130">Seleccioneu l'entorn del Customer Insights des del qual voleu obtenir dades.</span><span class="sxs-lookup"><span data-stu-id="79bc9-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="79bc9-131">Definiu l'assignació de camps als registres de l'aplicació del Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="79bc9-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="79bc9-132">Segons les dades del Customer Insights, podeu triar entre assignar les opcions següents:</span><span class="sxs-lookup"><span data-stu-id="79bc9-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="79bc9-133">Per dur a terme l'assignació a un contacte, seleccioneu el camp de l'entitat de client que coincideixi amb l'identificador de l'entitat del contacte.</span><span class="sxs-lookup"><span data-stu-id="79bc9-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="79bc9-134">Per dur a terme l'assignació a un compte, seleccioneu el camp de l'entitat de client que coincideixi amb l'identificador de l'entitat del compte.</span><span class="sxs-lookup"><span data-stu-id="79bc9-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79bc9-135">![Camp Identificador de contacte](media/contact-id-field.png "Camp Identificador de contacte")</span><span class="sxs-lookup"><span data-stu-id="79bc9-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="79bc9-136">Seleccioneu **Desa la configuració** per desar la configuració.</span><span class="sxs-lookup"><span data-stu-id="79bc9-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="79bc9-137">A continuació, heu d'assignar funcions de seguretat al Dynamics 365 per tal que els usuaris puguin personalitzar i veure la targeta del client.</span><span class="sxs-lookup"><span data-stu-id="79bc9-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="79bc9-138">Al Dynamics 365, aneu a **Configuració** > **Seguretat** > **Usuaris**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="79bc9-139">Seleccioneu els usuaris per editar funcions d'usuari i seleccioneu **Administra les funcions**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="79bc9-140">Assigneu la funció **Personalitzador de targetes del Customer Insights** a usuaris que personalitzaran el contingut que es mostra a la targeta per a tota l'organització.</span><span class="sxs-lookup"><span data-stu-id="79bc9-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="79bc9-141">Afegir controls de la targeta de client a formularis</span><span class="sxs-lookup"><span data-stu-id="79bc9-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="79bc9-142">Per afegir els controls de la targeta del client al formulari de contacte, aneu a **Configuració** > **Personalitzacions** al Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="79bc9-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="79bc9-143">Seleccioneu **Personalitza el sistema**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="79bc9-144">Navegueu a l'entitat **Contacte**, expandiu-la i seleccioneu **Formularis**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="79bc9-145">Seleccioneu el formulari de contacte al qual voleu afegir els controls de la targeta del client.</span><span class="sxs-lookup"><span data-stu-id="79bc9-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="79bc9-146">![Seleccioneu el formulari de contacte](media/contact-active-forms.png "Seleccioneu el formulari de contacte")</span><span class="sxs-lookup"><span data-stu-id="79bc9-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="79bc9-147">Per afegir un control, a l'editor de formularis, arrossegueu qualsevol camp de l'**Explorador de camps** a on voleu que aparegui el control.</span><span class="sxs-lookup"><span data-stu-id="79bc9-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="79bc9-148">Seleccioneu el camp al formulari que acabeu d'afegir i seleccioneu **Canvia les propietats**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="79bc9-149">Aneu a la pestanya **Controls** i seleccioneu **Afegeix un control**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="79bc9-150">Trieu un dels controls personalitzats disponibles i seleccioneu **Afegeix**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="79bc9-151">Al quadre de diàleg **Propietats del camp**, desactiveu la casella de selecció **Mostra l'etiqueta al formulari**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="79bc9-152">Seleccioneu l'opció **Web** per al control.</span><span class="sxs-lookup"><span data-stu-id="79bc9-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="79bc9-153">Per al control Enriquiment, seleccioneu el tipus d'enriquiment que voleu mostrar configurant el camp **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="79bc9-154">Afegiu un control d'enriquiment diferent per a cada tipus d'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="79bc9-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="79bc9-155">Seleccioneu **Desa** i **Publica** per publicar el formulari de contacte actualitzat.</span><span class="sxs-lookup"><span data-stu-id="79bc9-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="79bc9-156">Aneu al formulari de contacte publicat.</span><span class="sxs-lookup"><span data-stu-id="79bc9-156">Go to the published contact form.</span></span> <span data-ttu-id="79bc9-157">Es mostra el control acabat d'afegir.</span><span class="sxs-lookup"><span data-stu-id="79bc9-157">You'll see the newly added control.</span></span> <span data-ttu-id="79bc9-158">Pot ser que hàgiu d'iniciar la sessió la primera vegada que l'utilitzeu.</span><span class="sxs-lookup"><span data-stu-id="79bc9-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="79bc9-159">Per personalitzar el que voleu que es mostri en el control personalitzat, seleccioneu el botó Edita a la cantonada superior dreta.</span><span class="sxs-lookup"><span data-stu-id="79bc9-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="79bc9-160">Actualitzar el complement de targeta del client</span><span class="sxs-lookup"><span data-stu-id="79bc9-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="79bc9-161">El complement de targeta del client no s'actualitza automàticament.</span><span class="sxs-lookup"><span data-stu-id="79bc9-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="79bc9-162">Per actualitzar a l'última versió, seguiu aquest procediment a l'aplicació Dynamics 365 que té el complement instal·lat.</span><span class="sxs-lookup"><span data-stu-id="79bc9-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="79bc9-163">A l'aplicació Dynamics 365, aneu a **Configuració** > **Personalització** i seleccioneu **Solucions**.</span><span class="sxs-lookup"><span data-stu-id="79bc9-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="79bc9-164">A la taula de complements, cerqueu **CustomerInsightsCustomerCard** i seleccioneu la fila.</span><span class="sxs-lookup"><span data-stu-id="79bc9-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="79bc9-165">Seleccioneu **Aplica l'actualització de la solució** a la barra d'accions.</span><span class="sxs-lookup"><span data-stu-id="79bc9-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualitzar la solució a l'àrea Personalització de les aplicacions del Dynamics 365":::

1. <span data-ttu-id="79bc9-167">Després d'iniciar el procés d'actualització, veureu un indicador de càrrega fins que finalitzi l'actualització.</span><span class="sxs-lookup"><span data-stu-id="79bc9-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="79bc9-168">Si no hi ha cap versió nova, l'actualització mostrarà un missatge d'error.</span><span class="sxs-lookup"><span data-stu-id="79bc9-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
