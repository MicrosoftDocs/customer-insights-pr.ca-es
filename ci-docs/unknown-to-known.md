---
title: Personalitzar les experiències amb dades d'usuaris coneguts i desconeguts
description: Incorporeu la informació sobre usuaris desconeguts anteriorment quan conegueu la seva identitat.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173812"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalitzar les experiències amb dades d'usuaris coneguts i desconeguts

Gestionar les dades dels clients no és un repte nou, però cada vegada és més difícil a mesura que els usuaris naveguen pels diferents canals digitals que ofereixen les marques. Un usuari conegut (autenticat) en un canal es torna desconegut (no autenticat) en un altre si no ha iniciat la sessió. El problema sovint és que els usuaris no autenticats (desconeguts) no tenen un identificador comú. Es podria utilitzar per associar atributs de perfils significatius i generar perfils de clients unificats. El Customer Insights ajuda a resoldre aquest problema ingerint dades dels mètodes de seguiment als vostres sistemes d'origen. Els perfils consolidats desconeguts i coneguts proporcionen a les organitzacions una visió completa dels perfils actualitzats i de les seves transaccions històriques, comportaments i demografia. Fins i tot va un pas més enllà proporcionant una resolució d'identitat que us permet unificar l'activitat dels clients en diversos canals, inclòs el vostre lloc web, la compra a la botiga, els programes de fidelització, etc.

## <a name="sample-scenario"></a>Escenari d'exemple

Pensem en una cadena de cafè, que té una àmplia base de clients que compra cafè i menjar a les botigues i demana productes en línia. Sovint, els visitants en línia no s'autentiquen quan naveguen pels productes, cosa que els converteix en "usuaris desconeguts". És difícil per a la cadena de cafè oferir ofertes i experiències personalitzades si els usuaris són desconeguts. D'altra banda, els clients poden iniciar sessió en el seu compte i convertir-se en "usuaris coneguts" a l'empresa unint-se a un sistema de fidelització, que al seu torn permet experiències més personalitzades. El Customer Insights pot ajudar la cadena del cafè a obtenir informació sobre usuaris coneguts i desconeguts anteriorment.

Amb el Customer Insights, l'empresa pot combinar perfils de clients amb dades d'activitat de sessions no autenticades (desconegudes) després que un usuari iniciï la sessió i es conegui. La cadena del cafè pot portar dades d'altres fonts de dades mitjançant connectors integrats al Customer Insights per combinar identitats per a clients de diversos canals.

## <a name="prerequisites"></a>Requisits previs

- Les dades web es recopilen i contenen "identificadors de visitant" per a tots els visitants.
- Les dades web contenen "identificadors d'usuari autenticats" per als visitants que han iniciat la sessió. Aquests identificadors estan enllaçats amb el sistema de fidelització.
- Les dades d'esdeveniments d'alt valor, com ara "Visualització de producte" i "Pagament", es defineixen i s'inclouen a les dades d'origen juntament amb la marca de temps de l'esdeveniment i un identificador d'esdeveniment.

La taula següent mostra un exemple simplificat de com es podrien capturar esdeveniments web d'alt valor.

|EventID|EventTimeStamp|UserID|LoyaltyID|Nom de l'esdeveniment|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Visualització del producte|
|2|07-23-2022 10:05:00|abc123|707|Inici de sessió de fidelització|
|3|07-23-2022 10:10:00|abc123|707|Consulta|
|4|07-23-2022 10:20:00|xyz789|--|Visualització del producte|

## <a name="data-ingestion"></a>Ingestió de dades

Les dades sobre clients es poden originar al vostre lloc web com a dades d'esdeveniments i es poden emmagatzemar als vostres propis serveis d'anàlisi de dades interns o de tercers. Les dades web contenen usuaris coneguts i desconeguts si el lloc web té un flux d'autenticació que s'integra amb un servei d'autenticació. Per exemple, un sistema de comerç electrònic que requereix que els usuaris proporcionin les seves dades completes per finalitzar una transacció de compra. O un sistema de fidelització que requereixi autenticació per confirmar un destinatari vàlid dels descomptes de les recompenses.

