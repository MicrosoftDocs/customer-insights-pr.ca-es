---
title: Exportar dades del Customer Insights a DotDigital
description: Apreneu a configurar la connexió i exportar a DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976834"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="2bedf-103">Exportar llistes de segments a DotDigital (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="2bedf-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="2bedf-104">Exporteu els segments de perfils de client unificats a llibretes d'adreces de DotDigital i utilitzeu-los per a les campanyes, el màrqueting per correu electrònic i per crear segments de clients amb DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2bedf-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="2bedf-105">Requisits previs per a una connexió</span><span class="sxs-lookup"><span data-stu-id="2bedf-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="2bedf-106">Teniu un [compte de DotDigital](https://dotdigital.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="2bedf-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2bedf-107">Hi ha llibretes d'adreces a DotDigital amb els identificadors corresponents.</span><span class="sxs-lookup"><span data-stu-id="2bedf-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="2bedf-108">L'identificador es troba a l'adreça URL quan seleccioneu i obriu una llibreta d'adreces.</span><span class="sxs-lookup"><span data-stu-id="2bedf-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="2bedf-109">Per obtenir més informació, vegeu [Llibretes d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="2bedf-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="2bedf-110">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="2bedf-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2bedf-111">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="2bedf-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2bedf-112">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="2bedf-112">Known limitations</span></span>

- <span data-ttu-id="2bedf-113">Fins a un milió de perfils per exportació a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2bedf-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="2bedf-114">L'exportació a DotDigital es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="2bedf-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="2bedf-115">L'exportació de segments amb un total d'un milió de perfils pot durar fins a 3 hores a causa de les possibles limitacions del proveïdor.</span><span class="sxs-lookup"><span data-stu-id="2bedf-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="2bedf-116">El nombre de perfils que podeu exportar a DotDigital és limitat i dependrà del contracte que tingueu amb DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2bedf-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="2bedf-117">Configuració de la connexió a DotDigital</span><span class="sxs-lookup"><span data-stu-id="2bedf-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="2bedf-118">Aneu a **Administració** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="2bedf-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2bedf-119">Seleccioneu **Afegeix connexió** i trieu **DotDigital** per configurar la connexió.</span><span class="sxs-lookup"><span data-stu-id="2bedf-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="2bedf-120">Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="2bedf-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2bedf-121">El nom i el tipus de connexió descriuen aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="2bedf-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2bedf-122">Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.</span><span class="sxs-lookup"><span data-stu-id="2bedf-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2bedf-123">Trieu qui pot utilitzar aquesta connexió.</span><span class="sxs-lookup"><span data-stu-id="2bedf-123">Choose who can use this connection.</span></span> <span data-ttu-id="2bedf-124">Si no feu cap acció, el valor per defecte serà Administradors.</span><span class="sxs-lookup"><span data-stu-id="2bedf-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2bedf-125">Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2bedf-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2bedf-126">Introduïu el **nom d'usuari i la contrasenya de DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="2bedf-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="2bedf-127">Introduïu l'**[identificador de la llibreta d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="2bedf-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="2bedf-128">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="2bedf-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2bedf-129">Seleccioneu **Connecta't** per inicialitzar la connexió a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2bedf-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="2bedf-130">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2bedf-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2bedf-131">Seleccioneu **Desa** per completar la connexió.</span><span class="sxs-lookup"><span data-stu-id="2bedf-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="2bedf-132">Configurar una exportació</span><span class="sxs-lookup"><span data-stu-id="2bedf-132">Configure an export</span></span>

<span data-ttu-id="2bedf-133">Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus.</span><span class="sxs-lookup"><span data-stu-id="2bedf-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2bedf-134">Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2bedf-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2bedf-135">Vés a **Dades** > **Exportacions**.</span><span class="sxs-lookup"><span data-stu-id="2bedf-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2bedf-136">Per crear una exportació nova, seleccioneu **Afegeix una destinació**.</span><span class="sxs-lookup"><span data-stu-id="2bedf-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2bedf-137">Al camp **Connexió per a l'exportació**, trieu una connexió de la secció DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2bedf-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="2bedf-138">Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.</span><span class="sxs-lookup"><span data-stu-id="2bedf-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="2bedf-139">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="2bedf-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2bedf-140">Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom**, el **Cognom**, el **Nom complet**, el **Sexe** i el **Codi postal**.</span><span class="sxs-lookup"><span data-stu-id="2bedf-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="2bedf-141">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="2bedf-141">Select the segments you want to export.</span></span> <span data-ttu-id="2bedf-142">Podeu exportar fins a un total d'un milió de perfils de client a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2bedf-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="2bedf-143">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="2bedf-143">Select **Save**.</span></span>

<span data-ttu-id="2bedf-144">Si deseu una exportació, no s'executarà l'exportació immediatament.</span><span class="sxs-lookup"><span data-stu-id="2bedf-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2bedf-145">L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2bedf-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2bedf-146">També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2bedf-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="2bedf-147">A DotDigital, ara podeu cercar els vostres segments a les [llibretes d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="2bedf-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2bedf-148">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="2bedf-148">Data privacy and compliance</span></span>

<span data-ttu-id="2bedf-149">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a DotDigital, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="2bedf-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2bedf-150">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que DotDigital compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="2bedf-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2bedf-151">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2bedf-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2bedf-152">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="2bedf-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
