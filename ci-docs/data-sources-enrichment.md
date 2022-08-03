---
title: Enriquiment per a fonts de dades (visualització prèvia)
description: Enriquir les fonts de dades abans de passar pel procés d'unificació de dades.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207171"
---
# <a name="enrichment-for-data-sources-preview"></a>Enriquiment per a fonts de dades (visualització prèvia)

Utilitzeu dades de fonts com Microsoft i altres socis per enriquir les dades dels vostres clients abans de la unificació de dades. Font de dades enriquiments ajuden a produir una major integritat i qualitat de les dades que poden ajudar a obtenir millors resultats un cop unifiqueu les dades. Per exemple, l'ús d'un format normalitzat i estandarditzat per a les adreces augmenta la qualitat dels resultats de la coincidència. Per obtenir una llista d'enriquiments compatibles, vegeu [les opcions d'enriquiment font de dades admeses](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Enriquir una font de dades

Heu de tenir permisos [de col·laborador o d'administrador](permissions.md) per crear o editar enriquiments.  

1. Aneu a **Unificar dades** > **·**. Seleccioneu l'entitat que voleu enriquir i seleccioneu un atribut com a [clau](map-entities.md#select-primary-key-and-semantic-type-for-attributes) principal per a l'entitat.

1. Aneu a **Dades** > **Fonts de dades**.

1. Selecciona l'el·lipsi vertical (&vellip;) que hi ha al costat de la font de dades vols enriquir i selecciona **Enrich**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Pàgina de fonts de dades amb Enrich ressaltat":::

   La **pestanya Discover** mostra les opcions [d'enriquiment](#supported-data-source-enrichments) font de dades admeses.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Pàgina d'enriquiment de fonts de dades.":::

1. Seleccioneu **Enriqueix les meves dades** per configurar un enriquiment font de dades. El nom de l'entitat de sortida s'emplena automàticament.

## <a name="supported-data-source-enrichments"></a>Enriquiments font de dades suportats

Actualment hi ha disponibles els següents enriquiments per a les fonts de dades. Revisa els passos detallats per a l'enriquiment per aprendre a configurar-lo.

- [Adreces millorades](enrichment-enhanced-addresses.md)
- [Dades d'empresa millorades](enrichment-enhanced-company-data.md)
- [Dades d'identitat de LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Gestionar els enriquiments font de dades existents

Aneu a **Dades** > **Enriquiment**. A la **pestanya Els meus enriquiments**, visualitzeu els enriquiments configurats, el seu estat, el nombre de clients enriquits i l'última vegada que es van actualitzar les dades. Podeu ordenar la llista d'enriquiments per qualsevol columna o utilitzar el quadre de cerca per trobar l'enriquiment que voleu gestionar.

Seleccioneu l'enriquiment per veure les opcions disponibles. També podeu seleccionar els punts suspensius verticals (&vellip;) en un element de llista per veure les opcions.

Podeu veure, editar, executar o suprimir un enriquiment font de dades. Per obtenir més informació, vegeu [Administrar els enriquiments existents](enrichment-hub.md#manage-existing-enrichments).
