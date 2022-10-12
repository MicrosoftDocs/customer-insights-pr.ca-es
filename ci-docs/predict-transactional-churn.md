---
title: Predicció de la transacció (conté vídeo)
description: Predigueu si un client està en risc de deixar d'adquirir els vostres productes o serveis.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610500"
---
# <a name="predict-transaction-churn"></a>Predir la cancel·lació de transaccions

La predicció de rotació de transaccions ajuda a predir si un client deixarà de comprar els vostres productes o serveis en un determinat període.

Heu de tenir coneixements empresarials per entendre què significa churn per al vostre negoci. S'admeten definicions de rotació basades en el temps, és a dir, quan es considera que un client ha entrat en rotació després d'un període sense compres.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Per als entorns basats en comptes empresarials, podem preveure la cancel·lació de transaccions d'un compte i també una combinació de compte i un altre nivell d'informació, com ara la categoria de producte. Per exemple, afegir una dimensió pot ajudar a determinar la probabilitat que el compte "Contoso" deixi de comprar la categoria de producte "papereria d'oficina". A més, per als comptes empresarials, també podem utilitzar la IA per generar una llista de les raons potencials per les quals és probable que en un compte hi hagi cancel·lacions en una categoria d'informació de nivell secundari.

> [!TIP]
> Proveu el predicció de transaccions mitjançant dades d'exemple: [xuclador de transaccions predicció guia d'exemple](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [permisos de col·laborador](permissions.md).
- Almenys 10 perfils de clients, preferiblement més de 1.000 clients únics.
- Identificador de client, un identificador únic per fer coincidir les transaccions amb els vostres clients.
- Dades de transaccions durant almenys el doble de la finestra de temps seleccionada, com ara de dos a tres anys d'historial de transaccions. Idealment almenys dues transaccions per client. L'historial de transaccions ha d'incloure:
  - **Identificador** de transacció: identificador únic d'una compra o transacció.
  - **Data** d'operació: Data de la compra o transacció.
  - **Valor de l'operació**: Import moneda o valor numèric de l'operació.
  - **Identificador** únic de producte: identificador del producte o servei adquirit si les vostres dades es troben al nivell d'un article de línia.
  - **Si aquesta transacció va ser una devolució**: Camp true/false que identifica si la transacció va ser una devolució o no. Si el **valor de la transacció** és negatiu, inferim una rendibilitat.
- Dades de l'activitat del client:
  - Identificador de client, un identificador únic per assignar activitats als vostres clients.
  - **Clau primària:** identificador únic d'una activitat. Per exemple, una visita a un lloc web o un registre d'ús que revelen que el client ha provat una mostra del producte.
  - **Marca de temps:** data i hora de l'esdeveniment identificat per la clau principal.
  - **Esdeveniment:** nom de l'esdeveniment que voleu utilitzar. Per exemple, un camp anomenat "UserAction" d'una botiga de queviures podria ser un cupó que el client ha utilitzat.
  - **Detalls:** informació detallada de la incidència. Per exemple, un camp anomenat "CouponValue" d'una botiga de queviures podria ser el valor monetari del cupó.
- Menys del 20% dels valors que falten en el camp de dades de l'entitat facilitada

Per als comptes d'empresa (B a B), afegiu les dades dels clients alineades amb atributs més estàtics per garantir que el model funcioni millor:
- **CustomerID:** identificador únic per a un client.
- **Data de creació:** data en què es va afegir inicialment el client.
- **Estat o província:** ubicació de l'estat o província d'un client.
- **País:** País d'un client.
- **Indústria:** Tipus d'indústria d'un client. Per exemple, un camp anomenat "Sector" en un torrefactor de cafè podria indicar si el client era minorista.
- **Classificació:** Categorització d'un client per al teu negoci. Per exemple, un camp anomenat "ValueSegment" en un torrefactor de cafè podria ser el nivell de client segons la mida del client.

> [!NOTE]
> Per a una empresa amb alta freqüència de compra de clients (cada poques setmanes) es recomana seleccionar una definició de finestra de predicció i cancel·lació més curta. Per a una freqüència de compra baixa (cada pocs mesos o un cop l'any), trieu una definició de finestra predicció i cancel·lació més llarga.

## <a name="create-a-transaction-churn-prediction"></a>Crear una predicció de cancel·lació de transaccions

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Crea**, seleccioneu **Utilitza el model** a la **peça Model de churn** del client.

1. Seleccioneu **Transacció** per al tipus de churn i, a continuació, **Comenceu**.

1. **Anomeneu aquest model** i el **nom de l'entitat de sortida** per distingir-los d'altres models o entitats.

1. Seleccioneu **Següent**.

### <a name="define-customer-churn"></a>Definició de l'abandonament de clients

Seleccioneu **Desa l'esborrany** en qualsevol moment per desar el predicció com a esborrany. L'esborrany predicció es mostra a la **pestanya Les meves prediccions**.

1. Definiu la **finestra** de predicció. Per exemple, podeu predir el risc de rotació per als vostres clients en els pròxims 90 dies per alinear-lo amb les vostres estratègies de retenció de màrqueting. La predicció de risc de rotació durant un període de temps més llarg o curt pot fer que resulti més difícil abordar els factors del vostre perfil de risc de rotació, però això dependrà dels vostres requisits empresarials específics.

1. Introduïu el nombre de dies per definir-lo al camp de **definició** de Churn. Per exemple, si un client no ha fet cap compra en els darrers 30 dies, és possible que es consideri que és un problema per a la vostra empresa.

1. Seleccioneu **Següent**.

### <a name="add-purchase-history"></a>Afegeix l'historial de compres

1. Seleccioneu **Afegeix dades** per a **l'historial de transaccions de clients**.

1. Seleccioneu el tipus d'activitat semàntica, **SalesOrder** o **SalesOrderLine**, que conté la informació de l'historial de transaccions. Si l'activitat no s'ha configurat, seleccioneu **aquí** i creeu-la.

1. A **Activitats**, si els atributs d'activitat es van assignar semànticament quan es va crear l'activitat, trieu els atributs o l'entitat específics en què voleu centrar-vos en el càlcul. Si l'assignació semàntica no s'ha produït, seleccioneu **Edita** i assigna les dades.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Subfinestra lateral que mostra la tria d'activitats específiques sota el tipus semàntic.":::

1. Seleccioneu **Següent** i reviseu els atributs necessaris per a aquest model.

1. Seleccioneu **Desa**.

1. Afegiu més activitats o seleccioneu **Següent**.

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Afegir dades addicionals (opcional)

1. Seleccioneu **Afegeix dades** per a **les activitats** del client.

1. Seleccioneu el tipus d'activitat semàntica que conté les dades que voleu utilitzar. Si l'activitat no s'ha configurat, seleccioneu **aquí** i creeu-la.

1. A **Activitats**, si els atributs d'activitat es van assignar semànticament quan es va crear l'activitat, trieu els atributs o l'entitat específics en què voleu centrar-vos en el càlcul. Si l'assignació semàntica no s'ha produït, seleccioneu **Edita** i assigna les dades.

1. Seleccioneu **Següent** i reviseu els atributs necessaris per a aquest model.

1. Seleccioneu **Desa**.

1. Seleccioneu **Següent**

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

### <a name="select-prediction-level"></a>Seleccionar el nivell de predicció

La majoria de les prediccions es creen en el nivell del client. En algunes situacions, pot ser que no sigui prou granular per a les vostres necessitats empresarials. Utilitzeu aquesta funció per predir la quantitat d'una oficina d'un client, per exemple, en lloc de per al client en general.

1. Seleccioneu **Selecciona l'entitat per a un nivell** secundari. Si l'opció no està disponible, assegureu-vos que heu completat la secció anterior.

1. Expandiu les entitats de les quals voleu triar el nivell secundari o utilitzeu el quadre de filtre de cerca per filtrar les opcions seleccionades.

1. Trieu l'atribut que voleu utilitzar com a nivell secundari i seleccioneu **Afegeix**.

1. Seleccioneu **Següent**.

> [!NOTE]
> Les entitats disponibles en aquesta secció es mostren perquè tenen una relació amb l'entitat que heu triat a la secció anterior. Si no veieu l'entitat que voleu afegir, assegureu-vos que té una relació vàlida present a **Relacions**. Només les relacions d'un a un i de diversos a un són vàlides per a aquesta configuració.

### <a name="add-additional-data-optional"></a>Afegir dades addicionals (opcional)

1. Seleccioneu **Afegeix dades** per a **les activitats** del client.

1. Seleccioneu el tipus d'activitat semàntica que conté les dades que voleu utilitzar. Si l'activitat no s'ha configurat, seleccioneu **aquí** i creeu-la.

1. A **Activitats**, si els atributs d'activitat es van assignar semànticament quan es va crear l'activitat, trieu els atributs o l'entitat específics en què voleu centrar-vos en el càlcul. Si l'assignació semàntica no s'ha produït, seleccioneu **Edita** i assigna les dades.

1. Seleccioneu **Següent** i reviseu els atributs necessaris per a aquest model.

1. Seleccioneu **Desa**.

1. Seleccioneu **Següent**

1. O bé, seleccioneu **Afegeix dades** per a les **Dades de clients**.

1. Assigneu els atributs semàntics als camps de les vostres pròpies dades de client segons s'identifica. Les dades dels camps utilitzats no han de canviar sovint per garantir el millor rendiment del model. Per exemple, si seleccioneu un camp per a "Classificació" que canviï cada mes només tindreu l'últim valor utilitzat a la predicció, encara que històricament el mateix valor no s'apliqui al client en crear els patrons de predicció.

1. Seleccioneu **Següent**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Proporcionar una llista opcional de comptes de referència

Afegiu una llista de clients empresarials i de comptes que voleu utilitzar com a referències. Els [detalls d'aquests comptes de referència inclouen la seva puntuació i les característiques més influents](#view-prediction-results) que van afectar la seva predicció.

1. Seleccioneu **+ Afegeix clients**.

1. Trieu els clients que actuen com a referències.

1. Seleccioneu **Següent**.

---

### <a name="set-update-schedule"></a>Configurar la planificació d'actualització

1. **Al pas Actualitzacions** de dades, trieu una freqüència per reciclar el model. Aquesta configuració és important per actualitzar la precisió de les prediccions a mesura que s'ingereixen dades noves al Customer Insights. La majoria d'empreses poden tornar a entrenar un cop al mes i obtenir una bona precisió de les prediccions.

1. Seleccioneu **Següent**.

### <a name="review-and-run-the-model-configuration"></a>Revisar i executar la configuració del model

El **pas Revisa i executa** mostra un resum de la configuració i proporciona l'oportunitat de fer canvis abans de crear el predicció.

1. Seleccioneu **Edita** en qualsevol dels passos per revisar i fer qualsevol canvi.

1. Si esteu satisfet amb les vostres seleccions, seleccioneu **Desa i executa** per començar a executar el model. Seleccioneu **Fet**. La **pestanya Les meves prediccions** es mostra mentre es crea el predicció. El procés pot tardar unes quantes hores a completar-se en funció de la quantitat de dades que s'han utilitzat a la predicció.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Veure predicció resultats

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Les meves prediccions**, seleccioneu la predicció voleu visualitzar.

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

A la pàgina de resultats hi ha tres seccions principals de dades:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

A la pàgina de resultats hi ha tres seccions principals de dades:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Una **pàgina d'informació d'anàlisi** de funcions influents conté quatre seccions de dades:

- A la subfinestra de la dreta, seleccioneu un element entre **Clients** principals o **Clients de referència**. Ambdues llistes s'ordenen en ordre decreixent pel valor de la puntuació de rotació, tant si la puntuació és només per al client o una puntuació combinada de client i un nivell secundari, com ara la categoria de producte. L'element seleccionat determina el contingut d'aquesta pàgina.

  - **Clients principals**: llista de 10 clients amb el risc més alt de rotació i el risc més baix de rotació en funció de les seves puntuacions de rotació.
  - **Clients de referència**: llista de fins a 10 clients que es van seleccionar en configurar el model.

- **Puntuació de rotació:** mostra la puntuació de rotació per a l'element seleccionat a la subfinestra dreta.

- **Distribució del risc de Churn:** Mostra la distribució del risc entre els clients i el percentil en què es troba el client seleccionat.

- **Funcions principals que augmenten i disminueixen el risc de churn:** llista les cinc funcions principals que han augmentat i disminuït el risc de churn per a l'element seleccionat a la subfinestra dreta. Mostra el valor de la característica per a aquest element i la seva influència en la puntuació de churn per a cada característica influent. El valor mitjà de cada característica en els segments de rotació de clients baix, mitjà i alt també es mostra. Ajuda a contextualitzar millor els valors de les característiques més influents per a l'element seleccionat i comparar-lo amb els segments de rotació de clients baix, mitjà i alt.

  - Baixa: comptes o combinacions de compte i nivell secundari amb una puntuació entre 0 i 0,33.
  - Mitjà: comptes o combinacions de comptes i nivells secundaris amb una puntuació entre 0,33 i 0,66.
  - Alta: comptes o combinacions de comptes i nivells secundaris amb una puntuació superior a 0,66.

  Quan prediu la rotació al nivell de compte, tots els comptes es tenen en compte a l'hora de derivar els valors mitjans de les característiques dels segments de rotació. Per a les previsions de rotació en el nivell secundari de cada compte, la derivació dels segments de rotació depèn del nivell secundari de l'element seleccionat a la subfinestra lateral. Per exemple, si un article té un nivell secundari de categoria de producte (material d'oficina), només es tenen en compte els articles que tenen material d'oficina com a categoria de producte quan es deriven els valors mitjans de les funcions per als segments de churn. Aquesta lògica s'aplica per garantir una comparació justa dels valors de característica de l'element amb els valors mitjans en segments de rotació de nivell baix, mitjà i alt.

  En alguns casos, el valor mitjà dels segments de rotació de nivell baix, mitjà o alt està buit o no està disponible perquè no hi ha cap element que pertanyi als segments de rotació corresponents basant-se en la definició anterior.

  La interpretació dels valors sota la mitjana de les columnes baixa, mitjana i alta és diferent per a les característiques classificades, com ara el país o el sector. Com que la noció del valor de característica "mitjana" no s'aplica a les característiques classificades en categories, els valors d'aquestes columnes són la proporció dels clients en segments d'abandó baix, mitjà o alt que tenen el mateix valor de la característica de la categoria en comparació amb l'element seleccionat a la subfinestra lateral.

---

 > [!NOTE]
 > En l'entitat de sortida d'aquest model, *ChurnScore* mostra la probabilitat predita de churn i *IsChurn* és una etiqueta binària basada *en ChurnScore* amb llindar 0,5. Si aquest llindar predeterminat no funciona per al vostre escenari, [creeu un segment](segments.md#create-a-segment) nou amb el llindar preferit. No tots els clients són necessàriament clients actius. Alguns d'ells poden no haver tingut cap activitat durant molt de temps i es consideren ja cancel·lat, basant-se en la definició de cancel·lació. Predir el risc de rotació dels clients que ja han marxat no és útil perquè no són el públic d'interès.
>
> Per visualitzar la puntuació de churn, aneu a **Entitats** > **de dades** i visualitzeu la pestanya dades de l'entitat de sortida que heu definit per a aquest model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
