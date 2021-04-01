---
title: Exportar dades del Customer Insights a DotDigital
description: Apreneu a configurar la connexió a DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598004"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="b262e-103">Connector per a DotDigital (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="b262e-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="b262e-104">Exporteu els segments de perfils de client unificats a llibretes d'adreces de DotDigital i utilitzeu-los per a les campanyes, el màrqueting per correu electrònic i per crear segments de clients amb DotDigital.</span><span class="sxs-lookup"><span data-stu-id="b262e-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b262e-105">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="b262e-105">Prerequisites</span></span>

-   <span data-ttu-id="b262e-106">Teniu un [compte de DotDigital](https://dotdigital.com/) i les credencials d'administrador corresponents.</span><span class="sxs-lookup"><span data-stu-id="b262e-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b262e-107">Hi ha llibretes d'adreces a DotDigital amb els identificadors corresponents.</span><span class="sxs-lookup"><span data-stu-id="b262e-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="b262e-108">L'identificador es troba a l'adreça URL quan seleccioneu i obriu una llibreta d'adreces.</span><span class="sxs-lookup"><span data-stu-id="b262e-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="b262e-109">Per obtenir més informació, vegeu [Llibretes d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="b262e-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="b262e-110">Teniu [segments configurats](segments.md) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="b262e-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b262e-111">Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.</span><span class="sxs-lookup"><span data-stu-id="b262e-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="b262e-112">Connectar-se a DotDigital</span><span class="sxs-lookup"><span data-stu-id="b262e-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="b262e-113">Aneu a **Administració** > **Destinacions d'exportació**.</span><span class="sxs-lookup"><span data-stu-id="b262e-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b262e-114">A **DotDigital**, seleccioneu **Configura**.</span><span class="sxs-lookup"><span data-stu-id="b262e-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="b262e-115">Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="b262e-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Subfinestra de configuració de l'exportació a DotDigital.":::

1. <span data-ttu-id="b262e-117">Introduïu el **nom d'usuari i la contrasenya de DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="b262e-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="b262e-118">Introduïu l'**[identificador de la llibreta d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="b262e-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="b262e-119">Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.</span><span class="sxs-lookup"><span data-stu-id="b262e-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b262e-120">Seleccioneu **Connecta't** per inicialitzar la connexió a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="b262e-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="b262e-121">Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b262e-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b262e-122">Seleccioneu **Següent** per configurar l'exportació.</span><span class="sxs-lookup"><span data-stu-id="b262e-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b262e-123">Configurar el connector</span><span class="sxs-lookup"><span data-stu-id="b262e-123">Configure the connector</span></span>

1. <span data-ttu-id="b262e-124">A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client.</span><span class="sxs-lookup"><span data-stu-id="b262e-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b262e-125">Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom**, el **Cognom**, el **Nom complet**, el **Sexe** i el **Codi postal**.</span><span class="sxs-lookup"><span data-stu-id="b262e-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="b262e-126">Seleccioneu els segments que voleu exportar.</span><span class="sxs-lookup"><span data-stu-id="b262e-126">Select the segments you want to export.</span></span> <span data-ttu-id="b262e-127">Podeu exportar fins a un total d'un milió de perfils de client a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="b262e-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="b262e-128">Seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="b262e-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b262e-129">Exportar les dades</span><span class="sxs-lookup"><span data-stu-id="b262e-129">Export the data</span></span>

<span data-ttu-id="b262e-130">Podeu [exportar les dades segons demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b262e-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b262e-131">L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b262e-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b262e-132">A DotDigital, ara podeu cercar els vostres segments a les [llibretes d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="b262e-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b262e-133">Limitacions conegudes</span><span class="sxs-lookup"><span data-stu-id="b262e-133">Known limitations</span></span>

- <span data-ttu-id="b262e-134">Fins a un milió de perfils per exportació a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="b262e-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="b262e-135">L'exportació a DotDigital es limita als segments.</span><span class="sxs-lookup"><span data-stu-id="b262e-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="b262e-136">L'exportació de segments amb un total d'un milió de perfils pot durar fins a 3 hores a causa de les possibles limitacions del proveïdor.</span><span class="sxs-lookup"><span data-stu-id="b262e-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="b262e-137">El nombre de perfils que podeu exportar a DotDigital és limitat i dependrà del contracte que tingueu amb DotDigital.</span><span class="sxs-lookup"><span data-stu-id="b262e-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b262e-138">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="b262e-138">Data privacy and compliance</span></span>

<span data-ttu-id="b262e-139">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a DotDigital, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="b262e-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b262e-140">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que DotDigital compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="b262e-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b262e-141">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b262e-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b262e-142">L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="b262e-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]