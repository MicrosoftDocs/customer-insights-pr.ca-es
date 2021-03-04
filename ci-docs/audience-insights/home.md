---
title: Pàgina inicial de les conclusions del públic
description: Comenceu a explorar l'aplicació a la pàgina inicial.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477029"
---
# <a name="create-a-new-environment"></a>Crea un entorn nou

## <a name="create-a-trial-environment"></a>Crear un entorn de prova

Podeu registrar-vos en una prova a la [pàgina de registre en una prova](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Les proves caduquen després de 30 dies.

1. Trieu l'opció **Registra'm en una prova gratuïta** i seleccioneu **Registra'm ara**.

1. Proporcioneu la vostra adreça de correu electrònic laboral o acadèmica, doneu-nos més informació sobre vós i seleccioneu **Següent**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Diàleg per registrar-se a una instància de prova":::

1. Proporcioneu un **Nom** per al vostre nou entorn. 

1. Seleccioneu el tipus de prova.

1. Trieu la **Regió** per al vostre entorn.

1. De manera opcional, per als administradors d'una organització del Dynamics 365: seleccioneu **Configuració avançada** i proporcioneu l'URL de la vostra organització per utilitzar funcions de predicció com la cancel·lació dels clients.

1. Seleccioneu **Crea**. 

Després de crear l'entorn, veureu l'entorn **Demostració** que us permet explorar l'aplicació amb dades fictícies. Podeu canviar les dades d'exemple perquè coincideixin amb el vostre sector. Seleccioneu la icona **Configuració** a la capçalera i seleccioneu **Configuració de la demostració**. A més, podeu canviar el tema visual. 

[Canvieu a l'entorn](#switch-environments) creat durant el procés de registre per treballar amb les vostres pròpies dades.

## <a name="create-a-new-production-or-sandbox-environment"></a>Crear un entorn de producció o d'espai aïllat nou

A l'entorn, seleccioneu el selector **Entorns** a la capçalera de l'aplicació i seleccioneu **Nou**.

Seguiu els passos com si [creéssiu un entorn de prova](#create-a-trial-environment). Per defecte, les dades s'emmagatzemen al llac de dades administrat pel Customer Insights. Obtindreu una opció addicional quan seleccioneu **Configuració avançada** per emmagatzemar les vostres dades al vostre propi Azure Data Lake. Proporcioneu el vostre nom del compte i clau del compte per establir una connexió amb el vostre Azure Data Lake. 

> [!IMPORTANT]
> En desar les dades al vostre Azure Data Lake Storage, accepteu que es transferiran i s'emmagatzemaran a la ubicació geogràfica adequada per al compte d'emmagatzematge de l'Azure, que pot diferir de la ubicació on s'emmagatzemen les dades al Dynamics 365 Customer Insights. [Més informació al Centre de confiança de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorar la pàgina inicial

Podeu [accedir a les conclusions del públic des del Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) a l'adreça URL següent: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
A la pàgina **Inici** es mostra una descripció general dels segments, les mesures i les dades d'enriquiment (si es configuren) després de completar les fases d'[assignació](map-entities.md), [coincidència](match-entities.md) i [combinació](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Informació a la pàgina Inici](media/home-page-insights.png "Informació a la pàgina Inici")

A **Segments recents**, veureu grups de clients en funció d'atributs demogràfics, conductuals o transaccionals que heu definit. La [creació de segments](segments.md) us ajuda a agrupar la base de clients i a adreçar-vos millor a les vostres activitats empresarials.

**Mesures recents** mostra peces amb [indicadors clau de rendiment (KPI)](measures.md) que heu definit. Per exemple, la probabilitat mitjana d'un client de cancel·lar o la despesa en línia mitjana per client.

La secció **Enriquiments recents** mostra els resultats de les execucions d'enriquiment que s'han completat recentment. Els [enriquiments](enrichment-hub.md) afegeixen informació sobre la base de clients. Per exemple, podeu entendre els interessos i les marques amb les quals tenen afinitat.

## <a name="switch-environments"></a>Canvi d'entorn

Seleccioneu el control **Entorn** a la part superior dreta de la pàgina per canviar d'entorns.

> [!div class="mx-imgBorder"] 
> ![Canvia l'entorn](media/home-page-environment-switcher.png "Canvia l'entorn")

Els administradors poden crear i administrar [diversos entorns](manage-environments.md). Mantenir més d'un entorn pot ser útil si, per exemple, l'organització opera internacionalment i heu de separar les dades i la informació de diverses maneres.

## <a name="next-step"></a>Pas següent

Per veure la informació a la pàgina inicial, primer heu d'[afegir fonts de dades](data-sources.md) i [unificar](data-unification.md) les dades per tal de crear perfils de client.


[!INCLUDE[footer-include](../includes/footer-banner.md)]