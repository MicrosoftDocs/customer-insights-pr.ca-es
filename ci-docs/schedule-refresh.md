---
title: Planificar l'actualització del sistema
description: Programeu l'hora en què s'ha de refrescar el sistema
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610316"
---
# <a name="schedule-system-refresh"></a>Planificar l'actualització del sistema

Programeu actualitzacions automàtiques de totes les [fonts de dades ingerides](data-sources.md). Les actualitzacions automàtiques us ajuden a garantir que les actualitzacions de les fonts de dades es reflecteixin als perfils del client unificat.

> [!NOTE]
> Power Query les fonts de dades gestionades per vosaltres actualitzen les seves pròpies planificacions. Per programar l'actualització d'aquestes Power Query fonts de dades, configureu els paràmetres d'actualització en aquesta font de dades específica des **de la** pàgina Fonts de dades. Alineeu el temps amb la programació d'actualització de dades de la part superior perquè les actualitzacions no es produeixin totes alhora.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Configuració d'actualització del flux de dades.":::

## <a name="set-system-refresh-schedule"></a>Definir la planificació d'actualització del sistema

1. Aneu a **Sistema d'administració** > **i** seleccioneu la **pestanya Planificació**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Pestanya Actualitza la programació des de la pàgina Sistema.":::

1. L'estat per defecte de l'actualització planificada és **Desactivada**. Per habilitar les actualitzacions planificades, canvieu el commutador a la part superior de la pantalla a **Activat**.

1. Trieu entre les actualitzacions **Setmanals** (per defecte) i **Diàries**. Si intenteu planificar actualitzacions setmanals, seleccioneu un o diversos dies en què voleu executar l'actualització.

1. Definiu el **Fus horari** i, a continuació, utilitzeu el menú desplegable **Hora** per definir l'hora d'actualització. Si voleu planificar diverses actualitzacions en un sol dia, seleccioneu **Afegeix una altra hora**. Podeu afegir fins a quatre actualitzacions.

1. Seleccioneu **Desa** per aplicar els canvis.

[!INCLUDE [footer-include](includes/footer-banner.md)]
