---
title: Segments suggerits basats en mesures (previsualització)
description: Deixeu que l'aprenentatge automàtic us ajudi a trobar segments nous i interessants en funció dels atributs del client.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170945"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Segments suggerits basats en mesures (previsualització)

Descobriu segments interessants dels vostres clients amb l'ajuda d'un model d'IA. Aquesta característica basada en aprenentatge automàtic suggereix segments segons mesures o atributs del client. Pot ajudar a millorar els indicadors clau de rendiment (KPI) o entendre millor la influència dels atributs en el context d'altres atributs.

> [!NOTE]
> La funció de segments suggerits utilitza mitjans automatitzats per avaluar dades i fer prediccions basades en aquestes dades. Per tant, té la capacitat de ser utilitzat com a mètode d'elaboració de perfils, ja que aquest terme està definit pel Reglament General de Protecció de Dades ("GDPR"). L'ús d'aquesta característica per processar dades pot estar subjecte a l'RGPD o altres lleis o normatives. Us responsabilitzeu de garantir que l'ús del Dynamics 365 Customer Insights, incloent-hi aquesta característica, compleixi totes les lleis i normatives aplicables, incloent-hi la legislació relacionada amb la privadesa, les dades personals, les dades biomètriques, la protecció de dades i la confidencialitat de comunicació.

:::image type="content" source="media/suggested-segments.png" alt-text="Pàgina de segments suggerits que mostra els detalls d'un suggeriment en una subfinestra lateral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segments suggerits per millorar els KPI

Si utilitzeu [mesures creades](measures.md) per fer el seguiment dels KPI, creeu segments per veure les influències al KPI. Podeu utilitzar aquesta informació per publicar una campanya molt orientada.

Per exemple, feu el seguiment d'una mesura anomenada *TotalSpendPerCustomer*. Com a empresa, voleu que aquest nombre creixi. Si trieu una mesura com a atribut principal, seleccioneu els atributs que voleu avaluar per influir-hi. Suposem que són *nivell de subscripció*, *període de subscripció* i *ocupació*. A continuació, el Customer Insights pot suggerir un segment que us indica qui és la influència més important d'aquesta mesura. Per exemple, els *comptables* que són membres d'*or* i que han estat amb el vostre negoci durant *almenys cinc anys* són la influència més important de *TotalSpendPerCustomer*. Obtindreu una mida de segment estimada per a cada suggeriment. Podeu utilitzar aquesta informació per crear campanyes per als públics objectiu.

## <a name="understand-what-influences-a-customer-attribute"></a>Comprendre la influència d'un atribut de client

Podeu triar un atribut de client en lloc d'una mesura com a atribut principal. Segons la vostra opció d'atributs influents, el model d'IA crea una sèrie de suggeriments que mostren com influeixen els atributs seleccionats en l'atribut principal.

Per exemple, trieu *Membre de recompenses (Sí/No)* com a atribut principal. *Antiguitat*, *Ocupació* i *Nombre de sol·licituds d'assistència tècnica* es defineixen com altres atributs que influeixen. El model d'IA podria suggerir segments que indiquen que principalment els professionals de IT amb una antiguitat superior als dos anys són membres de recompenses. Un altre suggeriment podria ressaltar que els comptables amb una antiguitat de més d'un any i menys de tres sol·licituds d'assistència tècnica són membres de recompenses.

## <a name="artificial-intelligence-usage"></a>Ús d'intel·ligència artificial

Mitjançant l'atribut principal i els atributs que influeixen, un algorisme d'arbre de decisions suggereix segments interessants. Els suggeriments es basen en regles o patrons recollits per l'algorisme d'IA. Només es mostren com a suggeriments els segments que difereixen significativament de la població mitjana. La comparació amb la població mitjana es basa en la mesura o l'atribut principal seleccionat.

### <a name="responsible-ai"></a>IA responsable

Amb els segments suggerits, seleccioneu atributs per crear segments nous i processar les dades que seleccioneu. A l'hora de triar els atributs, incloent-hi els atributs confidencials, com ara la raça, l'orientació sexual o el gènere, heu de garantir que podeu i heu de processar aquestes dades. Sou el responsable de complir les lleis aplicables a la vostra organització i complir els principis i les normes de privadesa de la vostra organització.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Resultats diferents per als atributs principals amb valors categòrics i numèrics

