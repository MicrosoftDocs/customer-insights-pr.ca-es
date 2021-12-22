---
title: Predicció de rotació de transaccions (Vídeo)
description: Predigueu si un client està en risc de deixar d'adquirir els vostres productes o serveis.
ms.date: 10/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ad87e0fd848168d1a18f28f2ac5c507bb01e1f28
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/10/2021
ms.locfileid: "7904060"
---
# <a name="transaction-churn-prediction-preview"></a>Predicció de cancel·lació de transaccions (versió preliminar)

La predicció de rotació de transaccions ajuda a predir si un client deixarà de comprar els vostres productes o serveis en un determinat període. Per crear prediccions de rotació noves, aneu a **Intel·ligència** > **Prediccions**. Seleccioneu **Les meves prediccions** per veure la resta de prediccions que heu creat. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Per als entorns basats en comptes empresarials, podem preveure la cancel·lació de transaccions d'un compte i també una combinació de compte i un altre nivell d'informació, com ara la categoria de producte. Afegir una dimensió pot ajudar-vos a esbrinar la probabilitat que té el compte "Contoso" de deixar de comprar la categoria de producte "material d'oficina". A més, per als comptes empresarials, també podem utilitzar la IA per generar una llista de les raons potencials per les quals és probable que en un compte hi hagi cancel·lacions en una categoria d'informació de nivell secundari.

> [!TIP]
> Proveu el tutorial per fer una predicció de la cancel·lació de transaccions amb dades d'exemple: [Predicció de la cancel·lació de transaccions (versió preliminar)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Requisits previs

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.
- Coneixements empresarials per entendre què significa la rotació per a l'empresa. S'admeten definicions de rotació basades en el temps, és a dir, quan es considera que un client ha entrat en rotació després d'un període sense compres.
- Dades sobre les vostres transaccions/compres i historial corresponent:
    - Identificadors de transaccions per distingir compres o transaccions.
    - Identificadors de client per adaptar les transaccions als vostres clients.
    - Dates dels esdeveniments de les transaccions, que defineixen les dates en què es van produir les transaccions.
    - L'esquema de dades semàntiques per a compres o transaccions requereix la següent informació:
        - **ID de transacció**: identificador únic de la compra o la transacció.
        - **Data de la transacció**: data de la compra o la transacció.
        - **Valor de la transacció**: moneda i import en valor numèric de la transacció o l'article.
        - (Opcional) **ID de producte únic**: identificador del producte o servei adquirit quan les dades es troben en el nivell d'element de línia.
        - (Opcional) **Si aquesta transacció ha estat una devolució**: camp vertader o fals que identifica si la transacció ha estat una devolució o no. Si el **Valor de la transacció** és negatiu, també farem servir aquesta informació per inferir una devolució.
- (Opcional) Dades sobre les activitats del client:
    - Identificadors d'activitat per distingir les activitats del mateix tipus.
    - Identificadors de clients per assignar activitats als clients.
    - Informació d'activitat que conté el nom i la data de l'activitat.
    - L'esquema de dades semàntiques de les activitats del client inclou:
        - **Clau principal:** un identificador únic per a una activitat. Per exemple, una visita a un lloc web o un registre d'ús que revelen que el client ha provat una mostra del producte.
        - **Data i hora:** la data i l'hora de l'esdeveniment identificats per la clau principal.
        - **Incidència:** el nom de la incidència que voleu utilitzar. Per exemple, un camp anomenat "UserAction" d'una botiga de queviures podria ser un cupó que el client ha utilitzat.
        - **Detalls:** informació detallada de la incidència. Per exemple, un camp anomenat "CouponValue" d'una botiga de queviures podria ser el valor monetari del cupó.

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.
- Coneixements empresarials per entendre què significa la rotació per a l'empresa. S'admeten definicions de rotació basades en el temps, és a dir, quan es considera que un client ha entrat en rotació després d'un període sense compres.
- Dades sobre les vostres transaccions/compres i historial corresponent:
    - Identificadors de transaccions per distingir compres o transaccions.
    - Identificadors de client per adaptar les transaccions als vostres clients.
    - Dates dels esdeveniments de les transaccions, que defineixen les dates en què es van produir les transaccions.
    - L'esquema de dades semàntiques per a compres o transaccions requereix la següent informació:
        - **ID de transacció**: identificador únic de la compra o la transacció.
        - **Data de la transacció**: data de la compra o la transacció.
        - **Valor de la transacció**: moneda i import en valor numèric de la transacció o l'article.
        - (Opcional) **ID de producte únic**: identificador del producte o servei adquirit quan les dades es troben en el nivell d'element de línia.
        - (Opcional) **Si aquesta transacció ha estat una devolució**: camp vertader o fals que identifica si la transacció ha estat una devolució o no. Si el **Valor de la transacció** és negatiu, també farem servir aquesta informació per inferir una devolució.
