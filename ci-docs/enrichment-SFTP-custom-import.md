---
title: Enriquir perfils de clients amb importació personalitzada SFTP (visualització prèvia)
description: Informació general sobre l'enriquiment amb la importació personalitzada d'SFTP.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237754"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Enriquir perfils de clients amb importació personalitzada SFTP (visualització prèvia)

La importació personalitzada del protocol de transferència segura de fitxers (SFTP) us permet importar dades que no han de passar pel procés d'unificació de dades. Es tracta d'un mètode flexible, segur i fàcil d'incorporar les vostres dades. La importació personalitzada d'SFTP es pot utilitzar combinada amb [l'exportació d'SFTP](export-sftp.md), que us permet exportar les dades del perfil del client necessàries per a l'enriquiment. Les dades es poden processar i enriquir, i la importació personalitzada SFTP es pot utilitzar per tornar les dades enriquides a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisits previs

- Es coneix el nom del fitxer i la ubicació (ruta) del fitxer que s'importarà a l'amfitrió SFTP.

- Hi *ha disponible un fitxer model.json* que especifica l'esquema del Common Data Model per a les dades que s'han d'importar. Aquest fitxer s'ha de trobar al mateix directori que el fitxer que s'importarà.

- Es [configura una connexió](connections.md) SFTP [...](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Exemple d'esquema de fitxer

El directori que conté el fitxer que s'importarà al servidor SFTP també ha d'incloure un fitxer *model.json*. En aquest fitxer es defineix l'esquema que s'utilitzarà per importar les dades. L'esquema ha d'utilitzar el [Common Data Model](/common-data-model/) per especificar l'assignació de camps. Tot seguit es mostra un exemple senzill de fitxer model.json:

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurar la connexió per a la importació personalitzada de l'SFTP

Heu de ser [administrador](permissions.md#admin) al Customer Insights i tenir les credencials d'usuari, l'URL i el número de port de la ubicació SFTP des d'on voleu importar dades.

1. Seleccioneu **Afegeix connexió** en configurar un enriquiment o aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la peça Importació personalitzada.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Pàgina de configuració de connexió d'importació personalitzada.":::

1. Introduïu un nom per a la connexió.

1. Introduïu un nom d'usuari, una contrasenya i una adreça URL d'amfitrió vàlids per al servidor SFTP on resideixin les dades que s'han d'importar.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

## <a name="configure-the-import"></a>Configurar la importació

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la peça d'importació **personalitzada** SFTP.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Peça de la importació personalitzada d'SFTP.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Seleccioneu el **conjunt** de dades de clients i trieu el perfil o segment que voleu enriquir. L'entitat *Client* enriqueix tots els teus perfils de client, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Seleccioneu **Següent**.

1. Introduïu el **camí** i **el nom** del fitxer del fitxer de dades que voleu importar.

1. Seleccioneu **Següent**.

1. Proporcioneu un **nom** per a l'enriquiment i el nom de l'entitat **de sortida**.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o tancar per tornar a la **pàgina Enriquiments**.

## <a name="view-enrichment-results"></a>Veure resultats d'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
