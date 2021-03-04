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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquir els perfils de client amb dades personalitzades (versió preliminar)

La importació personalitzada del protocol de transferència segura de fitxers (SFTP) us permet importar dades que no han de passar pel procés d'unificació de dades. Es tracta d'un mètode flexible, segur i fàcil d'incorporar les vostres dades. La importació personalitzada d'SFTP es pot utilitzar combinada amb [l'exportació d'SFTP](export-sftp.md), que us permet exportar les dades del perfil del client necessàries per a l'enriquiment. Tot seguit, les dades es poden processar i enriquir; a més, la importació personalitzada d'SFTP es pot utilitzar per tornar les dades enriquides a la capacitat de conclusions del públic del Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisits previs

Per poder configurar la importació personalitzada d'SFTP, s'han de complir els requisits previs següents:

- Teniu credencials d'usuari (nom d'usuari i contrasenya) per a la ubicació d'SFTP des d'on s'importaran les dades.
- Teniu l'adreça URL i el número de port (normalment, 22) per a l'amfitrió d'SFTP.
- Teniu el nom i la ubicació del fitxer que s'importarà a l'amfitrió d'SFTP.
- Un fitxer *model.json* especifica l'esquema de les dades que s'importaran. Aquest fitxer s'ha de trobar al mateix directori que el fitxer que s'importarà.
- Teniu permisos d'[Administrador](permissions.md#administrator).

## <a name="configuration"></a>Configuració

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. A la **peça d'importació personalitzada d'SFTP**, seleccioneu **Enriqueix les meves dades**.

   > [!div class="mx-imgBorder"]
   > ![Peça de la importació personalitzada d'SFTP](media/SFTP_Custom_Import_tile.png "Peça de la importació personalitzada d'SFTP")

1. Seleccioneu **Comença** i indiqueu les credencials i l'adreça del servidor SFTP. Per exemple, sftp://elmeuservidorsftp.com:22.

1. Introduïu el nom del fitxer que conté les dades i el camí al fitxer del servidor SFTP si no es troba a la carpeta arrel.

1. Seleccioneu **Connecta't a la importació personalitzada** per confirmar totes les entrades.

   > [!div class="mx-imgBorder"]
   > ![Desplegable de la configuració d'importació personalitzada d'SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Desplegable de la configuració d'importació personalitzada d'SFTP")

## <a name="defining-field-mappings"></a>Definició de les assignacions de camps 

El directori que conté el fitxer que s'importarà al servidor SFTP també ha d'incloure un fitxer *model.json*. En aquest fitxer es defineix l'esquema que s'utilitzarà per importar les dades. L'esquema ha d'utilitzar [el Common Data Model](https://docs.microsoft.com/common-data-model/) per especificar l'assignació de camps. Tot seguit es mostra un exemple senzill de fitxer model.json:

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

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres. També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab). El temps de processament dependrà de la mida de les dades que s'importaran i de la connexió al servidor SFTP.

Un cop finalitzat el procés d'enriquiment, podeu revisar les dades de l'enriquiment personalitzat acabades d'importar a **Els meus enriquiments**. A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.

Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.

## <a name="next-steps"></a>Passos següents

Construïu a partir de les dades de clients enriquits. Creeu [segments](segments.md), [mesures](measures.md) i [exporteu les dades](export-destinations.md) per tal d'oferir experiències personalitzades als vostres clients.




[!INCLUDE[footer-include](../includes/footer-banner.md)]