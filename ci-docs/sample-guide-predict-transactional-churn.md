---
title: Guia d'exemples de predicció de rotació de transaccions
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de rotació de transaccions preparat per a l'ús.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741307"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guia d'exemples de predicció de rotació de transaccions

En aquesta guia, se us guiarà per un exemple íntegre de predicció de rotació de transaccions al Customer Insights mitjançant les dades següents. Les dades utilitzades en aquesta guia no són dades de clients reals i formen part del conjunt de dades de Contoso que es troba a l'entorn *Demo* de la vostra subscripció al Customer Insights.

## <a name="scenario"></a>Escenari

Contoso és una empresa que produeix cafè i cafeteres d'alta qualitat, productes que ven a través del seu lloc web de Contoso Coffee. El seu objectiu és saber quins clients que acostumen a comprar els seus productes de manera periòdica deixaran de ser clients actius en els propers 60 dies. Sabent quins dels seus clients és **probable que rotin**, pot ajudar l'empresa a estalviar estratègies i mesures de màrqueting centrades en mantenir-los.

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.
- Us recomanem que implementeu els passos següents [en un entorn nou](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tasca 1 - Ingerir dades

Reviseu els articles [sobre la ingestió](data-sources.md) de dades i [la importació de fonts de dades mitjançant Power Query connectors](connect-power-query.md) específicament. La informació següent suposa que ja esteu familiaritzat amb el concepte d'ingestió de dades en general. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dades de clients procedents de la plataforma de comerç electrònic

1. Creeu una font de dades **eCommerce**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.

1. Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscontacts.

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:

   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar DoB en Data.":::

1. Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommerceContacts**.

1. Deseu la font de dades.

### <a name="ingest-online-purchase-data"></a>Ingerir dades de compres en línia

1. Afegiu un altre conjunt de dades a la mateixa font de dades **eCommerce**. Torneu a triar el connector **Text/CSV**.

1. Introduïu l'adreça URL de les dades de **Compres en línia** https://aka.ms/ciadclassonline.

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:

   - **PurchasedOn**: data/hora
   - **TotalPrice**: moneda
   
1. Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommercePurchases**.

1. Deseu la font de dades.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dades de clients procedents de l'esquema de fidelització

1. Creeu una font de dades amb el nom **LoyaltyScheme**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.

1. Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscustomerloyalty.

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:

   - **DateOfBirth**: data
   - **RewardsPoints**: nombre enter
   - **CreatedOn**: data/hora

1. Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **loyCustomers**.

1. Deseu la font de dades.

## <a name="task-2---data-unification"></a>Tasca 2 - Unificació de les dades

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Tasca 3 - Configurar la predicció de rotació de transaccions

Amb els perfils de clients unificats, ara podem executar el predicció de la transacció. Per obtenir passos detallats, vegeu l'article [predicció de l'article](predict-transactional-churn.md) Predicció transacció. 

1. Aneu a **Intel·ligència** > **Detecta** i seleccioneu l'ús del **Model d'abandonament de clients**.

1. Seleccioneu l'opció **Transaccional** i seleccioneu **Comença**.

1. Anomeneu el model **Predicció de rotació de transaccions de comerç electrònic OOB** i l'entitat de sortida **OOBeCommerceChurnPrediction**.

1. Definiu dues condicions per al model de rotació:

   * **Finestra de predicció**: **com a mínim 60** dies. Amb aquesta configuració es defineix fins a quin punt en el futur volem predir la rotació de clients.

   * **Definició de la cancel·lació**: **com a mínim 60** dies. La duració sense comprar al cap de la qual es considera que un client és rotació.

     :::image type="content" source="media/model-levers.PNG" alt-text="seleccioneu les opcions del model Finestra de predicció i Definició de la cancel·lació.":::

1. Seleccioneu **Historial de compres (obligatori)** i seleccioneu **Afegeix dades** per a l'historial de compres.

1. Afegiu l'entitat **eCommercePurchases : eCommerce** i assigneu els camps del comerç electrònic als camps corresponents que requereix el model.

1. Uniu l'entitat **eCommercePurchases : eCommerce** amb **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Uniu entitats de comerç electrònic.":::

1. Seleccioneu **Següent** per definir la planificació del model.

   El model ha formar-se periòdicament per aprendre nous patrons quan hi ha dades noves ingerides. En aquest exemple, seleccioneu **Mensual**.

1. Un cop revisats tots els detalls, seleccioneu **Desa i executa**.

## <a name="task-4---review-model-results-and-explanations"></a>Tasca 4 - Revisar els resultats i les explicacions del model

Deixeu que el model completi la formació i la puntuació de les dades. Ara podeu revisar les explicacions del model de churn. Per obtenir més informació, vegeu [Revisar un estat de predicció i els resultats](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tasca 5 - Crear un segment de clients amb un alt risc de rotació

En executar el model de producció, es crea una entitat nova, que podreu veure a **Dades** > **Entitats**.   

Podeu crear un segment nou a partir de l'entitat creada pel model.

1.  Aneu a **Segments**. Seleccioneu **Nou** i trieu **Crea a partir de** > **Intel·ligència**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creació d'un segment amb la sortida del model.":::

1. Seleccioneu el **punt final OOBeCommerceChurnPrediction** i definiu el segment: 
   - Camp: ChurnScore
   - Operador: major que
   - Valor: 0,6

Ara teniu un segment que s'actualitza dinàmicament i que identifica clients d'alt risc de rotació.

Per a més informació, vegeu [Crear i administrar segments](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
