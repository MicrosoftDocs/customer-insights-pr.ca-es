---
title: Treballar amb comptes d'empresa
description: Obteniu informació sobre els comptes empresarials com a públic objectiu principal a Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303904"
---
# <a name="work-with-business-accounts"></a>Treballar amb comptes d'empresa

Us Dynamics 365 Customer Insights permet configurar l'entorn per a diferents públics objectiu principals: consumidors individuals (B a C) i comptes empresarials (de B a B). Als escenaris d'empresa a consumidor, les dades se centren en individus. Per als casos d'empresa a empresa, els públics de destinació principals són comptes, organitzacions o empreses, i contactes. Aquest article us ajuda a començar a utilitzar un entorn per a comptes empresarials. Enumera les diferències per a les àrees de característiques del Customer Insights, en funció de l'enfocament de l'entorn. Per obtenir més informació sobre les diferències, reviseu els documents de les àrees de característica. 

## <a name="create-an-environment-for-business-accounts"></a>Crear un entorn per a comptes empresarials

Els administradors poden [crear un entorn en una organització existent](create-environment.md). Un pas en el procés de creació d'un entorn nou demana als administradors quin és el públic de destinació principal de l'entorn. En cas que sigui la configuració inicial després de comprar una llicència, una experiència guiada ajuda a la creació del primer entorn.

A continuació, podeu [ingerir dades](data-sources.md) per a comptes empresarials i contactes relacionats com a fonts de dades de tots els orígens admesos.

 [Unifiqueu les](data-unification.md) dades del compte seguides de les dades de contacte per connectar les entitats de contacte i compte.

## <a name="switch-between-primary-target-audience"></a>Canviar el públic de destinació principal

Si la vostra organització manté entorns per a clients individuals i comptes empresarials, podeu utilitzar el commutador de la subfinestra esquerra per triar el públic de destinació principal.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Commutador per canviar el públic de destinació principal entre clients individuals i comptes empresarials.":::

## <a name="supported-feature-areas"></a>Àrees de característica admeses

- [Activitats](activities.md): compatibilitat amb comptes i contactes relacionats per crear activitats i mostrar-les en una cronologia.
- [Relacions](relationships.md): l'auxiliar d'activitats ajuda a crear relacions entre les entitats per tal que la visualització de compte pugui mostrar totes les activitats dels contactes. Els contactes poden desglossar-se per veure la visualització de contactes i es poden utilitzar jerarquies per a les agregacions d'activitats de compte.
- [Mesures](measures.md): admet mesures creades des del constructor de mesures amb un càlcul. Una configuració opcional permet l'agrupació de subcomptes quan es creen mesures.
- [Segments](segments.md): és compatible amb els segments creats de zero amb el creador de segments. Els segments es poden basar en comptes o contactes.
- [Ingesta de dades](data-sources.md): totes les característiques d'aquesta àrea són les mateixes per als comptes empresarials i per als clients individuals.
- La unificació de dades B-to-B és molt similar a la unificació de dades de B a C, però té un pas addicional per unificar els contactes després de la unificació del compte. Vegeu [Comptes d'empresa (B-to-B)](data-unification.md).
- [Enriquiment](enrichment-hub.md): alguns tipus d'enriquiment només estan disponibles per a escenaris de clients individuals i altres només estan disponibles per als comptes empresarials.
- [Prediccions i models estàndard](predictions-overview.md): la predicció de cancel·lació de transaccions conté passos addicionals per als comptes empresarials. Altres predictions només estan disponibles per a clients individuals.
- [Activació i exportació](export-destinations.md): les exportacions estan disponibles per a comptes empresarials i clients individuals. Per a algunes exportacions, cal que la configuració addicional i la informació de contacte projectada als segments subjacents sigui vàlida per als comptes empresarials.
- [Configuració del sistema](system.md) i [administració de dades](permissions.md): totes les característiques d'aquesta àrea són les mateixes per als comptes empresarials i per als clients individuals.

[!INCLUDE [footer-include](includes/footer-banner.md)]
