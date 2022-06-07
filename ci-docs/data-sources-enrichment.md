---
title: Font de dades enriquiment
description: Enriquir les fonts de dades abans de passar pel procés d'unificació de dades.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800269"
---
# <a name="enrichment-for-data-sources-preview"></a>Enriquiment per a fonts de dades (vista prèvia)

Utilitzeu dades d'orígens com Microsoft i altres socis per enriquir les dades dels clients abans de la unificació de dades. Font de dades enriquiments ajuden a produir una major integritat i qualitat de les dades que poden ajudar a aconseguir millors resultats una vegada que unifiqueu les vostres dades. Per exemple, l'ús d'un format normalitzat i estandarditzat per a adreces augmenta la qualitat dels resultats del partit. Per obtenir una llista d'enriquiments admesos, vegeu [opcions d'enriquiment font de dades compatibles](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Enriquir una font de dades

Heu de tenir permisos de col·laborador o administrador per crear o editar enriquiments. Per obtenir més informació, vegeu [Permisos](permissions.md).  

1. Aneu a Unificació de **dades** > **·**. Seleccioneu l'entitat que voleu enriquir i seleccioneu un atribut com a clau principal per a l'entitat. Per obtenir més informació, vegeu [Seleccionar la clau principal](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu l'el·lipsi vertical (&vellip;) al costat de la font de dades voleu enriquir i seleccioneu **Enrique**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Pàgina d'enriquiment de fonts de dades.":::

   La **pestanya Descobreix** mostra les opcions d'enriquiment [font de dades compatibles](#supported-data-source-enrichments).

1. Seleccioneu **Enriqueix les meves dades** per configurar un font de dades enriquiment. El nom de l'entitat de sortida s'emplena automàticament.

## <a name="supported-data-source-enrichments"></a>Enriquiments font de dades suportats

Actualment hi ha disponibles els següents enriquiments per a fonts de dades. Reviseu els passos detallats per a l'enriquiment per aprendre a configurar-lo.

- [Adreces millorades](enrichment-enhanced-addresses.md)
- [Dades d'empresa millorades](enrichment-enhanced-company-data.md)
- [Dades d'identitat de LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Gestionar els enriquiments font de dades existents

Aneu a la pestanya **Els meus enriquiments** per veure tots els enriquiments configurats.

Seleccioneu l'enriquiment per veure les opcions disponibles. També podeu seleccionar l'el·lipsi vertical (&vellip;) en un element de llista per veure les opcions. Si heu configurat diversos enriquiments, podeu utilitzar el quadre de cerca per trobar-lo ràpidament.

Podeu veure, editar, executar o suprimir un font de dades enriquiment. Per obtenir més informació, vegeu [Gestionar els enriquiments existents](enrichment-hub.md).
