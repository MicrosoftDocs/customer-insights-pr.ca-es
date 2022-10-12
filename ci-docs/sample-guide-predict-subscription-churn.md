---
title: Guia d'exemples de predicció de rotació de subscripcions
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de rotació de subscripcions preparat per a l'ús.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609994"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Guia d'exemples de predicció de rotació de subscripcions

Aquesta guia us explicarà un exemple d'extrem a extrem de la subscripció predicció mitjançant dades d'exemple. Et recomanem que provis aquesta predicció [en un entorn nou](manage-environments.md).

## <a name="scenario"></a>Escenari

Contoso és una empresa que produeix màquines de cafè i cafè d'alta qualitat. Venen els productes a través del seu lloc web Contoso Coffee. Fa poc, van iniciar un negoci de subscripció per als seus clients per rebre cafè de manera periòdica. El seu objectiu és entendre quins clients subscrits podrien cancel·lar la seva subscripció en els propers mesos. Saber quin dels seus clients és **probable que xucli** pot ajudar-los a estalviar esforços de màrqueting centrant-se en mantenir-los.

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.

## <a name="task-1---ingest-data"></a>Tasca 1 - Ingerir dades

Reviseu els articles [sobre la ingestió de](data-sources.md) dades i [la connexió a un Power Query font de dades](connect-power-query.md). La informació següent suposa que esteu familiaritzat amb la ingestió de dades en general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dades de clients procedents de la plataforma de comerç electrònic

1. Creeu una Power Query font de dades anomenada **eCommerce** i seleccioneu el **connector Text/CSV**.

1. Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscontacts.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeu la data de naixement en data.":::

1. **Al camp Nom** de la subfinestra de la dreta, canvieu el nom del vostre font de dades a **Comerç electrònicContactes**

1. Deseu la font de dades.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dades de clients procedents de l'esquema de fidelització

1. Creeu una font de dades anomenada **LoyaltyScheme** i seleccioneu el **connector Text/CSV**.

1. Introduïu l'URL per fidelitzar els clients https://aka.ms/ciadclasscustomerloyalty.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **DateOfBirth**: data
   - **RewardsPoints**: nombre enter
   - **CreatedOn**: data/hora

1. Al camp Nom **de** la subfinestra de la dreta, canvieu el nom del font de dades a **loyCustomers**.

1. Deseu la font de dades.

### <a name="ingest-subscription-information"></a>Ingerir la informació de subscripció

1. Creeu una font de dades anomenada **SubscriptionHistory** i seleccioneu el **connector Text/CSV**.

1. Introduïu l'URL de les subscripcions https://aka.ms/ciadchurnsubscriptionhistory.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **SubscriptioID**: nombre enter
   - **SubscriptionAmount**: moneda
   - **SubscriptionEndDate**: data/hora
   - **SubscriptionStartDate**: data/hora
   - **TransactionDate**: data/hora
   - **IsRecurring**: vertader/fals
   - **Is_auto_renew**: vertader/fals
   - **RecurringFrequencyInMonths**: nombre enter

1. Al camp Nom **de** la subfinestra de la dreta, canvieu el nom del font de dades a **SubscripcióHistory**.

1. Deseu la font de dades.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dades de clients des de ressenyes de llocs web

1. Creeu una font de dades anomenada **Lloc web** i seleccioneu el **connector Text/CSV**.

1. Introduïu l'URL de les ressenyes de https://aka.ms/ciadclasswebsite llocs web.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **ReviewRating**: nombre enter
   - **ReviewDate**: data

1. Al camp Nom **de** la subfinestra de la dreta, canvieu el nom del font de dades a **webReviews**.

## <a name="task-2---data-unification"></a>Tasca 2 - Unificació de les dades

Reviseu l'article [sobre la unificació de](data-unification.md) dades. La informació següent suposa que esteu familiaritzat amb la unificació de dades en general.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tasca 3- Crear l'activitat de l'historial de transaccions

Reviseu l'article [sobre les activitats](activities.md) dels clients. La informació següent suposa que esteu familiaritzat amb la creació d'activitats en general.

