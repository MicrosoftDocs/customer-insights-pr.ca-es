---
title: Predicció de rotació de transaccions
description: Predigueu si un client està en risc de deixar d'adquirir els vostres productes o serveis.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f120e9e3cf8d40d913c7fa6a81fbf9facd045e3c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597177"
---
# <a name="transactional-churn-prediction-preview"></a>Predicció de rotació de transaccions (versió preliminar)

La predicció de rotació de transaccions ajuda a predir si un client deixarà de comprar els vostres productes o serveis en un determinat període. Per crear prediccions de rotació noves, aneu a **Intel·ligència** > **Prediccions**. Seleccioneu **Les meves prediccions** per veure la resta de prediccions que heu creat.

> [!TIP]
> Proveu el tutorial de predicció de rotació de transaccions amb dades d'exemple: [Guia d'exemples de predicció de rotació de transaccions (versió preliminar)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.
- Coneixements empresarials per entendre què significa la rotació per a l'empresa. S'admeten definicions de rotació basades en el temps, és a dir, quan es considera que un client ha entrat en rotació després d'un període sense compres.
- Dades sobre les vostres transaccions/compres i historial corresponent:
    - Identificadors de transaccions per distingir compres o transaccions.
    - Identificadors de client per adaptar les transaccions als vostres clients.
    - Dates dels esdeveniments de les transaccions, que defineixen les dates en què es van produir les transaccions.
    - L'esquema de dades semàntiques per a compres o transaccions requereix la següent informació:
        - **ID de transacció:** identificador únic de la compra o la transacció.
        - **Data de la transacció:** data de la compra o la transacció.
        - **Valor de la transacció:** moneda i import en valor numèric de la transacció o l'article.
        - (Opcional) **ID de producte únic:** identificador del producte o servei adquirit quan les dades es troben en el nivell d'element de línia.
        - (Opcional) **Si aquesta transacció ha estat una devolució:** camp vertader o fals que identifica si la transacció ha estat una devolució o no. Si el **Valor de la transacció** és negatiu, també farem servir aquesta informació per inferir una devolució.
- (Opcional) Dades sobre les activitats del client:
    - Identificadors d'activitat per distingir les activitats del mateix tipus.
    - Identificadors de clients per assignar activitats als clients.
    - Informació d'activitat que conté el nom i la data de l'activitat.
    - L'esquema de dades semàntiques de les activitats del client inclou:
        - **Clau principal:** un identificador únic per a una activitat. Per exemple, una visita a un lloc web o un registre d'ús que revelen que el client ha provat una mostra del producte.
        - **Data i hora:** la data i l'hora de l'esdeveniment identificats per la clau principal.
        - **Incidència:** el nom de la incidència que voleu utilitzar. Per exemple, un camp anomenat "UserAction" d'una botiga de queviures podria ser un cupó que el client ha utilitzat.
        - **Detalls:** informació detallada de la incidència. Per exemple, un camp anomenat "CouponValue" d'una botiga de queviures podria ser el valor monetari del cupó.

## <a name="create-a-transactional-churn-prediction"></a>Crear una predicció de rotació de transaccions

1. Al Customer Insights, aneu a **Intel·ligència** > **Prediccions**.

1. Seleccioneu la peça **Model d'abandonament de clients (versió preliminar)** i seleccioneu **Utilitza aquest model**.
   
1. A la subfinestra **Model d'abandonament de clients**, trieu **Transaccional** i seleccioneu **Comença**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captura de pantalla amb l'opció transaccional seleccionada a la subfinestra Model d'abandonament de clients.":::

### <a name="name-model"></a>Assignació d'un nom al model

1. Proporcioneu un nom per al model per diferenciar-lo de la resta de models.

1. Proporcioneu un nom per a l'entitat de sortida només amb lletres i números, sense cap espai. Aquest és el nom que utilitzarà l'entitat del model. 

1. Seleccioneu **Següent**.

### <a name="define-customer-churn"></a>Definició de l'abandonament de clients

1. Definiu una rang de dies per predir la rotació al camp **Identifica els clients que poden cancel·lar en els pròxims**. Per exemple, podeu predir el risc de rotació per als vostres clients en els pròxims 90 dies per alinear-lo amb les vostres estratègies de retenció de màrqueting. La predicció de risc de rotació durant un període de temps més llarg o curt pot fer que resulti més difícil abordar els factors del vostre perfil de risc de rotació, però això dependrà dels vostres requisits empresarials específics. 
   >[!TIP]
   > Podeu seleccionar **Desa i tanca** en qualsevol moment per desar la predicció en forma d'esborrany. Trobareu l'esborrany de la predicció a la pestanya **Les meves prediccions** per continuar.

1. Introduïu el nombre de dies per definir la rotació al camp **Un client ha cancel·lat si no ha fet cap compra en:**. Per exemple, si un client no ha fet cap compra durant els darrers 30 dies, es podria considerar com a rotació per al vostre negoci. 

1. Per continuar, feu clic a **Següent**

### <a name="add-required-data"></a>Addició de les dades necessàries

1. Seleccioneu **Afegeix dades** per a l'**Historial de compres** i trieu l'entitat que proporciona la informació de l'historial de transaccions o compres tal com es descriu als [requisits previs](#prerequisites).

