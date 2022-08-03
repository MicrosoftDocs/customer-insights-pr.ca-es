---
title: Informació general sobre la unificació de dades
description: Seguiu el procés d'unificació de dades amb les vostres dades per crear un conjunt de dades únic de perfils de clients unificats.
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
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139463"
---
# <a name="data-unification-overview"></a>Informació general sobre la unificació de dades

Un cop [configurades les fonts de dades](data-sources.md), podeu unificar les dades. La unificació de dades us permet unificar fonts de dades un cop disparades en un únic conjunt de dades mestre que proporciona una visualització unificada d'aquestes dades. Per als consumidors individuals (B-to-C) en què les dades se centren al voltant dels individus, la unificació proporciona una visió unificada dels vostres clients. Per als comptes d'empresa (B a B) en què les dades se centren al voltant dels comptes, la unificació proporciona una visualització unificada dels comptes.

Les dades es poden unificar en una sola entitat o en diverses entitats. La unificació es realitza en el següent ordre:

1. [Camps](map-entities.md) d'origen (anteriorment anomenats Mapa): al pas dels camps d'origen, seleccioneu entitats i camps per incloure'ls en el procés d'unificació. Assigna camps a un tipus semàntic comú que descriu la finalitat del camp.

1. [Registres duplicats](remove-duplicates.md) (anteriorment part de Match): al pas de registres duplicats, opcionalment definiu regles per eliminar registres de client duplicats de cada entitat.

1. [Condicions](match-entities.md) de coincidència (anteriorment anomenat Match): al pas de condicions de coincidència, definiu regles que coincideixin amb els registres de clients entre entitats. Quan un client es troba en dues o més entitats, es crea un únic registre consolidat amb totes les columnes i dades de cada entitat.

1. [Camps](merge-entities.md) de client unificats (anteriorment anomenats Combinació): al pas dels camps de client unificats, determineu quins camps d'origen s'han d'incloure, excloure o combinar en un perfil de client unificat.  

1. [Reviseu](review-unification.md) i creeu el perfil unificat.

Després de completar la unificació de dades, opcionalment podeu:

- [Establir relacions entre entitats](relationships.md) per crear segments sofisticats.
- [Enriqueix les teves dades](enrichment-hub.md) per obtenir una gamma més àmplia d'estadístiques sobre els teus clients.
- [Definiu activitats](activities.md) a partir d'alguns dels atributs ingerits.
- [Construir mesures](measures.md) per comprendre millor els comportaments dels clients i el rendiment empresarial.

[!INCLUDE [footer-include](includes/footer-banner.md)]
