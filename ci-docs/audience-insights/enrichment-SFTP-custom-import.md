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
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304638"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquir els perfils de client amb dades personalitzades (versió preliminar)

La importació personalitzada del protocol de transferència segura de fitxers (SFTP) us permet importar dades que no han de passar pel procés d'unificació de dades. Es tracta d'un mètode flexible, segur i fàcil d'incorporar les vostres dades. La importació personalitzada d'SFTP es pot utilitzar combinada amb [l'exportació d'SFTP](export-sftp.md), que us permet exportar les dades del perfil del client necessàries per a l'enriquiment. A continuació, les dades es poden processar i enriquir, i la importació personalitzada de SFTP es pot utilitzar per recuperar les dades enriquides de les conclusions del públic del Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisits previs

Per poder configurar la importació personalitzada d'SFTP, s'han de complir els requisits previs següents:

- Teniu el nom de fitxer i la ubicació (camí) del fitxer que s'ha d'importar a l'amfitrió SFTP.
- Hi ha un fitxer *model.json* que especifica [l'esquema del Model de dades comú](/common-data-model/) per a les dades que s'han d'importar. Aquest fitxer s'ha de trobar al mateix directori que el fitxer que s'importarà.
- Un administrador ja ha configurat una connexió SFTP *o* teniu permisos d'[administrador](permissions.md#administrator). Necessitareu les credencials d'usuari, l'adreça URL i el número de port de la ubicació SFTP des d'on voleu importar les dades.


## <a name="configure-the-import"></a>Configurar la importació

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. A la **peça Importació personalitzada SFTP**, seleccioneu **Enriqueix les meves dades** i, a continuació, **Comença**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Peça de la importació personalitzada d'SFTP.":::

1. Seleccioneu una [connexió](connections.md) a la llista desplegable. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible. Si sou administrador, podeu crear una connexió seleccionant **Afegeix una connexió** i triant **Importació personalitzada SFTP** a la llista desplegable.

1. Seleccioneu **Connecta't a la importació personalitzada** per confirmar la connexió seleccionada.

1.  Seleccioneu **Següent** i introduïu el **camí** i el **nom de fitxer** del fitxer de dades que voleu importar.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de pantalla quan introduïu la ubicació de les dades.":::

1. Seleccioneu **Següent** i proporcioneu un nom per a l'enriquiment i un nom per a l'entitat de sortida. 

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurar la connexió per a la importació personalitzada de l'SFTP 

Heu de ser administrador per configurar les connexions. Seleccioneu **Afegeix una connexió** en configurar un enriquiment *o* aneu a **Administració** > **Connexions** i seleccioneu **Configuració** a la peça Importació personalitzada.

1. Introduïu un nom per a la connexió al quadre **Nom de visualització**.

1. Introduïu un nom d'usuari, una contrasenya i una adreça URL d'amfitrió vàlids per al servidor SFTP on resideixin les dades que s'han d'importar.

1. Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**.

1. Seleccioneu **Verifica** per validar la configuració.

1. Si la verificació s'ha completat, la connexió es pot desar seleccionant **Desa**.

   > [!div class="mx-imgBorder"]
   > ![Pàgina de configuració de connexió a Experian](media/enrichment-SFTP-connection.png "Pàgina de configuració de connexió a Experian")


## <a name="defining-field-mappings"></a>Definició de les assignacions de camps 

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

Construïu a partir de les dades de clients enriquits. Creeu [segments](segments.md) i [mesures](measures.md) i [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
