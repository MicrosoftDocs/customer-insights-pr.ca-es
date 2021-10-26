---
title: Enriquir els perfils de client amb dades de Microsoft
description: Utilitzeu dades propietat de Microsoft per enriquir les dades dels vostres clients amb similituds de marca i d'interessos.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 51b150cbf5d9cfb3a5df42e680bcfa57ec5496cb
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617865"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Enriquir els perfils de client amb afinitats de marca i d'interès (visualització prèvia)

Utilitzeu dades propietat de Microsoft per enriquir les dades dels vostres clients amb similituds de marca i d'interessos. Aquestes afinitats es basen en les dades de persones en un grup demogràfic similar als vostres clients. Aquesta informació us ajudarà a conèixer i segmentar millor els vostres clients segons les seves afinitats amb determinades marques i interessos.

A les conclusions del públic, aneu a **Dades** > **Enriquiment** per [configurar i visualitzar els enriquiments](enrichment-hub.md).

Per configurar l'enriquiment d'afinitats de marques, aneu a la pestanya **Detecta** i seleccioneu **Enriqueix les meves dades** a la peça **Marques**.

Per configurar l'enriquiment d'afinitats d'interessos, aneu a la pestanya **Detecta** i seleccioneu **Enriqueix les meves dades** a la peça **Interessos**.

   > [!div class="mx-imgBorder"]
   > ![Peces de marques i interessos.](media/BrandsInterest-tile-Hub.png "Peces de marques i interessos")

## <a name="how-we-determine-affinities"></a>Com determinem les similituds

Utilitzem les dades de la cerca en línia de Microsoft per trobar similituds per a marques i interessos en diversos segments demogràfics (definits per edat, gènere o ubicació). El volum de cerques en línia d'una marca o un interès determina la quantitat d'afinitat d'un segment demogràfic, en comparació amb altres segments, que té a aquesta marca o interès.

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

Seleccioneu **Entitat enriquida** i trieu el conjunt de dades que voleu enriquir amb les dades de l'empresa des de Microsoft. Podeu seleccionar l'entitat Client per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.

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

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, última data de processament i tots els errors i advertiments associats amb la tasca.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Després de l'execució del procés d'enriquiment, aneu a **Els meus enriquiments** per revisar el nombre total de clients enriquits i un desglossament de les marques o els interessos dels perfils de clients enriquits.

:::image type="content" source="media/my-enrichments.png" alt-text="Visualització prèvia dels resultats després d'executar el procés d'enriquiment.":::

Reviseu les dades enriquides seleccionant **Visualitza les dades enriquides** al gràfic. Les dades enriquits per a les marques van a l'entitat **BrandAffinityFromMicrosoft**. Les dades d'interès es troben a l'entitat **InterestAffinityFromMicrosoft**. També trobareu aquestes entitats enumerades al grup **Enriquiment** a **Dades** > **Entitats**.

Veureu un gràfic amb el nombre de perfils de clients enriquits al llarg del temps i una versió preliminar de l'entitat enriquida. Seleccioneu **Mostra'n més** a la peça de versió preliminar per obrir l'entitat enriquida.

## <a name="see-enrichment-data-on-the-customer-card"></a>Veure dades d'enriquiment a la targeta del client

Les afinitats de marca i d'interès també es poden visualitzar en targetes de clients individuals. Aneu a **Clients** i seleccioneu un perfil de client. A la targeta del client, trobareu gràfics per a les marques o els interessos per als quals els usuaris del perfil demogràfic del client tenen afinitat.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Targeta del client amb dades enriquides.":::

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
