---
title: Enriquiment de amb l'enriquiment de tercers d'Experian
description: Informació general sobre l'enriquiment de tercers d'Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896361"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="35c04-103">Enriquir perfils de clients amb dades demogràfiques d'Experian (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="35c04-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="35c04-104">Experian és un líder mundial en informes de consum i cedit empresarial i serveis de màrqueting.</span><span class="sxs-lookup"><span data-stu-id="35c04-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="35c04-105">Amb els serveis d'enriquiment de dades d'Experian, podeu obtenir una comprensió més profunda dels clients enriquint els perfils dels clients amb dades demogràfiques com la mida de la llar, els ingressos i més.</span><span class="sxs-lookup"><span data-stu-id="35c04-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="35c04-106">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="35c04-106">Prerequisites</span></span>

<span data-ttu-id="35c04-107">Per configurar Experian, cal complir els següents requisits previs:</span><span class="sxs-lookup"><span data-stu-id="35c04-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="35c04-108">Tenir una subscripció d'Experian activa.</span><span class="sxs-lookup"><span data-stu-id="35c04-108">You have an active Experian subscription.</span></span> <span data-ttu-id="35c04-109">Per obtenir una subscripció, [poseu-vos en contacte amb Experian](https://www.experian.com/marketing-services/contact) directament.</span><span class="sxs-lookup"><span data-stu-id="35c04-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="35c04-110">[Més informació sobre l'enriquiment de dades d'Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="35c04-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="35c04-111">Un administrador ja ha configurat una connexió de l'Experian *o* teniu permisos d'[administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="35c04-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="35c04-112">També necessiteu l'identificador d'usuari, l'identificador del grup i el número de model per al compte de Transport segur (ST) habilitat per a SSH que l'Experian ha creat.</span><span class="sxs-lookup"><span data-stu-id="35c04-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="35c04-113">Configurar l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="35c04-113">Configure the enrichment</span></span>

1. <span data-ttu-id="35c04-114">Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.</span><span class="sxs-lookup"><span data-stu-id="35c04-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="35c04-115">Seleccioneu **Enriqueix les meves dades** a la peça d'Experian.</span><span class="sxs-lookup"><span data-stu-id="35c04-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="35c04-116">![Peça d'Experian](media/experian-tile.png "Peça d'Experian")</span><span class="sxs-lookup"><span data-stu-id="35c04-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="35c04-117">Seleccioneu una [connexió](connections.md) a la llista desplegable.</span><span class="sxs-lookup"><span data-stu-id="35c04-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="35c04-118">Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.</span><span class="sxs-lookup"><span data-stu-id="35c04-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="35c04-119">Si sou un administrador, podeu crear una connexió seleccionant **Afegeix una connexió** i triant Experian al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="35c04-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="35c04-120">Seleccioneu **Connecta't a Experian** per confirmar la selecció de la connexió.</span><span class="sxs-lookup"><span data-stu-id="35c04-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="35c04-121">Seleccioneu **Següent** i trieu el **Conjunt de dades de client** que voleu enriquir amb les dades demogràfiques de l'Experian.</span><span class="sxs-lookup"><span data-stu-id="35c04-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="35c04-122">Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.</span><span class="sxs-lookup"><span data-stu-id="35c04-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. <span data-ttu-id="35c04-124">Seleccioneu **Següent** i definiu els tipus de camps dels perfils unificats que s'han d'utilitzar per cercar dades demogràfiques coincidents de l'Experian.</span><span class="sxs-lookup"><span data-stu-id="35c04-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="35c04-125">Cal com a mínim un dels camps **Nom i adreça**, **Telèfon** o **Correu electrònic**.</span><span class="sxs-lookup"><span data-stu-id="35c04-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="35c04-126">Per tenir una precisió de coincidència superior, es poden afegir fins a dos camps més.</span><span class="sxs-lookup"><span data-stu-id="35c04-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="35c04-127">Aquesta selecció afectarà els camps d'assignació als quals teniu accés al pas següent.</span><span class="sxs-lookup"><span data-stu-id="35c04-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="35c04-128">Si envieu més atributs d'identificador clau a Experian, probablement es produirà un percentatge de coincidència més alt.</span><span class="sxs-lookup"><span data-stu-id="35c04-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="35c04-129">Seleccioneu **Següent** per iniciar l'assignació de camp.</span><span class="sxs-lookup"><span data-stu-id="35c04-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="35c04-130">Definiu quins camps dels perfils unificats que s'han d'utilitzar per cercar dades demogràfiques coincidents de l'Experian.</span><span class="sxs-lookup"><span data-stu-id="35c04-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="35c04-131">Els camps obligatoris estan marcats.</span><span class="sxs-lookup"><span data-stu-id="35c04-131">Required fields are marked.</span></span>

1. <span data-ttu-id="35c04-132">Proporcioneu un nom per a l'enriquiment i un nom per a l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="35c04-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="35c04-133">Seleccioneu **Desa l'enriquiment** després de revisar les opcions.</span><span class="sxs-lookup"><span data-stu-id="35c04-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="35c04-134">Configurar la connexió per a l'Experian</span><span class="sxs-lookup"><span data-stu-id="35c04-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="35c04-135">Heu de ser administrador per configurar les connexions.</span><span class="sxs-lookup"><span data-stu-id="35c04-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="35c04-136">Seleccioneu **Afegeix una connexió** en configurar un enriquiment *o* aneu a **Administració** > **Connexions** i seleccioneu **Configuració** a la peça Experian.</span><span class="sxs-lookup"><span data-stu-id="35c04-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="35c04-137">Seleccioneu **Introducció**.</span><span class="sxs-lookup"><span data-stu-id="35c04-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="35c04-138">Introduïu un nom per a la connexió al quadre **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="35c04-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="35c04-139">Introduïu l'identificador d'usuari, l'identificador del grup i el número de model vàlids per al compte de transport segur d'Experian.</span><span class="sxs-lookup"><span data-stu-id="35c04-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="35c04-140">Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**</span><span class="sxs-lookup"><span data-stu-id="35c04-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="35c04-141">Seleccioneu **Verifica** per validar la configuració.</span><span class="sxs-lookup"><span data-stu-id="35c04-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="35c04-142">Després de completar la verificació, seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="35c04-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Subfinestra de configuració de la connexió d'Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="35c04-144">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="35c04-144">Enrichment results</span></span>

<span data-ttu-id="35c04-145">Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="35c04-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="35c04-146">També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="35c04-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="35c04-147">El temps de processament dependrà de la mida de les dades del client i dels processos d'enriquiment creats per al vostre compte per Experian.</span><span class="sxs-lookup"><span data-stu-id="35c04-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="35c04-148">Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**.</span><span class="sxs-lookup"><span data-stu-id="35c04-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="35c04-149">A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.</span><span class="sxs-lookup"><span data-stu-id="35c04-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="35c04-150">Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.</span><span class="sxs-lookup"><span data-stu-id="35c04-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="35c04-151">Passos següents</span><span class="sxs-lookup"><span data-stu-id="35c04-151">Next steps</span></span>

<span data-ttu-id="35c04-152">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="35c04-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="35c04-153">Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="35c04-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="35c04-154">Compliment i privadesa de les dades</span><span class="sxs-lookup"><span data-stu-id="35c04-154">Data privacy and compliance</span></span>

<span data-ttu-id="35c04-155">Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Experian, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals.</span><span class="sxs-lookup"><span data-stu-id="35c04-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="35c04-156">Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Experian compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir.</span><span class="sxs-lookup"><span data-stu-id="35c04-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="35c04-157">Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="35c04-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="35c04-158">L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.</span><span class="sxs-lookup"><span data-stu-id="35c04-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
