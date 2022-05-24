---
title: Guia d'exemples de predicció de rotació de subscripcions
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de rotació de subscripcions preparat per a l'ús.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741399"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Guia d'exemples de predicció de rotació de subscripcions

Se us guiarà per un exemple íntegre de predicció de rotació de subscripció mitjançant les dades d'exemple següents. 

## <a name="scenario"></a>Escenari

Contoso és una empresa que produeix cafè i cafeteres d'alta qualitat, productes que ven a través del seu lloc web de Contoso Coffee. Fa poc, van iniciar un negoci de subscripció per als seus clients per rebre cafè de manera periòdica. El seu objectiu és saber quins dels clients subscrits podrien cancel·lar la seva subscripció en els pròxims mesos. Sabent quins dels seus clients és **probable que rotin**, pot ajudar l'empresa a estalviar estratègies i mesures de màrqueting centrades en mantenir-los.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeu la data de naixement en data.":::

1. Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommerceContacts**.

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

### <a name="ingest-subscription-information"></a>Ingerir la informació de subscripció

1. Creeu una font de dades **SubscriptionHistory**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.

1. Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadchurnsubscriptionhistory.

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:

   - **SubscriptioID**: nombre enter
   - **SubscriptionAmount**: moneda
   - **SubscriptionEndDate**: data/hora
   - **SubscriptionStartDate**: data/hora
   - **TransactionDate**: data/hora
   - **IsRecurring**: vertader/fals
   - **Is_auto_renew**: vertader/fals
   - **RecurringFrequencyInMonths**: nombre enter

1. Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **SubscriptionHistory**.

1. Deseu la font de dades.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dades de clients des de ressenyes de llocs web

1. Creeu una font de dades **Website**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.

1. Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasswebsite.

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:

   - **ReviewRating**: nombre enter
   - **ReviewDate**: data

1. Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **webReviews**.

## <a name="task-2---data-unification"></a>Tasca 2 - Unificació de les dades

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Tasca 3 - Configurar la predicció de rotació de subscripcions

Amb els perfils de client unificats i a punt, ja podem executar la predicció de rotació de subscripcions. Per obtenir passos detallats, consulteu l'article [predicció](predict-subscription-churn.md) de subscripció. 

1. Aneu a **Intel·ligència** > **Detecta** i seleccioneu l'ús del **Model d'abandonament de clients**.

1. Seleccioneu l'opció **Subscripció** i seleccioneu **Comença**.

1. Anomeneu el model **Predicció de rotació de subscripcions OOB** i l'entitat de sortida **OOBSubscriptionChurnPrediction**.

1. Definiu dues condicions per al model de rotació:

   * **Dies des que va finalitzar la subscripció**: **com a mínim 60** dies. Si un client no renova la subscripció durant aquest temps després d'haver finalitzat la subscripció, se'l considerarà rotació. 

   * **Definició de la cancel·lació**: **com a mínim 93** dies. La duració durant la qual el model predirà quins clients podrien rotar. Com més enllà aneu en el futur, menys precisos seran els resultats.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="seleccioneu les opcions del model Finestra de predicció i Definició de la cancel·lació.":::

1. Seleccioneu **Addició de les dades necessàries** i seleccioneu **Afegeix dades** per a l'historial de subscripcions.

1. Afegiu l'entitat **Subscription : SubscriptionHistory** i assigneu els camps del comerç electrònic als camps corresponents que requereix el model.

1. Uniu-vos a l'entitat **Subscription : SubscriptionHistory** amb **eCommerceContacts : eCommerce**, i anomeneu la relació **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Uniu entitats de comerç electrònic.":::

1. A Activitats del client, afegiu l'entitat **webReviews : Website** i assigneu els camps de webReviews als camps corresponents que requereix el model. 
   - Clau principal: ReviewId
   - Data i hora: ReviewDate
   - Esdeveniment: ReviewRating

1. Configureu una activitat per a ressenyes de llocs web. Seleccioneu l'activitat **Opinió** i uniu l'entitat **webReviews : Website** amb **eCommerceContacts : eCommerce**.

1. Seleccioneu **Següent** per definir la planificació del model.

   El model ha formar-se periòdicament per aprendre nous patrons quan hi ha dades noves ingerides. En aquest exemple, seleccioneu **Mensual**.

1. Un cop revisats tots els detalls, seleccioneu **Desa i executa**.

## <a name="task-4---review-model-results-and-explanations"></a>Tasca 4 - Revisar els resultats i les explicacions del model

Deixeu que el model completi la formació i la puntuació de les dades. Ara ja podeu revisar les explicacions del model de rotació de subscripcions. Per obtenir més informació, vegeu [Revisar un estat de predicció i els resultats](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tasca 5 - Crear un segment de clients amb un alt risc de rotació

En executar el model de producció, es crea una entitat nova, que podreu veure a **Dades** > **Entitats**.   

Podeu crear un segment nou a partir de l'entitat creada pel model.

1.  Aneu a **Segments**. Seleccioneu **Nou** i trieu **Crea a partir de** > **Intel·ligència**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creació d'un segment amb la sortida del model.":::

1. Seleccioneu l'extrem **OOBSubscriptionChurnPrediction** i definiu el segment: 
   - Camp: ChurnScore
   - Operador: major que
   - Valor: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurar el segment de rotació de la subscripció.":::

Ja teniu un segment que s'actualitza dinàmicament i que identifica els clients amb un alt risc de rotació per a aquest negoci de subscripció.

Per a més informació, vegeu [Crear i administrar segments](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]