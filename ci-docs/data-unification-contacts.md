---
title: Crear un perfil de contacte unificat (visualització prèvia)
description: Seguiu el procés d'unificació de dades per crear un únic conjunt de dades mestres de contactes.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305066"
---
# <a name="create-a-unified-contact-profile-preview"></a>Crear un perfil de contacte unificat (visualització prèvia)

Després [d'unificar els](map-entities.md) comptes empresarials, opcionalment podeu unificar els contactes d'aquests comptes i enllaçar els contactes unificats als comptes unificats. El procés d'unificació de contactes assigna dades de contacte de diverses fonts de dades, elimina duplicats, coincideix amb les dades entre entitats, configura mapes semàntics, crea relacions entre contactes i comptes i, a continuació, crea un perfil de contacte unificat.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Els primers passos són idèntics als passos d'unificació de comptes.

## <a name="prerequisites"></a>Requisits previs

Els registres de compte i contacte han de tenir una clau única (anomenada clau externa) que els connecti. Per exemple, un identificador de compte existent al registre de comptes i al registre de contactes que vincula el compte i el contacte.

## <a name="preview-limitations"></a>Limitacions de visualització prèvia

- Els contactes sense un enllaç a un compte es deixen anar.
- Si es dedueix un compte, s'identifica un registre guanyador en funció de les preferències de combinació. Els registres perdedors no se seleccionen i, per tant, es deixen caure. Els contactes associats als registres perduts es deixen caure.
- Un compte pot tenir diversos contactes, però un contacte està enllaçat a un sol compte.
- Els atributs de contacte mapejats en el pas d'assignació semàntica són els únics atributs que es poden mostrar a la targeta client. No obstant això, hi ha 17 atributs disponibles.

## <a name="select-source-fields"></a>Seleccionar camps d'origen

1. A **Unificar contactes (visualització prèvia),** seleccioneu **Comença**.

1. [Seleccioneu les entitats i els camps](map-entities.md) de les fonts de dades de contacte, incloses les claus principals i els tipus d'atributs.

1. Seleccioneu **Següent**.

## <a name="remove-duplicate-records"></a>Suprimir registres duplicats

1. Opcionalment, [definiu regles](remove-duplicates.md) de deduplicació per a les entitats seleccionades.

1. Seleccioneu **Següent**.

## <a name="match-conditions"></a>Condicions del partit

1. [Definiu l'ordre de coincidència i les regles](match-entities.md) per a la coincidència entre entitats.

1. Seleccioneu **Següent**.

## <a name="unify-contact-fields"></a>Unificar camps de contacte

1. [Combineu i excloeu camps](merge-entities.md) de contacte.

1. Seleccioneu **Següent**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definiu els camps semàntics dels contactes unificats

Aquest pas en el procés d'unificació assigna els camps de contacte unificats a tipus semàntics. En B-to-B, les targetes de client mostren comptes. Quan se selecciona la targeta, es visualitzen tots els contactes associats al compte. Els camps que mapegeu en aquest pas són els camps que es mostraran a les targetes.

1. Seleccioneu el tipus semàntic que s'assigna a cada camp unificat. Seleccioneu **Cap** si no hi ha disponible un tipus semàntic.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Captura de pantalla de la pàgina de camps semàntics per definir els tipus semàntics." lightbox="media/semantic_mapping.png":::

1. Després d'assignar tots els camps unificats, seleccioneu **Següent**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Definir la relació entre contactes i comptes

Aquest pas del procés d'unificació connecta les dades de contacte amb les dades del compte corresponents.

1. Per a cada entitat, introduïu la informació següent:

   - **Clau externa de l'entitat** de contacte: trieu l'atribut que connecta l'entitat de contacte amb el compte.
   - **Per tenir en compte l'entitat**: trieu l'entitat del compte associada al contacte.

   :::image type="content" source="media/contact_relationship.png" alt-text="Captura de pantalla de la pàgina Relació per connectar les entitats de contacte i compte.":::

1. Seleccioneu **Següent**.

## <a name="review-contact-unification"></a>Revisar la unificació de contactes

Reviseu el resum dels canvis, creeu el perfil unificat i reviseu-ne els resultats.

### <a name="review-and-create-contact-profiles"></a>Revisa i crea perfils de contacte

Aquest últim pas del procés d'unificació mostra un resum dels passos del procés i proporciona l'oportunitat de fer canvis abans de crear el perfil de contacte unificat.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Captura de pantalla de Revisa i crea perfils de contacte.":::

1. Seleccioneu **Edita** en qualsevol dels passos d'unificació de contactes per revisar-lo i fer-hi canvis.

1. Si esteu satisfet amb les vostres seleccions, seleccioneu **Crea perfils de** contacte. La **pàgina Unify** es mostra mentre es crea el perfil de contacte unificat.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Captura de pantalla de la pàgina Unify Contactes amb les peces que mostren Cuued o Actualització.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

L'algorisme d'unificació triga un temps a completar-se i no podeu canviar la configuració fins que no es completi.

### <a name="view-the-results-of-contact-unification"></a>Veure els resultats de la unificació de contactes

Un cop finalitzada la unificació, la **pàgina Unificació** > **de dades** mostra el nombre de perfils de contactes unificats. Els resultats de cada pas en el procés d'unificació es mostren a cada rajola. Per exemple, **els camps** Font mostren el nombre d'atributs mapejats (camps) i **Els registres duplicats** mostren el nombre de registres duplicats trobats.

:::image type="content" source="media/unified_contacts.png" alt-text="Captura de pantalla de la pàgina Unify de dades després d'unificar els contactes.":::

> [!TIP]
> La **peça Condicions** de coincidència només es mostra si s'han seleccionat diverses entitats.

Us recomanem que reviseu els resultats, especialment la qualitat de les regles [del partit](data-unification-update.md#manage-match-rules) i que, si cal, les perfeccioneu.

Quan sigui necessari, [feu canvis a la configuració d'unificació de](data-unification-update.md) contactes i torneu a executar el perfil unificat.

### <a name="verify-output-entities-from-data-unification"></a>Verificar les entitats de sortida a partir de la unificació de dades

Aneu a **Entitats** > **de dades** per verificar les entitats de sortida.

L'entitat perfil de contacte unificat, anomenada *ContactProfile*, es mostra a la secció d'entitats **semàntiques**. La primera execució d'unificació reeixida crea l'entitat unificada *ContactProfile*. Totes les execucions posteriors amplien aquesta entitat.

L'entitat *ContactesPersonalitzador* (vista prèvia) es crea i es mostra a la **secció Perfils**. Aquesta entitat conté les dades de contacte sense els enllaços als comptes. Aquesta entitat s'utilitza com a entrada en l'assignació semàntica i els passos de relació de la unificació de contactes.

Les entitats de deduplicació i conflació es creen i es mostren a la **secció Sistema**. Es crea una entitat deduplicada per a cadascuna de les entitats d'origen amb el nom **Deduplication_DataSource_Entity**. L'entitat **ContactesConflationMatchPairs** conté informació sobre coincidències entre entitats.

Una entitat de sortida de desduplicació conté la informació següent:
- ID / Claus
  - Camps clau primària i identificador alternatiu. El camp Identificador alternatiu consisteix en tots els identificadors alternatius identificats per a un registre.
  - El camp Deduplication_GroupId mostra el grup o clúster identificat dins d'una entitat que agrupa tots els registres semblants en funció dels camps de desduplicació especificats. S'utilitza per al processament del sistema. Si no hi ha regles de desduplicació manuals especificades i s'apliquen regles de desduplicació definides pel sistema, potser no trobareu aquest camp a l'entitat de sortida de desduplicació.
  - Deduplication_WinnerId: aquest camp conté l'ID guanyador dels grups o clústers identificats. Si Deduplication_WinnerId és el mateix que el valor de la clau principal d'un registre, significa que el registre és el registre guanyador.
- Camps que s'utilitzen per definir les regles de desduplicació.
- Els camps Regla i Puntuació per denotar quines de les regles de desduplicació s'apliquen i la puntuació retornada per l'algorisme de coincidència.

## <a name="next-step"></a>Pas següent

Configureu [activitats](activities.md), [enriquiment](enrichment-hub.md) o [relacions](relationships.md) per obtenir més informació sobre els vostres contactes.
