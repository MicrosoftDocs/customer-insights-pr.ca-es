---
title: Suprimeix els duplicats abans d'unificar les dades
description: El segon pas del procés d'unificació és seleccionar quin registre conservar quan es trobin duplicats.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742926"
---
# <a name="remove-duplicates-before-unifying-data"></a>Suprimeix els duplicats abans d'unificar les dades

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Aquest pas en la unificació opcionalment us permet configurar regles per gestionar registres duplicats dins d'una entitat. *La deduplicació* identifica registres duplicats i els fusiona en un sol registre. Els registres d'origen s'enllacen al registre combinat amb ID alternatius. Si no es configuren regles, s'apliquen regles definides pel sistema.

## <a name="include-enriched-entities-preview"></a>Inclou entitats enriquides (previsualització)

Si heu enriquit entitats al nivell font de dades per ajudar a millorar els resultats de la unificació, seleccioneu-les. Per obtenir més informació, vegeu [Enriquiment per a fonts](data-sources-enrichment.md) de dades.

1. A la **pàgina Registres duplicats** **, seleccioneu** Utilitza les entitats enriquides a la part superior de la pàgina.

1. A la **subfinestra** Utilitza les entitats enriquides, trieu una o més entitats enriquides.

1. Seleccioneu **Fet**.

## <a name="define-deduplication-rules"></a>Defineix les regles de deduplicació

1. A la **pàgina Registres duplicats**, seleccioneu una entitat i seleccioneu **Afegeix una regla** per definir les regles de deduplicació.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Captura de pantalla de les pàgines de registres duplicats amb Mostra més ressaltat":::

   1. A la **subfinestra Afegeix regles**, introduïu la informació següent:
      - **Seleccioneu el camp**: trieu de la llista de camps disponibles de l'entitat que voleu comprovar si hi ha duplicats. Trieu els camps que probablement siguin únics per a cada client. Per exemple, una adreça electrònica o la combinació de nom, ciutat i número de telèfon.
      - **Normalitza**: seleccioneu les opcions de normalització següents per als atributs seleccionats.
        - **Numerals**: converteix altres sistemes numèrics, com ara els nombres romans, en nombres aràbics. *VIII* es converteix en *8*.
        - **Símbols**: elimina tots els símbols i caràcters especials. *Cap+espatlla* es converteix en *Capespatlla*.
        - **Text en minúscules: converteix tot el caràcter en minúscules**. *TOT MAJÚSCULES i títols* passa a ser *tot majúscules i títols*.
        - **Tipus (Telèfon, Nom, Adreça, Organització)**: Estandarditza noms, títols, números de telèfon, adreces, etc.
        - **Unicode a ASCII**: converteix la notació unicode en caràcters ASCII. */u00B2* es converteix en *2*.
        - **Espais en blanc**: elimina tots els espais. *Hola   món* es converteix en *Holamón*.
      - **Precisió**: definiu el nivell de precisió que voleu aplicar per a aquesta condició.
        - **Bàsic**: Tria entre *Baix (30%)*, *Mitjà (60%)*, *Alt (80%)*, i *Exacte (100%)*. Seleccioneu **Exacte** per coincidir només amb els registres que coincideixin amb el 100%.
        - **Personalitzat**: definiu un percentatge que han de complir els registres. El sistema només trobarà coincidències en els registres que compleixin aquest llindar.
      - **Nom**: Nom de la norma.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Captura de pantalla de la subfinestra Afegeix regles per suprimir duplicats.":::

   1. Opcionalment, seleccioneu **Afegeix** > **una condició** per afegir més condicions a la regla. Les condicions estan connectades amb un operador AND lògic i, per tant, només s'executen si es compleixen totes les condicions.

   1. Opcionalment, **afegeix una** > **excepció** per [afegir excepcions a la regla](match-entities.md#add-exceptions-to-a-rule). Les excepcions s'utilitzen per abordar casos rars de falsos positius i falsos negatius.

   1. Seleccioneu **Fet** per crear la norma.

1. Opcionalment, [afegiu més regles](#define-deduplication-rules).

1. Seleccioneu una entitat i editeu **les preferències** de combinació.

1. A la **subfinestra de preferències** Combina:
   1. Trieu una de les tres opcions per determinar quin registre conservar si es troba un duplicat:
      - **Més emplenat**: identifica el registre amb els atributs més emplenats com el registre guanyador. És l'opció de combinació per defecte.
      - **Més recent**: identifica el registre més recent com el registre guanyador. Requereix una data o un camp numèric per definir la qualitat de recent.
      - **Menys recent**: identifica el registre menys recent com el registre guanyador. Requereix una data o un camp numèric per definir la qualitat de recent.
      
      En cas d'empat, el registre del guanyador és el que té el MAX(PK) o el valor clau principal més gran.
      
   1. Opcionalment, per definir les preferències de combinació en atributs individuals d'una entitat, seleccioneu **Avançat** a la part inferior de la subfinestra. Per exemple, podeu triar mantenir el correu electrònic més recent i l'adreça més completa de diferents registres. Expandiu l'entitat per veure tots els seus atributs i definir quina opció s'utilitzarà per a atributs individuals. Si trieu una opció basada en la recència, també heu d'especificar un camp data/hora que defineixi la recència.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Subfinestra de preferències de combinació avançada que mostra el correu electrònic recent i l'adreça completa":::

   1. Seleccioneu **Fet** per aplicar les preferències de combinació.

1. Després de definir les regles de deduplicació i combinar preferències, seleccioneu **Següent**.
  
> [!div class="nextstepaction"]
> [Pas següent per a una sola entitat: Unifica els camps](merge-entities.md)

> [!div class="nextstepaction"]
> [Pas següent per a diverses entitats: condicions coincidents](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Sortida de la desduplicació com a entitat

El procés de deduplicació crea una entitat deduplicada nova per a cadascuna de les entitats d'origen. Aquestes entitats es poden trobar amb **ConflationMatchPairs:CustomerInsights** a la secció **Sistema** de la pàgina **Entitats**, amb el nom **Deduplication_DataSource_Entity**.

Una entitat de sortida de desduplicació conté la informació següent:

- ID / Claus
  - Clau principal i camps d'identificador alternatiu. El camp D'identificador alternatiu consisteix en tots els identificadors alternatius identificats per a un registre.
  - El camp Deduplication_GroupId mostra el grup o clúster identificat dins d'una entitat que agrupa tots els registres semblants en funció dels camps de desduplicació especificats. S'utilitza per al processament del sistema. Si no hi ha regles de desduplicació manuals especificades i s'apliquen regles de desduplicació definides pel sistema, potser no trobareu aquest camp a l'entitat de sortida de desduplicació.
  - Deduplication_WinnerId: aquest camp conté l'ID guanyador dels grups o clústers identificats. Si Deduplication_WinnerId és el mateix que el valor de la clau principal d'un registre, significa que el registre és el registre guanyador.
- Camps que s'utilitzen per definir les regles de desduplicació.
- Els camps Regla i Puntuació per denotar quines de les regles de desduplicació s'apliquen i la puntuació retornada per l'algorisme de coincidència.

[!INCLUDE[footer-include](includes/footer-banner.md)]