1. Creeu una activitat anomenada **SubscriptionHistory** amb l'entitat *Subscripció* i la seva clau principal, **CustomerId**.

1. Crea una relació entre *SubscriptionHistory:Subscription* i *eCommerceContacts:eCommerce* amb **CustomerID** com a clau externa per connectar les dues entitats.

1. Seleccioneu SubscriptionType per a EventActivity **i** **SubscriptionEndate** per a la **marca de temps**.**·**

1. Seleccioneu **Subscripció** per al Tipus **d'activitat** i assigneu semànticament les dades de l'activitat.

1. Executar l'activitat.

1. Afegiu una altra activitat i assigneu els noms dels seus camps als camps corresponents:
   - Entitat d'activitat dels clients: Reviews:Website
   - Clau principal: Website.Reviews.ReviewId
   - Marca de temps: Website.Reviews.ReviewDate
   - Incidència (nom de l'activitat): Website.Reviews.ActivityTypeDisplay
   - Detalls (import o valor): Website.Reviews.ReviewRating

1. Executar l'activitat.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Tasca 4 - Configurar la predicció de rotació de subscripcions

Amb els perfils de client unificats establerts i l'activitat creada, executeu la subscripció predicció. Per obtenir passos detallats, vegeu [Subscripció predicció](predict-subscription-churn.md).

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Crea**, seleccioneu **Utilitza el model** a la **peça Model de churn** del client.

1. Seleccioneu **Subscripció** per al tipus de churn i, a continuació, **Comenceu**.

1. Anomeneu el model **Predicció de rotació de subscripcions OOB** i l'entitat de sortida **OOBSubscriptionChurnPrediction**.

1. Definiu les preferències del model:
   - **Dies des que va** finalitzar la subscripció: **60** dies per indicar que un client es considera estafat si no renova la subscripció en aquest període després de finalitzar la subscripció.
   - **Dies per investigar el futur per predir el problema**: **93** dies, que és la durada que el model prediu quins clients podrien xuclar. Com més enllà aneu en el futur, menys precisos seran els resultats.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Seleccioneu les preferències del model i la definició de churn.":::

1. Seleccioneu **Següent**.

1. Al pas **Dades** obligatòries, seleccioneu **Afegeix dades** per proporcionar l'historial de subscripcions.

1. Seleccioneu **Subscripció** i l'entitat SubscriptionHistory i seleccioneu **Següent**. Les dades requerides s'emplenen automàticament des de l'activitat. Seleccioneu **Desa**.

1. A Activitats del client, seleccioneu **Afegeix dades**.

1. Per a aquest exemple, afegiu l'activitat de revisió web.

1. Seleccioneu **Següent**.

1. Al pas **Actualitzacions** de dades, seleccioneu **Mensual** per a la planificació del model.

1. Un cop revisats tots els detalls, seleccioneu **Desa i executa**.

## <a name="task-5---review-model-results-and-explanations"></a>Tasca 5 - Revisar els resultats i les explicacions del model

Deixeu que el model completi la formació i la puntuació de les dades. Reviseu les explicacions del model de subscripció. Per obtenir més informació, vegeu [Veure els resultats de predicció](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tasca 6 - Crear un segment de clients amb un alt risc de rotació

L'execució del model crea una entitat nova que es mostra a **Dades** > **Entitats**. Podeu crear un segment nou a partir de l'entitat creada pel model.

1. A la pàgina de resultats, seleccioneu **Crea un segment**.

1. Creeu una regla utilitzant l'entitat **OOBSubscriptionChurnPrediction** i definiu el segment:
   - **Camp**: ChurnScore
   - **Operador**: major de
   - **Valor**: 0.6

1. Seleccioneu **Desa** i **executa** el segment.

Ja teniu un segment que s'actualitza dinàmicament i que identifica els clients amb un alt risc de rotació per a aquest negoci de subscripció. Per a més informació, vegeu [Crear i administrar segments](segments.md).

> [!TIP]
> També podeu crear un segment per a un model de predicció des de la **pàgina Segments** seleccionant **Crea des** d'Intel·ligència i triant **Crea des d'Intel** > **·ligència**. Per obtenir més informació, vegeu [Crear un segment nou amb segments ràpids](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
