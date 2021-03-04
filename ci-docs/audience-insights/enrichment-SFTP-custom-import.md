---
title: Enriquiment amb la importació personalitzada d'SFTP
description: Informació general sobre l'enriquiment amb la importació personalitzada d'SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269594"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="5b531-103">Enriquir els perfils de client amb dades personalitzades (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="5b531-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="5b531-104">La importació personalitzada del protocol de transferència segura de fitxers (SFTP) us permet importar dades que no han de passar pel procés d'unificació de dades.</span><span class="sxs-lookup"><span data-stu-id="5b531-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="5b531-105">Es tracta d'un mètode flexible, segur i fàcil d'incorporar les vostres dades.</span><span class="sxs-lookup"><span data-stu-id="5b531-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="5b531-106">La importació personalitzada d'SFTP es pot utilitzar combinada amb [l'exportació d'SFTP](export-sftp.md), que us permet exportar les dades del perfil del client necessàries per a l'enriquiment.</span><span class="sxs-lookup"><span data-stu-id="5b531-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="5b531-107">Tot seguit, les dades es poden processar i enriquir; a més, la importació personalitzada d'SFTP es pot utilitzar per tornar les dades enriquides a la capacitat de conclusions del públic del Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b531-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5b531-108">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="5b531-108">Prerequisites</span></span>

<span data-ttu-id="5b531-109">Per poder configurar la importació personalitzada d'SFTP, s'han de complir els requisits previs següents:</span><span class="sxs-lookup"><span data-stu-id="5b531-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5b531-110">Teniu credencials d'usuari (nom d'usuari i contrasenya) per a la ubicació d'SFTP des d'on s'importaran les dades.</span><span class="sxs-lookup"><span data-stu-id="5b531-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="5b531-111">Teniu l'adreça URL i el número de port (normalment, 22) per a l'amfitrió d'SFTP.</span><span class="sxs-lookup"><span data-stu-id="5b531-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="5b531-112">Teniu el nom i la ubicació del fitxer que s'importarà a l'amfitrió d'SFTP.</span><span class="sxs-lookup"><span data-stu-id="5b531-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="5b531-113">Un fitxer *model.json* especifica l'esquema de les dades que s'importaran.</span><span class="sxs-lookup"><span data-stu-id="5b531-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="5b531-114">Aquest fitxer s'ha de trobar al mateix directori que el fitxer que s'importarà.</span><span class="sxs-lookup"><span data-stu-id="5b531-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="5b531-115">Teniu permisos d'[Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="5b531-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="5b531-116">Configuració</span><span class="sxs-lookup"><span data-stu-id="5b531-116">Configuration</span></span>

1. <span data-ttu-id="5b531-117">Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.</span><span class="sxs-lookup"><span data-stu-id="5b531-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="5b531-118">A la **peça d'importació personalitzada d'SFTP**, seleccioneu **Enriqueix les meves dades**.</span><span class="sxs-lookup"><span data-stu-id="5b531-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5b531-119">![Peça de la importació personalitzada d'SFTP](media/SFTP_Custom_Import_tile.png "Peça de la importació personalitzada d'SFTP")</span><span class="sxs-lookup"><span data-stu-id="5b531-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="5b531-120">Seleccioneu **Comença** i indiqueu les credencials i l'adreça del servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="5b531-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="5b531-121">Per exemple, sftp://elmeuservidorsftp.com:22.</span><span class="sxs-lookup"><span data-stu-id="5b531-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="5b531-122">Introduïu el nom del fitxer que conté les dades i el camí al fitxer del servidor SFTP si no es troba a la carpeta arrel.</span><span class="sxs-lookup"><span data-stu-id="5b531-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="5b531-123">Seleccioneu **Connecta't a la importació personalitzada** per confirmar totes les entrades.</span><span class="sxs-lookup"><span data-stu-id="5b531-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5b531-124">![Desplegable de la configuració d'importació personalitzada d'SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Desplegable de la configuració d'importació personalitzada d'SFTP")</span><span class="sxs-lookup"><span data-stu-id="5b531-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="5b531-125">Definició de les assignacions de camps</span><span class="sxs-lookup"><span data-stu-id="5b531-125">Defining field mappings</span></span> 

<span data-ttu-id="5b531-126">El directori que conté el fitxer que s'importarà al servidor SFTP també ha d'incloure un fitxer *model.json*.</span><span class="sxs-lookup"><span data-stu-id="5b531-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="5b531-127">En aquest fitxer es defineix l'esquema que s'utilitzarà per importar les dades.</span><span class="sxs-lookup"><span data-stu-id="5b531-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="5b531-128">L'esquema ha d'utilitzar [el Common Data Model](https://docs.microsoft.com/common-data-model/) per especificar l'assignació de camps.</span><span class="sxs-lookup"><span data-stu-id="5b531-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="5b531-129">Tot seguit es mostra un exemple senzill de fitxer model.json:</span><span class="sxs-lookup"><span data-stu-id="5b531-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="5b531-130">Resultats de l'enriquiment</span><span class="sxs-lookup"><span data-stu-id="5b531-130">Enrichment results</span></span>

<span data-ttu-id="5b531-131">Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="5b531-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="5b531-132">També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5b531-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5b531-133">El temps de processament dependrà de la mida de les dades que s'importaran i de la connexió al servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="5b531-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="5b531-134">Un cop finalitzat el procés d'enriquiment, podeu revisar les dades de l'enriquiment personalitzat acabades d'importar a **Els meus enriquiments**.</span><span class="sxs-lookup"><span data-stu-id="5b531-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="5b531-135">A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.</span><span class="sxs-lookup"><span data-stu-id="5b531-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="5b531-136">Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.</span><span class="sxs-lookup"><span data-stu-id="5b531-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b531-137">Passos següents</span><span class="sxs-lookup"><span data-stu-id="5b531-137">Next steps</span></span>

<span data-ttu-id="5b531-138">Construïu a partir de les dades de clients enriquits.</span><span class="sxs-lookup"><span data-stu-id="5b531-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="5b531-139">Creeu [segments](segments.md), [mesures](measures.md) i [exporteu les dades](export-destinations.md) per tal d'oferir experiències personalitzades als vostres clients.</span><span class="sxs-lookup"><span data-stu-id="5b531-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]