Els suggeriments de segment són diferents si trieu un atribut numèric o un atribut categòric com a atribut principal. Els valors d'un atribut categòric contenen dues o més categories o tipus. Un atribut numèric conté dades quantitatives i té una gran quantitat de mesura associada.

Amb un atribut numèric com *ingressos anuals* o *període de subscripció* com a atribut principal, el sistema suggereix segments que tenen un valor mitjà superior o inferior a l'atribut numèric en comparació amb tots els clients.

Un atribut categòric, com ara la *satisfacció del client* com a atribut principal, mostra els resultats dels segments suggerits que tenen un percentatge superior o inferior dels clients que pertanyen a una categoria concreta en comparació amb el percentatge de tots els clients que pertanyen a la mateixa categoria. Per exemple, *satisfacció del client* es tria com a atribut principal i consta de tres categories (*Baixa*, *Mitjana* i *Alta*). Per a cada categoria, es suggeriran segments que tinguin un percentatge més alt o inferior de clients que pertanyin a aquesta categoria en comparació amb la proporció de tots els clients d'una mateixa categoria. Si el 22 % de tots els clients tenen una satisfacció *alta*, només se suggeriran en aquesta categoria els segments que tinguin una proporció superior o inferior de clients amb una satisfacció *alta* en comparació amb el 22 %. De la mateixa manera, es suggeriran segments per a cadascuna de les altres categories (*Baixa* i *Mitjana*) si són estadísticament significatives.

> [!NOTE]
> Actualment només admetem atributs categòrics principals que tinguin fins a 10 categories. Si voleu veure suggeriments de segments basats en un atribut principal amb més de 10 categories, us recomanem que agrupeu algunes de les categories per reduir el nombre de categories a 10 o menys. Aquesta limitació només s'aplica als atributs principals. Per als atributs categòrics influents, actualment admetem un màxim de 100 categories.

## <a name="generate-suggested-segments"></a>Generar segments suggerits

1. Aneu a **Segments** i seleccioneu la **pestanya Suggeriments (previsualització).**

1. Seleccioneu **Cerca suggeriments** nous i trieu **Millora una mesura/mètrica**. Seleccioneu **Inicia**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Triar la mesura de millora en els segments suggerits.":::

1. Trieu un atribut o mesura de client com a atribut principal i seleccioneu **Següent**.

1. Seleccioneu els atributs que hi influeixen i seleccioneu **Executa**.

   > [!TIP]
   > La selecció de diversos atributs influents millora les possibilitats d'avaluar la manera com influeixen en l'atribut principal. No inclogueu atributs que no tinguin cap influència en l'atribut principal. Per exemple, si tots els clients són d'un país concret, no incloeu l'atribut *país* perquè no afectarà la sortida.

Segons el nombre de perfils de client i els atributs seleccionats, pot tardar uns minuts a processar els atributs seleccionats.

## <a name="manage-suggested-segments"></a>Gestionar els segments suggerits

Aneu a **Segments** i seleccioneu la **pestanya Suggeriments (previsualització).** A la **secció Suggeriments del segment basat en atributs**, seleccioneu un segment suggerit per veure les accions disponibles.

- **Visualitzeu** els detalls del segment suggerits i els valors o regles d'atributs que el model d'IA ha après.
- **Deseu com a segment** el suggeriment com a segment. Es mostra a la **pestanya Tots els segments** i es [pot actualitzar, editar o suprimir](segments.md).
- **Editeu els atributs** i modifiqueu els atributs configurats que substituiran els suggeriments actuals.
- **Actualitzeu els suggeriments** per actualitzar els suggeriments mantenint els atributs configurats.

## <a name="limitations"></a>Limitacions

1. No coincidència entre la mida dels segments estimada: si trieu un atribut principal que conté valors buits, la mida del segment prevista en els suggeriments de segment es pot veure afectada. Quan deseu aquest segment, la mida del segment real pot ser diferent de l'estimació original.

2. Els atributs principals de tipus booleà no funcionen: actualment només admetem els tipus de dades de cadenes i numèrics com a atribut principal.

3. Els segments suggerits no són prou rellevants: heu de tenir en compte que els atributs seleccionats i la distribució de valors d'aquests atributs influeixen en els resultats. Podeu canviar els atributs que influeixen o fins i tot l'atribut principal per obtenir resultats diferents.

[!INCLUDE [footer-include](includes/footer-banner.md)]