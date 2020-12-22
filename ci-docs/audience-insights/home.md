---
title: Pàgina inicial de les conclusions del públic
description: Comenceu a explorar l'aplicació a la pàgina inicial.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405153"
---
# <a name="create-a-new-environment"></a>Crea un entorn nou

## <a name="create-a-trial-environment"></a>Crear un entorn de prova

Podeu registrar-vos en una prova a la [pàgina de registre en una prova](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Les proves caduquen després de 30 dies.

1. Trieu l'opció **Registra'm en una prova gratuïta** i seleccioneu **Registra'm ara**.

1. Proporcioneu la vostra adreça de correu electrònic laboral o acadèmica, doneu-nos més informació sobre vós i seleccioneu **Següent**.

1. Proporcioneu un **Nom** per al vostre nou entorn. 

1. Seleccioneu el tipus de prova.

1. Trieu la **Regió** per al vostre entorn.

1. De manera opcional, per als administradors d'una organització del Dynamics 365: seleccioneu **Configuració avançada** i proporcioneu l'URL de la vostra organització per utilitzar funcions de predicció com la cancel·lació dels clients.

1. Seleccioneu **Crea**. 

Després de crear l'entorn, veureu l'entorn **Demostració** que us permet explorar l'aplicació amb dades fictícies. Podeu canviar les dades d'exemple perquè coincideixin amb el vostre sector. Seleccioneu la icona **Configuració** a la capçalera i seleccioneu **Configuració de la demostració**. A més, podeu canviar el tema visual. 

[Canvieu a l'entorn](#change-between-environments) creat durant el procés de registre per treballar amb les vostres pròpies dades.

## <a name="create-a-new-production-or-sandbox-environment"></a>Crear un entorn de producció o d'espai aïllat nou

Al vostre entorn, seleccioneu la icona **Configuració** a la capçalera i seleccioneu **Entorn nou**.

Seguiu els passos com si [creéssiu un entorn de prova](#create-a-trial-environment). Obtindreu una opció addicional quan seleccioneu **Configuració avançada** per emmagatzemar les vostres dades al vostre propi Azure Data Lake. Proporcioneu el vostre nom del compte i clau del compte per establir una connexió amb el vostre Azure Data Lake. Per defecte, les dades s'emmagatzemen al llac de dades administrat pel Customer Insights.

> [!IMPORTANT]
> En desar les dades al vostre Azure Data Lake Storage, accepteu que es transferiran i s'emmagatzemaran a la ubicació geogràfica adequada per al compte d'emmagatzematge de l'Azure, que pot diferir de la ubicació on s'emmagatzemen les dades al Dynamics 365 Customer Insights. [Més informació al Centre de confiança de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorar la pàgina inicial

Podeu [accedir al vostre entorn de Customer Insights](https://home.ci.ai.dynamics.com/) mitjançant l'adreça URL següent: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
La pàgina **Inici** mostra un resum de la base de clients i les mètriques clau per fer un seguiment de l'estat de la vostra empresa.

> [!div class="mx-imgBorder"] 
> ![Informació a la pàgina Inici](media/home-page-insights.png "Informació a la pàgina Inici")

A **Segments recents**, veureu grups de clients en funció d'atributs demogràfics, conductuals o transaccionals que heu definit. [Crear segments](segments.md) us ajuda a orientar millor les vostres activitats empresarials.

**Mesures recents** mostra peces amb [mesures](measures.md). Les mesures són indicadors clau de rendiment (KPI) que heu definit. Per exemple, la probabilitat mitjana d'abandonament dels clients o la despesa mitjana en línia per client.

La secció **Enriquiments recents** mostra els resultats de les execucions d'enriquiment que s'han completat recentment. Els enriquiments afegeixen informació sobre la base de clients. Per exemple, podeu entendre els interessos i les marques amb les quals tenen afinitat. Aquesta informació es pot desbloquejar mitjançant les capacitats d'[enriquiment](enrichment-microsoft-graph.md), després de completar les fases d'[assignació](map-entities.md), [coincidència](match-entities.md) i [combinació](merge-entities.md).

## <a name="change-between-environments"></a>Canviar entre entorns

Un cop configurades les [fonts de dades](data-sources.md), voldreu canviar d'un entorn de demostració a un entorn en directe. Amb l'entorn de producció podeu treballar amb les vostres pròpies dades de clients. Seleccioneu el control **Entorn** a la part superior dreta de la pàgina per canviar d'entorns.

> [!div class="mx-imgBorder"] 
> ![Canvia l'entorn](media/home-page-environment-switcher.png "Canvia l'entorn")

Els administradors poden crear i administrar [diversos entorns](manage-environments.md). Mantenir més d'un entorn pot ser útil si, per exemple, l'organització opera internacionalment i heu de separar les dades i la informació de diverses maneres.

## <a name="next-step"></a>Pas següent

Per veure la informació a la pàgina inicial, primer heu d'[afegir fonts de dades](data-sources.md) i [unificar](data-unification.md) les dades per tal de crear perfils de client.