Les dades d'esdeveniments del nostre exemple anterior contenen els identificadors de perfil diferents dels usuaris coneguts i desconeguts. En els esdeveniments 1 i 4, els usuaris són desconeguts mentre que en els esdeveniments 2 i 3 l'usuari amb l'ID abc123 s'inscriu en un programa de fidelització.

:::image type="content" source="media/website-data-source.png" alt-text="Fonts de dades, inclosa la pàgina web de Contoso.":::

Per obtenir més informació sobre les opcions disponibles per a la ingestió de dades, vegeu [Informació general de les fonts de dades](data-sources.md).

## <a name="data-unification"></a>Unificació de dades

La convergència d'identitats desconegudes amb identitats conegudes ajuda a permetre la personalització basada en comportaments dels usuaris, independentment del seu estat de perfil (conegut o desconegut). El contingut personalitzat per a tots els usuaris ajuda els clients a accedir ràpidament als productes o serveis més rellevants que els interessen en aquell moment.

Com que es coneixen alguns dels usuaris de les nostres dades, podem utilitzar el Coneixement del client per combinar aquestes dades amb el perfil de l'usuari. Per obtenir més informació sobre com unificar perfils de clients, vegeu [Informació general de la unificació de dades](data-unification.md).

1. Seleccioneu els camps d'origen de l'entitat de dades web. Utilitzeu les dades de perfil que s'emmagatzemen a les dades web i seleccioneu els camps que representen els identificadors amb dades demogràfiques.

   :::image type="content" source="media/website-source-fields.png" alt-text="Camps d'origen per a la font de dades web.":::

1. Afegiu regles per combinar registres duplicats. Per a les dades web, trieu les dades més emplenades.

1. Configureu regles i condicions de concordança. Les dades d'esdeveniments dels perfils web d'aquest exemple es relacionaran en identificadors amb els perfils de les altres fonts de dades que contenen informació dels clients. Configureu regles exactes de concordança als identificadors com a regles separades amb cadascuna de les altres entitats del perfil que tinguin una coincidència de clau principal o identificador corresponent. A l'exemple, les dades del perfil d'esdeveniment web s'utilitzen com a última entitat coincident de manera que primer es combinen altres dades de perfil.
   1. No comprovació **Incloure tots els registres** crea perfils unificats per a usuaris coneguts i inclou els seus corresponents ID d'usuari desconeguts. És útil en escenaris en què esteu interessats en veure les activitats de comportament anteriors d'usuaris coneguts quan encara eren desconeguts.
   1. La comprovació **Inclou tots els registres** crea registres de perfil independents per a usuaris desconeguts. Els usuaris desconeguts obtenen un identificador de client únic. En el futur, quan s'associï un perfil conegut a les dades del perfil d'esdeveniments web, el recorregut de l'usuari recentment conegut es pot veure i utilitzar per personalitzar-lo basant-se també en dades de comportament desconegudes del passat.

:::image type="content" source="media/website-match-rule.png" alt-text="Regla de coincidència per al lloc web font de dades entitat.":::

## <a name="get-insights"></a>Obtén informació detallada

Si es creen perfils de clients per a usuaris desconeguts i coneguts, les dades d'esdeveniments web d'alt valor es poden utilitzar com a [activitats](activities.md). Aquestes activitats es poden utilitzar per crear més coneixements. Per exemple, els clients que van visitar un lloc web fa sis mesos (quan encara eren desconeguts) o els clients que no tenen un identificador de fidelització mai no han completat cap compra.

:::image type="content" source="media/website-known-unknown.png" alt-text="Captura de pantalla de la pàgina del client amb clients coneguts i desconeguts.":::

[Enriqueix](enrichment-hub.md) les teves dades, crea [mesures](measures.md) i crea [segments](segments.md) per a una major activació.

Per exemple, podeu crear segments d'usuaris coneguts que hagin consultat alguns productes però que mai no hagin completat la compra.

Per obtenir més informació, vegeu [Informació general dels segments](segments.md).

## <a name="activate-insights"></a>Activar estadístiques

Hi ha diverses maneres d'exportar les dades i prendre mesures en funció de les estadístiques subjacents.

Per obtenir més informació, vegeu [Informació general de](export-destinations.md) les exportacions.
