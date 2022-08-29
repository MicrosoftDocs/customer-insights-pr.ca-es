---
title: Revisar la unificació de dades
description: Reviseu els passos d'unificació de dades, creeu perfils de clients unificats i reviseu els resultats
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303955"
---
# <a name="review-data-unification"></a>Revisar la unificació de dades

Reviseu el resum dels canvis, creeu el perfil unificat i reviseu-ne els resultats.

## <a name="review-and-create-customer-profiles"></a>Revisa i crea perfils de client

Aquest últim pas del procés d'unificació mostra un resum dels passos del procés i proporciona l'oportunitat de fer canvis abans de crear el perfil unificat.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Captura de pantalla de Revisar i crear perfils de clients.":::

1. Seleccioneu **Edita** en qualsevol dels passos d'unificació de dades per revisar i fer qualsevol canvi.

1. Si esteu satisfet amb les vostres seleccions, seleccioneu **Crea perfils de** client (o **Crea perfils de** compte per a B a B). La **pàgina Unify** es mostra mentre es crea el perfil de client unificat.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captura de pantalla de la pàgina Unify amb peces que mostren Cuued o Actualització.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

L'algorisme d'unificació triga un temps a completar-se i no podeu canviar la configuració fins que no es completi.

## <a name="view-the-results-of-data-unification"></a>Veure els resultats de la unificació de dades

Després de la unificació, la **pàgina Unificació** > **de dades** mostra el nombre de perfils de client unificats (o perfils de compte de B a B). Els resultats de cada pas del procés d'unificació es mostren a cada rajola. Per exemple, **els camps** Font mostren el nombre d'atributs mapejats (camps) i **Els registres duplicats** mostren el nombre de registres duplicats trobats.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla de la pàgina Unify de dades després d'unificar les dades.":::

> [!TIP]
> La **peça Condicions** de coincidència només es mostra si s'han seleccionat diverses entitats.

Us recomanem que reviseu els resultats, especialment la qualitat de les regles [del partit](data-unification-update.md#manage-match-rules) i que, si cal, les perfeccioneu.

Quan sigui necessari, [feu canvis a la configuració](data-unification-update.md) d'unificació i torneu a executar el perfil unificat.

### <a name="verify-output-entities-from-data-unification"></a>Verificar les entitats de sortida a partir de la unificació de dades

Aneu a **Entitats** > **de dades** per verificar les entitats de sortida.

L'entitat del perfil de client unificat, anomenada *Client*, es mostra a la **secció Perfils**. La primera execució d'unificació reeixida crea l'entitat client *unificada*. Totes les execucions posteriors amplien aquesta entitat.

Les entitats de deduplicació i conflació es creen i es mostren a la **secció Sistema**. Es crea una entitat deduplicada per a cadascuna de les entitats d'origen amb el nom **Deduplication_DataSource_Entity**. L'entitat **ConflationMatchPairs** conté informació sobre els partits entre entitats.

Una entitat de sortida de desduplicació conté la informació següent:
- ID / Claus
  - Camps clau primària i identificador alternatiu. El camp Identificador alternatiu consisteix en tots els identificadors alternatius identificats per a un registre.
  - El camp Deduplication_GroupId mostra el grup o clúster identificat dins d'una entitat que agrupa tots els registres semblants en funció dels camps de desduplicació especificats. S'utilitza per al processament del sistema. Si no hi ha regles de desduplicació manuals especificades i s'apliquen regles de desduplicació definides pel sistema, potser no trobareu aquest camp a l'entitat de sortida de desduplicació.
  - Deduplication_WinnerId: aquest camp conté l'ID guanyador dels grups o clústers identificats. Si Deduplication_WinnerId és el mateix que el valor de la clau principal d'un registre, significa que el registre és el registre guanyador.
- Camps que s'utilitzen per definir les regles de desduplicació.
- Els camps Regla i Puntuació per denotar quines de les regles de desduplicació s'apliquen i la puntuació retornada per l'algorisme de coincidència.

## <a name="next-step"></a>Pas següent

- Per a B a B, opcionalment realitzeu la [unificació de contactes](data-unification-contacts.md).

- Per a B-to-C, configureu [activitats](activities.md), [enriquiments](enrichment-hub.md), [relacions](relationships.md) o [mesures](measures.md) per obtenir més informació sobre els vostres clients.

[!INCLUDE[footer-include](includes/footer-banner.md)]
