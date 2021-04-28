---
title: Exportar dades del Customer Insights a l'Administrador d'anuncis del Facebook
description: Apreneu a configurar la connexió i exportar a Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906798"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="869c5-103">Exportar una llista de segments a Facebook Ads Manager (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="869c5-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="869c5-104">Exporteu els segments de perfils unificats de client al Facebook Ads Manager per crear campanyes a Facebook i a Instagram.</span><span class="sxs-lookup"><span data-stu-id="869c5-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="869c5-105">Requisits previs per a la connexió</span><span class="sxs-lookup"><span data-stu-id="869c5-105">Prerequisites for connection</span></span>

- <span data-ttu-id="869c5-106">Heu de tenir un [**compte publicitari de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclogui un [**compte empresarial de Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="869c5-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="869c5-107">Heu de ser un administrador del [**compte publicitari de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="869c5-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="869c5-108">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="869c5-108">Known limitations</span></span>

- <span data-ttu-id="869c5-109">Fins a 10 milions de perfils de client per exportació a Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="869c5-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="869c5-110">L'exportació a Facebook Ads Manager es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="869c5-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="869c5-111">Creeu o actualitzeu públics personalitzats a Facebook només del tipus *llista de clients*.</span><span class="sxs-lookup"><span data-stu-id="869c5-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="869c5-112">L'exportació de segments amb un total de 10 milions de perfils pot tardar fins a 90 minuts a completar-se.</span><span class="sxs-lookup"><span data-stu-id="869c5-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="869c5-113">Configuració de la connexió a Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="869c5-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="869c5-114">Per poder crear una exportació, abans un administrador ha de configurar la connexió amb el servei i permetre que els usuaris utilitzin la connexió.</span><span class="sxs-lookup"><span data-stu-id="869c5-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="869c5-115">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="869c5-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="869c5-116">Seleccioneu **Afegeix una connexió** i trieu **Facebook Ads Manager** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="869c5-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="869c5-117">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="869c5-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="869c5-118">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="869c5-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="869c5-119">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="869c5-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="869c5-120">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="869c5-120">Choose who can use this connection.</span></span> <span data-ttu-id="869c5-121">Si no feu cap acció, el valor per defecte serà **Administradors**.</span><span class="sxs-lookup"><span data-stu-id="869c5-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="869c5-122">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="869c5-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="869c5-123">Autentiqueu-vos a Facebook Ads Manager:</span><span class="sxs-lookup"><span data-stu-id="869c5-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="869c5-124">Seleccioneu **Continua amb Facebook** per iniciar la sessió al vostre compte publicitari de Facebook.</span><span class="sxs-lookup"><span data-stu-id="869c5-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="869c5-125">Activeu el permís **ads_management** un cop us hagueu autenticat amb el Facebook.</span><span class="sxs-lookup"><span data-stu-id="869c5-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="869c5-126">Seleccioneu el **compte publicitari de Facebook** que voleu fer servir.</span><span class="sxs-lookup"><span data-stu-id="869c5-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="869c5-127">Seleccioneu un **Públic personalitzat existent** de la llista desplegable o creeu un **Nou públic personalitzat**.</span><span class="sxs-lookup"><span data-stu-id="869c5-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="869c5-128">Per obtenir més informació, vegeu [**Públics al Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="869c5-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="869c5-129">Només podeu crear o actualitzar públics personalitzats a Facebook del tipus *llista de clients* amb aquesta exportació.</span><span class="sxs-lookup"><span data-stu-id="869c5-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="869c5-130">En alguns casos, a la llista desplegable es veuen públics personalitzats de diversos tipus.</span><span class="sxs-lookup"><span data-stu-id="869c5-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="869c5-131">Seleccionar un tipus diferent de *llista de clients* tindrà com a resultat una exportació fallada.</span><span class="sxs-lookup"><span data-stu-id="869c5-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="869c5-132">Reviseu la **Privadesa de les dades i el compliment** i, a continuació, seleccioneu **Accepto**.</span><span class="sxs-lookup"><span data-stu-id="869c5-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="869c5-133">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="869c5-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="869c5-134">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="869c5-134">Configure an export</span></span>

<span data-ttu-id="869c5-135">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="869c5-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="869c5-136">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="869c5-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="869c5-137">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="869c5-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="869c5-138">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="869c5-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="869c5-139">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="869c5-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="869c5-140">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="869c5-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="869c5-141">Al camp **Trieu el vostre identificador de clau**, seleccioneu **Correu electrònic**, **Nom i adreça** o **Telèfon** per enviar al Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="869c5-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="869c5-142">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="869c5-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="869c5-143">Assigneu els atributs corresponents de l'entitat del client unificat per a l'identificador de clau seleccionat.</span><span class="sxs-lookup"><span data-stu-id="869c5-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="869c5-144">[CONSELL] Les millors oportunitats perquè hi hagi una coincidència es produeixen si seleccioneu **Correu electrònic** com a identificador de clau.</span><span class="sxs-lookup"><span data-stu-id="869c5-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="869c5-145">L'addició d'identificadors addicionals podria millorar la coincidència.</span><span class="sxs-lookup"><span data-stu-id="869c5-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="869c5-146">Seleccioneu **Afegeix un atribut** per assignar més atributs per enviar-los a Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="869c5-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="869c5-147">Els atributs de Facebook Ads Manager s'assignen als noms de text descriptiu següents: **FN** = **Nom**, **LN** = **Cognom**, **FI** = **Primera inicial**, **PHONE** = **Telèfon**, **GEN** = **Gènere**, **DOB** = **Data de naixement**, **ST** = **Estat**, **CT** = **Ciutat**, **ZIP** = **Codi postal**, **COUNTRY** = **País/regió**</span><span class="sxs-lookup"><span data-stu-id="869c5-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="869c5-148">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="869c5-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="869c5-149">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="869c5-149">Select **Save**.</span></span>

<span data-ttu-id="869c5-150">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="869c5-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="869c5-151">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="869c5-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="869c5-152">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="869c5-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="869c5-153">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="869c5-153">Data privacy and compliance</span></span>

<span data-ttu-id="869c5-154">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a l'Administrador d'anuncis del Facebook, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="869c5-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="869c5-155">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Facebook Ads compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="869c5-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="869c5-156">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="869c5-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="869c5-157">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="869c5-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
