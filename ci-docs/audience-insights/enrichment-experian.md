---
title: Enriquiment de amb l'enriquiment de tercers d'Experian
description: Informació general sobre l'enriquiment de tercers d'Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597775"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="8757f-103">Enriquir perfils de clients amb dades demogràfiques d'Experian (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="8757f-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="8757f-104">Experian és un líder mundial en informes de consum i cedit empresarial i serveis de màrqueting.</span><span class="sxs-lookup"><span data-stu-id="8757f-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="8757f-105">Amb els serveis d'enriquiment de dades d'Experian, podeu obtenir una comprensió més profunda dels clients enriquint els perfils dels clients amb dades demogràfiques com la mida de la llar, els ingressos i més.</span><span class="sxs-lookup"><span data-stu-id="8757f-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8757f-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="8757f-106">Prerequisites</span></span>

<span data-ttu-id="8757f-107">Per configurar Experian, cal complir els següents requisits previs:</span><span class="sxs-lookup"><span data-stu-id="8757f-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8757f-108">Tenir una subscripció d'Experian activa.</span><span class="sxs-lookup"><span data-stu-id="8757f-108">You have an active Experian subscription.</span></span> <span data-ttu-id="8757f-109">Per obtenir una subscripció, [poseu-vos en contacte amb Experian](https://www.experian.com/marketing-services/contact) directament.</span><span class="sxs-lookup"><span data-stu-id="8757f-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="8757f-110">[Més informació sobre l'enriquiment de dades d'Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="8757f-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="8757f-111">Tenir l'ID d'usuari, l'ID de grup i el número de model per al vostre compte de transport segur (ST) amb SSH que Experian us ha creat.</span><span class="sxs-lookup"><span data-stu-id="8757f-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="8757f-112">Teniu permisos d'[Administrador](permissions.md#administrator) a les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="8757f-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="8757f-113">Configuració</span><span class="sxs-lookup"><span data-stu-id="8757f-113">Configuration</span></span>

1. <span data-ttu-id="8757f-114">Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.</span><span class="sxs-lookup"><span data-stu-id="8757f-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="8757f-115">Seleccioneu **Enriqueix les meves dades** a la peça d'Experian.</span><span class="sxs-lookup"><span data-stu-id="8757f-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8757f-116">![Peça d'Experian](media/experian-tile.png "Peça d'Experian")</span><span class="sxs-lookup"><span data-stu-id="8757f-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="8757f-117">Seleccioneu **Comença** i introduïu l'ID d'usuari, l'ID de grup i el número de model per al vostre compte de transport segur d'Experian.</span><span class="sxs-lookup"><span data-stu-id="8757f-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="8757f-118">Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**.</span><span class="sxs-lookup"><span data-stu-id="8757f-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="8757f-119">Confirmeu totes les entrades seleccionant **Aplica**.</span><span class="sxs-lookup"><span data-stu-id="8757f-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="8757f-120">Assignació dels camps</span><span class="sxs-lookup"><span data-stu-id="8757f-120">Map your fields</span></span>

1.  <span data-ttu-id="8757f-121">Seleccioneu **Afegeix dades** i trieu el **conjunt de dades del client** que voleu enriquir amb les dades demogràfiques d'Experian.</span><span class="sxs-lookup"><span data-stu-id="8757f-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="8757f-122">Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.</span><span class="sxs-lookup"><span data-stu-id="8757f-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="8757f-123">Seleccioneu els identificadors clau de **Nom i adreça**, **Correu electrònic** o **Telèfon** per enviar a Experian per a la resolució d'identitats.</span><span class="sxs-lookup"><span data-stu-id="8757f-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="8757f-124">Si envieu més atributs d'identificador clau a Experian, probablement es produirà un percentatge de coincidència més alt.</span><span class="sxs-lookup"><span data-stu-id="8757f-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="8757f-125">Seleccioneu **Següent** i assigneu els atributs corresponents de la vostra entitat de client unificat per als camps d'identificador clau seleccionats.</span><span class="sxs-lookup"><span data-stu-id="8757f-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="8757f-126">Seleccioneu **Afegeix un atribut** per assignar qualsevol atribut addicional que vulgueu enviar a Experian.</span><span class="sxs-lookup"><span data-stu-id="8757f-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="8757f-127">Seleccioneu **Desa** per completar l'assignació de camps.</span><span class="sxs-lookup"><span data-stu-id="8757f-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8757f-128">![Assignació de camps d'Experian](media/experian-field-mapping.png "Assignació de camps d'Experian")</span><span class="sxs-lookup"><span data-stu-id="8757f-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="8757f-129">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="8757f-129">Enrichment results</span></span>

<span data-ttu-id="8757f-130">Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="8757f-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8757f-131">També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8757f-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8757f-132">El temps de processament dependrà de la mida de les dades del client i dels processos d'enriquiment creats per al vostre compte per Experian.</span><span class="sxs-lookup"><span data-stu-id="8757f-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="8757f-133">Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**.</span><span class="sxs-lookup"><span data-stu-id="8757f-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8757f-134">A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.</span><span class="sxs-lookup"><span data-stu-id="8757f-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8757f-135">Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.</span><span class="sxs-lookup"><span data-stu-id="8757f-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8757f-136">Passos següents</span><span class="sxs-lookup"><span data-stu-id="8757f-136">Next steps</span></span>

<span data-ttu-id="8757f-137">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="8757f-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8757f-138">Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="8757f-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8757f-139">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="8757f-139">Data privacy and compliance</span></span>

<span data-ttu-id="8757f-140">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Experian, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="8757f-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8757f-141">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Experian compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="8757f-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8757f-142">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8757f-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8757f-143">L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="8757f-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]