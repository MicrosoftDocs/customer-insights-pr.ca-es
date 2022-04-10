---
title: Crea mesures a partir de plantilles
description: Definiu mesures utilitzant plantilles per a casos d'ús comú.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359951"
---
# <a name="use-a-template-to-build-a-measure"></a>Utilitzar una plantilla per crear una mesura

Podeu utilitzar plantilles predefinides de mesures [d'ús](measures.md) comú per crear-les. Les descripcions detallades de les plantilles i una experiència guiada us ajuden a crear una mesura de manera eficient. Les plantilles es creen a partir de dades assignades de l'entitat *Activitat unificada*. Per tant, assegureu-vos que heu configurat [activitats de client](activities.md) abans de crear una mesura a partir d'una plantilla.

Per crear mesures personalitzades, consulta [Utilitzar el creador de mesures per crear mesures des de zero](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

Plantilles de mesura disponibles: 
- Valor de transacció mitjà (ATV)
- Valor total de la transacció
- Mitjana d'ingressos diaris
- Mitjana d'ingressos anuals
- Recompte de transaccions
- Punts de fidelitat obtinguts
- Punts de fidelitat bescanviats
- Balanç de punts de fidelitat
- Vida del client activa
- Duració de la subscripció a la fidelitat
- Temps des de l'última compra

## <a name="build-a-new-measure-using-a-template"></a>Crear un compàs nou mitjançant una plantilla

1. Aneu a **Mesures**.

1. Seleccioneu **Crea** i seleccioneu **Tria una plantilla**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de pantalla del menú desplegable quan es crea una mesura nova amb el la plantilla destacada.":::

1. Cerqueu la plantilla que s'ajusti a les vostres necessitats i seleccioneu **Tria la plantilla**.

1. Reviseu les dades necessàries i seleccioneu **Introducció** si teniu totes les dades col·locades.

1. A la subfinestra **Edita el nom**, definiu el nom de la mesura i l'entitat de sortida. 

1. Seleccioneu **Fet**.

1. A la secció **Definiu el període de temps**, definiu el període de temps de les dades que voleu utilitzar. Trieu si voleu que la mesura nova cobreixi tot el conjunt de dades seleccionant **Tot el temps** o si voleu que la mesura se centri en un **Període de temps específic**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de pantalla que mostra la secció de període de temps en configurar una mesura a partir d'una plantilla.":::

1. A la secció següent, seleccioneu **Afegeix dades** per triar les activitats i assignar les dades corresponents de l'entitat *Activitat unificada*.

    1. Pas 1 de 2: a **Tipus d'activitat**, trieu el tipus d'entitat que voleu utilitzar. Per a les **Activitats**, seleccioneu les entitats que voleu assignar.
    1. Pas 2 de 2: trieu l'atribut de l'entitat *Activitat unificada* per al component que requereix la fórmula. Per exemple, per al valor de Transacció mitjana, és l'atribut que representa el Valor de transacció. Per a la **Marca horària de l'activitat**, trieu l'atribut de l'entitat Activitat unificada que representi la data i l'hora de l'activitat.
   
1. Un cop l'assignació de dades s'ha completat, podeu veure l'estat com a **Completat** i el nom de les activitats i els atributs assignats.

1. Ara podeu seleccionar **Executa** per calcular els resultats de la mesura. Per refinar-la més tard, seleccioneu **Desa l'esborrany**.

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

Aquesta característica només està disponible per a les mesures creades als entorns amb clients individuals com a públic de destinació principal.

---
