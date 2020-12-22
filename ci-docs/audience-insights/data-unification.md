---
title: Unificació de dades
description: Apreneu a unificar dades ingerides.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405131"
---
# <a name="data-unification"></a>Unificació de dades

Un cop [configurades les fonts de dades](data-sources.md), podeu unificar les dades. La unificació de dades inclou tres passos: **Assignació**, **Coincidència** i **Combinació**.

El procés d'unificació de dades us permet unificar fonts de dades dispars en un únic conjunt de dades mestre que proporciona una visualització unificada dels vostres clients. Les fases d'unificació són obligatòries i es realitzen en l'ordre següent:

1. [Assigna](map-entities.md)
2. [Match](match-entities.md)
3. [Combina](merge-entities.md)

Després de completar la unificació de dades, podeu, opcionalment,

- [configurar relacions entre entitats](relationships.md) per crear segments sofisticats
- [enriquir les dades](enrichment-hub.md) per tal d'obtenir un ampli ventall d'informació sobre els vostres clients
- [definir activitats](activities.md) d'alguns dels atributs ingerits
