---
title: Revisa la unificació de dades
description: Reviseu els passos d'unificació de dades, creeu perfils de clients unificats i reviseu els resultats
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742941"
---
# <a name="review-data-unification"></a>Revisa la unificació de dades

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Aquest últim pas en el procés d'unificació mostra un resum dels passos del procés i proporciona l'oportunitat de fer canvis abans de crear el perfil unificat.

:::image type="content" source="media/m3_review.png" alt-text="Captura de pantalla de Revisa i crea perfils de clients.":::

## <a name="review-the-data-unification-steps"></a>Revisar els passos d'unificació de dades

1. Seleccioneu **Edita** en qualsevol dels passos d'unificació de dades que voleu revisar i fer qualsevol canvi.

1. Si esteu satisfet amb les seleccions, seleccioneu **Crea perfils de client**. La **pàgina Unifica** es mostra mentre es crea el perfil de client unificat. L'algorisme d'unificació triga una mica a completar-se i no podeu canviar la configuració fins que es completi.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Quan es completa el procés d'unificació, l'entitat de perfil de client unificat, anomenada *Client*, apareix a la **pàgina Entitats** de la **secció Perfils**. La primera execució d'unificació correcta crea l'entitat Client *unificada*. Totes les versions posteriors amplien aquesta entitat.

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
