---
title: Segments suggerits en funció de l'activitat (visualització prèvia)
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
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170577"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Segments suggerits en funció de l'activitat (visualització prèvia)

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
Si proporciones assistència sanitària pública i el teu objectiu és minimitzar les despeses per a pacients individuals, podries intentar reduir les visites recurrents proporcionant la millor atenció possible en el menor nombre de visites possible. En aquest cas, el vostre objectiu és mantenir la freqüència de visita baixa i reduir al mínim el cost periòdic dels pacients. O bé, podeu identificar pacients que tenen cites freqüents i uns costos periòdics alts, i analitzar aquests casos per millorar la satisfacció de cada persona.

## <a name="required-data"></a>Dades obligatòries

Els suggeriments es generen a partir de les dades d'entrada seleccionades.

- Perfils de client: tots els clients o membres d'un segment específic.

- Període de temps: darrer mes, darrer any o període de temps personalitzat.

- Tipus d'activitat: compres, transaccions al detall, transaccions en línia, casos de suport al client, subscripcions, entre altres.  

- Entitat al Customer Insights que conté les dades d'activitat: l'entitat UnifiedActivity o l'entitat per a una activitat específica.

- Les mètriques que s'inclouen són: recent, freqüència o control monetari, segons les vostres necessitats empresarials.

## <a name="generate-suggested-segments"></a>Generar segments suggerits

1. Aneu a **Segments** i seleccioneu la **pestanya Suggeriments (previsualització).**

1. Seleccioneu **Cerca suggeriments nous** i trieu **Veure o anticipar el comportament del client**. Seleccioneu **Inicia**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primer pas de l'auxiliar de configuració d'un segment suggerit segons l'activitat.":::

1. Proporcioneu les dades d'entrada necessàries i seleccioneu **Següent**.

   - Trieu els clients: incloeu tots els clients o un segment concret.
   - Trieu l'activitat: seleccioneu el tipus d'activitat i les entitats que descriuen l'activitat.
   - Preferències: definiu el període de temps que cal tenir en compte, els factors dels suggeriments i assigneu els atributs.

1. Reviseu les entrades i seleccioneu **Executa** per executar el model i generar suggeriments.

Segons el nombre de perfils de client i de les activitats seleccionades, pot trigar uns minuts a completar-se.

Després de generar els suggeriments, podeu filtrar-los per la condició o el valor que més us interessi.

## <a name="manage-suggested-segments"></a>Gestionar els segments suggerits

Aneu a **Segments** i seleccioneu la **pestanya Suggeriments (previsualització).** A la **secció Suggeriments basats** en activitat, seleccioneu un segment suggerit per veure les accions disponibles.

- **Vegeu suggeriments** per veure els detalls d'aquest segment, com ara l'extensió de cada dimensió en comparació amb el grup objectiu. També destaca el nombre de membres potencials del segment i el percentatge corresponent del total de clients.
- **Creeu un segment** per desar el suggerit com a segment. Es mostra a la **pestanya Tots els segments** i es [pot actualitzar o suprimir](segments.md). No podeu editar els detalls del segment. No obstant això, podeu canviar els criteris d'entrada dels suggeriments i generar suggeriments diferents.
- **Editeu suggeriments** per modificar els atributs configurats que substituiran els suggeriments actuals.
- **Actualitzeu els suggeriments** per actualitzar els suggeriments mantenint els atributs configurats.

[!INCLUDE [footer-include](includes/footer-banner.md)]
