---
title: Planificar l'actualització del sistema
description: Programeu l'hora en què s'ha de refrescar el sistema
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246424"
---
# <a name="schedule-system-refresh"></a>Planificar l'actualització del sistema

Programeu actualitzacions automàtiques de totes les [fonts de dades ingerides](data-sources.md). Les actualitzacions automàtiques us ajuden a garantir que les actualitzacions de les fonts de dades es reflecteixin als perfils del client unificat.

> [!NOTE]
> Power Query les fonts de dades gestionades per vosaltres actualitzen les seves pròpies planificacions. Per programar l'actualització d'aquestes Power Query fonts de dades, configureu els paràmetres d'actualització en aquesta font de dades específica des **de la** pàgina Fonts de dades.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Configuració d'actualització del flux de dades.":::

## <a name="set-system-refresh-schedule"></a>Definir la planificació d'actualització del sistema

1. Aneu a **Sistema d'administració** > **i** seleccioneu la **pestanya Planificació**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Pestanya Actualitza la programació des de la pàgina Sistema.":::

1. L'estat per defecte de l'actualització planificada és **Desactivada**. Per habilitar les actualitzacions planificades, canvieu el commutador a la part superior de la pantalla a **Activat**.

1. Trieu entre les actualitzacions **Setmanals** (per defecte) i **Diàries**. Si intenteu planificar actualitzacions setmanals, seleccioneu un o diversos dies en què voleu executar l'actualització.

1. Definiu el **Fus horari** i, a continuació, utilitzeu el menú desplegable **Hora** per definir l'hora d'actualització. Si voleu planificar diverses actualitzacions en un sol dia, seleccioneu **Afegeix una altra hora**.

1. Seleccioneu **Desa** per aplicar els canvis.

[!INCLUDE [footer-include](includes/footer-banner.md)]
