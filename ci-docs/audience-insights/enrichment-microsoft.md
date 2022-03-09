---
title: Enriquir els perfils de client amb dades de Microsoft
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
ms.openlocfilehash: 12704ec46832e9463e6115db6c4df64e72bf4f97
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/02/2022
ms.locfileid: "8372661"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Enriquir perfils de clients amb afinitats i quota de veu (previsualització)

Utilitzeu les dades propietàries de Microsoft per enriquir les dades dels clients amb afinitats de marca, afinitats d'interessos i quota de veu (SoV). Aquestes afinitats i SoV es basen en dades de persones amb dades demogràfiques similars als teus clients. Aquesta informació t'ajuda a entendre millor i segmentar els teus clients en funció de les seves afinitats o SoV a marques i interessos específics.

A les conclusions del públic, aneu a **Dades** > **Enriquiment** per [configurar i visualitzar els enriquiments](enrichment-hub.md).

Per configurar les afinitats de marca i l'enriquiment del SoV, aneu a la **pestanya Descobreix** i seleccioneu **Enriqueix les meves dades** a la **peça Marques**.

Per configurar les afinitats d'interessos i l'enriquiment del SoV, aneu a la **pestanya Descobreix** i seleccioneu **Enriqueix les meves dades** a la **peça Interessos**.

   > [!div class="mx-imgBorder"]
   > ![Peces de marques i interessos.](media/BrandsInterest-tile-Hub.png "Peces de marques i interessos")

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

Per seleccionar un país o regió, obriu **Enriquiment de marques** o **Enriquiment d'interessos** i seleccioneu **Canvia** al costat de **País/Regió**. A la subfinestra **Configuració de país o regió**, trieu una opció i seleccioneu **Aplica**.

### <a name="implications-related-to-country-selection"></a>Implicacions relacionades amb la selecció de països o regions

- Quan [trieu les vostres pròpies marques](#define-your-brands-or-interests), el sistema ofereix suggeriments basats en el país o regió seleccionat.

- A l'hora de [triar un sector](#define-your-brands-or-interests), obtindreu les marques o els interessos més rellevants en funció del país o regió seleccionat.

- En [enriquir els perfils](#refresh-enrichment), enriquirem tots els perfils de clients per als quals obtenim dades per a les marques i els interessos seleccionats, incloent-hi els perfils que no es troben al país o regió seleccionats. Per exemple, si heu seleccionat Alemanya, enriquirem els perfils ubicats als Estats Units si tenim dades disponibles per a les marques i els interessos seleccionats als EUA.

## <a name="configure-enrichment"></a>Configurar l'enriquiment

Una experiència guiada us ajuda a través de la configuració dels enriquiments. 

### <a name="define-your-brands-or-interests"></a>Definir les marques o els interessos

Trieu fins a cinc marques o interessos utilitzant una opció o totes dues:

- **Sector**: seleccioneu el sector a la llista desplegable i trieu entre les marques o els interessos principals del sector.
- **Trieu la vostra pròpia**: introduïu una marca o un interès rellevant per a la vostra organització i trieu entre els suggeriments de coincidència. Si no enumerem una marca o un interès que cerqueu, envieu-nos els vostres comentaris mitjançant l'enllaç **Suggereix**.

### <a name="review-enrichment-preferences"></a>Revisar les preferències de l'enriquiment

Reviseu les vostres preferències d'enriquiment per defecte i actualitzeu-les segons calgui.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla de la finestra de preferències d'enriquiment.":::

### <a name="select-entity-to-enrich"></a>Seleccionar l'entitat que voleu enriquir

Seleccioneu **Entitat** enriquida i trieu el conjunt de dades que voleu enriquir amb les dades de Microsoft. Podeu seleccionar l'entitat Client per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.

### <a name="map-your-fields"></a>Assignació dels camps

Assigneu els camps de l'entitat de client unificada per definir el segment demogràfic que voleu que el sistema utilitzi per enriquir les dades de client. Assigneu els atributs País/Regió i, com a mínim, Data de naixement o Gènere. A més, heu d'assignar almenys un entre Ciutat (i Província o estat) o Codi postal. Seleccioneu **Edita** per definir l'assignació dels camps i seleccioneu **Aplica** quan acabeu. Seleccioneu **Desa** per completar l'assignació de camps.

S'admeten els valors i els formats que es mostren a continuació; els valors no distingeixen entre majúscules i minúscules:

- **Data de naixement**: us recomanem que la data de naixement es converteixi al tipus Data/Hora durant la ingestió de dades. Com a alternativa, pot ser una cadena en format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" or "aaaa-MM-ddTHH:mm:ss".
- **Gènere**: masculí, femení, desconegut.
- **Codi postal**: codis postals de cinc dígits per als Estats Units, codi postal estàndard a tot el món.
- **Ciutat**: nom de la ciutat en anglès.
- **Província o estat**: abreviatura de dues lletres per als Estats Units i Canadà. Abreviatura de dues o tres lletres per a Austràlia. No s'aplica per a França, Alemanya o el Regne Unit.
- **País o regió**:

  - US: Estats Units d'Amèrica, Estats Units, EUA
  - CA: Canadà, CA
  - GB: Regne Unit, UK, Gran Bretanya, GB, Regne Unit de la Gran Bretanya i Irlanda del Nord, Regne Unit de la Gran Bretanya
  - AU: Austràlia, AU, Commonwealth d'Austràlia
  - FR: França, FR, República Francesa
  - DE: Alemanya, Alemany, Deutschland, Allemagne, DE, República Federal d'Alemanya, República d'Alemanya

## <a name="review-and-name-the-enrichment"></a>Revisar i donar nom a l'enriquiment

Finalment, podeu revisar la informació i proporcionar un nom per a l'enriquiment.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pàgina de revisió i nom.":::

## <a name="refresh-enrichment"></a>Actualitzar l'enriquiment

Executeu l'enriquiment un cop hàgiu configurat les marques, els interessos i l'assignació de camps de les dades demogràfiques. Per iniciar el procés, seleccioneu **Executa** a la pàgina de configuració de l'interès o la marca. A més, podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una actualització planificada.

En funció de la mida de les dades dels clients, l'execució d'enriquiment pot trigar uns quants minuts a completar-se.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Després de l'execució del procés d'enriquiment, aneu a **Els meus enriquiments** per revisar el nombre total de clients enriquits i un desglossament de les marques o els interessos dels perfils de clients enriquits.

:::image type="content" source="media/my-enrichments.png" alt-text="Visualització prèvia dels resultats després d'executar el procés d'enriquiment.":::

Trobareu un gràfic amb el nombre de perfils de clients enriquits al llarg del temps i les visualitzacions prèvies de les entitats enriquides. Reviseu les dades enriquides seleccionant Mostra'n més **als gràfics Nivell** d'afinitat **o**"Compartir de veu **".** Les dades enriquides per a marques van a les **entitats BrandAffinityFromMicrosoft** i **BrandShareOfVoiceFromMicrosoft**. Les dades per interessos es troba a les **entitats InterestAffinityFromMicrosoft** i **InterestShareOfVoiceFromMicrosoft**. També trobareu aquestes entitats enumerades al grup **Enriquiment** a **Dades** > **Entitats**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Veure dades d'enriquiment a la targeta del client

El SoV de marca i interès també es pot veure a les targetes de client individuals. Aneu a **Clients** i seleccioneu un perfil de client. A la targeta de client, trobareu gràfics per a la marca o el SoV d'interès basats en persones del perfil demogràfic d'aquest client.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Targeta del client amb dades enriquides.":::

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
