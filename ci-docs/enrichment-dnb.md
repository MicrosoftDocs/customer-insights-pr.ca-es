---
title: Enriquiment de perfils d'empresa amb Dun &Bradstreet
description: Informació general sobre l'enriquiment de tercers dun &bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755388"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Enriquiment de perfils d'empresa amb Dun &Bradstreet (Preview)

Dun &Bradstreet proporciona dades comercials, anàlisis i estadístiques per a empreses. Permet enriquir les dades als clients amb perfils de clients unificats per a les empreses. Els enriquiments inclouen atributs com el número DUNS, la mida de l'empresa, la ubicació, la indústria i molt més.

## <a name="prerequisites"></a>Requisits previs

Per configurar un enriquiment Dun &Bradstreet, s'han de complir els requisits previs següents:

- Teniu una llicència Dun &Bradstreet [activa](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- Tenir [perfils de clients unificats](customer-profiles.md) per a empreses.
- Un administrador configura una connexió [Dun &Bradstreet](connections.md). Podeu crear-lo si teniu [permisos d'administrador](permissions.md#admin) i les credencials de Dun &Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>Configurant el teu projecte Dun &Bradstreet

Com a usuari amb llicència de Dun &Bradstreet, podeu configurar un projecte a [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Inicieu la sessió a [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Per recuperar les credencials, [restaureu la contrasenya](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Baixeu [el nostre fitxer](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) de plantilla csv que s'utilitzarà per assignar els camps del Customer Insights als camps Dun &Bradstreet corresponents.

1. Pengeu el fitxer al **pas Carrega dades** de l'experiència de creació del projecte Dun &Bradstreet.

1. Seleccioneu els punts horitzontals sota la font **rellevant** del projecte Dun &Bradstreet acabat de crear per veure les opcions disponibles.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de pantalla de punts en un projecte Dun &Bradstreet.":::

1. Trieu **Obtén els detalls** de s3. Emmagatzemeu aquesta informació en un lloc segur. La necessitareu per [configurar la connexió per a l'enriquiment](#configure-a-connection-for-dun--bradstreet) a Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de pantalla de selecció d'informació s3 en un projecte Dun &Bradstreet.":::

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment**.

1. Seleccioneu **Enriqueix les meves dades** a la peça Dun &Bradstreet i seleccioneu **Comença**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de pantalla de la rajola Dun &Bradstreet.":::

1. Seleccioneu una [connexió](connections.md) a la llista desplegable. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible. Si sou administrador, podeu crear una connexió. Seleccioneu **Afegeix connexió** i trieu **Dun &Bradstreet**.

1. Seleccioneu **Connecta't a Dun &Bradstreet** per confirmar la connexió.

1. Seleccioneu **A continuació** i trieu el **conjunt** de dades del client que voleu enriquir amb les dades de l'empresa de Dun &Bradstreet. Podeu seleccionar l'entitat **Client** per enriquir tots els vostres perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client unificats continguts en aquest segment.

1. Seleccioneu **Següent** i definiu quins camps dels perfils unificats s'utilitzen per cercar dades d'empresa coincidents de Dun &Bradstreet. Cal **un número** DUNS o **un nom de l'empresa** i **dels camps país**. El camp de país admet [codis](https://www.iso.org/iso-3166-country-codes.html) de país de dues o tres lletres, el nom del país en anglès, el nom del país en llengua materna i el prefix del telèfon. Algunes variants de país comunes inclouen:

- Estats Units: Estats Units d'Amèrica, Estats Units, EUA, Amèrica.
- CA: Canadà.
- GB: Regne Unit, Regne Unit, Gran Bretanya, GB, Regne Unit de La Gran Bretanya i Irlanda del Nord, Regne Unit de la Gran Bretanya.
- Austràlia, Mancomunitat d'Austràlia.
- Fr: França, República Francesa.
- Alemanya, Alemanya, Alemanya, Alemanya, Alemanya, Allemagne, República Federal d'Alemanya, República d'Alemanya.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Subfinestra dun & Bradstreet field-mapping.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un nom per a l'enriquiment i seleccioneu **Desa l'enriquiment** després de revisar les vostres opcions.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configura una connexió per a Dun &Bradstreet

Heu de ser administrador per configurar les connexions. Seleccioneu **Afegeix una connexió** quan configureu un enriquiment *o* aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la peça Dun &Bradstreet.

1. Seleccioneu **Introducció**.

1. Introduïu un nom per a la connexió al quadre **Nom de visualització**.

1. Proporcioneu credencials vàlides de Dun & Bradstreet i detalls *del projecte Dun & Bradstreet Regió, Camí de carpeta Drop i Nom* de la carpeta Drop. Aquesta [informació](#setting-up-your-dun--bradstreet-project) prové del projecte Dun &Bradstreet.

1. Reviseu i proporcioneu el vostre consentiment per a la **Privadesa de les dades i conformitat** seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració.

1. Després de completar la verificació, seleccioneu **Desa**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet pàgina de configuració de la connexió.":::

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Després d'actualitzar l'enriquiment, podeu revisar les dades d'empresa enriquides recentment a [Els meus enriquiments](enrichment-hub.md). Podeu trobar-hi l'hora de l'última actualització i el nombre de perfils enriquits.

Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights transmetre dades a Dun & Bradstreet, permeteu la transferència de dades fora del límit de compliment de Dynamics 365 Customer Insights, incloses dades potencialment sensibles, com ara dades personals. Microsoft transferirà aquestes dades a les vostres instruccions, però sou responsable d'assegurar-vos que Dun &Bradstreet compleixi amb qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

[!INCLUDE[footer-include](includes/footer-banner.md)]
