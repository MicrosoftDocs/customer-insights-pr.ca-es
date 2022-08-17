---
title: Enriquir els perfils d'empresa amb Dun & Bradstreet (preview)
description: Informació general sobre l'enriquiment de tercers de Dun & Bradstreet.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237892"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Enriquir els perfils d'empresa amb Dun & Bradstreet (preview)

Dun & Bradstreet proporciona dades comercials, anàlisis i estadístiques per a les empreses. Permet enriquir les dades als clients amb perfils de clients unificats per a les empreses. Els enriquiments inclouen atributs com el número DUNS, la mida de l'empresa, la ubicació, la indústria i molt més.

## <a name="prerequisites"></a>Requisits previs

- Una llicència de Dun & Bradstreet [activa](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Perfils de clients unificats](customer-profiles.md) per a empreses.
- Es posa en marxa un projecte [Dun & Bradstreet](#set-up-your-dun--bradstreet-project).
- Un administrador configura una [connexió](connections.md)[Dun & Bradstreet](#configure-a-connection-for-dun--bradstreet).

## <a name="set-up-your-dun--bradstreet-project"></a>Configura el teu projecte Dun & Bradstreet

Com a usuari amb llicència de Dun & Bradstreet, podeu configurar un projecte a [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Inicieu sessió a [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Per recuperar les credencials, [restaureu la contrasenya](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Baixeu el [nostre fitxer](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) de plantilla CSV que s'utilitzarà per assignar els camps del Customer Insights als camps Dun i Bradstreet corresponents.

1. Carregueu el fitxer al **pas De càrrega de dades** de l'experiència de creació del projecte Dun & Bradstreet.

1. Seleccioneu els punts horitzontals sota la font **corresponent** al projecte Dun & Bradstreet acabat de crear per veure les opcions disponibles.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de pantalla de punts en un projecte de Dun & Bradstreet.":::

1. Trieu **Obtén els detalls** de S3. Emmagatzemeu aquesta informació en un lloc segur. El necessitareu per configurar la connexió per a [l'enriquiment](#configure-a-connection-for-dun--bradstreet) al Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de pantalla de la selecció d'informació s3 en un projecte de Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurar una connexió per a Dun & Bradstreet

Heu de ser [administrador](permissions.md#admin) al Customer Insights i tenir les credencials de Dun & Bradstreet Connect.

1. Seleccioneu **Afegeix connexió** en configurar un enriquiment o aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la peça Dun & Bradstreet.

1. Introduïu un nom per a la connexió.

1. Proporcioneu credencials vàlides de Dun & Bradstreet i detalls del *projecte Dun & Bradstreet Regió, Ruta de la carpeta Desplegable i Nom* de la carpeta Drop. Obteniu [aquesta informació](#set-up-your-dun--bradstreet-project) del projecte Dun & Bradstreet.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Pàgina de configuració de la connexió Dun & Bradstreet.":::

## <a name="supported-countries-or-regions"></a>Països o regions admesos

Actualment admetem les següents opcions de país o regió: Canadà (anglès) o Estats Units (anglès).

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a les dades **de l'empresa** per a la rajola Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de pantalla de la rajola Dun & Bradstreet.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió i confirmeu. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Seleccioneu **Següent**.

1. Seleccioneu el conjunt **de dades de clients i trieu el perfil o segment que voleu enriquir amb les dades de l'empresa** de Dun & Bradstreet. L'entitat *Client* enriqueix tots els teus perfils de client, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Definiu quin tipus de camps dels vostres perfils unificats voleu utilitzar per fer coincidir les dades de l'empresa de Dun & Bradstreet. Cal com a mínim un dels camps **Nom i adreça**, **Telèfon** o **Correu electrònic**.

1. Seleccioneu **Següent**

1. Assigneu els vostres camps a les dades de l'empresa de Dun & Bradstreet. Es **requereix el número DUNS o** els **camps Nom de l'empresa** i **País**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun i Bradstreet panell de cartografia de camp.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un **nom** per a l'enriquiment i el nom de l'entitat **de sortida**.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o tancar per tornar a la **pàgina Enriquiments**.

## <a name="view-enrichment-results"></a>Veure resultats d'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
