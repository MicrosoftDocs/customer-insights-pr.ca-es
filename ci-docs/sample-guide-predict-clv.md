---
title: Guia de mostra per a les prediccions de valor de vida dels clients
description: Utilitzeu aquesta guia d'exemple per provar el model de predicció del valor de vida dels clients.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 9f8d1d0f0757d8003ad3859fab75362f3988cd00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642353"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guia de mostra per a les prediccions de valor de vida dels clients (CLV)

Aquesta guia us explicarà un exemple final de la predicció del valor de vida dels clients (CLV) al Customer Insights mitjançant dades d'exemple.

## <a name="scenario"></a>Escenari

Contoso és una empresa que produeix màquines de cafè i cafè d'alta qualitat. Venen els productes a través de la seva pàgina web Contoso Coffee. L'empresa vol comprendre el valor (ingressos) que poden generar els seus clients en els propers 12 mesos. Conèixer el valor esperat dels seus clients durant els propers 12 mesos els ajudarà a dirigir els seus esforços de màrqueting cap als clients d'alt valor.

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.
- Us recomanem que implementeu els passos següents [en un entorn nou](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tasca 1 - Ingerir dades

Reviseu els articles [sobre la ingestió](data-sources.md) de dades i [la importació d'orígens de dades mitjançant Power Query connectors](connect-power-query.md). La informació següent suposa que ja esteu familiaritzat amb el concepte d'ingestió de dades en general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dades de clients procedents de la plataforma de comerç electrònic

1. Creeu una font de dades anomenada **eCommerce**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.

1. Introduïu l'adreça URL dels contactes d'eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:
   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformeu la data de naixement en data.":::

1. Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades **Query** per **eCommerceContacts**.

1. **Deseu** la font de dades.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dades de clients des de ressenyes de llocs web

1. Creeu una font de dades **Website**, trieu l'opció d'importació i seleccioneu el connector **Text/CSV**.

1. Introduïu l'adreça URL dels contactes de comerç electrònic https://aka.ms/CI-ILT/WebReviews.

1. Mentre editeu les dades, seleccioneu **Transforma** i, a continuació, **Utilitza la primera fila com a capçaleres**.

1. Actualitzeu el tipus de dades de les columnes següents:

   - **ReviewRating**: nombre decimal
   - **ReviewDate**: data

1. Al camp "Nom" de la subfinestra de la dreta, canvieu el nom de la font de dades de **Consulta** a **Comentaris**.

1. **Deseu** la font de dades.

## <a name="task-2---data-unification"></a>Tasca 2 - Unificació de les dades

Després d'ingerir les dades, comencem el procés d'unificació de dades per crear un perfil de client unificat. Per obtenir més informació, vegeu [Unificació de les dades](data-unification.md).

### <a name="map"></a>Assignació

1. Un cop ingerides les dades, assigneu contactes de les dades de comerç electrònic i fidelització a tipus de dades comuns. Aneu a **Dades** > **Unifica** > **Assigna**.

1. Seleccioneu les entitats que representen el perfil del client (**eCommerceContacts** i **loyCustomers**). A continuació, seleccioneu **Aplica**.

   ![unificar les fonts de dades de comerç electrònic i de fidelització.](media/unify-ecommerce-loyalty.png)

1. Seleccioneu **ContactId** com a clau principal per a **eCommerceContacts** i **LoyaltyID** com a clau principal per a **loyCustomers**.

   ![Unifiqueu LoyaltyId com a clau principal.](media/unify-loyaltyid.png)

1. Seleccioneu **Desa**.

### <a name="match"></a>Coincidència

1. Aneu a la pestanya **Coincidència** i seleccioneu **Definició d'ordre**.

1. A la llista desplegable **Principal**, trieu **eCommerceContacts: eCommerce** com a font principal i incloeu tots els registres.

1. A la llista desplegable **Entitat 2**, trieu **loyCustomers: LoyaltyScheme** i incloeu tots els registres.

   ![Unifiqueu la coincidència de comerç electrònic i de fidelització.](media/unify-match-order.png)

1. Seleccioneu **Afegeix una regla**

1. Afegiu la primera condició amb el FullName.

   - Per a eCommerceContacts seleccioneu **FullName** al desplegable.
   - Per a loyCustomers seleccioneu **FullName** al desplegable.
   - Seleccioneu el desplegable **Normalització** i trieu **Tipus (Telèfon, Nom, Adreça, ...)**.
   - Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.

1. Introduïu el nom **Nom complet, correu electrònic** per a la regla nova.

   - Per afegir una segona condició per a l'adreça electrònica seleccioneu **Afegeix una condició**.
   - Per a l'entitat eCommerceContacts, trieu **EMail** al desplegable.
   - Per a l'entitat loyCustomers, trieu **EMail** al desplegable.
   - Deixeu Normalitza en blanc.
   - Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.

   ![Unifiqueu la regla de coincidència per al nom i el correu electrònic.](media/unify-match-rule.png)

1. Seleccioneu **Fet**.

1. Seleccioneu **Desa** i **Executa**.

### <a name="merge"></a>Combinació

1. Aneu a la pestanya **Combinació**.

1. Al **ContactId** de l'entitat **loyCustomers**, canvieu el nom de visualització per **ContactIdLOYALTY** per diferenciar-lo dels altres identificadors ingerits.

   ![canvieu el nom de contactid de l'identificador de fidelització.](media/unify-merge-contactid.png)

1. Seleccioneu **Desa** i **Executa la combinació i els processos descendents**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Tasca 3: configurar la predicció del valor de vida dels clients

Amb els perfils de client unificats al seu lloc, ara podem executar la predicció del valor de vida dels clients. Per obtenir passos detallats, vegeu [Valor de vida del client predicció](predict-customer-lifetime-value.md).

1. Aneu a **Intel·ligència**  > **Prediccions** i seleccioneu el **Model de valor de vida dels clients**.

1. Passeu per la informació de la subfinestra lateral i seleccioneu **Comença**.

1. Poseu un nom al model **Predicció del CLV a OOB eCommerce** i a l'entitat de sortida **OOBeCommerceCLVPrediction**.

1. Definiu les preferències del model per al model CLV:
   - **Període de temps de la predicció**: **12 mesos o 1 any**. Aquesta configuració defineix fins a quin punt del futur cal preveure el valor de vida dels clients.
   - **Clients actius**: especifiqueu què signifiquen els clients actius per a la vostra empresa. Definiu el període de temps històric en què un client ha d'haver tingut com a mínim una transacció per considerar-lo actiu. El model només predirà el CLV per als clients actius. Trieu entre permetre que el model calculi el període de temps segons les dades de transaccions històriques o proporcioneu un període de temps específic. En aquesta guia d'exemple, **fem que el model calculi l'interval de compra**, que és l'opció per defecte.
   - **Clients d'alt valor**: definiu els clients d'alt valor com a percentil de clients que més paguen. El model utilitza aquesta entrada per proporcionar resultats que s'ajustin a la definició empresarial de clients d'alt valor. Podeu triar que el model defineixi els clients d'alt valor. Utilitza una regla heurística que deriva el percentil. També podeu definir els clients d'alt valor com a percentil de clients que més pagaran. En aquesta guia d'exemple, definim manualment els clients d'alt valor com el **30% superior dels clients actius que paguen** i seleccionem **Següent**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Pas de preferències de l'experiència guiada per al model del CLV.":::

1. Al pas **Dades necessàries**, seleccioneu **Afegeix dades** per proporcionar les dades de l'historial de transaccions.

1. Afegiu l'entitat **eCommercePurchases: eCommerce** i assigneu els atributs que necessita el model:
   - Identificador de transacció: eCommerce.eCommercePurchases.PurchaseId
   - Data de transacció: eCommerce.eCommercePurchases.PurchasedOn
   - Import de les transaccions: eCommerce.eCommercePurchases.TotalPrice
   - ID del producte: eCommerce.eCommercePurchases.ProductId

1. Seleccioneu **Següent**.

1. Establiu la relació entre l'entitat **eCommercePurchases: eCommerce** i **eCommerceContacts: eCommerce**.

1. El pas **Dades addicionals (opcional)** us permet afegir més dades d'activitats dels clients. Aquestes dades poden ajudar a obtenir més informació sobre les interaccions dels clients amb el vostre negoci, la qual cosa pot contribuir al CLV. Afegir interaccions clau dels clients, com ara registres web, registres del servei d'atenció al client o l'historial del programa de recompenses pot millorar la precisió de les previsions. Seleccioneu **Afegeix dades** per incloure més dades d'activitat dels clients.

1. Afegiu l'entitat de l'activitat dels clients i assigneu els noms dels camps als camps corresponents que necessita el model:
   - Entitat d'activitat dels clients: Reviews:Website
   - Clau principal: Website.Reviews.ReviewId
   - Marca de temps: Website.Reviews.ReviewDate
   - Incidència (nom de l'activitat): Website.Reviews.ActivityTypeDisplay
   - Detalls (import o valor): Website.Reviews.ReviewRating

1. Seleccioneu **Següent** i configureu l'activitat i la relació entre les dades de transacció i les dades del client:  
   - Tipus d'activitat: trieu-ne una d'existent
   - Etiqueta de l'activitat: Review
   - Etiqueta corresponent: Website.Reviews.UserId
   - Entitat de client: eCommerceContacts:eCommerce
   - Relació: WebsiteReviews

1. Seleccioneu **Següent** per definir la planificació del model.

   El model ha d'entrenar-se periòdicament per aprendre nous patrons quan s'ingesten dades noves. En aquest exemple, trieu **Mensual**.

1. Un cop revisats tots els detalls, seleccioneu **Desa i executa**.

## <a name="task-4---review-model-results-and-explanations"></a>Tasca 4 - Revisar els resultats i les explicacions del model

Deixeu que el model completi la formació i la puntuació de les dades. A continuació, podeu revisar els resultats i les explicacions del model del CLV. Per obtenir més informació, vegeu [Revisar un estat de predicció i els resultats](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Tasca 5: crear un segment de clients d'alt valor

L'execució del model crea una entitat nova que es mostra a **Dades** > **Entitats**. Podeu crear un segment de client nou basat en l'entitat creada pel model.

1. Aneu a **Segments**. 

1. Seleccioneu **Nou** i trieu **Crea a partir de** > **Intel·ligència**.

   ![Creació d'un segment amb la sortida del model.](media/segment-intelligence.png)

1. Seleccioneu l'entitat **OOBeCommerceCLVPrediction** i definiu el segment:
  - Camp: CLVScore
  - Operador: major que
  - Valor: 1500

1. Seleccioneu **Revisa** i **Deseu** el segment.

Ara teniu un segment que identifica els clients que es preveu que generin més de 1500 USD d'ingressos en els propers 12 mesos. Aquest segment s'actualitza dinàmicament si s'ingesten més dades.

Per a més informació, vegeu [Crear i administrar segments](segments.md).
