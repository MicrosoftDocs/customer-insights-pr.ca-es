---
title: Informació general sobre la unificació de dades
description: Feu el procés d'unificació de dades amb les vostres dades per crear un únic conjunt de dades de perfils de clients unificats.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 0dbc3b2c75365e94758a1b6330e8cb557e6bd768
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082213"
---
# <a name="data-unification-overview"></a>Informació general sobre la unificació de dades

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Un cop [configurades les fonts de dades](data-sources.md), podeu unificar les dades. La unificació de dades us permet unificar fonts de dades una vegada dispars en un únic conjunt de dades mestre que proporciona una visualització unificada d'aquestes dades. Per als consumidors individuals (B-to-C) on les dades se centren en individus, la unificació proporciona una visió unificada dels vostres clients. En el cas dels comptes d'empresa (B a B) en què les dades se centren en els comptes, la unificació proporciona una visualització unificada dels comptes.

Les dades es poden unificar en una sola entitat o en diverses entitats. La unificació es realitza en el següent ordre:

1. [Camps](map-entities.md) d'origen (anteriorment anomenat Mapa): al pas de camps d'origen, seleccioneu entitats i camps que voleu incloure al procés d'unificació. Assigna camps a un tipus semàntic comú que descrigui el propòsit del camp.

1. [Registres duplicats](remove-duplicates.md) (anteriorment part de Match): al pas de registres duplicats, opcionalment definiu regles per suprimir registres de client duplicats de cada entitat.

1. [Condicions](match-entities.md) de coincidència (anteriorment anomenades Coincidència): al pas de condicions coincidents, definiu regles que coincideixin amb els registres de clients entre entitats. Quan es troba un client en dues o més entitats, es crea un únic registre consolidat amb totes les columnes i dades de cada entitat.

1. [Camps](merge-entities.md) de client unificats (anteriorment anomenats Merge): al pas de camps de client unificats, determineu quins camps d'origen s'han d'incloure, excloure o combinar en un perfil de client unificat.  

1. [Revisa](review-unification.md) i crea el perfil unificat.

Després de completar la unificació de dades, opcionalment podeu:

- [Configureu relacions entre entitats](relationships.md) per crear segments sofisticats.
- [Enriquiu les vostres dades](enrichment-hub.md) per obtenir una gamma més àmplia d'estadístiques sobre els vostres clients.
- [Definir activitats](activities.md) a partir d'alguns dels atributs ingerits.
- [Construir mesures](measures.md) per comprendre millor el comportament dels clients i el rendiment del negoci.

[!INCLUDE [footer-include](includes/footer-banner.md)]
