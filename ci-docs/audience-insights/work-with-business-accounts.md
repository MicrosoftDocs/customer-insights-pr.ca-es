---
title: Començar a utilitzar els comptes empresarials com a públic de destinació principal
description: Obteniu més informació sobre començar a utilitzar els comptes empresarials com a públic de destinació principal al Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 88882dc727c37262c9f204fbc8049abe17bd21a3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353530"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Treballar amb comptes empresarials a les conclusions del públic

La capacitat de conclusions del públic del Dynamics 365 Customer Insights us permet configurar l'entorn per a diferents públics de destinació principals: consumidors individuals (d'empresa a consumidor) i comptes empresarials (d'empresa a empresa). Als escenaris d'empresa a consumidor, les dades se centren en individus. Per als casos d'empresa a empresa, els públics de destinació principals són comptes, organitzacions o empreses, i contactes. Aquest article us ajuda a començar a utilitzar un entorn per a comptes empresarials. Inclou les diferències en les àrees de característica de les conclusions del públic, en funció del focus del vostre entorn. Per obtenir més informació sobre les diferències, reviseu els documents de les àrees de característica. 

## <a name="create-an-environment-for-business-accounts"></a>Crear un entorn per a comptes empresarials

Els administradors poden [crear un entorn en una organització existent](create-environment.md). Un pas en el procés de creació d'un entorn nou demana als administradors quin és el públic de destinació principal de l'entorn. Si és la configuració inicial de les conclusions del públic després de comprar una llicència, una experiència guiada ajuda en la creació del primer entorn.

A continuació, podeu [ingerir dades](data-sources.md) per a comptes empresarials i contactes relacionats com a fonts de dades de tots els orígens admesos.

Després d'unificar les dades, [especifiqueu les jerarquies de comptes](relationships.md#set-up-account-hierarchies) com a part de la configuració de la relació. També podeu [configurar assignacions semàntiques](semantic-mappings.md) per connectar les entitats de contacte i compte. 

## <a name="switch-between-primary-target-audience"></a>Canviar el públic de destinació principal

Si la vostra organització manté entorns per a clients individuals i comptes empresarials, podeu utilitzar el commutador de la subfinestra esquerra per triar el públic de destinació principal.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Commutador per canviar el públic de destinació principal entre clients individuals i comptes empresarials.":::

## <a name="supported-feature-areas"></a>Àrees de característica admeses

- [Activitats](activities.md): compatibilitat amb comptes i contactes relacionats per crear activitats i mostrar-les en una cronologia.
- [Relacions](relationships.md): l'auxiliar d'activitats ajuda a crear relacions entre les entitats per tal que la visualització de compte pugui mostrar totes les activitats dels contactes. Els contactes poden desglossar-se per veure la visualització de contactes i es poden utilitzar jerarquies per a les agregacions d'activitats de compte.
- [Mesures](measures.md): admet mesures creades des del constructor de mesures amb un càlcul. Una configuració opcional permet l'agrupació de subcomptes quan es creen mesures.
- [Segments](segments.md): és compatible amb els segments creats de zero amb el creador de segments. Els nous operadors permeten incorporar la jerarquia de comptes a l'hora de crear segments.
- [Ingesta de dades](data-sources.md): totes les característiques d'aquesta àrea són les mateixes per als comptes empresarials i per als clients individuals.
- [Unificació de dades](data-unification.md): totes les característiques d'aquesta àrea són les mateixes per als comptes empresarials i per als clients individuals.
- [Enriquiment](enrichment-hub.md): alguns tipus d'enriquiment només estan disponibles per a escenaris de clients individuals i altres només estan disponibles per als comptes empresarials.
- [Prediccions i models estàndard](predictions-overview.md): la predicció de cancel·lació de transaccions conté passos addicionals per als comptes empresarials. Altres predictions només estan disponibles per a clients individuals.
- [Activació i exportació](export-destinations.md): les exportacions estan disponibles per a comptes empresarials i clients individuals. Per a algunes exportacions, cal que la configuració addicional i la informació de contacte projectada als segments subjacents sigui vàlida per als comptes empresarials.
- [Configuració del sistema](system.md) i [administració de dades](permissions.md): totes les característiques d'aquesta àrea són les mateixes per als comptes empresarials i per als clients individuals.

