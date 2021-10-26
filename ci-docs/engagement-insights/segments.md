---
title: Visualitzar i crear segments
description: Com crear, editar i suprimir segments i on s'utilitzen.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: f6bba645a78173fb00dc75e6080f2aeda0b5a143
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623575"
---
# <a name="view-and-create-segments"></a>Visualitzar i crear segments

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Els segments us permeten identificar subconjunts de visitants segons les característiques o interaccions amb el lloc web. Els segments permeten aplicar filtres i analitzar aquests subconjunts. L'anàlisi pot ajudar a examinar i respondre a les tendències del vostre negoci. 

:::image type="content" source="media/segments-page.png" alt-text="Captura de pantalla de l'aplicació dels coneixements d'interacció que mostra la llista de segments existents en una àrea de treball.":::

## <a name="view-segments"></a>Visualitza segments

1. Aneu a **Dades** a la subfinestra de navegació esquerra. 

1. Seleccioneu la pestanya **Segments** per veure una llista de tots els segments de l'àrea de treball. 

## <a name="create-a-segment"></a>Creació d’un segment

Els segments consisteixen en regles i condicions connectades amb operadors lògics. Les condicions apliquen filtres a una dimensió seleccionada. Cada segment pot utilitzar fins a cinc mètriques.

A l'exemple següent es mostra un segment amb dues condicions en una regla. Filtra totes les incidències del lloc web on es troba el navegador del Chrome i els sistemes operatius són iOS o Android.

:::image type="content" source="media/segment-sample.png" alt-text="Segments d'exemple amb dues condicions en una regla per filtrar per a les incidències del lloc web.":::

Aquesta secció descriu com es crea un *segment en blanc* des de zero.

1. Aneu a **Dades** > **Segments**.

1. Seleccioneu **Nou segment**.

1. A la **Biblioteca de recursos**, seleccioneu (+) al costat de l'atribut pel qual voleu filtrar. Actualment, només podeu crear segments basats en dimensions.

   :::image type="content" source="media/create-new-segment.png" alt-text="Crear un segment nou.":::

1. A la secció **Regla**, trieu un operador i un valor per a l'atribut seleccionat. Són compatibles les operacions següents.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Trieu un operador per al segment nou.":::

   - **és**: requereix una coincidència exacta per incloure valors. Utilitza **igual que** per a un únic valor o **qualsevol de** per incloure diversos valors.
   - **no és**: requereix una coincidència exacta per excloure valors. Utilitza **igual que** per a un únic valor o **qualsevol de** per incloure diversos valors.
   - **comença amb**: una cadena amb la qual comencen els valors coincidents.
   - **acaba amb**: una cadena amb la qual acaben els valors coincidents.
   - **conté**: una cadena que es troba als valors coincidents.

1. Per afegir més condicions a un grup, podeu utilitzar operadors lògics. Els atributs previstos es factoritzen quan s'utilitzen operadors de conjunts.
   - Operador **AND**: cal complir ambdues condicions com a part del procés de segmentació. Aquesta opció és més útil quan definiu les condicions entre diverses entitats diferents.
   - Operador **OR**: una de les condicions ha de complir-se com a part del procés de segmentació. Aquesta opció és més útil quan definiu diverses condicions per a la mateixa entitat.

1. Seleccioneu **Desa** i anomeneu el segment. 

El segment es mostrarà a la pàgina **Segments** i el podeu aplicar a tots els informes i embuts de l'àrea de treball.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Utilitzar un segment en un informe o un embut

Podeu aplicar segments a un informe o a un embut per filtrar-los segons les condicions del segment. No obstant això, no podeu aplicar segments a l'informe d'ús en temps real.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Informe de visualitzacions de pàgina amb una llista desplegable ampliada per triar els segments que voleu aplicar.":::

Per aplicar un segment, obriu l'informe o embut. Seleccioneu **+ Afegeix una condició** i trieu **Filtra per segment**. Trieu el segment de la llista que voleu aplicar. El segment s'aplica a l'informe. Si un gràfic no admet el segment, es mostra un error. Per obtenir més informació, vegeu [Crear i administrar informes d'embut](funnel-reports.md).
 
Podeu aplicar *fins a tres segments* a un informe o a un embut.

## <a name="edit-a-segment"></a>Editar un segment

1. Aneu a **Dades** > **Segments**.
1. Seleccioneu el segment de la llista per obrir-lo. 
1. Canvieu-ne valors o afegiu-n'hi segons calgui.
1. Seleccioneu **Desa** per aplicar els canvis.

## <a name="change-the-name-of-a-segment"></a>Canviar el nom d'un segment

1. Aneu a **Dades** > **Segments**.
1. A la llista de segments, seleccioneu **Més [...]**. 
1. A la llista desplegable, trieu **Edita el nom**.
1. Introduïu el nom nou i seleccioneu **Canvia el nom**.

## <a name="delete-a-segment"></a>Suprimir un segment

1. Aneu a **Dades** > **Segments**.
1. A la llista de segments, seleccioneu **Més [...]**. 
1. A la llista desplegable, trieu **Suprimeix**.
1. Seleccioneu **Suprimeix** per confirmar.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
