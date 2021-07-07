---
title: Guia d'exemple per a la predicció de recomanacions de productes
description: Utilitzeu aquesta guia d'exemples per provar el model de predicció de recomanacions de productes preparat per a l'ús.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306154"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Guia d'exemple per a la predicció de recomanacions de productes (versió preliminar)

Se us guiarà per un exemple íntegre de predicció de recomanacions de productes mitjançant les dades d'exemple següents.

## <a name="scenario"></a>Escenari

Contoso és una empresa que produeix cafè i cafeteres d'alta qualitat que venen mitjançant el seu lloc web de Contoso Coffee. El seu objectiu és comprendre quins productes han de recomanar als seus clients periòdics. Conèixer el que és **probable que comprin** els clients els pot ajudar a estalviar esforços de màrqueting centrant-se en articles concrets.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeu la data de naixement en data.":::

5. Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommerceContacts**.

6. **Deseu** la font de dades.

### <a name="ingest-online-purchase-data"></a>Ingerir dades de compres en línia

1. Afegiu un altre conjunt de dades a la mateixa font de dades **eCommerce**. Torneu a triar el connector **Text/CSV**.

1. Introduïu l'adreça URL de les dades de **Compres en línia** https://aka.ms/ciadclassonline.

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **PurchasedOn**: data/hora
   - **TotalPrice**: moneda

1. Al camp **Nom** de la subfinestra lateral, canvieu el nom de la font de dades **Query** per **eCommercePurchases**.

1. **Deseu** la font de dades.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dades de clients procedents de l'esquema de fidelització

1. Creeu una font de dades amb el nom **LoyaltyScheme**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.

1. Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/ciadclasscustomerloyalty.

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **DateOfBirth**: data
   - **RewardsPoints**: nombre enter
   - **CreatedOn**: data/hora

1. Al camp **Nom** de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **loyCustomers**.

1. **Deseu** la font de dades.

## <a name="task-2---data-unification"></a>Tasca 2 - Unificació de les dades

Després d'ingerir les dades, comencem el procés d'unificació de dades per crear un perfil de client unificat. Per obtenir més informació, vegeu [Unificació de les dades](data-unification.md).

### <a name="map"></a>Assignació

1. Un cop ingerides les dades, assigneu contactes de les dades de comerç electrònic i fidelització a tipus de dades comuns. Aneu a **Dades** > **Unifica** > **Assigna**.

2. Seleccioneu les entitats que representen el perfil del client (**eCommerceContacts** i **loyCustomers**).

   ![unificar les fonts de dades de comerç electrònic i de fidelització.](media/unify-ecommerce-loyalty.png)

3. Seleccioneu **ContactId** com a clau principal per a **eCommerceContacts** i **LoyaltyID** com a clau principal per a **loyCustomers**.

   ![Unifiqueu LoyaltyId com a clau principal.](media/unify-loyaltyid.png)

### <a name="match"></a>Coincidència

1. Aneu a la pestanya **Coincidència** i seleccioneu **Definició d'ordre**.

2. A la llista desplegable **Principal**, trieu **eCommerceContacts: eCommerce** com a font principal i incloeu tots els registres.

3. A la llista desplegable **Entitat 2**, trieu **loyCustomers: LoyaltyScheme** i incloeu tots els registres.

   ![Unifiqueu la coincidència de comerç electrònic i de fidelització.](media/unify-match-order.png)

4. Seleccioneu **Crea una regla nova**.

5. Afegiu la primera condició amb el FullName.

   - Per a eCommerceContacts seleccioneu **FullName** al desplegable.
   - Per a loyCustomers seleccioneu **FullName** al desplegable.
   - Seleccioneu la llista desplegable **Normalitza** i trieu el **Tipus (Telèfon, Nom, Adreça...)**.
   - Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.

