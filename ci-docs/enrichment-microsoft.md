---
title: Enriquir perfils de clients amb marques i dades d'interessos de Microsoft
description: Utilitzeu dades propietàries de Microsoft per enriquir les vostres dades de clients amb afinitats i compartir la veu.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953753"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Enriquir perfils de clients amb afinitats i quota de veu (previsualització)

Utilitzeu les dades propietàries de Microsoft per enriquir les dades dels clients amb afinitats de marca, afinitats d'interessos i quota de veu (SoV). Aquestes afinitats i SoV es basen en dades de persones amb dades demogràfiques similars als teus clients. Aquesta informació t'ajuda a entendre millor i segmentar els teus clients en funció de les seves afinitats o SoV a marques i interessos específics.

## <a name="how-we-determine-affinities-and-sov"></a>Com determinem les afinitats i el SoV

Utilitzem les dades de cerca en línia de Microsoft per trobar afinitats i SoV per a marques i interessos en diversos segments demogràfics (definits per edat, sexe o ubicació). El volum de cerca en línia d'una marca o interès constitueix la base per determinar l'afinitat o el SoV. No obstant això, cadascuna proporciona una perspectiva diferent per entendre els seus clients.

- L'afinitat és una comparació entre segments demogràfics. Podeu utilitzar aquesta informació per identificar segments demogràfics que tenen més afinitat per una marca o un interès determinats, en comparació amb altres segments.

- La quota de veu és una comparació entre les vostres marques o interessos seleccionats. Podeu utilitzar aquesta informació per identificar quina marca o interès té la major quota de veu d'un segment demogràfic determinat, en comparació amb altres marques o interessos que heu seleccionat.

## <a name="affinity-level-and-score"></a>Nivell d'afinitat i puntuació

A cada perfil de client enriquit, proporcionem dos valors relacionats: el nivell d'afinitat i la puntuació d'afinitat. Aquests valors us ajuden a determinar la robustesa d'afinitat del segment demogràfic d'aquest perfil, d'una marca o interès, en comparació amb altres segments demogràfics.

El *nivell d'afinitat* consta de quatre nivells i una *puntuació d'afinitat* es calcula a una escala de 100 punts que s'assigna als nivells d'afinitat.

|Nivell d'afinitat |Puntuació d'afinitat  |
|---------|---------|
|Molt alta     | 85-100       |
|Alta     | 70-84        |
|Mitjà     | 35-69        |
|Baixa     | 1-34        |

Depenent de la granularitat que voleu per mesurar l'afinitat, podeu utilitzar el nivell d'afinitat o la puntuació. La puntuació d'afinitat us proporciona un control més precís.

## <a name="share-of-voice-sov"></a>Quota de veu (SoV)

Calculem sov en una escala de 100 punts. El SoV total en totes les marques o interessos per a cada perfil de client enriquit suma 100. A diferència de les afinitats, SoV és relatiu a les marques i interessos que seleccioneu. Per exemple, els valors de SoV per a 'Microsoft' poden ser diferents si les marques seleccionades són ('Microsoft', 'GitHub') versus ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Països o regions admesos

Actualment, admeten a les següents opcions de país o regió: Austràlia, Canadà (anglès), França, Alemanya, Regne Unit o Estats Units (anglès).

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

   - Per configurar les afinitats de marca i l'enriquiment del SoV, seleccioneu **Enriqueix les meves dades** a la **peça Marques**.

   - Per configurar les afinitats d'interessos i l'enriquiment del SoV, seleccioneu **Enriqueix les meves dades** a la **peça Interessos**.

   > [!div class="mx-imgBorder"]
   > ![Peces de marques i interessos.](media/BrandsInterest-tile-Hub.png "Peces de marques i interessos")

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Per canviar el país o la regió, selecciona **Canvia** al costat d'Un **país o una regió**. A la **subfinestra** Configuració país o regió, trieu un [país o regió](#supported-countriesregions) compatible i seleccioneu **Aplica**.

   > [!NOTE]
   > Quan trieu les vostres pròpies marques, el sistema ofereix suggeriments basats en el país o regió seleccionat. A l'hora de triar un sector, obtindreu les marques o els interessos més rellevants en funció del país o regió seleccionat.

1. Trieu fins a cinc marques o interessos utilitzant una opció o totes dues:

   - **Sector**: seleccioneu el sector a la llista desplegable i trieu entre les marques o els interessos principals del sector.
   - **Trieu la vostra pròpia**: introduïu una marca o un interès rellevant per a la vostra organització i trieu entre els suggeriments de coincidència. Si no enumerem una marca o un interès que cerqueu, envieu-nos els vostres comentaris mitjançant l'enllaç **Suggereix**.

1. Seleccioneu **Endavant** i reviseu les preferències d'enriquiment per defecte i actualitzeu-les segons calgui.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla de la finestra de preferències d'enriquiment.":::

1. Seleccioneu **Següent**.

1. Seleccioneu el **conjunt de dades del client** i trieu el perfil o el segment que voleu enriquir amb les dades de Microsoft. L'entitat *Client* enriqueix tots els vostres perfils de clients, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Seleccioneu **Següent**.

1. Assigneu els camps de l'entitat de client unificada a les dades de Microsoft.

   > [!NOTE]
   > Es requereixen com a mínim atributs de data de naixement o de gènere. Es requereix un país o regió i, com a mínim, ciutat (i estat/província) o codi postal. Recomanem que la data de naixement es converteixi al tipus DateTime durant la ingestió de dades. Com a alternativa, pot ser una cadena en format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" or "aaaa-MM-ddTHH:mm:ss".

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un nom per a l'enriquiment. El **nom** de l'entitat Sortida se selecciona automàticament.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pàgina de revisió i nom.":::

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o a prop per tornar a la **pàgina Enriquiments**.

   En enriquir els perfils, enriquirem tots els perfils de clients per als quals obtenim dades per a les marques i els interessos seleccionats, incloent-hi els perfils que no es troben al país o regió seleccionats. Per exemple, si heu seleccionat Alemanya, enriquirem els perfils ubicats als Estats Units si tenim dades disponibles per a les marques i els interessos seleccionats als EUA.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Visualització prèvia dels resultats després d'executar el procés d'enriquiment.":::

Els resultats inclouen **el nivell d'afinitat** o **la quota dels gràfics de veu**.

Les entitats creades a partir dels enriquiments s'enumeren al grup d'enriquiment **a** **Entitats de** > **dades**. Les dades enriquides per a marques van a les **entitats BrandAffinityFromMicrosoft** i **BrandShareOfVoiceFromMicrosoft**. Les dades per interessos es troba a les **entitats InterestAffinityFromMicrosoft** i **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Veure dades d'enriquiment a la targeta del client

El SoV de marca i interès també es pot veure a les targetes de client individuals. Aneu a **Clients** i seleccioneu un perfil de client. A la targeta de client, trobareu gràfics per a la marca o el SoV d'interès basats en persones del perfil demogràfic d'aquest client.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Targeta del client amb dades enriquides.":::

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
