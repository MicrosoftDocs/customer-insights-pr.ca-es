---
title: Enriquiment amb la importació personalitzada d'SFTP
description: Informació general sobre l'enriquiment amb la importació personalitzada d'SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896269"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="7665d-103">Enriquir els perfils de client amb dades personalitzades (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="7665d-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="7665d-104">La importació personalitzada de protocol de transferència segura de fitxers (SFTP) permet importar dades que no han de passar pel procés d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="7665d-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="7665d-105">Es tracta d'un mètode flexible, segur i fàcil d'incorporar les vostres dades.</span><span class="sxs-lookup"><span data-stu-id="7665d-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="7665d-106">La importació personalitzada d'SFTP es pot utilitzar combinada amb [l'exportació d'SFTP](export-sftp.md), que us permet exportar les dades del perfil del client necessàries per a l'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="7665d-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="7665d-107">Tot seguit, les dades es poden processar i enriquir; a més, la importació personalitzada d'SFTP es pot utilitzar per tornar les dades enriquides a la capacitat de conclusions del públic del Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7665d-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7665d-108">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="7665d-108">Prerequisites</span></span>

<span data-ttu-id="7665d-109">Per poder configurar la importació personalitzada d'SFTP, s'han de complir els requisits previs següents:</span><span class="sxs-lookup"><span data-stu-id="7665d-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7665d-110">Teniu el nom de fitxer i la ubicació (camí) del fitxer que s'ha d'importar a l'amfitrió de l'SFTP.</span><span class="sxs-lookup"><span data-stu-id="7665d-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="7665d-111">Hi ha un fitxer *model.json* que especifica [l'esquema del Model de dades comú](/common-data-model/) per a les dades que s'han d'importar.</span><span class="sxs-lookup"><span data-stu-id="7665d-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="7665d-112">Aquest fitxer s'ha de trobar al mateix directori que el fitxer que s'importarà.</span><span class="sxs-lookup"><span data-stu-id="7665d-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="7665d-113">Un administrador ja ha configurat una connexió SFTP *o* teniu permisos d'[administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="7665d-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="7665d-114">Necessitareu les credencials d'usuari, l'adreça URL i el número de port de la ubicació SFTP des d'on voleu importar les dades.</span><span class="sxs-lookup"><span data-stu-id="7665d-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="7665d-115">Configurar la importació</span><span class="sxs-lookup"><span data-stu-id="7665d-115">Configure the import</span></span>

1. <span data-ttu-id="7665d-116">Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.</span><span class="sxs-lookup"><span data-stu-id="7665d-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="7665d-117">A la **peça Importació personalitzada SFTP**, seleccioneu **Enriqueix les meves dades** i, a continuació, **Comença**.</span><span class="sxs-lookup"><span data-stu-id="7665d-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Peça de la importació personalitzada d'SFTP.":::

1. <span data-ttu-id="7665d-119">Seleccioneu una [connexió](connections.md) a la llista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7665d-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="7665d-120">Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.</span><span class="sxs-lookup"><span data-stu-id="7665d-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="7665d-121">Si sou un administrador, podeu crear una connexió seleccionant **Afegeix una connexió** i triant **Importació personalitzada d'SFTP** al menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="7665d-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="7665d-122">Seleccioneu **Connecta't a la importació personalitzada** per confirmar la connexió seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7665d-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="7665d-123">Seleccioneu **Següent** i introduïu el **Nom de fitxer** i el **Camí** del fitxer de dades que voleu importar.</span><span class="sxs-lookup"><span data-stu-id="7665d-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de pantalla quan introduïu la ubicació de les dades.":::

1. <span data-ttu-id="7665d-125">Seleccioneu **Següent** i proporcioneu un nom per a l'enriquiment i un nom per a l'entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="7665d-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="7665d-126">Seleccioneu **Desa l'enriquiment** després de revisar les opcions.</span><span class="sxs-lookup"><span data-stu-id="7665d-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="7665d-127">Configurar la connexió per a la importació personalitzada de l'SFTP</span><span class="sxs-lookup"><span data-stu-id="7665d-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="7665d-128">Heu de ser administrador per configurar les connexions.</span><span class="sxs-lookup"><span data-stu-id="7665d-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="7665d-129">Seleccioneu **Afegeix una connexió** en configurar un enriquiment *o* aneu a **Administració** > **Connexions** i seleccioneu **Configuració** a la peça Importació personalitzada.</span><span class="sxs-lookup"><span data-stu-id="7665d-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="7665d-130">Introduïu un nom per a la connexió al quadre **Nom de visualització**.</span><span class="sxs-lookup"><span data-stu-id="7665d-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="7665d-131">Introduïu un nom d'usuari, una contrasenya i una adreça URL d'amfitrió vàlides per al servidor d'STFP on resideixin les dades que s'han d'importar.</span><span class="sxs-lookup"><span data-stu-id="7665d-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="7665d-132">Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**.</span><span class="sxs-lookup"><span data-stu-id="7665d-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="7665d-133">Seleccioneu **Verifica** per validar la configuració.</span><span class="sxs-lookup"><span data-stu-id="7665d-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="7665d-134">Quan la verificació s'hagi completat, feu clic a **Desa** per desar la connexió.</span><span class="sxs-lookup"><span data-stu-id="7665d-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="7665d-135">![Pàgina de configuració de la connexió d'Experian](media/enrichment-SFTP-connection.png "Pàgina de configuració de la connexió d'Experian")</span><span class="sxs-lookup"><span data-stu-id="7665d-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="7665d-136">Definició de les assignacions de camps</span><span class="sxs-lookup"><span data-stu-id="7665d-136">Defining field mappings</span></span> 

<span data-ttu-id="7665d-137">El directori que conté el fitxer que s'importarà al servidor SFTP també ha d'incloure un fitxer *model.json*.</span><span class="sxs-lookup"><span data-stu-id="7665d-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="7665d-138">En aquest fitxer es defineix l'esquema que s'utilitzarà per importar les dades.</span><span class="sxs-lookup"><span data-stu-id="7665d-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="7665d-139">L'esquema ha d'utilitzar [el Common Data Model](/common-data-model/) per especificar l'assignació de camps.</span><span class="sxs-lookup"><span data-stu-id="7665d-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="7665d-140">Tot seguit es mostra un exemple senzill de fitxer model.json:</span><span class="sxs-lookup"><span data-stu-id="7665d-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="7665d-141">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="7665d-141">Enrichment results</span></span>

<span data-ttu-id="7665d-142">Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="7665d-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="7665d-143">També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7665d-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7665d-144">El temps de processament dependrà de la mida de les dades que s'importaran i de la connexió al servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="7665d-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="7665d-145">Un cop finalitzat el procés d'enriquiment, podeu revisar les dades de l'enriquiment personalitzat acabades d'importar a **Els meus enriquiments**.</span><span class="sxs-lookup"><span data-stu-id="7665d-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="7665d-146">A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.</span><span class="sxs-lookup"><span data-stu-id="7665d-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="7665d-147">Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.</span><span class="sxs-lookup"><span data-stu-id="7665d-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7665d-148">Passos següents</span><span class="sxs-lookup"><span data-stu-id="7665d-148">Next steps</span></span>

<span data-ttu-id="7665d-149">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="7665d-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7665d-150">Creeu [segments](segments.md), [mesures](measures.md) i [exporteu les dades](export-destinations.md) per tal d'oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="7665d-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
