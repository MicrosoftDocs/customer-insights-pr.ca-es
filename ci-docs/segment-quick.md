---
title: Creeu segments senzills amb segments ràpids
description: Creeu segments senzills de clients per agrupar-los en funció de diversos atributs.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171152"
---
# <a name="create-simple-segments-with-quick-segments"></a>Creeu segments senzills amb segments ràpids

Els segments ràpids us permeten crear segments senzills amb un sol operador ràpidament per obtenir informació més ràpida. Els segments ràpids només estan admesos als entorns per a **clients individuals**.

## <a name="create-a-new-segment-with-quick-segments"></a>Crear un segment nou amb segments ràpids

1. Aneu a **Segments**.

1. Seleccioneu **Crea nova** > **des de**.
   - Seleccioneu l'opció **Perfils** per crear un segment que es basi en l'entitat de *client unificat*.
   - Seleccioneu l'opció **Mesures** per crear un segment en les mesures que heu creat anteriorment.
   - Seleccioneu l'opció **Intel·ligència** per crear un segment sobre una de les entitats de sortida que heu generat mitjançant les funcionalitats **Prediccions** o **Models personalitzats**.

1. Al quadre de diàleg **Crea un segment ràpid**, seleccioneu un atribut del desplegable **Camp**. A partir de la vostra selecció, el sistema proporciona diferents valors.
   - Per als camps categòrics, es mostren els 10 recomptes de clients principals. Seleccioneu un **Valor** i seleccioneu **Revisa**.
   - Per a un atribut numèric, el sistema mostra quin valor de l'atribut es troba per sota del percentil de cada client. Trieu un **Operador** i un **Valor** i, a continuació, seleccioneu **Revisa**.

1. El sistema proporciona una **mida de segment estimada**. Trieu si voleu generar el segment que heu definit o torneu enrere per triar un camp diferent.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nom i estimació per a un segment ràpid.":::

1. Proporcioneu un nom **i** un **nom** d'entitat de sortida per al segment. Opcionalment, afegiu [etiquetes](work-with-tags-columns.md#manage-tags).

1. Seleccioneu **Desa** per crear el segment. Es **mostra la pàgina Segments**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Passos següents

[Exporteu un segment](export-destinations.md) i exploreu la [integració amb la targeta de client](customer-card-add-in.md) per utilitzar segments en altres aplicacions.

[!INCLUDE [footer-include](includes/footer-banner.md)]
