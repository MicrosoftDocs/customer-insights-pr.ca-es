---
title: Enriquir perfils de client amb el Microsoft Graph
description: Utilitzeu les dades propietàries del Microsoft Graph per enriquir les dades dels clients amb afinitats de marca i d'interès.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405135"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Enriquir els perfils de client amb afinitats de marca i d'interès (visualització prèvia)

Utilitzeu les dades propietàries del Microsoft Graph per enriquir les dades dels clients amb afinitats de marca i d'interès. Aquestes afinitats es determinen segons les dades de les persones amb dades demogràfiques similars als clients. Aquesta informació us ajudarà a conèixer i segmentar millor els vostres clients segons les seves afinitats amb determinades marques i interessos.

A les conclusions del públic, aneu a **Dades** > **Enriquiment** per [configurar i visualitzar els enriquiments](enrichment-hub.md).

Per configurar l'enriquiment d'afinitats de marques, aneu a la pestanya **Detecta** i seleccioneu **Enriqueix les meves dades** a la peça **Marques**.

Per configurar l'enriquiment d'afinitats d'interessos, aneu a la pestanya **Detecta** i seleccioneu **Enriqueix les meves dades** a la peça **Interessos**.

   > [!div class="mx-imgBorder"]
   > ![Peces de marques i interessos](media/BrandsInterest-tile-Hub.png "Peces de marques i interessos")

## <a name="about-microsoft-graph"></a>Quant al Microsoft Graph

Utilitzem dades de la cerca en línia del Microsoft Graph per cercar afinitats per a marques i interessos en diversos segments demogràfics (definits per edat, gènere o ubicació). El volum de cerques en línia d'una marca o un interès determina la quantitat d'afinitat d'un segment demogràfic, en comparació amb altres segments, que té a aquesta marca o interès.

