---
title: Crear mesures a partir de plantilles
description: Definir mesures mitjançant plantilles per a casos d'ús comú.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170761"
---
# <a name="create-measures-from-templates"></a>Crear mesures a partir de plantilles

Utilitzeu plantilles predefinides de mesures [d'ús](measures.md) comú per crear-les. Les plantilles es creen a partir de dades assignades de l'entitat *Activitat unificada*. Per tant, assegureu-vos que heu configurat [activitats de client](activities.md) abans de crear una mesura a partir d'una plantilla.

Les plantilles de mesura només s'admeten en entorns per a **clients individuals**. Per crear mesures personalitzades o crear mesures per a B a B, vegeu [Utilitzar el creador de mesures](measure-builder.md).

Plantilles de mesura disponibles:
- Valor de transacció mitjà (ATV)
- Valor total de la transacció
- Mitjana d'ingressos diaris
- Mitjana d'ingressos mensuals
- Mitjana d'ingressos anuals
- Recompte de transaccions
- Punts de fidelitat obtinguts
- Punts de fidelitat bescanviats
- Balanç de punts de fidelitat
- Vida del client activa
- Duració de la subscripció a la fidelitat
- Temps des de l'última compra

## <a name="build-a-new-measure-using-a-template"></a>Creeu una mesura nova mitjançant una plantilla

1. Anar a **Mesures**.

1. Seleccioneu **Crea** i seleccioneu **Tria una plantilla**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de pantalla del menú desplegable quan es crea una mesura nova amb el la plantilla destacada.":::

1. Cerqueu la plantilla que s'ajusti a les vostres necessitats i seleccioneu **Tria la plantilla**.

1. Reviseu les dades necessàries i seleccioneu **Introducció** si teniu totes les dades col·locades.

1. Seleccioneu **Edita els detalls** al costat de Nom de la mesura. Proporcioneu un nom per a la mesura. Opcionalment, afegiu [etiquetes](work-with-tags-columns.md#manage-tags) a la mesura.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Edita els detalls del quadre de diàleg.":::

1. Seleccioneu **Fet**.

1. A la secció Defineix el **període de** temps, definiu el període de temps de les dades. Trieu si voleu que la mesura nova cobreixi tot el conjunt de dades seleccionant **Tot el temps** o si voleu que la mesura se centri en un **Període de temps específic**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de pantalla que mostra la secció de període de temps en configurar una mesura a partir d'una plantilla.":::

1. A la secció següent, seleccioneu **Afegeix dades** per triar les activitats i assignar les dades corresponents de l'entitat *Activitat unificada*.

    1. Pas 1 de 2: a **Tipus d'activitat**, trieu el tipus d'entitat que voleu utilitzar. Per a **Activitats**, seleccioneu les entitats que voleu assignar i, a continuació, seleccioneu **Següent**.
    1. Pas 2 de 2: trieu l'atribut de l'entitat *Activitat unificada* per al component que requereix la fórmula. Per exemple, per al valor de Transacció mitjana, és l'atribut que representa el Valor de transacció. Per a **marca de temps de l'activitat**, trieu l'atribut de l'entitat *Activitat* unificada que representa la data i l'hora de l'activitat.
    1. Seleccioneu **Desa**.

    Quan l'assignació de dades és correcta, l'estat mostra **Complet** i es mostra el nom de les activitats i atributs mapejats.

1. Seleccioneu **Executa** per calcular els resultats de la mesura. Seleccioneu **Desa l'esborrany** si voleu mantenir la configuració actual i executar la mesura més endavant. Es **mostra la pàgina Mesures**.

## <a name="next-step"></a>Pas següent

Utilitzeu les mesures existents per crear [un segment](segments.md) de clients.

[!INCLUDE [footer-include](includes/footer-banner.md)]
