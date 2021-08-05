---
title: Guia d'exemples de predicció de rotació de transaccions
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de rotació de transaccions preparat per a l'ús.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 72f3bd1f32b813fef04dc14618331e3d707b5052
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556249"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a>Guia d'exemples de predicció de rotació de transaccions (versió preliminar)

En aquesta guia, se us guiarà per un exemple íntegre de predicció de rotació de transaccions al Customer Insights mitjançant les dades següents. Totes les dades utilitzades en aquesta guia no són dades reals dels clients i formen part del conjunt de dades de Contoso que es troba a l'entorn *Demostració* de la vostra subscripció al Customer Insights.

## <a name="scenario"></a>Escenari

Contoso és una empresa que produeix cafè i cafeteres d'alta qualitat que venen mitjançant el seu lloc web de Contoso Coffee. El seu objectiu és saber quins clients que acostumen a comprar els seus productes de manera periòdica deixaran de ser clients actius en els propers 60 dies. Sabent quins dels seus clients és **probable que rotin**, pot ajudar l'empresa a estalviar estratègies i mesures de màrqueting centrades en mantenir-los.

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.
- Us recomanem que implementeu els passos següents [en un entorn nou](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tasca 1 - Ingerir dades

Reviseu els articles [sobre la ingestió de dades](data-sources.md) i, més concretament, [la importació de fonts de dades mitjançant els connectors del Power Query](connect-power-query.md). La informació següent suposa que ja esteu familiaritzat amb el concepte d'ingestió de dades en general. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dades de clients procedents de la plataforma de comerç electrònic

1. Creeu una font de dades **eCommerce**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.

1. Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscontacts.

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:

   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/zona

   [!div class="mx-imgBorder"]
   ![Transformar DoB en Data.](media/ecommerce-dob-date.PNG "transformar la data de naixement en data")

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

Un cop feta la ingestió de les dades, començarem el procés d'**assignació, coincidència i combinació** per tal de crear un perfil de client unificat. Per obtenir més informació, vegeu [Unificació de les dades](data-unification.md).

### <a name="map"></a>Assignació

1. Un cop ingerides les dades, assigneu contactes de les dades de comerç electrònic i fidelització a tipus de dades comuns. Aneu a **Dades** > **Unifica** > **Assigna**.

1. Seleccioneu les entitats que representen el perfil del client (**eCommerceContacts** i **loyCustomers**). 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar les fonts de dades de comerç electrònic i de fidelització.":::

1. Seleccioneu **ContactId** com a clau principal per a **eCommerceContacts** i **LoyaltyID** com a clau principal per a **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifiqueu LoyaltyId com a clau principal.":::

### <a name="match"></a>Coincidència

1. Aneu a la pestanya **Coincidència** i seleccioneu **Definició d'ordre**.

1. A la llista desplegable **Principal**, trieu **eCommerceContacts: eCommerce** com a font principal i incloeu tots els registres.

1. A la llista desplegable **Entitat 2**, trieu **loyCustomers: LoyaltyScheme** i incloeu tots els registres.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unifiqueu la coincidència de comerç electrònic i de fidelització.":::

1. Seleccioneu **Crea una regla nova**.

1. Afegiu la primera condició amb el FullName.

   * Per a eCommerceContacts seleccioneu **FullName** al desplegable.
   * Per a loyCustomers seleccioneu **FullName** al desplegable.
   * Seleccioneu la llista desplegable **Normalitza** i trieu el **Tipus (Telèfon, Nom, Adreça...)**.
   * Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.

1. Introduïu el nom **Nom complet, correu electrònic** per a la regla nova.

   * Per afegir una segona condició per a l'adreça electrònica seleccioneu **Afegeix una condició**.
   * Per a l'entitat eCommerceContacts, trieu **EMail** al desplegable.
   * Per a l'entitat loyCustomers, trieu **EMail** al desplegable. 
   * Deixeu Normalitza en blanc. 
   * Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unifiqueu la regla de coincidència per al nom i el correu electrònic.":::

7. Seleccioneu **Desa** i **Executa**.

### <a name="merge"></a>Combinació

1. Aneu a la pestanya **Combinació**.

1. Al **ContactId** de l'entitat **loyCustomers**, canvieu el nom de visualització per **ContactIdLOYALTY** per diferenciar-lo dels altres identificadors ingerits.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="canvieu el nom de contactid de l'identificador de fidelització.":::

1. Seleccioneu **Desa** i **Executa** per iniciar el procés de combinació.



## <a name="task-3---configure-transaction-churn-prediction"></a>Tasca 3 - Configurar la predicció de rotació de transaccions

Amb els perfils de client unificats i a punt, ja podem executar la predicció de rotació de subscripcions. Per veure'n els passos detallats, vegeu l'article [Predicció de rotació de subscripcions (versió preliminar)](predict-subscription-churn.md). 

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]