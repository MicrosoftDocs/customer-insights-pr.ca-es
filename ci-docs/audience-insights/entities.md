---
title: Entitats i conjunts de dades
description: Visualitzeu dades de la pàgina Entitats.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2a207a3dcad4bf192efb6ee1554195f10b19670b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732068"
---
# <a name="entities-in-audience-insights"></a>Entitats a les conclusions del públic

Després de [configurar les fonts de dades](data-sources.md), aneu a la pàgina [Entitats](data-sources.md) per avaluar la qualitat de les dades que heu ingerit. Les entitats es consideren conjunts de dades. Es construeixen múltiples capacitats de Dynamics 365 Customer Insights al voltant d'aquestes entitats. Revisar-les amb atenció us pot ajudar a validar la sortida d'aquestes funcions.

A la pàgina **Entitats** s'enumeren entitats i inclou diverses columnes:

- **Nom**: nom de l'entitat de dades. Si veieu un símbol d'advertiment al costat del nom d'una entitat, vol dir que les dades de l'entitat no s'han carregat correctament.
- **Font**: tipus de font de dades que ha ingerit l'entitat
- **Creat per**: nom de la persona que ha creat l'entitat
- **Data de creació**: data i hora de creació de l'entitat
- **·** Actualització: Nom de la persona que ha actualitzat l'entitat
- **Estat** : detalls sobre l'última actualització de l'entitat

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Explorar les dades d'una entitat concreta

Seleccioneu una entitat per explorar els diferents camps i registres inclosos dins d'aquesta entitat.

> [!div class="mx-imgBorder"]
> ![Permet seleccionar una entitat.](media/data-manager-entities-data.png "Seleccioneu una entitat")

- A la pestanya **Dades** es mostra una taula amb els detalls dels registres individuales de l'entitat.

> [!div class="mx-imgBorder"]
> ![Taula de camps.](media/data-manager-entities-fields.PNG "Taula de camps")

- La pestanya **Atributs** se selecciona per defecte i mostra una taula per revisar els detalls de l'entitat seleccionada, com ara els noms dels camps, els tipus de dades i els tipus. A la columna **Tipus** es mostren els tipus associats del Common Data Model, els quals són identificats automàticament pel sistema o [assignats manualment](map-entities.md) pels usuaris. Aquests tipus són tipus semàntics que poden diferir dels tipus de dades dels atributs. Per exemple, el camp *Correu electrònic* de sota té un tipus de dades *Text*, però el seu tipus (semàntic) del model de dades comú podria ser *Correu electrònic* o *Adreça electrònica*.

> [!NOTE]
> Ambdues taules mostren només una mostra de les dades de l'entitat. Per visualitzar el conjunt de dades complet, aneu a la pàgina **Fonts de dades**, seleccioneu una entitat, seleccioneu **Edita** i, a continuació, visualitzeu les dades d'aquesta entitat amb l'editor del Power Query com s'explica a [Fonts de dades](data-sources.md).

Per obtenir més informació sobre les dades que s'ingereixen a l'entitat, la columna **Resum** us ofereix algunes característiques importants de les dades, com ara valors inexistents, valor que falten, valors únics, recomptes i distribucions, segons s'apliqui a les vostres dades.

Seleccioneu la icona del gràfic per veure el resum de les dades.

> [!div class="mx-imgBorder"]
> ![Símbol de resum.](media/data-manager-entities-summary.png "Taula de resum de dades")

## <a name="entity-specific-information"></a>Informació específica de l'entitat

La secció següent proporciona informació sobre algunes entitats creades pel sistema.

### <a name="corrupted-data-sources"></a>Fonts de dades malmeses

Els camps d'una font de dades ingerida poden contenir dades malmeses. Els registres amb camps malmesos s'exposen a les entitats creades pel sistema. Conèixer els registres malmesos us ajuda a identificar quines dades cal revisar i actualitzar al sistema d'origen. Després de la propera actualització de la font de dades, els registres corregits s'ingereixen al Customer Insights i es transmeten a processos descendents. 

Per exemple, una columna "aniversari" té el tipus de dades definit com a "data". Un registre de client té el seu aniversari introduït com al "01/01/19777". El sistema marcarà aquest registre com a malmès. Ara algú pot canviar l'aniversari a "1977" al sistema d'origen. Després d'una actualització automatitzada de les fonts de dades, el camp ara té un format vàlid i el registre se suprimirà de l'entitat malmesa. 

Aneu a **Dades** > **Entitats** i cerqueu les entitats malmeses a la secció **Sistema**. Esquema de nomenclatura de les entitats malmeses: "DataSourceName_EntityName_corrupt".

El Customer Insights encara processa registres malmesos. No obstant això, poden causar problemes quan es treballa amb les dades unificades.

Les comprovacions següents s'executen a les dades ingerides per identificar registres malmesos: 

- El valor d'un camp no coincideix amb el tipus de dades de la seva columna.
- Els camps contenen caràcters que fan que les columnes no coincideixin amb l'esquema esperat. Per exemple: cometes amb format incorrecte, cometes sense escapar o caràcters de línia nova.
- Si hi ha columnes datetime/date/datetimeoffset, el seu format s'ha d'especificar al model si no segueix el format ISO estàndard.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
