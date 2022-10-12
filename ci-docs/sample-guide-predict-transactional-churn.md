---
title: Guia d'exemples de predicció de rotació de transaccions
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de rotació de transaccions preparat per a l'ús.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609672"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guia d'exemples de predicció de rotació de transaccions

Aquesta guia us explicarà un exemple d'extrem a extrem de la predicció transaccional mitjançant dades d'exemple. Et recomanem que provis aquesta predicció [en un entorn nou](manage-environments.md).

## <a name="scenario"></a>Escenari

Contoso és una empresa que produeix màquines de cafè i cafè d'alta qualitat. Venen els productes a través del seu lloc web Contoso Coffee. El seu objectiu és saber quins clients que acostumen a comprar els seus productes de manera periòdica deixaran de ser clients actius en els propers 60 dies. Sabent quins dels seus clients és **probable que rotin**, pot ajudar l'empresa a estalviar estratègies i mesures de màrqueting centrades en mantenir-los.

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [permisos de col·laborador](permissions.md).

## <a name="task-1---ingest-data"></a>Tasca 1 - Ingerir dades

Reviseu els articles [sobre la ingestió de](data-sources.md) dades i [la connexió a un Power Query font de dades](connect-power-query.md). La informació següent suposa que esteu familiaritzat amb la ingestió de dades en general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dades de clients procedents de la plataforma de comerç electrònic

1. Creeu una font de dades anomenada **eCommerce** i seleccioneu el **connector Text/CSV**.

1. Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscontacts.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:

   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar DoB en Data.":::

1. **Al camp Nom** de la subfinestra de la dreta, canvieu el nom del vostre font de dades a **Comerç electrònicContactes**

1. Deseu la font de dades.

### <a name="ingest-online-purchase-data"></a>Ingerir dades de compres en línia

1. Afegiu un altre conjunt de dades a la mateixa font de dades **eCommerce**. Torneu a triar el connector **Text/CSV**.

1. Introduïu l'URL de les dades de compres en línia https://aka.ms/ciadclassonline.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:

   - **PurchasedOn**: data/hora
   - **TotalPrice**: moneda

1. Al camp Nom **de** la subfinestra de la dreta, canvieu el nom del vostre font de dades a **eCommerceComprases**.

1. Deseu la font de dades.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dades de clients procedents de l'esquema de fidelització

1. Creeu una font de dades anomenada **LoyaltyScheme** i seleccioneu el **connector Text/CSV**.

1. Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscustomerloyalty.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:

   - **DateOfBirth**: data
   - **RewardsPoints**: nombre enter
   - **CreatedOn**: data/hora

1. Al camp Nom **de** la subfinestra de la dreta, canvieu el nom del font de dades a **loyCustomers**.

1. Deseu la font de dades.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Tasca 4 - Configurar la predicció de rotació de transaccions

Amb els perfils de clients unificats establerts i l'activitat, executeu la transacció predicció.

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Crea**, seleccioneu **Model** d'ús al **model** De client.

1. Seleccioneu **Transaccional** per al tipus de churn i, a continuació, **Comenceu**.

1. Anomeneu el model **Predicció de rotació de transaccions de comerç electrònic OOB** i l'entitat de sortida **OOBeCommerceChurnPrediction**.

1. Seleccioneu **Següent**.

1. Definiu les preferències del model:

   - **predicció finestra**: **60** dies per definir fins a quin punt en el futur volem predir el creixement del client.

   - **Definició de churn**: **60** dies per indicar la durada sense compra després de la qual es considera que un client està vacunat.

     :::image type="content" source="media/model-levers.PNG" alt-text="Seleccioneu les preferències del model predicció definició de finestra i churn.":::

1. Seleccioneu **Següent**.

1. Seleccioneu **Historial de compres (obligatori)** i seleccioneu **Afegeix dades** per a l'historial de compres.

1. Seleccioneu **SalesOrderLine** i l'entitat eCommerceCompra i seleccioneu **Següent**. Les dades requerides s'emplenen automàticament des de l'activitat. Seleccioneu **Desa** i, a continuació, **Següent**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Uniu entitats de comerç electrònic.":::

1. Omet el **pas Dades addicionals (opcional**).

1. Al pas **Actualitzacions** de dades, seleccioneu **Mensual** per a la planificació del model.

1. Un cop revisats tots els detalls, seleccioneu **Desa i executa**.

## <a name="task-5---review-model-results-and-explanations"></a>Tasca 5 - Revisar els resultats i les explicacions del model

Deixeu que el model completi la formació i la puntuació de les dades. Reviseu les explicacions del model churn. Per obtenir més informació, vegeu [Veure predicció resultats](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tasca 6 - Crear un segment de clients amb un alt risc de rotació

L'execució del model de producció crea una entitat nova, que apareix a **Entitats** > **de dades**. Podeu crear un segment nou a partir de l'entitat creada pel model.

1. A la pàgina de resultats, seleccioneu **Crea un segment**.

1. Creeu una regla mitjançant l'entitat **OOBeCommerceChurnPrediction** i definiu el segment:
   - **Camp**: ChurnScore
   - **Operador**: major de
   - **Valor**: 0.6

1. Seleccioneu **Desa** i **executa** el segment.

Ara teniu un segment que s'actualitza dinàmicament i que identifica clients d'alt risc. Per a més informació, vegeu [Crear i administrar segments](segments.md).

> [!TIP]
> També podeu crear un segment per a un model de predicció des de la **pàgina Segments** seleccionant **Crea des** d'Intel·ligència i triant **Crea des d'Intel** > **·ligència**. Per obtenir més informació, vegeu [Crear un segment nou amb segments ràpids](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
