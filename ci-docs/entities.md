---
title: Entitats al Customer Insights
description: Visualitzeu dades de la pàgina Entitats.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183529"
---
# <a name="entities-in-customer-insights"></a>Entitats al Customer Insights

Després de [configurar les fonts de dades](data-sources.md), aneu a la pàgina **Entitats** per avaluar la qualitat de les dades que heu ingerit. Les entitats es consideren conjunts de dades. Diverses capacitats del Dynamics 365 Customer Insights es construeixen al voltant d'aquestes entitats. Revisar-les amb atenció us pot ajudar a validar la sortida d'aquestes funcions.

Mentre treballeu al Customer Insights enriquint les vostres dades o creant segments, mesures i activitats, les entitats que es creen a partir d'aquestes accions es mostren a la **pàgina Entitats**.

## <a name="view-a-list-of-entities"></a>Veure una llista d'entitats

Aneu a **Entitats** > **de dades** per veure una llista d'entitats. Es mostra la informació següent per a cada entitat.

- **Nom**: Nom de l'entitat de dades. Si veieu un símbol d'advertiment al costat del nom d'una entitat, vol dir que les dades de l'entitat no s'han carregat correctament.
- **Font**: Tipus de font de dades que va ingerir l'entitat.
- **Actualitzat**: Hora de l'última actualització de l'entitat.
- **Estat**: Detalls sobre l'última actualització de l'entitat.

## <a name="explore-a-specific-entitys-data"></a>Explorar les dades d'una entitat concreta

1. Aneu a **Entitats** > **de dades**.
1. Seleccioneu una entitat per obrir la pàgina de detalls.  
1. Exploreu els diferents camps i registres inclosos per a aquesta entitat.

- La **pestanya Atributs** està seleccionada per defecte i mostra detalls de l'entitat seleccionada, com ara noms de camp, tipus de dades i tipus. A la columna **Tipus** es mostren els tipus associats del Common Data Model, els quals són identificats automàticament pel sistema o [assignats manualment](map-entities.md) pels usuaris. Aquests tipus són tipus semàntics que poden diferir dels tipus de dades dels atributs. Per exemple, el camp *Correu electrònic* següent té un tipus de cadena de *tipus* de dades, però el seu tipus de model de dades comú (semàntic) pot ser *Correu electrònic*, *Correu electrònic* O *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Taula de camps.":::

   > [!NOTE]
   > Aquesta pàgina només mostra una mostra de les dades de la vostra entitat. Per visualitzar el conjunt de dades complet, aneu a la **pàgina Fonts** de dades, seleccioneu una entitat, seleccioneu **Edita i, a continuació, visualitzeu** les dades d'aquesta entitat amb l'editor Power Query tal com s'explica a [Fonts](data-sources.md) de dades.

   Per obtenir més informació sobre les dades ingerides a l'entitat, la **columna Resum** proporciona algunes característiques importants de les dades, com ara nuls, valors que falten, valors únics, recomptes i distribucions, tot allò que sigui aplicable a les vostres dades. Seleccioneu la icona del gràfic per veure el resum de les dades.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Taula resum de dades.":::

- La **pestanya Dades** mostra detalls sobre els registres individuals de l'entitat. Els detalls que s'enumeren depenen del tipus de dades de l'entitat.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Permet seleccionar una entitat.":::

- La **pestanya Informes** (disponible per a algunes entitats) us permet visualitzar les dades mitjançant la creació d'un informe, que inclou aquestes columnes:

  - **Nom** de l'informe: Nom de l'informe.
  - **Creat per**: Nom de la persona que ha creat l'entitat.
  - **Creat**: Data i hora de creació de l'entitat.
  - **Editat per**: Nom de la persona que ha modificat l'entitat.
  - **Editat**: Data i hora de la modificació de l'entitat.

## <a name="entity-specific-information"></a>Informació específica de l'entitat

La secció següent proporciona informació sobre algunes entitats creades pel sistema.

### <a name="corrupted-data-sources"></a>Fonts de dades malmeses

Els camps d'una font de dades ingerida poden contenir dades malmeses. Els registres amb camps malmesos s'exposen a les entitats creades pel sistema. Conèixer els registres malmesos us ajuda a identificar quines dades cal revisar i actualitzar al sistema d'origen. Després de la propera actualització de la font de dades, els registres corregits s'ingereixen al Customer Insights i es transmeten a processos descendents. 

Per exemple, una columna "aniversari" té el tipus de dades definit com a "data". Un registre de client té el seu aniversari introduït com al "01/01/19777". El sistema marcarà aquest registre com a malmès. Ara algú pot canviar l'aniversari a "1977" al sistema d'origen. Després d'una actualització automatitzada de les fonts de dades, el camp ara té un format vàlid i el registre se suprimirà de l'entitat malmesa.

Aneu a **Dades** > **Entitats** i cerqueu les entitats malmeses a la secció **Sistema**. Esquema de nomenclatura de les entitats malmeses: "DataSourceName_EntityName_corrupt". Seleccioneu una entitat malmesa per identificar els camps danyats i el motiu al nivell de registre individual.

   :::image type="content" source="media/corruption-reason.png" alt-text="Raó de corrupció.":::

El Customer Insights encara processa registres malmesos. No obstant això, poden causar problemes quan es treballa amb les dades unificades.

Les comprovacions següents s'executen a les dades ingerides per identificar registres malmesos:

- El valor d'un camp no coincideix amb el tipus de dades de la seva columna.
- Els camps contenen caràcters que fan que les columnes no coincideixin amb l'esquema esperat. Per exemple: cometes amb format incorrecte, cometes sense escapar o caràcters de línia nova.
- Si hi ha columnes datetime/datetimeoffset, el seu format s'ha d'especificar al model si no segueix el format ISO estàndard.

[!INCLUDE [footer-include](includes/footer-banner.md)]