- (Opcional) Dades sobre les activitats del client:
    - Identificadors d'activitat per distingir les activitats del mateix tipus.
    - Identificadors de clients per assignar activitats als clients.
    - Informació d'activitat que conté el nom i la data de l'activitat.
    - L'esquema de dades semàntiques de les activitats del client inclou:
        - **Clau principal:** un identificador únic per a una activitat. Per exemple, una visita a un lloc web o un registre d'ús que revelen que el client ha provat una mostra del producte.
        - **Data i hora:** la data i l'hora de l'esdeveniment identificats per la clau principal.
        - **Incidència:** el nom de la incidència que voleu utilitzar. Per exemple, un camp anomenat "UserAction" d'una botiga de queviures podria ser un cupó que el client ha utilitzat.
        - **Detalls:** informació detallada de la incidència. Per exemple, un camp anomenat "CouponValue" d'una botiga de queviures podria ser el valor monetari del cupó.
- (Opcional) Dades sobre els clients:
    - Aquestes dades s'han d'alinear amb els atributs més estàtics per assegurar-vos que el model s'ajusti millor.
    - L'esquema de dades semàntiques per a les dades dels clients inclou:
        - **CustomerID:** Identificador únic d'un client.
        - **Data de creació:** la data en què inicialment es va afegir el client.
        - **Estat o província:** la ubicació de l'estat o la província d'un client.
        - **País:** el país d'un client.
        - **Sector:** el tipus de sector d'un client. Per exemple, un camp anomenat "Sector" en un torrefactor de cafè podria indicar si el client era minorista.
        - **Classificació:** la classificació d'un client per al vostre negoci. Per exemple, un camp anomenat "ValueSegment" en un torrefactor de cafè podria ser el nivell de client segons la mida del client.

---

- Característiques de les dades suggerides:
    - Dades històriques suficients: dades de transacció per almenys el doble de la finestra de temps seleccionada. Preferentment, de dos a tres anys de l'historial de transaccions. 
    - Múltiples compres per client: idealment almenys dues transaccions per client.
    - Nombre de clients: almenys 10 perfils de client, preferentment més de 1.000 clients únics. El model fallarà amb menys de 10 clients i dades històriques insuficients.
    - Integritat de les dades: menys del 20% de valors inexistents al camp de dades de l'entitat proporcionada.

