---
title: Gestionar perfils desconeguts amb el Customer Insights
description: Treballar amb perfils de clients desconeguts que es creen i gestionen en Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776809"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Gestionar perfils desconeguts amb el Customer Insights

Els usuaris d'Internet sovint no estan identificats o anònims en línia. Fins i tot els clients més fidels poden semblar "desconeguts" si no han iniciat la sessió en diferents dispositius. Per a moltes marques, els usuaris coneguts o autenticats són la minoria tot i les creixents expectatives dels clients al voltant de la personalització. Amb el futur de les cookies de tercers en qüestió, gestionar les preferències de l'usuari a partir de dades pròpies és crucial per aconseguir experiències personalitzades.

La personalització memorable depèn del grau de coneixement del vostre client i les estadístiques de clients us ajuden a fer-ho fent un seguiment de tots els vostres clients.  No heu de limitar ni aturar l'ús de les dades recollides a l'inici de la recorregut del client. El Customer Insights us permet aportar les vostres pròpies dades per crear un perfil de client per a usuaris desconeguts. A continuació, podeu utilitzar aquest perfil per a més accions, tot i que falti informació de contacte. Importeu dades pròpies de fonts com ara sistemes web, mòbils o CRM al Customer Insights per enriquir els perfils de clients contínuament. A mesura que unifiqueu més interaccions, [convertiu el *client desconegut* en un *client conegut*](unknown-to-known.md).

## <a name="sample-scenario"></a>Escenari mostral

Suposem que un usuari utilitza el seu dispositiu mòbil per navegar pel vostre lloc de comerç electrònic. El lloc web assigna al visitant "mobile_guest123" com a identificador únic i comenceu a recopilar activitats de comportament basades en la seva activitat en línia. Per exemple, quines pàgines van visitar, quant de temps van passar en aquestes pàgines o en quins enllaços van fer clic. No sabeu el seu nom ni la seva adreça electrònica, però aquestes dades poden ajudar a proporcionar a les marques estadístiques significatives sobre aquest usuari concret. Al seu torn, podeu posar aquestes estadístiques a funcionar la propera vegada que l'usuari visiti el lloc. Consulteu el Customer Insights per a "mobile_guest123" per recuperar la llista de segments de l'usuari, com ara "clients orgànics", "clients de pre-comanda per a mòbils", "clients d'alt valor", etc., o recupereu el perfil per crear experiències web personalitzades. També podeu exportar les dades a qualsevol sistema d'activació per fer el mateix.

## <a name="prerequisites"></a>Requisits previs

- Ingerir dades pròpies al Customer Insights
- Cada entitat té un identificador únic que es defineix com a clau principal
- Cada entitat amb una clau principal per a la personalització està unificada
- El sistema de gestió de continguts del vostre lloc web pot utilitzar API (per a la personalització web basada en la comunicació directa amb el Customer Insights)

La taula següent mostra un exemple simplificat de com es podrien capturar esdeveniments web d'alt valor.

|EventID|EventTimeStamp|UserID|Clau primària|Nom de l'esdeveniment|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|GaletaID1|Visualització del producte|
|2|09-18-2022 10:05:00|abc123|GaletaID1|Visualització del producte|
|3|09-18-2022 10:10:00|abc123|GaletaID1|Afegeix al carretó|
|4|09-21-2022 09:05:00|abc123|GaletaID1|Visualització del producte|

## <a name="data-ingestion"></a>Ingestió de dades

Per obtenir més informació sobre les opcions disponibles per a la ingestió de dades, vegeu [Informació general de les fonts de dades](data-sources.md).

## <a name="data-unification"></a>Unificació de dades

Per obtenir més informació sobre com unificar perfils de clients, vegeu [Informació general](data-unification.md) de la unificació de dades.

## <a name="get-insights"></a>Obtén informació detallada

[Enriqueix](enrichment-hub.md) les teves dades, crea [mesures](measures.md) i crea [segments](segments.md) per a una major activació.

Per exemple, podeu crear segments d'usuaris desconeguts que hagin navegat per les mateixes pàgines del producte però que mai no hagin completat la compra.

## <a name="activation"></a>Activació

Amb les dades del Customer Insights i les estadístiques a punt per començar, podeu utilitzar el Customer Insights per personalitzar-les:

1. Utilitzar l'API [oData](apis.md) per recuperar una pertinença al segment o un perfil de client Per obtenir més exemples, vegeu [exemples de consulta d'OData per a les API](odata-examples.md) del Customer Insights.

1. [Exporta](export-destinations.md) les teves dades als teus sistemes d'activació.

Exemple: un usuari desconegut visita un lloc web diverses vegades i visita pàgines de productes per a diversos models de sabates de cuir. Amb aquestes dades disponibles al Customer Insights, podeu incloure l'usuari desconegut al segment de persones interessades en les sabates de cuir. Utilitzeu aquest segment per informar la personalització de la creació del vostre lloc web per als visitants recurrents. En la propera visita, el lloc reconeix l'usuari desconegut i podria oferir-li un cupó del 10 % en sabates de cuir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
