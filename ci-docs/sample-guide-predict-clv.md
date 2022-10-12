---
title: Guia de mostra per a les prediccions de valor de vida dels clients (CLV)
description: Utilitzeu aquesta guia d'exemple per provar el model de predicció del valor de vida dels clients.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609626"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guia de mostra per a les prediccions de valor de vida dels clients (CLV)

Aquesta guia us guiarà per un exemple d'extrem a extrem del valor del cicle de client (CLV) predicció al Customer Insights mitjançant dades d'exemple. Et recomanem que provis aquesta predicció [en un entorn nou](manage-environments.md).

## <a name="scenario"></a>Escenari

Contoso és una empresa que produeix màquines de cafè i cafè d'alta qualitat. Venen els productes a través del seu lloc web Contoso Coffee. L'empresa vol comprendre el valor (ingressos) que poden generar els seus clients en els propers 12 mesos. Conèixer el valor esperat dels seus clients durant els propers 12 mesos els ajudarà a dirigir els seus esforços de màrqueting cap als clients d'alt valor.

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [permisos de col·laborador](permissions.md).

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

1. **Deseu** la font de dades.

### <a name="ingest-online-purchase-data"></a>Ingerir dades de compres en línia

1. Afegiu un altre conjunt de dades a la mateixa font de dades **eCommerce**. Torneu a triar el connector **Text/CSV**.

1. Introduïu l'adreça URL de les dades de **Compres en línia** https://aka.ms/ciadclassonline.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **PurchasedOn**: data/hora
   - **TotalPrice**: moneda

1. Al camp Nom **de** la subfinestra lateral, canvieu el nom del vostre font de dades a **Compres de comerç electrònic**.

1. **Deseu** la font de dades.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dades de clients procedents de l'esquema de fidelització

1. Creeu una font de dades anomenada **LoyaltyScheme** i seleccioneu el **connector Text/CSV**.

1. Introduïu l'URL per fidelitzar els clients https://aka.ms/ciadclasscustomerloyalty.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **DateOfBirth**: data
   - **RewardsPoints**: nombre enter
   - **CreatedOn**: data/hora

1. Al camp Nom **de** la subfinestra de la dreta, canvieu el nom del font de dades a **loyCustomers**.

1. **Deseu** la font de dades.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dades de clients des de ressenyes de llocs web

1. Creeu una font de dades anomenada **Lloc web** i seleccioneu el **connector Text/CSV**.

1. Introduïu l'URL de les ressenyes de llocs web https://aka.ms/CI-ILT/WebReviews.

1. Mentre editeu les dades, seleccioneu Transforma **i**, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **ReviewRating**: nombre decimal
   - **ReviewDate**: data

1. Al camp Nom **de** la subfinestra de la dreta, canvieu el nom del font de dades a **Ressenyes**.

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

1. Afegiu una altra activitat i assigneu els noms dels seus camps als camps corresponents:
   - **Entitat** de l'activitat: Ressenyes:Lloc web
   - **Clau principal**: ReviewId
   - **Marca de** temps: RevisióDate
   - **Activitat** de l'esdeveniment: ActivityTypeDisplay
   - **Detall** addicional: ReviewRating
   - **Tipus** d'activitat: Revisió

1. Executar l'activitat.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Tasca 4: configurar la predicció del valor de vida dels clients

Amb els perfils de client unificats i l'activitat creada, executeu el valor de vida del client (CLV) predicció. Per obtenir passos detallats, vegeu [predicció del Valor del](predict-customer-lifetime-value.md) vida del client.

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Crea**, seleccioneu **Utilitza el model** a la peça Valor **del cicle de vida del** client.

1. Seleccioneu **Introducció**.

1. Poseu un nom al model **Predicció del CLV a OOB eCommerce** i a l'entitat de sortida **OOBeCommerceCLVPrediction**.

1. Definiu les preferències del model:
   - **predicció període de** temps: **12 mesos o 1 any** per definir fins a quin punt en el futur s'ha de predir el CLV.
   - **Clients actius**: **Permet calcular l'interval** de compra, que és el període de temps en què un client ha d'haver tingut almenys una transacció per considerar-se actiu.
   - **Client d'alt valor**: defineix manualment els clients d'alt valor com **el 30% superior dels clients actius**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Pas de preferències de l'experiència guiada per al model del CLV.":::

1. Seleccioneu **Següent**.

1. Al pas **Dades necessàries**, seleccioneu **Afegeix dades** per proporcionar les dades de l'historial de transaccions.

    :::image type="content" source="media/clv-model-required.png" alt-text="Afegiu el pas de dades necessàries a l'experiència guiada per al model CLV.":::

1. Seleccioneu **SalesOrderLine** i l'entitat eCommerceCompra i seleccioneu **Següent**. Les dades requerides s'emplenen automàticament des de l'activitat. Seleccioneu **Desa** i, a continuació, **Següent**.

1. El **pas Dades addicionals (opcional)** us permet afegir més dades d'activitat dels clients per obtenir més estadístiques de les interaccions amb els clients. Per a aquest exemple, seleccioneu **Afegeix dades** i afegiu l'activitat de revisió web.

1. Seleccioneu **Següent**.

1. Al pas **Actualitzacions** de dades, seleccioneu **Mensual** per a la planificació del model.

1. Seleccioneu **Següent**.

1. Un cop revisats tots els detalls, seleccioneu **Desa i executa**.

## <a name="task-5---review-model-results-and-explanations"></a>Tasca 5 - Revisar els resultats i les explicacions del model

Deixeu que el model completi la formació i la puntuació de les dades. Reviseu els resultats i explicacions [del](predict-customer-lifetime-value.md#view-prediction-results) model CLV.

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Tasca 6: crear un segment de clients d'alt valor

L'execució del model crea una entitat nova que es mostra a **Dades** > **Entitats**. Podeu crear un segment de client nou basat en l'entitat creada pel model.

1. A la pàgina de resultats, seleccioneu **Crea un segment**.

1. Creeu una regla mitjançant l'entitat **OOBeCommerceCLVPrediction** i definiu el segment:
   - **Camp**: CLVScore
   - **Operador**: major de
   - **Valor**: 1500

1. Seleccioneu **Desa** i **executa** el segment.

Ara teniu un segment que identifica els clients que es preveu que generin més de 1500 USD d'ingressos en els propers 12 mesos. Aquest segment s'actualitza dinàmicament si s'ingesten més dades. Per a més informació, vegeu [Crear i administrar segments](segments.md).

> [!TIP]
> També podeu crear un segment per a un model de predicció des de la **pàgina Segments** seleccionant **Crea des** d'Intel·ligència i triant **Crea des d'Intel** > **·ligència**. Per obtenir més informació, vegeu [Crear un segment nou amb segments ràpids](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