> [!NOTE]
> Per a una empresa amb alta freqüència de compra de clients (cada poques setmanes) es recomana seleccionar una definició de finestra de predicció i cancel·lació més curta. Per a una freqüència de compra baixa (cada pocs mesos o un cop l'any), trieu una definició de finestra predicció i cancel·lació més llarga.

## <a name="create-a-transaction-churn-prediction"></a>Crear una predicció de cancel·lació de transaccions

1. Al Customer Insights, aneu a **Intel·ligència** > **Prediccions**.

1. Seleccioneu la peça **Model d'abandonament de clients (versió preliminar)** i seleccioneu **Utilitza aquest model**.

1. A la subfinestra **Model de rotació de clients**, trieu **Transacció** i seleccioneu **Comença**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captura de pantalla amb l'opció de transacció seleccionada a la subfinestra del model de rotació de clients.":::

### <a name="name-model"></a>Assignació d'un nom al model

1. Proporcioneu un nom per al model per diferenciar-lo de la resta de models.

1. Proporcioneu un nom per a l'entitat de sortida només amb lletres i números, sense cap espai. Aquest és el nom que utilitzarà l'entitat del model. 

1. Seleccioneu **Següent**.

### <a name="define-customer-churn"></a>Definició de l'abandonament de clients

1. Definiu una rang de dies per predir la rotació al camp **Identifica els clients que poden cancel·lar en els pròxims**. Per exemple, podeu predir el risc de rotació per als vostres clients en els pròxims 90 dies per alinear-lo amb les vostres estratègies de retenció de màrqueting. La predicció de risc de rotació durant un període de temps més llarg o curt pot fer que resulti més difícil abordar els factors del vostre perfil de risc de rotació, però això dependrà dels vostres requisits empresarials específics.
   >[!TIP]
   > Podeu seleccionar **Desa i tanca** en qualsevol moment per desar la predicció en forma d'esborrany. Trobareu l'esborrany de la predicció a la pestanya **Les meves prediccions** per continuar.

1. Introduïu el nombre de dies per definir la rotació al camp **Un client ha cancel·lat si no ha fet cap compra en:**. Per exemple, si un client no ha fet cap compra durant els darrers 30 dies, es podria considerar com a rotació per al vostre negoci. 

1. Per continuar, feu clic a **Següent**.

### <a name="add-required-data"></a>Addició de les dades necessàries

1. Seleccioneu **Afegeix dades** i trieu el tipus d'activitat a la subfinestra lateral que conté la informació de l'historial de transacció o de compra.

1. A **Tria les activitats**, trieu les activitats específiques de l'activitat seleccionada en la qual voleu centrar el càlcul.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Subfinestra lateral que mostra la tria d'activitats específiques sota el tipus semàntic.":::

1. Si encara no heu assignat l'activitat a un tipus semàntic, seleccioneu **Edita** per fer-ho. S'obrirà l'experiència guiada per assignar activitats administrades. Assigneu les dades als camps corresponents del tipus d'activitat seleccionat.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Tipus d'activitat de configuració de pàgina.":::

1. Després d'assignar l'activitat al tipus semàntic corresponent, seleccioneu **Següent** per continuar

1. Assigneu els atributs semàntics als camps necessaris per executar el model. Si els següents camps no estan emplenats, configureu la relació des de l'entitat de l'historial de compres a l'entitat *Client*.

1. Seleccioneu **Següent**.

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Afegir dades addicionals (opcional)

Configureu la relació des de l'entitat d'activitat de client a l'entitat *Client*.

1. Seleccioneu el camp que identifica el client a la taula de l'activitat del client. Pot estar directament relacionat amb l'ID de client principal de l'entitat *Client*.

1. Seleccioneu l'entitat que és l'entitat *Client* principal.

1. Introduïu un nom que descrigui la relació.

#### <a name="customer-activities"></a>Activitats del client

1. També podeu seleccionar **Afegeix dades** per a les **Activitats del client**.

1. Seleccioneu el tipus d'activitat semàntica que conté les dades que voleu utilitzar i, a continuació, seleccioneu una o diverses activitats a la secció **Activitats**.

1. Seleccioneu un tipus d'activitat que coincideixi amb el tipus d'activitat del client que configureu. Seleccioneu **Crea'n un de nou** i trieu un tipus d'activitat disponible o bé creeu un nou tipus.

1. Seleccioneu **Següent** i, a continuació **Desa**.

1. Si teniu altres activitats del client que vulgueu incloure, repetiu els passos anteriors.

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

### <a name="select-prediction-level"></a>Seleccionar el nivell de predicció

La majoria de les prediccions es creen en el nivell del client. En algunes situacions, pot ser que no sigui prou granular per a les vostres necessitats empresarials. Podeu utilitzar aquesta característica per predir la rotació per a una branca d'un client, per exemple, no pas per al client en conjunt.

1. Per crear una predicció en un nivell més granular que el de client, seleccioneu **Seleccioneu l'entitat per a un nivell secundari**. Si l'opció no està disponible, assegureu-vos que heu completat la secció anterior.

1. Expandiu les entitats de les quals voleu triar el nivell secundari o utilitzeu el quadre de filtre de cerca per filtrar les opcions seleccionades.

1. Trieu l'atribut que voleu utilitzar com a nivell secundari i seleccioneu **Afegeix**.

1. Seleccioneu **Següent**.

> [!NOTE]
> Les entitats disponibles en aquesta secció es mostren perquè tenen una relació amb l'entitat que heu triat a la secció anterior. Si no veieu l'entitat que voleu afegir, assegureu-vos que té una relació vàlida present a **Relacions**. Només les relacions d'un a un i de diversos a un són vàlides per a aquesta configuració.

### <a name="add-additional-data-optional"></a>Afegir dades addicionals (opcional)

Configureu la relació des de l'entitat d'activitat de client a l'entitat *Client*.

1. Seleccioneu el camp que identifica el client a la taula de l'activitat del client. Pot estar directament relacionat amb l'ID de client principal de l'entitat *Client*.

1. Seleccioneu l'entitat que és l'entitat *Client* principal.

1. Introduïu un nom que descrigui la relació.

#### <a name="customer-activities"></a>Activitats del client

1. També podeu seleccionar **Afegeix dades** per a les **Activitats del client**.

1. Seleccioneu el tipus d'activitat semàntica que conté les dades que voleu utilitzar i, a continuació, seleccioneu una o diverses activitats a la secció **Activitats**.

1. Seleccioneu un tipus d'activitat que coincideixi amb el tipus d'activitat del client que configureu. Seleccioneu **Crea'n un de nou** i trieu un tipus d'activitat disponible o bé creeu un nou tipus.

1. Seleccioneu **Següent** i, a continuació **Desa**.

1. Si teniu altres activitats del client que vulgueu incloure, repetiu els passos anteriors.

#### <a name="customers-data"></a>Dades dels clients

1. O bé, seleccioneu **Afegeix dades** per a les **Dades de clients**.

1. Assigneu els atributs semàntics als camps de les vostres pròpies dades de client segons s'identifica. Les dades dels camps utilitzats no han de canviar sovint per garantir el millor rendiment del model. Per exemple, si seleccioneu un camp per a "Classificació" que canviï cada mes només tindreu l'últim valor utilitzat a la predicció, encara que històricament el mateix valor no s'apliqui al client en crear els patrons de predicció.

1. Seleccioneu **Següent**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Proporcionar una llista opcional de comptes de referència

Afegiu una llista de clients empresarials i de comptes que voleu utilitzar com a referències. Obtindreu [detalls per a aquests comptes de referència](#review-a-prediction-status-and-results) com, per exemple, la puntuació de rotació i les característiques que han influït més en la seva predicció de rotació.

1. Seleccioneu **+ Afegeix clients**.

1. Trieu els clients que actuen com a referències.

1. Per continuar, feu clic a **Següent**.

---

### <a name="set-schedule-and-review-configuration"></a>Definir la planificació i revisar la configuració

1. Definiu una freqüència per tornar a entrenar el model. Aquesta configuració és important per actualitzar la precisió de les prediccions a mesura que es van ingerint dades noves. La majoria d'empreses poden tornar a entrenar un cop al mes i obtenir una bona precisió de les prediccions.

1. Seleccioneu **Següent**.

1. Reviseu la configuració de la predicció. Per tornar als passos posteriors, seleccioneu **Edita** a sota del valor que es mostra. O bé, podeu seleccionar un pas de configuració a l'indicador de progrés.

1. Si tots els valors s'han configurat correctament, seleccioneu **Desa i executa** per iniciar el procés de predicció. A la pestanya **Les meves prediccions**, podeu veure l'estat de les vostres prediccions. El procés pot tardar unes quantes hores a completar-se en funció de la quantitat de dades que s'han utilitzat a la predicció.

## <a name="review-a-prediction-status-and-results"></a>Revisar l'estat i els resultats de la predicció

1. Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.

1. Seleccioneu la predicció que voleu revisar.
   - **Nom de la predicció:** nom de la predicció que es proporcionarà en crear-la.
   - **Tipus de predicció:** tipus de model utilitzat per a la predicció
   - **Entitat de sortida:** nom de l'entitat per emmagatzemar els resultats de la predicció. Podeu trobar una entitat amb aquest nom a **Dades** > **Entitats**.
     A l'entitat de sortida, *ChurnScore* és la probabilitat predita de cancel·lació i *IsChurn* és una etiqueta binària basada en *ChurnScore* amb un llindar de 0,5. És possible que el llindar per defecte no funcioni per al vostre escenari. [Creeu un segment nou](segments.md#create-a-new-segment) amb el llindar preferit.
     No tots els clients són necessàriament clients actius. Alguns d'ells poden no haver tingut cap activitat durant molt de temps i es consideren ja cancel·lat, basant-se en la definició de cancel·lació. Predir el risc de rotació dels clients que ja han marxat no és útil perquè no són el públic d'interès.
   - **Camp predit**: aquest camp només s'emplena per a alguns tipus de prediccions i no es fa servir a la predicció de rotació.
   - **Estat:** estat de l'execució de la predicció.
        - **En cua**: la predicció està esperant que s'executin altres processos.
        - **S'està actualitzant**: la predicció s'està executant per produir resultats que passaran a l'entitat de sortida.
        - **Error:** s'ha produït un error en executar la predicció. Per obtenir més informació, [reviseu els registres](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Correcta:** la predicció s'ha realitzat correctament. Seleccioneu **Visualitza** a sota dels tres punts verticals per revisar la predicció
   - **Editat:** la data en què es va canviar la configuració de la predicció.
   - **Última actualització:** la data en què s'han actualitzat els resultats de la predicció a l'entitat de sortida.

1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció de la qual voleu revisar els resultats i seleccioneu **Visualitza**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Control de visualització per veure els resultats d'una predicció.":::

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

1. A la pàgina de resultats hi ha tres seccions principals de dades:
   - **Rendiment del model d'entrenament**: A, B o C són les puntuacions possibles. Aquesta puntuació indica el rendiment de la predicció i pot ser que us ajudi a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida. La puntuació es determina en funció de les regles següents: 
        - **A** quan el model ha predit correctament com a mínim el 50 % del total de les prediccions, i el percentatge de prediccions precises per als clients que han rotat és superior a la ràtio de referència com a mínim en un 10 %.
            
        - **B** quan el model ha predit correctament com a mínim el 50 % del total de les prediccions, i el percentatge de prediccions precises per als clients que han rotat és fins a un 10 % superior al valor de referència.
            
        - **C** quan el model ha predit correctament menys del 50 % del total de les prediccions, o el percentatge de prediccions precises per als clients que han rotat és inferior al valor de referència.
               
        - La **línia de base** pren l'entrada del període de predicció per al model (per exemple, un any) i el model crea diferents fraccions de temps dividint-ho per 2 fins que arriba a un mes o menys. Utilitza aquestes fraccions per crear una regla de negocis per als clients que no han comprat durant aquest període. Aquests clients es consideren rotació. La regla de negocis basada en el temps amb la capacitat més elevada de predir qui és probable que roti es tria com a model de referència.
            
    - **Probabilitat de rotació (nombre de clients)**: grups de clients segons el risc predit de rotació. Aquestes dades us poden ajudar més endavant si voleu crear un segment de clients amb un alt risc de rotació. Aquests segments ajuden a entendre on heu de definit la data límit de la subscripció del segment.
       
    - **Factors més influents**: hi ha molts factors que s'han de tenir en compte a l'hora de crear la predicció. Cadascun dels factors té la seva importància calculada per a les prediccions agregades que crea un model. Podeu utilitzar aquests factors per ajudar-vos a validar els resultats de la predicció o utilitzar aquesta informació més endavant per [crear segments](segments.md) que puguin ajudar a influir en el risc de rotació dels clients.


# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

1. A la pàgina de resultats hi ha tres seccions principals de dades:
   - **Rendiment del model d'entrenament**: A, B o C són les puntuacions possibles. Aquesta puntuació indica el rendiment de la predicció i pot ser que us ajudi a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida. La puntuació es determina en funció de les regles següents: 
        - **A** quan el model ha predit correctament com a mínim el 50 % del total de les prediccions, i el percentatge de prediccions precises per als clients que han rotat és superior a la ràtio de referència com a mínim en un 10 %.
            
        - **B** quan el model ha predit correctament com a mínim el 50 % del total de les prediccions, i el percentatge de prediccions precises per als clients que han rotat és fins a un 10 % superior al valor de referència.
            
        - **C** quan el model ha predit correctament menys del 50 % del total de les prediccions, o el percentatge de prediccions precises per als clients que han rotat és inferior al valor de referència.
               
        - La **línia de base** pren l'entrada del període de predicció per al model (per exemple, un any) i el model crea diferents fraccions de temps dividint-ho per 2 fins que arriba a un mes o menys. Utilitza aquestes fraccions per crear una regla de negocis per als clients que no han comprat durant aquest període. Aquests clients es consideren rotació. La regla de negocis basada en el temps amb la capacitat més elevada de predir qui és probable que roti es tria com a model de referència.
            
    - **Probabilitat de rotació (nombre de clients)**: grups de clients segons el risc predit de rotació. Aquestes dades us poden ajudar més endavant si voleu crear un segment de clients amb un alt risc de rotació. Aquests segments ajuden a entendre on heu de definit la data límit de la subscripció del segment.
       
    - **Factors més influents**: hi ha molts factors que s'han de tenir en compte a l'hora de crear la predicció. Cadascun dels factors té la seva importància calculada per a les prediccions agregades que crea un model. Podeu utilitzar aquests factors per ajudar-vos a validar els resultats de la predicció o utilitzar aquesta informació més endavant per [crear segments](segments.md) que puguin ajudar a influir en el risc de rotació dels clients.


1. Per als comptes empresarials, trobareu una pàgina d'informació d'**Anàlisi de característiques influents**. Conté quatre seccions de dades:

    - L'element seleccionat a la subfinestra dreta determina el contingut d'aquesta pàgina. Seleccioneu un element a **Clients principals** o **Clients de referència**. Ambdues llistes s'ordenen en ordre decreixent pel valor de la puntuació de rotació, tant si la puntuació és només per al client o una puntuació combinada de client i un nivell secundari, com ara la categoria de producte.
        
        - **Clients principals**: llista de 10 clients amb el risc més alt de rotació i el risc més baix de rotació en funció de les seves puntuacions de rotació. 
        - **Clients de referència**: llista de fins a 10 clients que es van seleccionar en configurar el model.
 
    - **Puntuació de rotació:** mostra la puntuació de rotació per a l'element seleccionat a la subfinestra dreta.
    
    - **Distribució de risc de rotació:** mostra la distribució de risc de rotació entre tots els clients i el percentatge en què està seleccionat el client. 
    
    - **Característiques principals que han augmentat i disminuït el risc de rotació:** per a l'element seleccionat a la subfinestra dreta, es mostren les cinc característiques principals que han augmentat i disminuït el risc de rotació. Per a cada característica influent, trobareu el valor de la característica per a aquest element i la seva influència en la puntuació de rotació. El valor mitjà de cada característica en els segments de rotació de clients baix, mitjà i alt també es mostra. Ajuda a contextualitzar millor els valors de les característiques més influents per a l'element seleccionat i comparar-lo amb els segments de rotació de clients baix, mitjà i alt.

       - Baix: comptes o combinacions de compte i nivell secundari amb una puntuació de rotació entre 0 i 0,33
       - Mitjà: comptes o combinacions de comptes i nivells secundaris amb una puntuació de rotació entre 0,33 i 0,66
       - Alt: comptes o combinacions de comptes i nivells secundaris amb una puntuació de rotació superior a 0,66
    
       Quan prediu la rotació al nivell de compte, tots els comptes es tenen en compte a l'hora de derivar els valors mitjans de les característiques dels segments de rotació. Per a les previsions de rotació en el nivell secundari de cada compte, la derivació dels segments de rotació depèn del nivell secundari de l'element seleccionat a la subfinestra lateral. Per exemple, si un article té un nivell secundari de categoria de producte = material d'oficina, només es consideren els elements que tenen material d'oficina com a categoria de producte a l'hora de derivar els valors mitjans de característica dels segments de rotació. Aquesta lògica s'aplica per garantir una comparació justa dels valors de característica de l'element amb els valors mitjans en segments de rotació de nivell baix, mitjà i alt.

       En alguns casos, el valor mitjà dels segments de rotació de nivell baix, mitjà o alt està buit o no està disponible perquè no hi ha cap element que pertanyi als segments de rotació corresponents basant-se en la definició anterior.
       
       > [!NOTE]
       > La interpretació dels valors sota la mitjana de les columnes baixa, mitjana i alta és diferent per a les característiques classificades, com ara el país o el sector. Com que la noció del valor de característica "mitjana" no s'aplica a les característiques classificades en categories, els valors d'aquestes columnes són la proporció dels clients en segments d'abandó baix, mitjà o alt que tenen el mateix valor de la característica de la categoria en comparació amb l'element seleccionat a la subfinestra lateral.

---

## <a name="manage-predictions"></a>Administrar prediccions

Es pot optimitzar, solucionar els problemes, actualitzar o suprimir predictions. Reviseu un informe d'ús de dades d'entrada per obtenir informació sobre com es pot realitzar una predicció més fiable més ràpidament. Per obtenir més informació, aneu a [Administrar les prediccions](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