1. Assigneu els camps semàntics als atributs de l'entitat d'historial de compres i seleccioneu **Següent**. Per a les descripcions dels camps, consulteu els [requisits previs](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Assigneu camps semàntics de l'entitat de compra.":::

1. Si els següents camps no estan emplenats, configureu la relació des de l'entitat de l'historial de compres a l'entitat del client.
    1. Seleccioneu l'**Entitat de l'historial de compres**.
    1. Seleccioneu el **Camp** que identifica el client a l'entitat de l'historial de compres. S'ha de relacionar amb l'identificador del client principal de l'entitat Client.
    1. Seleccioneu l'**entitat Client** que coincideixi amb l'entitat Client principal.
    1. Introduïu un nom que descrigui la relació.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pàgina Historial de compres que mostra la creació d'una relació amb el client.":::
   
1. Seleccioneu **Següent**.

1. També podeu seleccionar **Afegeix dades** per a les **Activitats del client**. Trieu l'entitat que proporciona la informació de l'activitat del client tal com es descriu als requisits previs.

1. Assigneu els camps semàntics als atributs de l'entitat de l'activitat del client i seleccioneu **Següent**. Per a les descripcions dels camps, consulteu els [requisits previs](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Assignar camps de client per a dades transaccionals.":::

1. Seleccioneu un tipus d'activitat que coincideixi amb el tipus d'activitat del client que configureu. Seleccioneu **Crea'n un de nou** i trieu un tipus d'activitat disponible o bé creeu un nou tipus.

1. Haureu de configurar la relació des de l'entitat Activitat del client a l'entitat Client.
    1. Seleccioneu el camp que identifica el client a la taula de l'activitat del client. Pot estar directament relacionat amb l'ID de client principal de l'entitat del client.
    1. Seleccioneu l'entitat Client que coincideixi amb l'entitat Client principal
    1. Introduïu un nom que descrigui la relació.

1. Seleccioneu **Desa**.

1. Si teniu altres activitats del client que vulgueu incloure, repetiu els passos anteriors.

1. Seleccioneu **Següent**.

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
   - **Camp predit:** aquest camp només s'emplena per a alguns tipus de prediccions i no es fa servir a la predicció de rotació.
   - **Estat:** estat de l'execució de la predicció.
        - **En cua:** la predicció està esperant que s'executin altres processos.
        - **S'està actualitzant:** la predicció s'està executant per produir resultats que passaran a l'entitat de sortida.
        - **Error:** s'ha produït un error en executar la predicció. Per obtenir més informació, [reviseu els registres](#troubleshoot-a-failed-prediction).
        - **Ha reeixit:** la predicció s'ha realitzat correctament. Seleccioneu **Visualitza** a sota dels tres punts verticals per revisar la predicció
   - **Editat:** la data en què es va canviar la configuració de la predicció.
   - **Última actualització:** la data en què s'han actualitzat els resultats de la predicció a l'entitat de sortida.

1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció de la qual voleu revisar els resultats i seleccioneu **Visualitza**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Control de visualització per veure els resultats d'una predicció.":::   

1. A la pàgina de resultats hi ha tres seccions principals de dades:
    1. **Rendiment del model d'entrenament:** A, B o C són les puntuacions possibles. Aquesta puntuació indica el rendiment de la predicció i pot ser que us ajudi a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida. La puntuació es determina en funció de les regles següents:
         
         - **A** quan el model ha predit correctament com a mínim el 50 % del total de les prediccions, i el percentatge de prediccions precises per als clients que han rotat és superior a la ràtio de referència com a mínim en un 10 %.
            
         - **B** quan el model ha predit correctament com a mínim el 50 % del total de les prediccions, i el percentatge de prediccions precises per als clients que han rotat és fins a un 10 % superior al valor de referència.
            
         - **C** quan el model ha predit correctament menys del 50 % del total de les prediccions, o el percentatge de prediccions precises per als clients que han rotat és inferior al valor de referència.
               
         - La **línia de base** pren l'entrada del període de predicció per al model (per exemple, un any) i el model crea diferents fraccions de temps dividint-ho per 2 fins que arriba a un mes o menys. Utilitza aquestes fraccions per crear una regla de negocis per als clients que no han comprat durant aquest període. Aquests clients es consideren rotació. La regla de negocis basada en el temps amb la capacitat més elevada de predir qui és probable que roti es tria com a model de referència.
            
    1. **Probabilitat de rotació (nombre de clients):** grups de clients segons el risc predit de rotació. Aquestes dades us poden ajudar més endavant si voleu crear un segment de clients amb un alt risc de rotació. Aquests segments ajuden a entendre on heu de definit la data límit de la subscripció del segment.
       
    1. **Factors més influents:** hi ha molts factors que s'han de tenir en compte a l'hora de crear la predicció. Cadascun dels factors té la seva importància calculada per a les prediccions agregades que crea un model. Podeu utilitzar aquests factors per ajudar a validar els resultats de la predicció. O bé, podeu utilitzar aquesta informació més endavant per [crear segments](segments.md) que ajudin a influir en el risc de rotació dels clients.

## <a name="troubleshoot-a-failed-prediction"></a>Resoldre problemes relacionats amb una predicció fallida

1. Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.

1. Seleccioneu els punts suspensius verticals que hi ha al costat de la predicció els registres d'error de la qual voleu visualitzar.

1. Seleccioneu **Registres**.

1. Reviseu tots els errors. Hi ha diversos tipus d'errors que es poden produir i que descriuen la condició que ha causat l'error. Per exemple, un error que indica que no hi ha prou dades per predir amb precisió se sol resoldre amb la càrrega de dades addicionals al Customer Insights.

## <a name="refresh-a-prediction"></a>Actualitzar una predicció

Les prediccions s'actualitzaran automàticament amb la mateixa [planificació d'actualització de les dades](system.md#schedule-tab) definida a la configuració. Podeu actualitzar-les manualment també.

1. Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.

1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció que voleu actualitzar.

1. Seleccioneu **Actualitza**.

## <a name="delete-a-prediction"></a>Suprimir una predicció

La supressió d'una predicció també comporta la supressió de la seva entitat de sortida.

1. Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.

1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció que voleu suprimir.

1. Seleccioneu **Suprimeix**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]