---
title: Enriquir perfils de clients amb importació personalitzada SFTP (vista prèvia)
description: Informació general sobre l'enriquiment amb la importació personalitzada d'SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 88fc366ab9478c3b67034af794e237ff4573da7c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082318"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Enriquir perfils de clients amb importació personalitzada SFTP (vista prèvia)

La importació personalitzada del protocol de transferència segura de fitxers (SFTP) us permet importar dades que no han de passar pel procés d'unificació de dades. Es tracta d'un mètode flexible, segur i fàcil d'incorporar les vostres dades. La importació personalitzada d'SFTP es pot utilitzar combinada amb [l'exportació d'SFTP](export-sftp.md), que us permet exportar les dades del perfil del client necessàries per a l'enriquiment. Les dades es poden processar i enriquir, i la importació personalitzada SFTP es pot utilitzar per tornar les dades enriquides a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisits previs

- Es coneix el nom del fitxer i la ubicació (camí) del fitxer que s'importarà a l'amfitrió SFTP.

- Hi *ha disponible un fitxer model.json* que especifica l'esquema del model de dades comú per a les dades que s'importaran. Aquest fitxer s'ha de trobar al mateix directori que el fitxer que s'importarà.

- S'ha configurat una connexió [SFTP](connections.md) [...](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Exemple d'esquema de fitxers

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

Heu de ser administrador [del Customer Insights i tenir les credencials d'usuari](permissions.md#admin), l'URL i el número de port de la ubicació SFTP des d'on voleu importar dades.

1. Seleccioneu **Afegeix una connexió** en configurar un enriquiment o aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la peça Importa personalitzada.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Pàgina de configuració de la connexió d'importació personalitzada.":::

1. Introduïu un nom per a la connexió.

1. Introduïu un nom d'usuari, una contrasenya i una adreça URL d'amfitrió vàlids per al servidor SFTP on resideixin les dades que s'han d'importar.

1. Reviseu i proporcioneu el vostre consentiment per a la [Privadesa de les dades i conformitat](#data-privacy-and-compliance) seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

### <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights transmetre dades mitjançant importació personalitzada, permeteu la transferència de dades fora del límit Dynamics 365 Customer Insights de compliment de, incloses dades potencialment sensibles, com ara dades personals. Microsoft transferirà aquestes dades a les vostres instruccions, però sou responsable d'assegurar-vos que les dades compleixin les obligacions de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

## <a name="configure-the-import"></a>Configurar la importació

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la peça d'importació **personalitzada** SFTP.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Peça de la importació personalitzada d'SFTP.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió. Poseu-vos en contacte amb un administrador si no n'hi ha cap disponible.

1. Seleccioneu el **conjunt de dades del client** i trieu el perfil o el segment que voleu enriquir. L'entitat *Client* enriqueix tots els vostres perfils de clients, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Seleccioneu **Següent**.

1. Introduïu el **camí** i **el nom del fitxer** de dades que voleu importar.

1. Seleccioneu **Següent**.

1. Proporcioneu un **nom** per a l'enriquiment i el nom **de l'entitat** Sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o a prop per tornar a la **pàgina Enriquiments**.

## <a name="view-enrichment-results"></a>Veure resultats d'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
