---
title: Visió general de les mesures
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
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245361"
---
# <a name="measures-overview"></a>Visió general de les mesures

Les mesures us ajuden a comprendre millor els comportaments dels clients i el rendiment empresarial. Miren els valors rellevants dels [perfils unificats](data-unification.md). Per exemple, una empresa vol veure la *despesa total per client* per comprendre l'historial de compra d'un client individual o mesurar les *vendes totals de l'empresa* per comprendre els ingressos del nivell agregat de tot el negoci.

Creeu mesures per planificar les activitats empresarials consultant les dades dels clients i extraient informació. Per exemple, creeu una mesura de la despesa total per client *i* de *la rendibilitat total per client* per ajudar a identificar un grup de clients amb una despesa elevada però una rendibilitat elevada. A continuació, [creeu un segment](segments.md) basat en aquestes mesures per impulsar les properes millors accions.

## <a name="create-a-measure"></a>Crear una mesura

Trieu com voleu crear una mesura en funció del vostre públic objectiu.

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

- Des de zero amb el creador de mesures: [Construeix el teu propi](measure-builder.md).
- A partir de mesures d'ús comú: [Utilitzeu plantilles](measure-templates.md) predefinides.

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

Des de zero amb el creador de mesures: [Construeix el teu propi](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Gestionar les mesures existents

Aneu a la **pàgina Mesures** per veure les mesures que heu creat, el seu estat, el tipus de mesura i l'última vegada que es van actualitzar les dades. Podeu ordenar la llista de mesures per qualsevol columna o utilitzar el quadre de cerca per trobar la mesura que voleu gestionar.

Seleccioneu al costat d'una mesura per veure les accions disponibles. Seleccioneu el nom de la mesura per previsualitzar la sortida i baixar un fitxer CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Accions per administrar mesures individuals."lightbox="media/measures-actions.png":::

- **Editeu** la mesura per canviar-ne les propietats.
- **Actualitzeu** la mesura per incloure les dades més recents.
- **Canvieu el nom** de la mesura.
- **Activar** o **Desactivar** la mesura. Les mesures inactives no s'actualitzaran durant una [actualització](schedule-refresh.md) programada i tindran l'estat **com** a **Omès**, cosa que indica que ni tan sols s'ha intentat actualitzar.
- **Etiqueta** per gestionar les [etiquetes](work-with-tags-columns.md#manage-tags) de la mesura.
- **Suprimiu** la mesura.
- **Columnes** per [personalitzar les columnes](work-with-tags-columns.md#customize-columns) que es mostren.
- **Filtrar** per [filtrar a les etiquetes](work-with-tags-columns.md#filter-on-tags).
- **Cerqueu nom** per cercar per nom de mesura.

## <a name="refresh-measures"></a>Mesures d'actualització

Les mesures es poden actualitzar amb una programació automàtica o actualitzar-se manualment sota demanda. Per actualitzar manualment una o més mesures, selecciona-les i selecciona **Actualitza**. Per [programar una actualització](schedule-refresh.md) automàtica, aneu a **Planificació del sistema d'administració** > **·** > **·**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
