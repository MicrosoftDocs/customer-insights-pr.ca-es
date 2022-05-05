---
title: Segments suggerits basats en l'activitat.
description: Deixeu que l'aprenentatge automàtic trobi segments nous i interessants basats en l'activitat del client.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 85c3cef3a8d531b31b64a7e5decbdc122c4383fc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642329"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segments suggerits basats en les dades d'activitat (versió preliminar)

Descobriu segments rellevants dels clients segons les dades d'activitat del client que s'incorporen al Customer Insights. Alguns exemples de dades d'activitat són transaccions, duració de les trucades de suport, compres o devolucions. Per suggerir segments, les dades d'activitats s'analitzen per aconseguir una recuperació, una freqüència i un valor monetari (o una duració). O bé, es poden generar [segments suggerits per millorar una mesura o comprendre millor què influeix en un atribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Pestanya de segments suggerits que mostra els suggeriments de segments per a segments basats en l'activitat i basats en atributs.":::

## <a name="categorize-customers-by-activity"></a>Classificar els clients per activitat

Amb les [dades d'activitat](activities.md) disponibles al Customer Insights, podem generar suggeriments que representin grups de clients:

- clients més actius 
- clients que han realitzat més compres 
- clients que han generat més ingressos 
- clients que no han estat actius darrerament 
- clients que interactuen sovint amb el vostre negoci  

Si teniu una empresa minorista, podríeu esbrinar quins clients generen més ingressos i recompensar-los amb un descompte. O bé podeu identificar clients ocasionals i oferir-los que s'uneixin a un programa de recompenses per tal que visitin el vostre negoci amb més freqüència.
Si sou del sector de l'atenció sanitària, oferiu atenció sanitària públic i el vostre objectiu és minimitzar les despeses dels pacients individuals. Una manera de fer-ho podria ser reduir les visites periòdiques oferint la millor atenció possible amb el mínim de visites. En aquest cas, el vostre objectiu és mantenir la freqüència de visita baixa i reduir al mínim el cost periòdic dels pacients. O bé, podeu identificar pacients que tenen cites freqüents i uns costos periòdics alts, i analitzar aquests casos per millorar la satisfacció de cada persona. 

## <a name="required-data"></a>Dades obligatòries

Els suggeriments es generen a partir de les dades d'entrada seleccionades. 

- Perfils de client: tots els clients o membres d'un segment específic. 

- Període de temps: darrer mes, darrer any o període de temps personalitzat.

- Tipus d'activitat: compres, transaccions al detall, transaccions en línia, casos de suport al client, subscripcions, entre altres.  

- Entitat al Customer Insights que conté les dades d'activitat: l'entitat UnifiedActivity o l'entitat per a una activitat específica. 

- Les mètriques que s'inclouen són: recent, freqüència o control monetari, segons les vostres necessitats empresarials.

## <a name="generate-suggested-segments"></a>Generar segments suggerits

1. Aneu a **Segments**.

1. Seleccioneu la pestanya **Suggeriments (versió preliminar)**.

1. Seleccioneu **Cerca suggeriments nous** i trieu **Veure o anticipar el comportament del client**. Seleccioneu **Comença** per executar l'experiència guiada.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primer pas de l'auxiliar de configuració d'un segment suggerit segons l'activitat.":::

1. Proporcioneu les dades d'entrada necessàries i seleccioneu **Següent** per continuar.

   - Trieu els clients: incloeu tots els clients o un segment concret.
   - Trieu l'activitat: seleccioneu el tipus d'activitat i les entitats que descriuen l'activitat.
   - Preferències: definiu el període de temps que cal tenir en compte, els factors dels suggeriments i assigneu els atributs.

1. Reviseu les entrades i seleccioneu **Executa** per executar el model i generar suggeriments.

1. Segons el nombre de perfils de client i de les activitats seleccionades, pot trigar uns minuts a completar-se. 

Després de generar els suggeriments, podeu filtrar-los per la condició o el valor que més us interessi. 

## <a name="view-details-of-a-suggested-segment"></a>Veure els detalls del segment suggerit

Un cop generats els suggeriments, els trobareu enumerats a la secció **Segments** > **Suggeriments (versió preliminar)** a la secció **Suggeriments basats en l'activitat**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Subfinestra lateral expandida que mostra dades detallades d'un segment suggerit.":::

Seleccioneu **Vegeu el suggeriment** en un segment suggerit per visualitzar-ne els detalls. La subfinestra lateral proporciona detalls com l'extensió de cada propietat en comparació amb el grup de destinació. També destaca el nombre de membres potencials del segment i el percentatge corresponent del total de clients. Si voleu conservar el suggeriment com a segment, seleccioneu **Crea un segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Desar un suggeriment com a segment

1. Aneu a **Segments** > **Suggeriments (versió preliminar)**.

1. Seleccioneu el segment que voleu desar. 

1. A la subfinestra lateral, seleccioneu **Crea un segment**. 

1. Després de desar el segment, es mostrarà a la llista de segments a la pestanya **Tots els segments**. Ara es pot [actualitzar o suprimir com qualsevol altre segment](segments.md). No podeu editar els detalls del segment. No obstant això, podeu canviar els criteris d'entrada dels suggeriments i generar suggeriments diferents.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Actualitzar o editar un conjunt de suggeriments

1. Aneu a **Segments** > **Suggeriments (versió preliminar)** i cerqueu el segment a la secció **Suggeriments basats en l'activitat**.

1. Seleccioneu **Actualitza els suggeriments** per actualitzar els suggeriments mantenint els atributs configurats. O seleccioneu **Edita els suggeriments** per modificar els atributs configurats. El sistema tornarà a executar el procés, generarà suggeriments de segments basats en les dades més recents i substituirà els suggeriments actuals.

[!INCLUDE [footer-include](includes/footer-banner.md)]
