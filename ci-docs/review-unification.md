---
title: Revisar la unificació de dades
description: Reviseu els passos d'unificació de dades, creeu perfils de clients unificats i reviseu els resultats
ms.date: 06/02/2022
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
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139559"
---
# <a name="review-data-unification"></a>Revisar la unificació de dades

Aquest últim pas del procés d'unificació mostra un resum dels passos del procés i proporciona l'oportunitat de fer canvis abans de crear el perfil unificat.

:::image type="content" source="media/m3_review.png" alt-text="Captura de pantalla de Revisió i creació de perfils de clients.":::

## <a name="review-the-data-unification-steps"></a>Revisar els passos d'unificació de dades

1. Seleccioneu **Edita** en qualsevol dels passos d'unificació de dades per revisar i fer qualsevol canvi.

1. Si esteu satisfet amb les vostres seleccions, seleccioneu **Crea perfils de client**. La **pàgina Unify** es mostra mentre es crea el perfil de client unificat. Totes les fitxes, excepte **els camps** Font, mostren **l'estat en cua** o **d'actualització**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captura de pantalla de la pàgina Unify amb peces que mostren Cuued o Actualització.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

L'algorisme d'unificació triga un temps a completar-se i no podeu canviar la configuració fins que no es completi. Quan es completa el procés d'unificació, l'entitat unificada del perfil de client, anomenada Client, apareix a la *pàgina Entitats* de la **secció Perfils**.**·** La primera execució d'unificació reeixida crea l'entitat client *unificada*. Totes les execucions posteriors amplien aquesta entitat.

## <a name="review-the-results-of-data-unification"></a>Revisar els resultats de la unificació de dades

Després de la unificació, la **pàgina Unificació** > **de dades** mostra el nombre de perfils de client unificats. Els resultats de cada pas del procés d'unificació es mostren a cada rajola. Per exemple, **els camps** Font mostren el nombre d'atributs mapejats (camps) i **Els registres duplicats** mostren el nombre de registres duplicats trobats.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla de la pàgina Unify de dades després d'unificar les dades.":::

> [!TIP]
> La **peça Condicions** de coincidència només es mostra si s'han seleccionat diverses entitats.

Us recomanem que reviseu els resultats, especialment la qualitat de les regles [del partit](data-unification-update.md#manage-match-rules) i que, si cal, les perfeccioneu.

Quan sigui necessari, [feu canvis a la configuració](data-unification-update.md) d'unificació i torneu a executar el perfil unificat.

## <a name="next-step"></a>Pas següent

Configureu activitats, enriquiment [...](activities.md), relacions [o](enrichment-hub.md) mesures [per obtenir més informació sobre els vostres clients.](relationships.md)[...](measures.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
