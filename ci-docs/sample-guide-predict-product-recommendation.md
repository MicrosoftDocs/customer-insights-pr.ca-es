---
title: Guia d'exemple per a la predicció de recomanacions de productes
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de recomanacions de productes preparat per a l'ús.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762674"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guia d'exemple per a la predicció de recomanacions de productes

Se us guiarà per un exemple íntegre de predicció de recomanacions de productes mitjançant les dades d'exemple següents.

## <a name="scenario"></a>Escenari

Contoso és una empresa que produeix cafè i cafeteres d'alta qualitat, productes que ven a través del seu lloc web de Contoso Coffee. El seu objectiu és comprendre quins productes han de recomanar als seus clients periòdics. Conèixer el que és **probable que comprin** els clients els pot ajudar a estalviar esforços de màrqueting centrant-se en articles concrets.

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.
- Us recomanem que implementeu els passos següents [en un entorn nou](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tasca 1 - Ingerir dades

Reviseu els articles [sobre la ingestió](data-sources.md) de dades i [la importació de fonts de dades mitjançant Power Query connectors](connect-power-query.md) específicament. La informació següent suposa que ja esteu familiaritzat amb el concepte d'ingestió de dades en general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dades de clients procedents de la plataforma de comerç electrònic

1. Creeu una font de dades **eCommerce**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.

1. Introduïu l'URL dels contactes de comerç electrònic: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeu la data de naixement en data.":::

1. Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommerceContacts**.

1. **Deseu** la font de dades.

### <a name="ingest-online-purchase-data"></a>Ingerir dades de compres en línia

1. Afegiu un altre conjunt de dades a la mateixa font de dades **eCommerce**. Torneu a triar el connector **Text/CSV**.

1. Introduïu l'adreça URL de **les dades de compres** en línia [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **PurchasedOn**: data/hora
   - **TotalPrice**: moneda

1. Al camp **Nom** de la subfinestra lateral, canvieu el nom de la font de dades **Query** per **eCommercePurchases**.

1. **Deseu** la font de dades.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dades de clients procedents de l'esquema de fidelització

1. Creeu una font de dades amb el nom **LoyaltyScheme**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.

1. Introduïu l'URL dels contactes de comerç electrònic [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **DateOfBirth**: data
   - **RewardsPoints**: nombre enter
   - **CreatedOn**: data/hora

1. Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **loyCustomers**.

1. **Deseu** la font de dades.

## <a name="task-2---data-unification"></a>Tasca 2 - Unificació de les dades

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Tasca 3: Configurar la predicció de recomanació de producte

Amb els perfils de clients unificats, ara podem executar la recomanació del producte predicció.

1. Aneu a **Intel·ligència** > **Predicció** i trieu **Recomanació de producte**.

1. Seleccioneu **Introducció**.

1. Anomeneu el model **Predicció del model de recomanació de productes de fàbrica** i l'entitat de sortida **OOBProductRecommendationModelPrediction**.

1. Definiu tres condicions per al model:

   - **Nombre de productes**: definiu aquest valor en **5**. Aquesta configuració defineix quants productes voleu recomanar als clients.

   - **Repeteix les compres previstes**: seleccioneu **Sí** per indicar que voleu incloure productes a la recomanació que els vostres clients ja han adquirit.

   - **Finestra de cerca en el passat**: seleccioneu com a mínim **365 dies**. Aquesta configuració defineix quin temps en el passat consultarà el model a l'activitat del client per utilitzar-la com a entrada de les seves recomanacions.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferències del model per al model de recomanació de producte.":::

1. Al pas Afegeix les **dades** necessàries, seleccioneu **Afegeix dades**.

1. A la **subfinestra Afegeix dades**, trieu SalesOrderLine **com** a entitat de l'historial de compres. En aquest punt, és probable que encara no estigui configurat. Obriu l'enllaç a la subfinestra per crear l'activitat amb els passos següents:
   1. Introduïu un nom **d'activitat** i trieu *eCommercePurchases:eCommerce* com a **entitat** Activitat. La **clau** principal és *PurchaseId*.
   1. Definiu i anomeneu la relació amb l'entitat *eCommerceContacts: eCommerce* i trieu **ContactId** com a clau estrangera.
   1. Per a la unificació de l'activitat, definiu **l'activitat** de l'esdeveniment com a *TotalPrice* i marca horària a *PurchasedOn*. Podeu especificar més camps tal com s'indica a [Activitats](activities.md) del client.
   1. Per al **tipus** Activitat, trieu *SalesOrderLine*. Assigna els camps d'activitat següents:
      - Identificador de la línia de comanda: PurchaseId
      - Identificador de comanda: PurchaseId
      - Dades de la comanda: PurchasedOn
      - Identificador del producte: ProductId
      - Import: TotalPrice
   1. Reviseu i acabeu l'activitat abans de tornar a la configuració del model.

1. Torneu al pas Selecció d'activitats **·**, trieu l'activitat creada recentment a la **secció Activitats**. Seleccioneu **Següent** i l'assignació d'atributs ja s'ha emplenat. Seleccioneu **Desa**.

1. En aquesta guia d'exemple, ometem el conjunt Afegeix informació **del** producte i **Filtres** de producte perquè no tenim dades d'informació del producte.

1. **Al pas Actualitzacions** de dades, definiu la planificació del model.

   El model ha formar-se periòdicament per aprendre nous patrons quan hi ha dades noves ingerides. En aquest exemple, seleccioneu **Mensual**.

1. Un cop revisats tots els detalls, seleccioneu **Desa i executa**. Trigarà uns minuts a executar el model per primera vegada.

## <a name="task-4---review-model-results-and-explanations"></a>Tasca 4 - Revisar els resultats i les explicacions del model

Deixeu que el model completi la formació i la puntuació de les dades. Ara ja podeu revisar les explicacions del model de recomanació de productes. Per obtenir més informació, vegeu [Revisar un estat de predicció i els resultats](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tasca 5: crear un segment de productes molt adquirits

En executar el model de producció, es crea una entitat nova, que podreu veure a **Dades** > **Entitats**.

Podeu crear un segment nou a partir de l'entitat creada pel model.

1. Aneu a **Segments**. Selecciona **Crea** i selecciona **Crea des d'Intel·ligència**.

   ![Creació d'un segment amb la sortida del model.](media/segment-intelligence.png)

1. Seleccioneu l'extrem **OOBProductRecommendationModelPrediction** i definiu el segment:

   - Camp: ProductID
   - Valor: seleccioneu els tres ID de producte principals

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Creeu un segment a partir dels resultats del model.":::

Ara teniu un segment que s'actualitza dinàmicament i que identifica els clients que podrien estar interessats a comprar els tres productes més recomanats.

Per a més informació, vegeu [Crear i administrar segments](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
