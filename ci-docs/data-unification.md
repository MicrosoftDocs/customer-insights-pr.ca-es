---
title: Crear una visualització unificada dels clients
description: Seguiu el procés d'unificació de dades amb les vostres dades per crear un únic conjunt de dades mestres de perfils de comptes o clients.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304415"
---
# <a name="data-unification-overview"></a>Informació general sobre la unificació de dades

Un cop [configurades les fonts de dades](data-sources.md), podeu unificar les dades. La unificació de dades us permet unificar fonts de dades un cop disparades en un únic conjunt de dades mestre que proporciona una visualització unificada d'aquestes dades.

Per als consumidors individuals (B-to-C) en què les dades se centren al voltant dels individus, la unificació proporciona una visió unificada dels vostres clients. Per als comptes d'empresa (B a B) en què les dades se centren al voltant dels comptes, la unificació proporciona una visualització unificada dels comptes. [La unificació de contactes (previsualització)](data-unification-contacts.md) permet que els contactes d'aquests comptes s'unifiquin per separat i s'associïn amb els comptes.

Les dades es poden unificar en una sola entitat o en diverses entitats.

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

El procés d'unificació assigna les dades dels clients de les vostres fonts de dades, elimina duplicats, coincideix amb les dades entre entitats i crea un perfil unificat. La unificació es realitza en el següent ordre:

1. [Camps](map-entities.md) d'origen (anteriorment anomenats Mapa): al pas dels camps d'origen, seleccioneu entitats i camps per incloure'ls en el procés d'unificació. Assigna camps a un tipus semàntic comú que descriu la finalitat del camp.

1. [Registres duplicats](remove-duplicates.md) (anteriorment part de Match): al pas de registres duplicats, opcionalment definiu regles per eliminar registres de client duplicats de cada entitat.

1. [Condicions](match-entities.md) de coincidència (anteriorment anomenat Match): al pas de condicions de coincidència, definiu regles que coincideixin amb els registres de clients entre entitats. Quan un client es troba en dues o més entitats, es crea un únic registre consolidat amb totes les columnes i dades de cada entitat.

1. [Camps](merge-entities.md) de client unificats (anteriorment anomenats Combinació): al pas dels camps de client unificats, determineu quins camps d'origen s'han d'incloure, excloure o combinar en un perfil de client unificat.  

1. [Reviseu](review-unification.md) i creeu el perfil unificat.

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

El procés d'unificació assigna les dades del compte de les fonts de dades, elimina duplicats, coincideix amb les dades entre entitats i crea un perfil unificat. La unificació es realitza en el següent ordre:

1. [Camps](map-entities.md) d'origen (abans anomenats Mapa): al pas dels camps d'origen, seleccioneu entitats i camps per incloure'ls en el procés d'unificar el compte. Assigna camps a un tipus semàntic comú que descriu la finalitat del camp.

1. [Registres duplicats](remove-duplicates.md) (anteriorment part de Match): al pas de duplicar registres, definiu opcionalment regles per eliminar registres de compte duplicats de cada entitat.

1. [Condicions](match-entities.md) de coincidència (anteriorment anomenat Match): al pas de condicions de coincidència, definiu regles que coincideixin amb els registres del compte entre entitats. Quan un compte es troba en dues o més entitats, es crea un únic registre consolidat amb totes les columnes i dades de cada entitat.

1. [Camps](merge-entities.md) de client unificats (anteriorment anomenats Combinació): al pas dels camps de client unificats, determineu quins camps d'origen s'han d'incloure, excloure o combinar en un perfil de client unificat.  

1. [Reviseu](review-unification.md) i creeu el perfil unificat.

Després d'unificar comptes, opcionalment [podeu unificar els contactes (previsualització)](data-unification-contacts.md) d'aquests comptes i enllaçar els contactes unificats als comptes unificats.

---

Després de completar la unificació de dades, opcionalment podeu:

- [Establir relacions entre entitats](relationships.md) per crear segments sofisticats.
- [Enriqueix les teves dades](enrichment-hub.md) per obtenir una gamma més àmplia d'estadístiques sobre els teus clients.
- [Definiu activitats](activities.md) a partir d'alguns dels atributs ingerits.
- [Construir mesures](measures.md) per comprendre millor els comportaments dels clients i el rendiment empresarial.

[!INCLUDE [footer-include](includes/footer-banner.md)]
