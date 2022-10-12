---
title: Guia d'exemple per a la predicció de recomanacions de productes
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de recomanacions de productes preparat per a l'ús.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610132"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guia d'exemple per a la predicció de recomanacions de productes

Aquesta guia us guiarà per un exemple d'extrem a extrem de recomanacions de productes predicció utilitzar dades d'exemple. Et recomanem que provis aquesta predicció [en un entorn nou](manage-environments.md).

## <a name="scenario"></a>Escenari

Contoso és una empresa que produeix màquines de cafè i cafè d'alta qualitat. Venen els productes a través del seu lloc web Contoso Coffee. El seu objectiu és comprendre quins productes han de recomanar als seus clients periòdics. Saber quins clients tenen més **probabilitats de comprar** els pot ajudar-los a estalviar esforços de màrqueting centrant-se en articles específics.

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.

## <a name="task-1---ingest-data"></a>Tasca 1 - Ingerir dades

Reviseu els articles [sobre la ingestió de](data-sources.md) dades i [la connexió a un Power Query font de dades](connect-power-query.md). La informació següent suposa que esteu familiaritzat amb la ingestió de dades en general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dades de clients procedents de la plataforma de comerç electrònic

1. Creeu una Power Query font de dades anomenada **eCommerce** i seleccioneu el **connector Text/CSV**.

1. Introduïu l'URL dels contactes de comerç electrònic:https://aka.ms/ciadclasscontacts.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeu la data de naixement en data.":::

1. Al camp Nom **de** la subfinestra de la dreta, canvieu el nom del vostre font de dades a **Comerç electrònicContactes**.

1. **Deseu** la font de dades.

### <a name="ingest-online-purchase-data"></a>Ingerir dades de compres en línia

1. Afegiu un altre conjunt de dades a la mateixa font de dades **eCommerce**. Torneu a triar el connector **Text/CSV**.

1. Introduïu l'URL de les dades de compres en línia https://aka.ms/ciadclassonline.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **PurchasedOn**: data/hora
   - **TotalPrice**: moneda

1. Al camp Nom **de** la subfinestra lateral, canvieu el nom del vostre font de dades a **Compres de comerç electrònic**.

1. **Deseu** la font de dades.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dades de clients procedents de l'esquema de fidelització

1. Creeu una font de dades anomenada **LoyaltyScheme** i seleccioneu el **connector Text/CSV**.

1. Introduïu l'URL per a clients fidels https://aka.ms/ciadclasscustomerloyalty.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **DateOfBirth**: data
   - **RewardsPoints**: nombre enter
   - **CreatedOn**: data/hora

1. Al camp Nom **de** la subfinestra de la dreta, canvieu el nom del font de dades a **loyCustomers**.

1. **Deseu** la font de dades.

## <a name="task-2---data-unification"></a>Tasca 2 - Unificació de les dades

Reviseu l'article [sobre la unificació de](data-unification.md) dades. La informació següent suposa que esteu familiaritzat amb la unificació de dades en general.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tasca 3- Crear l'activitat de l'historial de transaccions

Reviseu l'article [sobre les activitats](activities.md) dels clients. La informació següent suposa que esteu familiaritzat amb la creació d'activitats en general.

1. Crear una activitat anomenada **eCommerceComprases** amb l'entitat *eCommerceComprases:eCommerce* i la seva clau principal, **PurchaseId**.

1. Crea una relació entre *eCommerceComprases:eCommerce* i *eCommerceContactes:eCommerce* amb **ContactID** com a clau externa per connectar les dues entitats.

1. Seleccioneu TotalPrice **per a** EventActivity **i** PurchasedOn **per a la** marca de temps **.**

1. Seleccioneu **SalesOrderLine** per al Tipus **d'activitat** i assigneu semànticament les dades d'activitat.

1. Executar l'activitat.

## <a name="task-4---configure-product-recommendation-prediction"></a>Tasca 4: Configurar la predicció de recomanació de producte

Amb els perfils de client unificats establerts i l'activitat creada, executeu la recomanació de productes predicció.

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Crea**, seleccioneu **Utilitza el model** a la peça Recomanacions de **producte (visualització prèvia).**

1. Seleccioneu **Introducció**.

1. Anomeneu el model **Predicció del model de recomanació de productes de fàbrica** i l'entitat de sortida **OOBProductRecommendationModelPrediction**.

1. Seleccioneu **Següent**.

1. Definiu les preferències del model:
   - **Nombre de productes**: **5** per definir quants productes vols recomanar als teus clients.
   - **Repetiu les compres previstes**: **sí** per incloure productes comprats prèviament a la recomanació.
   - **Mirar enrere:** **365 dies** per definir fins a quin punt el model es veurà enrere abans de tornar a recomanar un producte.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferències del model per al model de recomanació de producte.":::

1. Seleccioneu **Següent**.

1. Al pas Afegeix l'historial **de** compres, selecciona **Afegeix dades**.

1. Seleccioneu **SalesOrderLine** i l'entitat eCommerceCompra i seleccioneu **Següent**. Les dades requerides s'emplenen automàticament des de l'activitat. Seleccioneu **Desa** i, a continuació, **Següent**.

1. Omet els **passos Afegeix informació** de producte i **Filtres** de producte perquè no tenim dades d'informació de producte.

1. Al pas **Actualitzacions** de dades, seleccioneu **Mensual** per a la planificació del model.

1. Seleccioneu **Següent**.

1. Un cop revisats tots els detalls, seleccioneu **Desa i executa**.

## <a name="task-5---review-model-results-and-explanations"></a>Tasca 5 - Revisar els resultats i les explicacions del model

Deixeu que el model completi la formació i la puntuació de les dades. Reviseu les explicacions del [model de recomanació de productes](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Tasca 6: crear un segment de productes molt adquirits

L'execució del model crea una entitat nova que es mostra a **Dades** > **Entitats**. Podeu crear un segment nou a partir de l'entitat creada pel model.

1. A la pàgina de resultats, seleccioneu **Crea un segment**.

1. Creeu una regla utilitzant l'entitat **OOBProductRecommendationModelPrediction** i definiu el segment:
   - **Camp**: ProductID
   - **Valor**: seleccioneu els tres identificadors de producte principals

1. Seleccioneu **Desa** i **executa** el segment.

Ara tens un segment que s'actualitza dinàmicament i que identifica els clients que podrien estar interessats a adquirir els cinc productes més recomanats. Per a més informació, vegeu [Crear i administrar segments](segments.md).

> [!TIP]
> També podeu crear un segment per a un model de predicció des de la **pàgina Segments** seleccionant **Crea des** d'Intel·ligència i triant **Crea des d'Intel** > **·ligència**. Per obtenir més informació, vegeu [Crear un segment nou amb segments ràpids](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