[Més informació sobre el Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Puntuació d'afinitat i confiança

La **puntuació d'afinitat** es calcula en una escala de 100 punts, on 100 representa el segment que té la màxima afinitat per una marca o un interès.

La **confiança de l'afinitat** també es calcula en una escala de 100 punts. Indica el nivell de confiança del sistema que un segment tingui una afinitat per la marca o l'interès. El nivell de confiança es basa en la mida del segment i la granularitat del segment. La mida de la segment es determina per la quantitat de dades que tenim per a un segment determinat. La granularitat del segment es determina per la disponibilitat de diversos atributs (edat, gènere i ubicació) en un perfil.

No es normalitza la puntuació per al conjunt de dades. Per tant, pot ser que no veieu tots els valors d'afinitat possibles per al conjunt de dades. Per exemple, pot ser que no hi hagi cap perfil de client enriquit amb la puntuació d'afinitat de 100 a les dades. Això és possible si no hi ha cap client al segment demogràfic que hagi puntuat amb 100 una marca o un interès determinat.

> [!TIP]
> Quan [creeu segments](segments.md) mitjançant puntuacions d'afinitat, reviseu la distribució de les puntuacions d'afinitat del conjunt de dades abans de decidir els llindars de puntuació adients. Per exemple, un puntuació d'afinitat de 10 es pot considerar significativa en un conjunt de dades en què la puntuació d'afinitat més alta és de només 25 per a una marca o un interès determinat.

## <a name="supported-countriesregions"></a>Països o regions admesos

Actualment, admeten a les següents opcions de país o regió: Austràlia, Canadà (anglès), França, Alemanya, Regne Unit o Estats Units (anglès).

Per seleccionar un país o regió, obriu **Enriquiment de la marca** o **Enriquiment de l'interès** i seleccioneu **Canvia** al costat de **País o regió**. A la subfinestra **Configuració de país o regió**, trieu una opció i seleccioneu **Aplica**.

### <a name="implications-related-to-country-selection"></a>Implicacions relacionades amb la selecció de països o regions

- En [triar les vostres pròpies marques](#define-your-brands-or-interests), farem suggeriments en funció del país o regió que hàgiu seleccionat.

- En [triar un sector](#define-your-brands-or-interests), identificarem les marques o interessos més rellevants en funció del país/regió seleccionat.

- En [assignar els camps](#map-your-fields), si el camp País o regió no està assignat, farem servir les dades del Microsoft Graph del país o regió seleccionat per enriquir els perfils dels clients. També farem servir aquesta selecció per enriquir els perfils dels clients que no tenen dades de país o regió disponibles.

- En [enriquir perfils](#refresh-enrichment), enriquirem tots els perfils dels clients per als quals disposem de dades del Microsoft Graph per a les marques i els interessos seleccionats, incloent-hi els perfils que no es troben al país o regió seleccionat. Per exemple, si heu seleccionat Alemanya, s'enriquiran els perfils ubicats als Estats Units si tenim dades del Microsoft Graph disponibles per a les marques i els interessos seleccionats als EUA.

## <a name="configure-enrichment"></a>Configurar l'enriquiment

La configuració de l'enriquiment de marques o interessos consisteix en dos passos:

### <a name="define-your-brands-or-interests"></a>Definir les marques o els interessos

Seleccioneu una de les opcions següents:

- **Sector**: el sistema identifica les principals marques o interessos rellevants per al sector i enriqueix les dades dels vostres clients.
- **Trieu els vostres propis**: seleccioneu fins a cinc elements de la llista de marques o interessos que siguin més rellevants per a la vostra organització.

Per afegir una marca o un interès, introduïu-la a l'àrea d'entrada per obtenir suggeriments segons els termes coincidents. Si no enumerem una marca o un interès que cerqueu, envieu-nos els vostres comentaris mitjançant l'enllaç **Suggereix**.

### <a name="map-your-fields"></a>Assignació dels camps

Assigneu els camps de l'entitat de client unificat a almenys dos atributs per definir el segment demogràfic que voleu que utilitzem per enriquir les dades dels clients. Seleccioneu **Edita** per definir l'assignació dels camps i seleccioneu **Aplica** quan acabeu. Seleccioneu **Desa** per completar l'assignació de camps.

S'admeten els valors i els formats que es mostren a continuació; els valors no distingeixen entre majúscules i minúscules:

- **Data de naixement**: us recomanem que la data de naixement es converteixi al tipus Data/Hora durant la ingestió de dades. Alternativament, pot ser una cadena en format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), com ara "aaaa-MM-dd" o "aaaa-MM-ddTHH:mm: ssZ".
- **Sexe**: masculí, femení, desconegut
- **Codi postal**: codis postals de cinc dígits per als Estats Units, codi postal estàndard a la resta de llocs
- **Ciutat**: nom de la ciutat en anglès
- **Província o estat**: abreviatura de dues lletres per als Estats Units i Canadà. Abreviatura de dues o tres lletres per a Austràlia. No s'aplica per a França, Alemanya o el Regne Unit.
- **País o regió**:

  - US: Estats Units d'Amèrica, Estats Units, EUA
  - CA: Canadà, CA
  - GB: Regne Unit, UK, Gran Bretanya, GB, Regne Unit de la Gran Bretanya i Irlanda del Nord, Regne Unit de la Gran Bretanya
  - AU: Austràlia, AU, Mancomunitat d'Austràlia
  - FR: França, FR, República Francesa
  - DE: Alemanya, Alemany, Deutschland, Allemagne, DE, República Federal d'Alemanya, República d'Alemanya

## <a name="refresh-enrichment"></a>Actualitzar l'enriquiment

Executeu l'enriquiment un cop hàgiu configurat les marques, els interessos i l'assignació de camps de les dades demogràfiques. Per iniciar el procés, seleccioneu **Executa** a la pàgina de configuració de l'interès o la marca. A més, podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una actualització planificada.
En funció de la mida de les dades dels clients, l'execució d'enriquiment pot trigar uns quants minuts a completar-se.

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Després de l'execució del procés d'enriquiment, aneu a **Els meus enriquiments** per revisar el nombre total de clients enriquits i un desglossament de les marques o els interessos dels perfils de clients enriquits.

:::image type="content" source="media/my-enrichments.png" alt-text="Visualització prèvia dels resultats després d'executar el procés d'enriquiment":::

Reviseu les dades enriquides seleccionant **Visualitza les dades enriquides** al gràfic. Les dades enriquits per a les marques van a l'entitat **BrandAffinityFromMicrosoft**. Les dades d'interès es troben a l'entitat **InterestAffinityFromMicrosoft**. També trobareu aquestes entitats enumerades al grup **Enriquiment** a **Dades** > **Entitats**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Veure dades d'enriquiment a la targeta del client

Les afinitats de marca i d'interès també es poden visualitzar en targetes de clients individuals. Aneu a **Clients** i seleccioneu un perfil de client. A la targeta del client, trobareu gràfics per a les marques o els interessos per als quals els usuaris del perfil demogràfic del client tenen afinitat.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Targeta del client amb dades enriquides":::

## <a name="next-steps"></a>Passos següents

Construïu a partir de les dades de clients enriquits. Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.
