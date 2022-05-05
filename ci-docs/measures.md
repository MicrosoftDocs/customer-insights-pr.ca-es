---
title: Comprendre i gestionar les mesures
description: Obtén informació sobre com les mesures ajuden a analitzar i reflectir el rendiment de la teva empresa.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642264"
---
# <a name="measures-overview"></a>Visió general de les mesures

Les mesures us ajuden a comprendre millor els comportaments dels clients i el rendiment empresarial. Miren els valors rellevants dels [perfils unificats](data-unification.md). Per exemple, una empresa vol veure la *despesa total per client* per comprendre l'historial de compra d'un client individual o mesurar les *vendes totals de l'empresa* per comprendre els ingressos del nivell agregat de tot el negoci.  

Les mesures es creen [utilitzant el constructor](measure-builder.md) de mesures, una plataforma de consulta de dades amb diversos operadors i opcions d'assignació simples. Permet filtrar les dades, agrupar els resultats, detectar [rutes de relació d'entitats](relationships.md) i obtenir una visualització prèvia de la sortida. Podeu [utilitzar plantilles](measure-templates.md) predefinides per configurar de manera eficient mesures d'ús comú.

Utilitzeu el creador de mesures per planificar activitats empresarials consultant dades de clients i extreure informació. Per exemple, la creació d'una mesura de *despesa total per client* i *retorn total per client* ajuda a identificar un grup de clients amb una despesa alta però amb un retorn alt. Podeu [crear un segment](segments.md) basat en aquestes mesures per impulsar les accions més recomanades següents.

## <a name="manage-your-measures"></a>Administrar les mesures

Podeu consultar la llista de mesures a la pàgina **Mesures**.

Trobareu informació sobre el tipus de mesura, l'autor, la data de creació, l'estat i l'estat. Quan seleccioneu una mesura de la llista, podeu obtenir una visualització prèvia de la sortida i baixar un fitxer CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Accions per administrar mesures individuals."lightbox="media/measures-actions.png":::

Les accions següents estan disponibles quan seleccioneu un compàs:

- **Editeu** la configuració de la mesura.
- **Duplicar** un compàs. Podeu editar-ne les propietats immediatament o simplement desar el duplicat.
- **Actualitzeu** la mesura segons les dades més recents. Per actualitzar totes les mesures al mateix temps, seleccioneu tots els compassos i **actualitzeu**.
- **Canvieu el nom** de la mesura.
- **Activeu** o **desactiveu-la**. Les mesures inactives no s'actualitzaran durant una [actualització planificada](system.md#schedule-tab).
- **Etiqueta** per [administrar etiquetes](work-with-tags-columns.md#manage-tags) per al segment.
- **Suprimiu** la mesura.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Pas següent

Podeu utilitzar les mesures existents per crear un [segment de client](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
