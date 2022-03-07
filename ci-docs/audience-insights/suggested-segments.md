---
title: Segments suggerits basats en aprenentatge automàtic
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
ms.openlocfilehash: 82345a7d7cf7fd38d74080552799de0b92461d78
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353577"
---
# <a name="suggested-segments-preview"></a>Segments suggerits (versió preliminar)

Descobriu segments interessants dels vostres clients amb l'ajuda d'un model d'IA. Aquesta característica basada en aprenentatge automàtic suggereix segments segons mesures o atributs del client. Pot ajudar a millorar els KPI o comprendre millor la influència dels atributs en el context d'altres atributs. 

> [!NOTE]
> La característica de segments suggerits utilitza mitjans automatitzats per avaluar dades i fer previsions basades en aquestes dades i, per tant, té la capacitat d'utilitzar-se com a mètode de generació de perfils, tal com es defineix aquest terme al Reglament general de protecció de dades ("RGPD"). L'ús d'aquesta característica per processar dades pot estar subjecte a l'RGPD o altres lleis o normatives. Us responsabilitzeu de garantir que l'ús del Dynamics 365 Customer Insights, incloent-hi aquesta característica, compleixi totes les lleis i normatives aplicables, incloent-hi la legislació relacionada amb la privadesa, les dades personals, les dades biomètriques, la protecció de dades i la confidencialitat de comunicació.

:::image type="content" source="media/suggested-segments.png" alt-text="Pàgina de segments suggerits que mostra els detalls d'un suggeriment en una subfinestra lateral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segments suggerits per millorar els KPI

Com a usuari de conclusions del públic, és possible que tingueu una sèrie de [mesures creades](measures.md) que ajuden a fer el seguiment dels indicadors clau de rendiment (KPI). És important comprendre com influeixen alguns atributs en aquests KPI per crear segments i executar una campanya molt concreta.   
Per exemple, feu el seguiment d'una mesura anomenada *TotalSpendPerCustomer*. Com a empresa, voleu que aquest nombre creixi. Triar una mesura com a atribut principal us permet seleccionar els atributs que voleu valorar com a influències. Suposem que són *nivell de subscripció*, *període de subscripció* i *ocupació*. A continuació, el Customer Insights pot suggerir un segment que us indica qui és la influència més important d'aquesta mesura. Per exemple, els *comptables* que són membres d'*or* i que han estat amb el vostre negoci durant *almenys cinc anys* són la influència més important de *TotalSpendPerCustomer*. Obtindreu una mida de segment estimada per a cada suggeriment. Podeu utilitzar aquesta informació per crear campanyes per als públics objectiu.

## <a name="understand-what-influences-a-customer-attribute"></a>Comprendre la influència d'un atribut de client

Podeu triar un atribut de client en lloc d'una mesura com a atribut principal. Segons la vostra opció d'atributs influents, el model d'IA crea una sèrie de suggeriments que mostren com influeixen els atributs seleccionats en l'atribut principal.   
Per exemple, trieu *Membre de recompenses (Sí/No)* com a atribut principal. *Antiguitat*, *Ocupació* i *Nombre de sol·licituds d'assistència tècnica* es defineixen com altres atributs que influeixen. El model d'IA podria suggerir segments que indiquen que principalment els professionals de IT amb una antiguitat superior als dos anys són membres de recompenses. Un altre suggeriment podria ressaltar que els comptables amb una antiguitat de més d'un any i menys de tres sol·licituds d'assistència tècnica són membres de recompenses. 

## <a name="artificial-intelligence-usage"></a>Ús d'intel·ligència artificial

Mitjançant l'atribut principal i els atributs que influeixen, un algorisme d'arbre de decisions suggereix segments interessants. Els suggeriments es basen en regles o patrons recollits per l'algorisme d'IA. Només es mostren com a suggeriments els segments que difereixen significativament de la població mitjana. La comparació amb la població mitjana es basa en la mesura o l'atribut principal seleccionat.

### <a name="responsible-ai"></a>IA responsable

Els segments suggerits us permeten seleccionar atributs per crear segments nous i processar les dades que seleccioneu. A l'hora de triar els atributs, incloent-hi els atributs confidencials, com ara la raça, l'orientació sexual o el gènere, heu de garantir que podeu i heu de processar aquestes dades. Sou el responsable de complir les lleis aplicables a la vostra organització i complir els principis i les normes de privadesa de la vostra organització.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Resultats diferents per als atributs principals amb valors categòrics i numèrics

Els suggeriments de segment són diferents si trieu un atribut numèric o un atribut categòric com a atribut principal. Els valors d'un atribut categòric contenen dues o més categories o tipus. Un atribut numèric conté dades quantitatives i té una gran quantitat de mesura associada.

