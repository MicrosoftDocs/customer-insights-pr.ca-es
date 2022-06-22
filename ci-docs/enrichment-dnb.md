---
title: Enriquiment de perfils d'empresa amb Dun &Bradstreet
description: Informació general sobre l'enriquiment de tercers dun &bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953879"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Enriquiment de perfils d'empresa amb Dun &Bradstreet (Preview)

Dun &Bradstreet proporciona dades comercials, anàlisis i estadístiques per a empreses. Permet enriquir les dades als clients amb perfils de clients unificats per a les empreses. Els enriquiments inclouen atributs com el número DUNS, la mida de l'empresa, la ubicació, la indústria i molt més.

## <a name="prerequisites"></a>Requisits previs

- Una llicència dun & Bradstreet [activa](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Perfils de clients unificats](customer-profiles.md) per a empreses.
- S'ha creat un projecte [Dun & Bradstreet](#set-up-your-dun--bradstreet-project).
- Un administrador configura [una connexió](connections.md)[Dun &Bradstreet](#configure-a-connection-for-dun--bradstreet).

## <a name="set-up-your-dun--bradstreet-project"></a>Configura el teu projecte Dun &Bradstreet

Com a usuari amb llicència de Dun &Bradstreet, podeu configurar un projecte a [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Inicieu la sessió a [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Per recuperar les credencials, [restaureu la contrasenya](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Baixeu [el nostre fitxer](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) de plantilla csv que s'utilitzarà per assignar els camps del Customer Insights als camps Dun &Bradstreet corresponents.

1. Pengeu el fitxer al **pas Carrega dades** de l'experiència de creació del projecte Dun &Bradstreet.

1. Seleccioneu els punts horitzontals sota la font **rellevant** del projecte Dun &Bradstreet acabat de crear per veure les opcions disponibles.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de pantalla de punts en un projecte Dun &Bradstreet.":::

1. Trieu **Obtén els detalls** de s3. Emmagatzemeu aquesta informació en un lloc segur. La necessitareu per [configurar la connexió per a l'enriquiment](#configure-a-connection-for-dun--bradstreet) a Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de pantalla de selecció d'informació s3 en un projecte Dun &Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configura una connexió per a Dun &Bradstreet

Heu de ser administrador [del](permissions.md#admin) Customer Insights i tenir les credencials de Dun &Bradstreet Connect.

1. Seleccioneu **Afegeix una connexió** quan configureu un enriquiment o aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la peça Dun &Bradstreet.

1. Introduïu un nom per a la connexió.

1. Proporcioneu credencials vàlides de Dun & Bradstreet i detalls *del projecte Dun & Bradstreet Regió, Camí de carpeta Drop i Nom* de la carpeta Drop. Aquesta [informació](#set-up-your-dun--bradstreet-project) prové del projecte Dun &Bradstreet.

1. Reviseu i proporcioneu el vostre consentiment per a la [Privadesa de les dades i conformitat](#data-privacy-and-compliance) seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet pàgina de configuració de la connexió.":::

### <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights transmetre dades a Dun & Bradstreet, permeteu la transferència de dades fora del límit de compliment de Dynamics 365 Customer Insights, incloses dades potencialment sensibles, com ara dades personals. Microsoft transferirà aquestes dades a les vostres instruccions, però sou responsable d'assegurar-vos que Dun &Bradstreet compleixi amb qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

## <a name="supported-countries-or-regions"></a>Països o regions admesos

Actualment admetem les següents opcions de país o regió: Canadà (anglès) o Estats Units (anglès).

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a les dades **de l'empresa per a la** peça Dun &Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de pantalla de la rajola Dun &Bradstreet.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió i confirmeu-la. Poseu-vos en contacte amb un administrador si no n'hi ha cap disponible.

1. Seleccioneu **Següent**.

1. Seleccioneu el **conjunt** de dades del client i trieu el perfil o segment que voleu enriquir amb les dades de l'empresa de Dun &Bradstreet. L'entitat *Client* enriqueix tots els vostres perfils de clients, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Definiu quin tipus de camps dels perfils unificats s'utilitzaran per fer coincidir les dades de l'empresa de Dun &Bradstreet. Cal com a mínim un dels camps **Nom i adreça**, **Telèfon** o **Correu electrònic**.

1. Seleccioneu **Següent**

1. Assigna els teus camps a les dades de l'empresa de Dun &Bradstreet. Cal **un número** DUNS o **un nom de l'empresa** i **dels camps país**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Subfinestra dun & Bradstreet field-mapping.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un **nom** per a l'enriquiment i el nom **de l'entitat** Sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o a prop per tornar a la **pàgina Enriquiments**.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
