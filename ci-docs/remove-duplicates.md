---
title: Suprimir duplicats abans d'unificar dades
description: El segon pas del procés d'unificació és seleccionar quin registre cal conservar quan es trobin duplicats.
recommendations: false
ms.date: 08/01/2022
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
ms.openlocfilehash: 7f4829cfc14af623f724c6594e834f3fac1c15a9
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213615"
---
# <a name="remove-duplicates-before-unifying-data"></a>Suprimir duplicats abans d'unificar dades

Aquest pas opcional d'unificació us permet configurar regles per eliminar registres duplicats **dins** d'una entitat. La deduplicació identifica diversos registres per a un client i selecciona el millor registre a conservar (basat en les preferències bàsiques de combinació) o fusiona els registres en un de sol (basat en les preferències avançades de combinació). Els registres d'origen s'enllacen al registre combinat amb ID alternatius. Si no es configuren les regles, s'apliquen regles definides pel sistema.

## <a name="default-deduplication"></a>Deduplicació per defecte

Les regles definides pel sistema s'apliquen si no s'afegeixen regles de deduplicació.

- La clau primària es dedueix.
  Per a qualsevol registre amb la mateixa clau primària, el **registre Més emplenat** (el que té menys valors nuls) és el guanyador.
- A l'entitat s'apliquen totes les regles de coincidència entre entitats.
  Per exemple: al pas de coincidència, si l'entitat A coincideix amb l'entitat B a FullName *i* DateofBirth *, l'entitat A també es dedueix amb* FullName *i* DateofBirth *·*. Com que *FullName* i *DateofBirth* són claus vàlides per identificar un client a l'entitat A, aquestes claus també són vàlides per identificar clients duplicats a l'entitat A.

## <a name="include-enriched-entities-preview"></a>Incloure entitats enriquides (vista prèvia)

Si heu enriquit entitats del nivell font de dades per ajudar a millorar els resultats de la unificació, seleccioneu-les. Per obtenir més informació, vegeu [Enriquiment per a les fonts de](data-sources-enrichment.md) dades.

1. A la **pàgina Duplica els registres**, seleccioneu **Utilitza entitats** enriquides a la part superior de la pàgina.

1. Des del panell **Utilitza entitats** enriquides, trieu una o més entitats enriquides.

1. Seleccioneu **Fet**.

## <a name="define-deduplication-rules"></a>Definir regles de deduplicació

