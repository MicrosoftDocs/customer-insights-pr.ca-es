---
title: Cercar clients similars amb IA (previsualització) (conté vídeo)
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
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170715"
---
# <a name="find-similar-customers-with-ai-preview"></a>Cercar clients similars amb IA (previsualització)

Cerqueu clients semblants a la base de clients mitjançant la intel·ligència artificial. Necessiteu almenys un segment creat per utilitzar aquesta funció. Ampliar els criteris d'un segment existent ajuda a trobar clients similars a aquest segment.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Trobar clients* similars utilitza mitjans automatitzats per avaluar dades i fer prediccions basades en aquestes dades. Per tant, té la capacitat de ser utilitzat com a mètode d'elaboració de perfils, ja que aquest terme està definit pel Reglament General de Protecció de Dades ("GDPR"). L'ús del client d'aquesta característica per processar les dades pot estar subjecte a l'RGPD o altres lleis o regulacions. Us responsabilitzeu de garantir que l'ús del Dynamics 365 Customer Insights, incloent-hi prediccions, compleixi totes les lleis i normatives aplicables, incloent-hi la legislació relacionada amb la privadesa, les dades personals, les dades biomètriques, la protecció de dades i la confidencialitat de comunicació.

## <a name="find-similar-customers"></a>Cerca clients similars

1. Aneu a **Segments** i seleccioneu el segment en què voleu basar el segment nou. Aquest és el vostre *segment d'origen*.

1. Seleccioneu **Cerca clients similars**.

1. Reviseu el nom suggerit per al segment nou i canvieu-lo si cal.

1. Opcionalment, afegiu [etiquetes](work-with-tags-columns.md#manage-tags) al segment nou.

1. Reviseu els camps que defineixen el segment nou. Aquests camps defineixen la base en què el sistema tractarà de cercar clients semblants al vostre segment d'origen. El sistema selecciona els camps recomanats per defecte. Si cal, afegiu més camps.
  Els camps que poden reduir significativament el rendiment del model s'exclouen automàticament:
  
   - Camps amb els tipus de dades següents: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Camps amb una cardinalitat (nombre d'elements d'un camp) de menys de 2 o més de 30

1. Trieu si voleu incloure **tots els clients** excepte el segment d'origen o només els clients d'un **segment** diferent del segment nou.

1. Per defecte, el sistema suggereix incloure només el 20% de la mida del públic de destinació a la sortida. Editeu aquest llindar segons calgui. Si augmenteu el llindar, es reduirà la precisió.

1. Incloeu clients al segment d'origen seleccionant la **casella inclou membres del segment d'origen, a més de clients amb atributs** similars.

1. Seleccioneu **Executa** a la part inferior de la pàgina per iniciar una [tasca](#about-similarity-scores) de classificació binària (un mètode de Aprenentatge automàtic) que analitzi el conjunt de dades.

## <a name="view-the-similar-segment"></a>Visualitzar el segment similar

Després de processar el segment similar, trobareu el segment nou a la **pàgina Segments** amb el tipus **Expansió**.

Seleccioneu **Visualització** per veure la distribució dels resultats entre [les puntuacions](#about-similarity-scores) de similitud i els valors de la puntuació de similitud a la **previsualització** dels membres del segment.

:::image type="content" source="media/expanded-segment.png" alt-text="Segment de clients similars.":::

## <a name="manage-a-similar-segment"></a>Gestionar un segment similar

[Treballeu i gestioneu un segment](segments.md#manage-existing-segments) similar al que feu amb altres segments. Per exemple, exporteu el segment o creeu una mesura.

Editeu, actualitzeu, canvieu el nom, baixeu i suprimiu un segment similar. L'edició d'un segment similar torna a processar les dades. El segment creat prèviament s'actualitza amb les dades actualitzades.

## <a name="about-similarity-scores"></a>Quant a les puntuacions de similitud

El model d'aprenentatge automàtic de classificació binària assigna una puntuació als clients al segment semblant. La puntuació es basa en la similitud amb els clients del segment d'origen.

- Les puntuacions de similitud per sota de 0,55 són clients que el sistema ha classificat com a *no similars* als clients del segment d'origen
- Les puntuacions de similitud entre 0,55-0,7 es classifiquen com a *força semblants*
- Les puntuacions de similitud entre 0,7-0,85 es classifiquen com a *semblants*
- Les puntuacions de similitud entre 0,85-1 són clients que el sistema ha classificat com a *molt semblants*

Els clients amb resultats de similitud per sota de 0,4 no s'inclouen a la sortida del model. El sistema no els considera prou semblants al segment d'origen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
