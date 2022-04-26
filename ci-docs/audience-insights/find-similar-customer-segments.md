---
title: Cercar clients similars amb IA (conté vídeo)
description: Cerqueu segments de client semblants amb la intel·ligència artificial.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 851ea2c3388de603c1beef4a58e359aa989c9c46
ms.sourcegitcommit: e129a1fa8b020b6bfb6efc3c53fa9d89e1614ad1
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "8561513"
---
# <a name="similar-customers-preview"></a>Clients semblants (versió preliminar)

Aquesta característica us permet trobar clients semblants a la base de clients mitjançant la intel·ligència artificial. Heu de tenir com a mínim un segment creat per utilitzar aquesta característica. Expandir els criteris d'un segment existent ajuda a cercar clients que siguin semblants a aquest segment.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Cerca clients similars* utilitza mitjans automatitzats per avaluar dades i fer prediccions basades en les dades, i per tant té la capacitat d'utilitzar-se com a mètode de perfilació, tal com es defineix el terme al Reglament general de protecció de dades ("RGPD"). L'ús del client d'aquesta característica per processar les dades pot estar subjecte a l'RGPD o altres lleis o regulacions. Us responsabilitzeu de garantir que l'ús del Dynamics 365 Customer Insights, incloent-hi prediccions, compleixi totes les lleis i normatives aplicables, incloent-hi la legislació relacionada amb la privadesa, les dades personals, les dades biomètriques, la protecció de dades i la confidencialitat de comunicació.

## <a name="finding-similar-customers"></a>Cercar clients semblants

1. A les conclusions del públic, aneu a **Segments** i seleccioneu el segment en què voleu basar el nou segment. Aquest és el vostre *segment d'origen*.

1. A la barra d'accions, seleccioneu **Cerca clients similars**.

1. Reviseu el nom suggerit per al segment nou i canvieu-lo si cal.

1. Opcionalment, afegiu [etiquetes](work-with-tags-columns.md#manage-tags) al segment nou.

1. Reviseu els camps que defineixen el segment nou. Aquests camps defineixen la base en què el sistema tractarà de cercar clients semblants al vostre segment d'origen. El sistema seleccionarà els camps recomanats per defecte.
  Els camps que poden reduir significativament el rendiment del model s'exclouen automàticament:
  
   - Camps amb els tipus de dades següents: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Camps amb una cardinalitat (nombre d'elements d'un camp) de menys de 2 o més de 30

1. Trieu si voleu incloure **tots els clients** o només els clients d'un **segment existent específic** al segment nou.

1. Per defecte, el sistema suggereix incloure només el 20% de la mida del públic de destinació a la sortida. Editeu aquest llindar segons calgui. Si augmenteu el llindar, es reduirà la precisió.

1. Incloeu clients al segment d'origen seleccionant la **casella Inclou membres del segment d'origen, a més de clients amb atributs** similars.

1. Seleccioneu **Executa** a la part inferior de la pàgina per iniciar una tasca de classificació binària (un mètode d'aprenentatge automàtic) que analitza el conjunt de dades.

## <a name="view-the-similar-segment"></a>Visualitzar el segment similar

Després de processar el segment similar, trobareu el nou segment a la pàgina **Segments**.

> [!div class="mx-imgBorder"]
> ![Segment de clients similars.](media/expanded-segment.png "Segment de clients similars")

Seleccioneu **Visualitza** a la barra d'accions per obrir el detall del segment. Aquesta visualització conté informació sobre la distribució dels resultats en les [puntuacions de similitud](#about-similarity-scores). També trobareu els valors de puntuació de similitud a la **Visualització prèvia dels membres del segment**.

## <a name="use-the-output-of-a-similar-segment"></a>Utilitzar la sortida d'un segment similar

Podeu [treballar amb la sortida d'un segment semblant](segments.md) com ho feu amb altres segments. Per exemple, exporteu el segment o creeu una mesura.

## <a name="refresh-and-edit-a-similar-segment"></a>Actualitzar i editar un segment similar

Per actualitzar un segment similar, seleccioneu-lo a la pàgina **Segments** i seleccioneu **Actualitza** a la barra d'accions.

En editar un segment semblant s'han de tornar a processar les dades. El segment creat prèviament s'actualitza amb les dades actualitzades.
Per editar un segment similar, seleccioneu-lo a la pàgina **Segments** i seleccioneu **Edita** a la barra d'accions. Apliqueu els canvis i seleccioneu **Executa** per iniciar el processament.

## <a name="delete-a-similar-segment"></a>Suprimir un segment similar

Seleccioneu el segment a la pàgina **Segments** i seleccioneu **Suprimeix** a la barra d'accions. A continuació, confirmeu la supressió.

## <a name="about-similarity-scores"></a>Quant a les puntuacions de similitud

El model d'aprenentatge automàtic de classificació binària assigna una puntuació als clients al segment semblant. La puntuació es basa en la similitud amb els clients del segment d'origen.

- Les puntuacions de similitud per sota de 0,55 són clients que el sistema ha classificat com a *no similars* als clients del segment d'origen
- Les puntuacions de similitud entre 0,55-0,7 es classifiquen com a *força semblants*
- Les puntuacions de similitud entre 0,7-0,85 es classifiquen com a *semblants*
- Les puntuacions de similitud entre 0,85-1 són clients que el sistema ha classificat com a *molt semblants*

Els clients amb resultats de similitud per sota de 0,4 no s'inclouen a la sortida del model. El sistema no els considera prou semblants al segment d'origen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
