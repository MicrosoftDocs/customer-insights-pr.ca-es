---
title: Revisa la unificació de dades
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
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844074"
---
# <a name="review-data-unification"></a>Revisa la unificació de dades

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Aquest últim pas en el procés d'unificació mostra un resum dels passos del procés i proporciona l'oportunitat de fer canvis abans de crear el perfil unificat.

:::image type="content" source="media/m3_review.png" alt-text="Captura de pantalla de Revisa i crea perfils de clients.":::

## <a name="review-the-data-unification-steps"></a>Revisar els passos d'unificació de dades

1. Seleccioneu **Edita** en qualsevol dels passos d'unificació de dades que voleu revisar i fer qualsevol canvi.

1. Si esteu satisfet amb les seleccions, seleccioneu **Crea perfils de client**. La **pàgina Unifica** es mostra mentre es crea el perfil de client unificat. Totes les peces, excepte els **camps** d'origen, mostren **l'estat de la** cua o **l'actualització**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captura de pantalla de la pàgina Unify amb peces que mostren la cua o l'actualització.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

L'algorisme d'unificació triga una mica a completar-se i no podeu canviar la configuració fins que es completi. Quan es completa el procés d'unificació, l'entitat de perfil de client unificat, anomenada *Client*, apareix a la **pàgina Entitats** de la **secció Perfils**. La primera execució d'unificació correcta crea l'entitat Client *unificada*. Totes les versions posteriors amplien aquesta entitat.

## <a name="review-the-results-of-data-unification"></a>Revisar els resultats de la unificació de dades

Després de la unificació, la **pàgina Unifica** > **les dades** mostra el nombre de perfils de clients unificats. Els resultats de cada pas del procés d'unificació es mostren a cada peça. Per exemple, **els camps** d'origen mostren el nombre d'atributs assignats (camps) i **Els registres duplicats** mostren el nombre de registres duplicats trobats.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla de la pàgina Unificació de dades després d'unificar les dades.":::

> [!TIP]
> La **peça Condicions coincidents** només es mostra si s'han seleccionat diverses entitats.

Us recomanem que reviseu els resultats, en particular la qualitat de les regles [del](data-unification-update.md#manage-match-rules) partit i refineu-los si cal.

Quan sigui necessari, [feu canvis a la configuració](data-unification-update.md) d'unificació i torneu a executar el perfil unificat.

## <a name="next-step"></a>Pas següent

Configureu [activitats](activities.md), [enriquiment](enrichment-hub.md), [relacions](relationships.md) o [mesures](measures.md) per obtenir més informació sobre els vostres clients.

[!INCLUDE[footer-include](includes/footer-banner.md)]