1. A la **pàgina Duplica els registres**, seleccioneu una entitat i seleccioneu **Afegeix una regla** per definir les regles de deduplicació.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Captura de pantalla de les pàgines de registres duplicats amb Mostra més ressaltada":::

   1. A la **subfinestra Afegeix una regla**, introduïu la informació següent:
      - **Seleccioneu el camp**: trieu un dels camps disponibles de l'entitat que voleu comprovar si hi ha duplicats. Trieu els camps que probablement siguin únics per a cada client. Per exemple, una adreça electrònica o la combinació de nom, ciutat i número de telèfon.
      - **Normalitza**: seleccioneu les opcions de normalització següents per als atributs seleccionats.
        - **Numerals**: Converteix altres sistemes numèrics, com els nombres romans, a nombres aràbics. *VIII* es converteix en *8*.
        - **Símbols**: elimina tots els símbols i caràcters especials. *Cap+espatlla* es converteix en *Capespatlla*.
        - **Text en minúscula: converteix tots els caràcters en minúscules**. *TOT MAJÚSCULES i títols* passa a ser *tot majúscules i títols*.
        - **Tipus (Telèfon, Nom, Adreça, Organització)**: Estandarditza noms, títols, números de telèfon, adreces, etc.
        - **Unicode a ASCII**: Converteix la notació unicode a caràcters ASCII. */u00B2* es converteix en *2*.
        - **Espai en blanc**: Elimina tots els espais. *Hola   món* es converteix en *Holamón*.
      - **Precisió**: definiu el nivell de precisió que voleu aplicar per a aquesta condició.
        - **Bàsic**: Tria entre *Baix (30%)*, *Mitjà (60%)*, *Alt (80%)*, Exacte *(100%)*. Seleccioneu **Exacte** perquè només coincideixin amb els registres que coincideixin amb el 100 per cent.
        - **Personalitzat**: definiu un percentatge que han de complir els registres. El sistema només trobarà coincidències en els registres que compleixin aquest llindar.
      - **Nom**: Nom de la regla.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Captura de pantalla d'Afegeix una subfinestra de regles per eliminar duplicats.":::

   1. Opcionalment, seleccioneu **Afegeix** > **una condició** per afegir més condicions a la regla. Les condicions estan connectades amb un operador AND lògic i, per tant, només s'executen si es compleixen totes les condicions.

   1. Opcionalment, **Afegiu** > **una excepció** per [afegir excepcions a la regla](match-entities.md#add-exceptions-to-a-rule). Les excepcions s'utilitzen per abordar casos rars de falsos positius i falsos negatius.

   1. Seleccioneu **Fet** per crear la regla.

1. Opcionalment, [afegiu més regles](#define-deduplication-rules).

1. Seleccioneu una entitat i, a continuació, **Editeu les preferències** de combinació.

1. A la **subfinestra de preferències** Combina:
   1. Trieu una d'aquestes tres opcions per determinar quin registre voleu conservar si es troba un duplicat:
      - **Més emplenat**: identifica el registre amb els atributs més emplenats com el registre guanyador. És l'opció de combinació per defecte.
      - **Més recent**: identifica el registre més recent com el registre guanyador. Requereix una data o un camp numèric per definir la qualitat de recent.
      - **Menys recent**: identifica el registre menys recent com el registre guanyador. Requereix una data o un camp numèric per definir la qualitat de recent.
      
      En cas d'empat, el registre guanyador és el que té el VALOR MAX (PK) o la clau primària més gran.
      
   1. Opcionalment, per definir les preferències de combinació dels atributs individuals d'una entitat, seleccioneu **Avançat** a la part inferior de la subfinestra. Per exemple, podeu optar per mantenir el correu electrònic més recent I l'adreça més completa de diferents registres. Expandiu l'entitat per veure'n tots els atributs i definiu quina opció voleu utilitzar per a atributs individuals. Si trieu una opció basada en recència, també heu d'especificar un camp data/hora que defineixi la recència.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Tauler de preferències de combinació avançada que mostra el correu electrònic recent i l'adreça completa":::

   1. Seleccioneu **Fet** per aplicar les vostres preferències de combinació.

1. Després de definir les regles de deduplicació i combinar preferències, seleccioneu **Següent**.
  
> [!div class="nextstepaction"]
> [Pas següent per a una única entitat: unificar camps](merge-entities.md)

> [!div class="nextstepaction"]
> [Pas següent per a diverses entitats: Condicions de coincidència](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Sortida de la desduplicació com a entitat

El procés de deduplicació crea una nova entitat deduplicada per a cadascuna de les entitats d'origen. Aquestes entitats es poden trobar amb **ConflationMatchPairs:CustomerInsights** a la secció **Sistema** de la pàgina **Entitats**, amb el nom **Deduplication_DataSource_Entity**.

Una entitat de sortida de desduplicació conté la informació següent:

- ID / Claus
  - Camps clau primària i identificador alternatiu. El camp Identificador alternatiu consisteix en tots els identificadors alternatius identificats per a un registre.
  - El camp Deduplication_GroupId mostra el grup o clúster identificat dins d'una entitat que agrupa tots els registres semblants en funció dels camps de desduplicació especificats. S'utilitza per al processament del sistema. Si no hi ha regles de desduplicació manuals especificades i s'apliquen regles de desduplicació definides pel sistema, potser no trobareu aquest camp a l'entitat de sortida de desduplicació.
  - Deduplication_WinnerId: aquest camp conté l'ID guanyador dels grups o clústers identificats. Si Deduplication_WinnerId és el mateix que el valor de la clau principal d'un registre, significa que el registre és el registre guanyador.
- Camps que s'utilitzen per definir les regles de desduplicació.
- Els camps Regla i Puntuació per denotar quines de les regles de desduplicació s'apliquen i la puntuació retornada per l'algorisme de coincidència.

[!INCLUDE[footer-include](includes/footer-banner.md)]