6. Introduïu el nom **Nom complet, correu electrònic** per a la regla nova.

   - Per afegir una segona condició per a l'adreça electrònica seleccioneu **Afegeix una condició**.
   - Per a l'entitat eCommerceContacts, trieu **EMail** al desplegable.
   - Per a l'entitat loyCustomers, trieu **EMail** al desplegable.
   - Deixeu Normalitza en blanc.
   - Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.

   ![Unifiqueu la regla de coincidència per al nom i el correu electrònic.](media/unify-match-rule.png)

7. Seleccioneu **Desa** i **Executa**.

### <a name="merge"></a>Combinació

1. Aneu a la pestanya **Combinació**.

1. Al **ContactId** de l'entitat **loyCustomers**, canvieu el nom de visualització per **ContactIdLOYALTY** per diferenciar-lo dels altres identificadors ingerits.

   ![canvieu el nom de contactid de l'identificador de fidelització.](media/unify-merge-contactid.png)

1. Seleccioneu **Desa** i **Executa** per iniciar el procés de combinació.

## <a name="task-3---configure-product-recommendation-prediction"></a>Tasca 3: Configurar la predicció de recomanació de producte

Amb els perfils de client unificats i a punt, ja podem executar la predicció de rotació de subscripcions.

1. Aneu a **Intel·ligència** > **Predicció** i trieu **Recomanació de producte**.

1. Seleccioneu **Introducció**.

1. Anomeneu el model **Predicció del model de recomanació de productes de fàbrica** i l'entitat de sortida **OOBProductRecommendationModelPrediction**.

1. Definiu tres condicions per al model:

   - **Nombre de productes**: definiu aquest valor en **5**. Aquesta configuració defineix quants productes voleu recomanar als clients.

   - **Repeteix les compres previstes**: seleccioneu **Sí** per indicar que voleu incloure productes a la recomanació que els vostres clients ja han adquirit.

   - **Finestra de cerca en el passat**: seleccioneu com a mínim **365 dies**. Aquesta configuració defineix quin temps en el passat consultarà el model a l'activitat del client per utilitzar-la com a entrada de les seves recomanacions.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferències del model per al model de recomanació de producte.":::

1. Seleccioneu **Dades necessàries** i seleccioneu **Afegeix dades** per a l'historial de compres.

1. Afegiu l'entitat **eCommercePurchases : eCommerce** i assigneu els camps del comerç electrònic als camps corresponents que requereix el model.

1. Uniu l'entitat **eCommercePurchases : eCommerce** amb **eCommerceContacts : eCommerce**.

   ![Uniu entitats de comerç electrònic.](media/model-purchase-join.png)

1. Seleccioneu **Següent** per definir la planificació del model.

   El model ha formar-se periòdicament per aprendre nous patrons quan hi ha dades noves ingerides. En aquest exemple, seleccioneu **Mensual**.

1. Un cop revisats tots els detalls, seleccioneu **Desa i executa**.


## <a name="task-4---review-model-results-and-explanations"></a>Tasca 4 - Revisar els resultats i les explicacions del model

Deixeu que el model completi la formació i la puntuació de les dades. Ara ja podeu revisar les explicacions del model de recomanació de productes. Per obtenir més informació, vegeu [Revisar un estat de predicció i els resultats](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tasca 5: crear un segment de productes molt adquirits

En executar el model de producció, es crea una entitat nova, que podreu veure a **Dades** > **Entitats**.

Podeu crear un segment nou a partir de l'entitat creada pel model.

1. Aneu a **Segments**. Seleccioneu **Nou** i trieu **Crea a partir de** > **Intel·ligència**.

   ![Creació d'un segment amb la sortida del model.](media/segment-intelligence.png)

1. Seleccioneu l'extrem **OOBProductRecommendationModelPrediction** i definiu el segment:

   - Camp: ProductID
   - Operador: Valor
   - Valor: seleccioneu els tres ID de producte principals

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Creeu un segment a partir dels resultats del model.":::

Ara teniu un segment que s'actualitza dinàmicament i que identifica els clients que estan més disposats a comprar els tres productes més recomanats 

Per a més informació, vegeu [Crear i administrar segments](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
