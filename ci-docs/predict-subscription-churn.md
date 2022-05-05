---
title: Predicció de churn de subscripció (conté vídeo)
description: Es prediu si un client està en risc de deixar d'utilitzar els productes o els serveis de la subscripció de l'empresa.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 415cd5d675512b4f434998afaa8265c8e45c562b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642411"
---
# <a name="subscription-churn-prediction"></a>Predicció de rotació de la subscripció

La predicció de rotació de subscripcions ajuda a predir si un client està en risc de deixar d'utilitzar els productes o els serveis de la subscripció de l'empresa. Podeu crear una nova predicció de rotació de subscripcions a la pàgina **Intel·ligència** > **Prediccions**. Seleccioneu **Les meves prediccions** per veure la resta de prediccions que heu creat.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Proveu el tutorial de predicció de rotació de subscripcions amb dades d'exemple: [Guia d'exemples de predicció de rotació de subscripcions](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [permisos de col·laborador](permissions.md).
- Coneixements empresarials per entendre què significa la rotació per a l'empresa. Admetem les definicions de rotacions basades en temps, fet que vol dir que un client es considera que ha completat la rotació d'un període de temps després d'haver-se acabat la subscripció.
- Dades sobre les subscripcions i l'historial:
    - Identificadors de subscripció per distingir subscripcions.
    - Identificadors de clients per coincidir amb les subscripcions dels clients.
    - Dates d'incidències de subscripció, que defineixen les dates d'inici, les dates d'acabament i les dates en què s'han produït incidències de subscripció.
    - Informació de subscripció per definir si es tracta d'una subscripció periòdica i amb quina freqüència es renova.
    - L'esquema de dades semàntiques de subscripcions requereix la següent informació:
        - **Identificador de la subscripció:** és un identificador únic d'una subscripció.
        - **Data d'acabament de la subscripció:** la data en què caduca la subscripció del client.
        - **Data d'inici de la subscripció:** la data en què s'inicia la subscripció del client.
        - **Data de la transacció:** la data en què es va produir un canvi de subscripció. Per exemple, un client que compra o cancel·la una subscripció.
        - **És una subscripció periòdica:** un camp booleà true o false que determina si la subscripció es renovarà amb el mateix identificador de subscripció sense la intervenció del client
        - **Freqüència de periodicitat (en mesos):** per a subscripcions periòdiques, és el període pel qual es renovarà la subscripció. Es representa en mesos. Per exemple, una subscripció anual que es renova automàticament per a un client cada any durant un altre any té el valor 12.
        - (Opcional) **Import de la subscripció:** l'import que un client paga per renovar la subscripció. Pot ajudar a identificar patrons per a diferents nivells de subscripcions.
- Dades sobre les activitats dels clients:
    - Identificadors d'activitat per distingir les activitats del mateix tipus.
    - Identificadors de clients per assignar activitats als clients.
    - Informació d'activitat que conté el nom i la data de l'activitat.
    - L'esquema de dades semàntiques de les activitats del client inclou:
        - **Clau principal:** un identificador únic per a una activitat. Per exemple, una visita a un lloc web o un registre d'ús que mostra que el client ha vist un episodi d'un programa de televisió.
        - **Data i hora:** la data i l'hora de l'esdeveniment identificats per la clau principal.
        - **Incidència:** el nom de la incidència que voleu utilitzar. Per exemple, un camp anomenat "UserAction" d'un servei de transmissió de vídeos podria tenir el valor "Vist".
        - **Detalls:** informació detallada de la incidència. Per exemple, un camp anomenat "ShowTitle" d'un servei de transmissió de vídeos podria tenir el valor d'un vídeo que el client ha vist.
- Característiques de les dades suggerides:
    - Dades històriques suficients: dades de subscripció per almenys el doble de la finestra de temps seleccionada. Preferentment, de dos a tres anys de dades de subscripció.
    - Estat de la subscripció: les dades inclouen subscripcions actives i inactives per a cada client, de manera que hi ha diverses entrades per identificador de client.
    - Nombre de clients: almenys 10 perfils de client, preferentment més de 1.000 clients únics. El model fallarà amb menys de 10 clients i dades històriques insuficients.
    - Integritat de les dades: menys del 20% de valors inexistents al camp de dades de l'entitat proporcionada.
   
   > [!NOTE]
   > Necessitareu com a mínim dos registres d'activitat per al 50% dels clients per als quals voleu calcular la rotació.

## <a name="create-a-subscription-churn-prediction"></a>Crear una predicció de rotació de subscripcions

1. Aneu a **Intel·ligènciaPredictions** > **·**.
1. Seleccioneu la peça del **model de rotació** de subscripció i seleccioneu **Utilitza aquest model**.
   > [!div class="mx-imgBorder"]
   > ![Icona Model de rotació de subscripcions amb el botó Utilitza aquest model.](media/subscription-churn-usethismodel.PNG "Icona Model de rotació de subscripcions amb el botó Utilitza aquest model")

### <a name="name-model"></a>Assignació d'un nom al model

1. Proporcioneu un nom per al model per diferenciar-lo de la resta de models.
1. Proporcioneu un nom per a l'entitat de sortida només amb lletres i números, sense cap espai. Aquest és el nom que utilitzarà l'entitat del model. A continuació, seleccioneu **Següent**.

### <a name="define-customer-churn"></a>Defineix la cancel·lació dels clients

1. Introduïu el nombre de **Dies des que ha finalitzat la subscripció** que l'empresa considera que un client pot estar en un estat de rotació. Aquest període sol estar vinculat a activitats empresarials, com ara ofertes o altres iniciatives de màrqueting, que intenten evitar perdre el client.
1. Introduïu el nombre de **Dies en el futur que es consultaran per predir la rotació** per definir una finestra per predir la rotació. Per exemple, per predir el risc de rotació per als vostres clients en els pròxims 90 dies per alinear-lo als vostres esforços de retenció de màrqueting. Predir el risc de cancel·lació durant períodes de temps més llargs o més curts pot dificultar donar resposta als factors del vostre perfil de risc de cancel·lació, en funció de les necessitats específiques de la vostra empresa. Per continuar, feu clic a **Següent**
   >[!TIP]
   > Podeu seleccionar **Desa l'esborrany** en qualsevol moment per desar la predicció com a esborrany. Trobareu l'esborrany de la predicció a la pestanya **Les meves prediccions** per continuar.

### <a name="add-required-data"></a>Addició de les dades necessàries

1. Seleccioneu **Afegeix dades** a **Historial de subscripcions** i trieu l'entitat que proporcioni la informació de l'historial de subscripcions tal com es descriu als [requisits previs](#prerequisites).
1. Si els camps següents no s'han emplenat, configureu la relació des de l'entitat Historial de subscripcions a l'entitat Client.
    1. Seleccioneu l'**entitat Historial de subscripcions**.
    1. Seleccioneu el **Camp** que identifica el client a l'entitat Historial de subscripcions. S'ha de relacionar amb l'identificador del client principal de l'entitat Client.
    1. Seleccioneu l'**entitat Client** que coincideixi amb l'entitat Client principal.
    1. Introduïu un nom que descrigui la relació.
       > [!div class="mx-imgBorder"]
       > ![Pàgina Historial de subscripcions que mostra la creació d'una relació amb el client.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Pàgina Historial de subscripcions que mostra la creació d'una relació amb el client")
1. Seleccioneu **Següent**.
1. Assigneu els camps semàntics als atributs de l'entitat Historial de subscripcions i seleccioneu **Desa**. Per a les descripcions dels camps, consulteu els [requisits previs](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Pàgina Historial de subscripcions que mostra els atributs semàntics assignats als camps de l'entitat Historial de subscripcions seleccionada.](media/subscription-churn-subscriptionhistorymapping.PNG "Pàgina Historial de subscripcions que mostra els atributs semàntics assignats als camps de l'entitat Historial de subscripcions seleccionada")
1. Seleccioneu **Afegeix dades** a **Activitats del client** i trieu l'entitat que proporcioni la informació de l'activitat del client tal com es descriu als requisits previs.
1. Seleccioneu un tipus d'activitat que coincideixi amb el tipus d'activitat del client que configureu.  Seleccioneu **Crea** i proporcioneu un nom si no veieu una opció que coincideixi amb el tipus d'activitat que necessiteu.
1. Haureu de configurar la relació des de l'entitat Activitat del client a l'entitat Client.
    1. Seleccioneu el camp que identifica el client a la taula d'activitat del client, que pot estar directament relacionada amb l'identificador de client principal de l'entitat Client.
    1. Seleccioneu l'entitat Client que coincideixi amb l'entitat Client principal
    1. Introduïu un nom que descrigui la relació.
1. Seleccioneu **Següent**.
1. Assigneu els camps semàntics als atributs de l'entitat Activitat del client i seleccioneu **Desa**. Per a les descripcions dels camps, consulteu els [requisits previs](#prerequisites).
1. (Opcional) Si teniu altres activitats del client que voleu incloure, repetiu els passos anteriors.
   > [!div class="mx-imgBorder"]
   > ![Definiu la relació de l'entitat.](media/subscription-churn-customeractivitiesmapping.PNG "Pàgina Activitats del client que mostra els atributs semàntics assignats als camps de l'entitat Activitat del client seleccionada")
1. Seleccioneu **Següent**.

### <a name="set-schedule-and-review-configuration"></a>Definir la planificació i revisar la configuració

1. Definiu una freqüència per tornar a entrenar el model. Aquesta configuració és important per actualitzar la precisió de les prediccions a mesura que s'ingereixen dades noves a Customer Insights. La majoria d'empreses poden tornar a entrenar un cop al mes i obtenir una bona precisió de les prediccions.
1. Seleccioneu **Següent**.
1. Reviseu la configuració. Podeu tornar enrere en qualsevol part de la configuració de predicció. Per fer-ho, seleccioneu **Edita** sota el valor que es mostra. O bé, podeu seleccionar un pas de configuració a l'indicador de progrés.
1. Si tots els valors s'han configurat correctament, seleccioneu **Desa i executa** per iniciar el procés de predicció. A la pestanya **Les meves prediccions**, podeu veure l'estat de les vostres prediccions. El procés pot tardar unes quantes hores a completar-se en funció de la quantitat de dades que s'han utilitzat a la predicció.

## <a name="review-a-prediction-status-and-results"></a>Revisar l'estat i els resultats de la predicció

1. Aneu a la pestanya **Les meves prediccions** a **Intel·ligència** > **Prediccions**.
   > [!div class="mx-imgBorder"]
   > ![Visualització de la pàgina Les meves prediccions.](media/subscription-churn-mypredictions.PNG "Visualització de la pàgina Les meves prediccions")
1. Seleccioneu la predicció que voleu revisar.
   - **Nom de la predicció:** el nom de la predicció proporcionat en crear-la.
   - **Tipus de predicció:** el tipus de model utilitzat per a la predicció
   - **Entitat de sortida:** nom de l'entitat per emmagatzemar els resultats de la predicció. Podeu trobar una entitat amb aquest nom a **Dades** > **Entitats**.    
     A l'entitat de sortida, *ChurnScore* és la probabilitat predita de cancel·lació i *IsChurn* és una etiqueta binària basada en *ChurnScore* amb un llindar de 0,5. És possible que el llindar per defecte no funcioni per al vostre escenari. [Creeu un segment nou](segments.md#create-a-new-segment) amb el llindar preferit.
   - **Camp predit:** aquest camp només s'emplena per a alguns tipus de prediccions i no es fa servir a la predicció de rotació de subscripcions.
   - **Estat:** l'estat actual de l'execució de la predicció.
        - **A la cua:** la predicció actualment està a l'espera de l'execució d'altres processos.
        - **S'està actualitzant:** la predicció està executant actualment la fase de processament "puntuació" per produir resultats que fluiran a l'entitat de sortida.
        - **Error:** s'ha produït un error en la predicció. Seleccioneu **Registres** per obtenir més informació.
        - **Ha reeixit:** la predicció s'ha dut a terme correctament. Seleccioneu **Visualitza** a sota dels tres punts verticals per revisar la predicció
   - **Editat:** la data en què es va canviar la configuració de la predicció.
   - **Última actualització:** la data en què s'han actualitzat els resultats de la predicció a l'entitat de sortida.
1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció de la qual voleu revisar els resultats i seleccioneu **Visualitza**.
   > [!div class="mx-imgBorder"]
   > ![Visualització d'opcions del menú dels tres punts verticals d'una predicció, que inclou l'edició, l'actualització, la visualització, els registres i la supressió.](media/subscription-churn-verticalellipses.PNG "Visualització d'opcions del menú dels tres punts verticals d'una predicció, que inclou l'edició, l'actualització, la visualització, els registres i la supressió")
1. A la pàgina de resultats hi ha tres seccions principals de dades:
    1. **Rendiment del model d'entrenament:** A, B o C són les puntuacions possibles. Aquesta puntuació indica el rendiment de la predicció i pot ser que us ajudi a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida.
        - La puntuació es determina en funció de les regles següents:
            - **A** quan el model ha previst correctament com a mínim el 50% del total de les prediccions, i quan el percentatge de prediccions precises per als clients que han canviat supera la taxa històrica de rotació mitjana com a mínim en un 10% de la taxa de rotació mitjana històrica.
            - **B** quan el model ha previst correctament com a mínim el 50% del total de les prediccions, i quan el percentatge de prediccions precises per als clients que han canviat supera la taxa històrica de rotació mitjana fins a un 10% de la taxa de rotació mitjana històrica.
            - **C** quan el model ha predit amb precisió menys el 50% del total de les prediccions, o quan el percentatge de prediccions precises per als clients que han canviat és inferior a la taxa de rotació mitjana històrica.
               > [!div class="mx-imgBorder"]
               > ![Visualització del resultat del rendiment del model.](media/subscription-churn-modelperformance.PNG "Visualització del resultat del rendiment del model")
    1. **Probabilitat de rotació (nombre de clients):** grups de clients segons el risc predit de rotació. Aquestes dades us poden ajudar més endavant si voleu crear un segment de clients amb un alt risc de rotació. Aquests segments ajuden a entendre on heu de definit la data límit de la subscripció del segment.
       > [!div class="mx-imgBorder"]
       > ![Gràfic que mostra la distribució dels resultats de rotació, desglossat en intervals entre 0-100 %.](media/subscription-churn-resultdistribution.PNG "Gràfic que mostra la distribució dels resultats de rotació, desglossat en intervals entre 0-100%")
    1. **Factors més influents:** hi ha molts factors que s'han de tenir en compte a l'hora de crear la predicció. Cadascun dels factors té la seva importància calculada per a les prediccions agregades que crea un model. Podeu utilitzar aquests factors per ajudar a validar els resultats de la predicció. O bé, podeu utilitzar aquesta informació més endavant per [crear segments](segments.md) que ajudin a influir en el risc de rotació dels clients.
       > [!div class="mx-imgBorder"]
       > ![Llista que mostra els factors influents i la seva importància en la predicció del resultat de rotació.](media/subscription-churn-influentialfactors.PNG "Llista que mostra els factors influents i la seva importància en la predicció del resultat de rotació")

## <a name="manage-predictions"></a>Administrar prediccions

Es pot optimitzar, solucionar els problemes, actualitzar o suprimir predictions. Reviseu un informe d'ús de dades d'entrada per obtenir informació sobre com es pot realitzar una predicció més fiable més ràpidament. Per obtenir més informació, vegeu [Administrar prediccions](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