Amb un atribut numèric com *ingressos anuals* o *període de subscripció* com a atribut principal, el sistema suggereix segments que tenen un valor mitjà superior o inferior a l'atribut numèric en comparació amb tots els clients.

Un atribut categòric, com ara la *satisfacció del client* com a atribut principal, mostra els resultats dels segments suggerits que tenen un percentatge superior o inferior dels clients que pertanyen a una categoria concreta en comparació amb el percentatge de tots els clients que pertanyen a la mateixa categoria. Per exemple, *satisfacció del client* es tria com a atribut principal i consta de tres categories (*Baixa*, *Mitjana* i *Alta*). Per a cada categoria, se suggeriran els segments que tinguin un percentatge superior o inferior als clients que pertanyin a la mateixa categoria en comparació amb la proporció de tots els clients de la mateixa categoria. Si el 22 % de tots els clients tenen una satisfacció *alta*, només se suggeriran en aquesta categoria els segments que tinguin una proporció superior o inferior de clients amb una satisfacció *alta* en comparació amb el 22 %. De la mateixa manera, es suggeriran segments per a cadascuna de les altres categories (*Baixa* i *Mitjana*) si són estadísticament significatives.

> [!NOTE]
> Actualment només admetem atributs categòrics principals que tinguin fins a 10 categories. Si voleu veure suggeriments de segments basats en un atribut principal amb més de 10 categories, és recomanable agrupar algunes de les categories per reduir el nombre de categories a 10 o menys. Aquesta limitació només s'aplica als atributs principals. Per als atributs categòrics influents, actualment admetem un màxim de 100 categories.

## <a name="generate-suggested-segments"></a>Generar segments suggerits

1. Aneu a **Segments**.

1. Seleccioneu la pestanya **Suggeriments (versió preliminar)**.

1. Seleccioneu **Obtén suggeriments nous** per iniciar l'experiència guiada.

1. Trieu una mesura o atribut de client com a atribut principal i seleccioneu **Següent**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Triar l'atribut principal dels suggeriments dels segments suggerits.":::

1. Seleccioneu els atributs que influeixen i seleccioneu **Desa**.
   
   > [!TIP]
   > La selecció de diversos atributs influents millora les possibilitats d'avaluar la manera com influeixen en l'atribut principal. No incloeu atributs que no influeixin en l'atribut principal. Per exemple, si tots els clients són d'un país concret, no incloeu l'atribut *país* perquè no afectarà la sortida.

1. Segons el nombre de perfils de client i els atributs seleccionats, pot tardar uns minuts a processar els atributs seleccionats. 

## <a name="view-details-of-a-suggested-segment"></a>Veure els detalls del segment suggerit

Quan el model d'IA hagi generat els suggeriments, els trobareu enumerats a **Segments** > **Suggeriments (versió preliminar)**.
 
Seleccioneu un segment suggerit per revisar-ne els detalls. També podeu revisar els valors o les regles dels atributs que el model d'IA ha après a suggerir el segment seleccionat.

## <a name="save-a-suggestion-as-a-segment"></a>Desar un suggeriment com a segment

1. Aneu a **Segments** > **Suggeriments (versió preliminar)**.

1. Seleccioneu el segment que voleu desar. 

1. A la subfinestra lateral, seleccioneu **Desa com a segment**. 

1. Després de desar el segment, es mostrarà a la llista de segments a la pestanya **Tots els segments**. Ara es pot [actualitzar, editar o suprimir, com qualsevol altre segment](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Actualitzar o editar un conjunt de suggeriments

1. Aneu a **Segments** > **Suggeriments (versió preliminar)**.

1. Seleccioneu **Actualitza els suggeriments** per actualitzar els suggeriments mantenint els atributs configurats. O seleccioneu **Edita els atributs** per modificar els atributs configurats. El sistema tornarà a executar el model d'IA, generarà suggeriments de segment basats en les dades més recents i substituirà els suggeriments actuals.

## <a name="limitations"></a>Limitacions

1. No coincidència entre la mida dels segments estimada: si trieu un atribut principal que conté valors buits, la mida del segment prevista en els suggeriments de segment es pot veure afectada. Quan deseu aquest segment, la mida del segment real pot ser diferent de l'estimació original.
 
2. Els atributs principals de tipus booleà no funcionen: actualment només admetem els tipus de dades de cadenes i numèrics com a atribut principal.

3. Els segments suggerits no són prou rellevants: heu de tenir en compte que els atributs seleccionats i la distribució de valors d'aquests atributs influeixen en els resultats. Podeu canviar els atributs que influeixen o fins i tot l'atribut principal per obtenir resultats diferents.



[!INCLUDE[footer-include](../includes/footer-banner.md)]