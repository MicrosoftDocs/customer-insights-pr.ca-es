---
title: Segmentar la informació de segments existents
description: Obtingueu informació sobre els segments existents per veure'n les diferències i els aspectes comuns.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2856888d6ac64d5daabcc5a234f13bc6f88bb3df
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306062"
---
# <a name="segment-insights-preview"></a>Informació dels segments (versió preliminar)

Descobriu informació addicional i estadístiques sobre els segments existents. Esbrineu en què es diferencien dos segments o què tenen en comú.

## <a name="segment-overlap"></a>Superposició de segments

L'anàlisi de superposició de segments mostra quants i quins clients són comuns en dos o més segments. Per exemple, com un segment de clients freqüents se superposa amb un segment que conté els clients satisfets amb un producte o servei.
També podeu analitzar com canvia la superposició per atributs específics.

### <a name="run-an-overlap-analysis"></a>Executar una anàlisi de superposició

1. Aneu a **Segments** i seleccioneu la pestanya **Informació (versió preliminar)**.

1. Seleccioneu **Nou** i trieu l'opció **Superposició** a la subfinestra **Trieu un tipus d'informació**.

1. Trieu els segments d'interès i seleccioneu **Següent**.

1. Opcionalment, trieu un o diversos camps d'interès per analitzar les superposicions per a cada valor de camp possible i seleccioneu **Següent**.

1. Proporcioneu un nom per a l'anàlisi de superposició, un nom de visualització opcional i una descripció.

1. Seleccioneu **Desa** per iniciar l'anàlisi. L'anàlisi de superposició està preparada quan l'estat canvia d'Actualitzant a Correcte.

### <a name="view-and-optimize-an-overlap-analysis"></a>Visualitzar i optimitzar una anàlisi de superposició

Després de completar l'anàlisi, trobareu detalls sobre aquesta informació a **Segments** > **Informació (versió preliminar)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalls de la informació de superposició de segments":::

Seleccioneu una informació per veure els resultats de l'anàlisi:

- Nombre de membres que solapen els segments seleccionats per a l'anàlisi.
- Nombre de membres que s'inclouen en un dels segments però no a la resta de segments.
- Si heu seleccionat camps en configurar l'anàlisi de superposició, els trobareu a les pestanyes corresponents. Podeu utilitzar el desplegable de filtre per seleccionar qualsevol nivell d'interès d'atribut i la taula de la part inferior mostrarà les dades corresponents.

## <a name="segment-differentiators"></a>Diferenciadors del segment

Els diferenciadors del segment us ajudaran a descobrir els elements diferencials d'un segment de la resta de clients o d'un altre segment. Només heu de seleccionar un segment i el sistema identificarà els atributs i les mesures de perfil que distingeixen el segment seleccionat.

### <a name="run-a-differentiator-analysis"></a>Executar una anàlisi diferenciadora

1. Aneu a **Segments** i seleccioneu la pestanya **Informació (versió preliminar)**.

1. Seleccioneu **Nou** i trieu l'opció **Superposició** a la subfinestra **Trieu un tipus d'informació**.

1. Trieu el segment que voleu analitzar com a **Segment principal** i seleccioneu **Següent**.

1. Trieu **Tots els clients** o un **segment secundari** per comparar amb el segment principal i seleccioneu **Següent**.

1. Opcionalment, trieu un o diversos camps d'interès per centrar l'anàlisi sobre els atributs específics i seleccioneu **Següent**.

1. Proporcioneu un nom per a l'anàlisi de superposició, un nom de visualització opcional i una descripció.

1. Seleccioneu **Desa** per iniciar l'anàlisi. L'anàlisi de superposició està preparada quan l'estat canvia d'Actualitzant a Correcte.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Visualitzar i optimitzar una anàlisi de diferenciadors

Després de completar l'anàlisi, trobareu detalls sobre aquesta informació a **Segments** > **Informació (versió preliminar)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalls de la informació de diferenciador de segments":::

Seleccioneu una informació per veure els resultats de l'anàlisi. Una anàlisi de diferenciador inclou dues pestanyes. La pestanya **Atributs** enumera els atributs del perfil considerats com a diferenciadors. La pestanya **Mesures** enumera els diferenciadors. Cada pestanya inclou els detalls següents:

- Llista classificada de diferenciadors, ordenats per la puntuació de la diferència.
- La **Puntuació de la diferència** per a cada diferenciador. La puntuació de diferència representa el grau de diferència d'un atribut entre dos segments. Com més gran sigui la puntuació, més difereixen els atributs entre els dos segments. Seleccioneu una puntuació per obrir la subfinestra **Puntuació de diferència** amb les distribucions de valors per a l'atribut.

## <a name="manage-segment-insights"></a>Administrar la informació detallada de segments

Podeu utilitzar les opcions següents sobre la informació a la barra d'ordres:

- **Enrere** per tornar a la llista d'informació
- **Actualitza** per tornar a executar l'anàlisi
- **Suprimeix** per suprimir aquesta informació


[!INCLUDE[footer-include](../includes/footer-banner.md)]