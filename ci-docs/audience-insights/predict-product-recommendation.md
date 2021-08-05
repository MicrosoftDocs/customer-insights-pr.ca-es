---
title: Predicció de recomanacions de productes
description: Predieu els productes que pot comprar o interactuar un client.
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: bcbafa513c2c61b0280c91aa7ed71e211c32c35c
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556112"
---
# <a name="product-recommendation-prediction-preview"></a>Predicció de recomanacions de productes (versió preliminar)

El model de recomanació de productes crea conjunts de recomanacions de producte predictives. Les recomanacions es basen en el comportament de compra anterior i els clients amb patrons de compra similars. Podeu crear noves predictions de recomanació de productes a la pàgina **Intel·ligència** > **Prediccions**. Seleccioneu **Les meves prediccions** per veure la resta de prediccions que heu creat.

Les recomanacions de productes poden estar subjectes a les lleis i regulacions locals i a les expectatives dels clients, que el model no està construït per tenir específicament en compte.  Com a usuari d'aquesta capacitat predictiva, **heu de revisar les recomanacions abans de lliurar-les als vostres clients** per assegurar-vos que compliu les lleis o regulacions aplicables i les expectatives dels clients sobre el que podeu recomanar. 

A més, la sortida d'aquest model us proporcionarà recomanacions basades en l'identificador del producte. El mecanisme de lliurament haurà d'assignar els identificadors de producte previstos al contingut adequat perquè els clients tinguin en compte la localització, el contingut d'imatge i altres continguts o comportaments específics de l'empresa.

## <a name="sample-guide"></a>Guia d'exemple

Si esteu interessat a provar aquesta característica però no teniu dades per completar els requisits següents, podeu [crear una implementació d'exemple](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.

- Coneixements empresarials per comprendre diversos tipus de productes per a la vostra empresa i com interactuen els vostres clients. Admeten la recomanació de productes que ja han adquirit els vostres clients o recomanacions per a productes nous.

- Dades sobre les vostres transaccions, compres i historial:
    - Identificadors de transaccions per distingir compres o transaccions.
    - Identificadors de client per assignar les transaccions als vostres clients.
    - Dates dels esdeveniments de les transaccions que especifiquen les dates en què es van produir les transaccions.
    - Informació de l'identificador del producte per a la transacció.
    - (Opcional) Entitat de dades del catàleg de productes per utilitzar un filtre de producte.
    - (Opcional) Si una transacció és una devolució o no.
    - L'esquema de dades semàntiques requereix la següent informació:
        - **ID de transacció:** identificador únic de la compra o la transacció.
        - **Data de la transacció:** data de la compra o la transacció.
        - **Valor de la transacció:** valor numèric de la compra o la transacció.
        - **ID de producte únic:** identificador del producte o servei adquirit quan les dades es troben en el nivell d'element de línia.
        - (Opcional) **Compra o devolució:** un camp booleà on el valor *true* identifica que una transacció era una devolució. Si no es faciliten les dades de Compra o Devolució en el model i el **Valor de la transacció** és negatiu, també utilitzarem aquesta informació per inferir una devolució.
- Característiques de les dades suggerides:
    - Dades històriques suficients: almenys un any de dades transaccionals, preferiblement de dos a tres anys per incloure una mica d'estacionalitat.
    - Múltiples compres per client: tres o més transaccions per identificador de client
    - Nombre de clients: almenys 100 clients, preferentment més de 10.000 clients únics. El model fallarà amb menys de 100 clients.

> [!NOTE]
> - El model requereix l'historial de transaccions dels clients. La definició d'una transacció és bastant flexible. Qualsevol dada que descrigui una interacció usuari-producte pot funcionar com una entrada. Per exemple, comprar un producte, fer una classe o assistir a un esdeveniment.
> - Actualment només es pot configurar una entitat de l'historial de transaccions. Si hi ha diverses entitats de compra, uniu-les a Power Query abans de la ingestió de dades.
> - Si la comanda i els detalls de la comanda són entitats diferents, uniu-los abans d'utilitzar-los al model. El model no funciona amb un sol identificador de comanda o identificador de rebut en una entitat.


## <a name="create-a-product-recommendation-prediction"></a>Crear una predicció de recomanacions de productes

1. Al Customer Insights, aneu a **Intel·ligència** > **Prediccions**.

1. Seleccioneu la peça **Model de recomanacions de productes (versió preliminar)** i seleccioneu **Utilitza aquest model**.
   > [!div class="mx-imgBorder"]
   > ![Peça Model de recomanació de productes amb el botó Utilitza aquest model.](media/product-recommendation-usethismodel.PNG "Peça Model de recomanació de productes amb el botó Utilitza aquest model")

1. Reviseu la informació sobre els requisits del model. Si teniu les dades necessàries, seleccioneu **Comença**.

### <a name="name-model"></a>Assignació d'un nom al model

1. Proporcioneu un nom per al model per diferenciar-lo de la resta de models.

1. Introduïu un nom per a l'entitat de sortida utilitzant només lletres i números, sense espais. Aquest és el nom que utilitzarà l'entitat del model. A continuació, seleccioneu **Següent**.

### <a name="define-product-recommendation-configuration"></a>Definir la configuració de recomanació de producte

1. Definiu el **nombre de productes** que voleu recomanar a un client. Aquest valor depèn de com el mètode de lliurament emplena les dades. Si podeu recomanar tres productes, definiu aquest valor segons això.
   
   >[!TIP]
   > Podeu seleccionar **Desa i tanca** en qualsevol moment per desar la predicció en forma d'esborrany. Trobareu l'esborrany de predicció a la pestanya **Les meves prediccions**.

1. Trieu si voleu **suggerir productes que els clients han comprat recentment**.

1. Si heu seleccionat que *no* recomaneu els productes adquirits recentment, definiu la **Finestra de cerca en el passat**. Aquesta configuració especifica el període de temps que el model té en compte abans de recomanar el producte a l'usuari un altre cop. Per exemple, indica que un client compra un portàtil cada dos anys. Aquesta finestra analitzarà l'historial de compres dels dos últims anys i, si troba un article, el filtrarà a partir de les recomanacions.

1. Seleccioneu **Següent**

### <a name="add-required-data"></a>Addició de les dades necessàries

1. Seleccioneu **Afegeix dades** per a l'**Historial de transaccions del client** i trieu l'entitat que proporciona la informació de l'historial de transaccions o compres tal com es descriu als [requisits previs](#prerequisites).

1. Assigneu els camps semàntics als atributs de l'entitat d'historial de compres i seleccioneu **Següent**. Per a les descripcions dels camps, consulteu els [requisits previs](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definiu la relació de l'entitat.](media/product-recommendation-purchasehistorymapping.PNG "Pàgina de compra de l'historial que mostra els atributs administrats que estan assignats a camps de l'entitat de l'historial de compra seleccionat")

1. Si els següents camps no estan emplenats, configureu la relació des de l'entitat de l'historial de compres a l'entitat *Client*.
    1. Seleccioneu l'**Entitat de l'historial de compres**.
    1. Seleccioneu el **Camp** que identifica el client a l'entitat de l'historial de compres. S'ha de relacionar amb l'identificador del client principal de l'entitat *Client*.
    1. Seleccioneu l'**entitat Client** que coincideixi amb l'entitat Client principal.
    1. Introduïu un nom que descrigui la relació.
       > [!div class="mx-imgBorder"]
       > ![Pàgina Historial de compres que mostra la creació d'una relació amb el client.](media/model-purchase-join.png "Pàgina Historial de compres que mostra la creació d'una relació amb el client")

1. Seleccioneu **Desa**.

1. Seleccioneu **Següent**.

### <a name="configure-product-filters"></a>Configurar filtres de productes

De vegades, només certs productes són beneficiosos o adequats per al tipus de predicció que construïu. Els filtres de producte us permeten identificar un subconjunt de productes amb característiques específiques per recomanar als vostres clients. El model utilitzarà tots els productes disponibles per aprendre patrons, però només utilitzarà els productes que coincideixin amb el filtre de producte en la seva sortida.

1. Al pas **Afegeix informació del producte**, afegiu el catàleg de productes amb informació per a cada producte. Assigneu la informació necessària i seleccioneu **Següent**.

3. Al pas **Filtres de producte**, trieu entre les opcions següents.

   * **Sense filtres**: utilitzeu tots els productes de la predicció de recomanació de productes.

   * **Definir filtres de producte específics**: utilitzeu productes específics a la predicció de recomanació de productes.

1. Seleccioneu **Següent**.

1. Si decidiu definir un filtre de producte, heu de definir-lo ara. A la subfinestra **Atributs del catàleg de productes**, seleccioneu els atributs de l'*entitat Catàleg de productes* que voleu incloure al filtre.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Subfinestra lateral que es mostra atribuïda a l'entitat del catàleg de productes per seleccionar els filtres de producte.":::

1. Trieu si voleu que el filtre de producte utilitzi els connectors **and** o **or** per combinar lògicament la selecció d'atributs del catàleg de productes.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Configuració d'exemple de filtres de producte combinats amb connectors AND lògics.":::

1. Seleccioneu **Següent**.

### <a name="set-update-schedule-and-review-configuration"></a>Definir la planificació de la configuració i la revisió

1. Definiu una freqüència per tornar a entrenar el model. Aquesta configuració és important per actualitzar la precisió de les prediccions amb la importació de dades noves al Customer Insights. La majoria d'empreses poden tornar a entrenar un cop al mes i obtenir una bona precisió de les prediccions.

1. Seleccioneu **Següent**.

1. Reviseu la configuració. Podeu tornar enrere en qualsevol part de la configuració de predicció. Per fer-ho, seleccioneu **Edita** sota el valor que es mostra. O bé, podeu seleccionar un pas de configuració a l'indicador de progrés.

1. Si tots els valors s'han configurat correctament, seleccioneu **Desa i executa** per iniciar el procés de predicció. A la pestanya **Les meves prediccions**, podeu veure l'estat de les vostres prediccions. El procés pot tardar unes quantes hores a completar-se en funció de la quantitat de dades que s'han utilitzat a la predicció.

## <a name="review-a-prediction-status-and-results"></a>Revisar l'estat i els resultats de la predicció

1. Aneu a la pestanya **Les meves prediccions** a **Intel·ligència** > **Prediccions**.
   > [!div class="mx-imgBorder"]
   > ![Visualització de la pàgina Les meves prediccions.](media/product-recommendation-mypredictions.PNG "Visualització de la pàgina Les meves prediccions")

1. Seleccioneu la predicció que voleu revisar.
   - **Nom de la predicció:** el nom de la predicció proporcionat en crear-la.
   - **Tipus de predicció:** el tipus de model utilitzat per a la predicció
   - **Entitat de sortida:** nom de l'entitat per emmagatzemar els resultats de la predicció. Podeu trobar una entitat amb aquest nom a **Dades** > **Entitats**.    
      La *puntuació* en l'entitat de sortida és una mesura quantitativa de la recomanació. El model recomana productes amb una puntuació més alta abans que els productes amb una puntuació més baixa.
   - **Camp predit:** aquest camp s'omple només per a alguns tipus de prediccions i no s'utilitza a la predicció de Recomanació de productes.
   - **Estat:** l'estat actual de l'execució de la predicció.
        - **A la cua:** la predicció actualment està a l'espera de l'execució d'altres processos.
        - **S'està actualitzant:** la predicció està executant actualment la fase de processament "puntuació" per produir resultats que fluiran a l'entitat de sortida.
        - **Error:** s'ha produït un error en la predicció. Seleccioneu **Registres** per obtenir més informació.
        - **Ha reeixit:** la predicció s'ha dut a terme correctament. Seleccioneu **Visualitza** a sota dels tres punts verticals per revisar la predicció
   - **Editat:** la data en què es va canviar la configuració de la predicció.
   - **Última actualització:** la data en què s'han actualitzat els resultats de la predicció a l'entitat de sortida.

1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció de la qual voleu revisar els resultats i seleccioneu **Visualitza**.
   > [!div class="mx-imgBorder"]
   > ![Visualització d'opcions del menú dels tres punts verticals d'una predicció, que inclou l'edició, l'actualització, la visualització, els registres i la supressió.](media/product-recommendation-verticalellipses.PNG "Visualització d'opcions del menú dels tres punts verticals d'una predicció, que inclou l'edició, l'actualització, la visualització, els registres i la supressió")

1. Hi ha cinc seccions principals de dades a la pàgina de resultats:
    1. **Rendiment del model d'entrenament:** A, B o C són les puntuacions possibles. Aquesta puntuació indica el rendiment de la predicció i pot ser que us ajudi a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida.
        - La puntuació es determina en funció de les regles següents:
            - **A** Un model es considerarà de qualitat **A** si la mètrica "Èxit @ K" és com a mínim un 10% superior a la línia de base. 
            - **B** Un model es considerarà de qualitat **B** si la mètrica "Èxit @ K" és d'un 0% a un 10% superior a la línia de base.
            - **C** Un model es considerarà de qualitat **C** si la mètrica "Èxit @ K" és inferior a la línia de base.
               
               > [!div class="mx-imgBorder"]
               > ![Visualització del resultat del rendiment del model.](media/product-recommendation-modelperformance.PNG "Visualització del resultat del rendiment del model")
            - **Referència**: el model agafa els productes més recomanats pel nombre de compres de tots els clients i utilitza regles apreses identificades pel model per crear un conjunt de recomanacions per als clients. A continuació, les previsions es comparen amb els productes principals, segons el nombre de clients que havien adquirit el producte. Si un client té com a mínim un producte en els seus productes recomanats que també s'ha observat als productes que s'han adquirit més, es consideren part de la referència. Si hi havia 10 d'aquests clients que havien adquirit un producte recomanat de 100 clients totals, la referència seria del 10%.
            - **Èxit @ K**: mitjançant un conjunt de validació de període de temps de les transaccions, es creen recomanacions per a tots els clients i es comparen amb el conjunt de transaccions de validació. Per exemple, en un període de 12 mesos, el mes 12 es podria separar com a conjunt de dades de validació. Si el model preveu almenys un producte que adquiriríeu al mes 12 segons el que s'ha après dels 11 mesos anteriors, el client augmentaria la mètrica "Èxit @ K".
    
    1. **Productes més suggerits (amb recompte):** els cinc millors productes que es van predir per als vostres clients.
       > [!div class="mx-imgBorder"]
       > ![Gràfic que mostra els 5 productes més recomanats.](media/product-recommendation-topproducts.PNG "Gràfic que mostra els 5 productes més recomanats")
    
    1. **Factors clau de recomanació:** el model utilitza l'historial de transaccions dels clients per fer recomanacions de productes. Aprèn patrons basats en compres passades i troba similituds entre clients i productes. Aquestes similituds s'utilitzen per generar recomanacions de productes.
    Aquests són els factors que podrien influir en una recomanació de producte generada pel model. 
        - **Transaccions anteriors**: els patrons de compra en el passat van ser utilitzats pel model per generar recomanacions de productes. Per exemple, el model pot recomanar un _Ratolí Surface Arc_ si algú ha comprat recentment un _Surface Book 3_ i un _Surface Pen_. El model ha après que històricament molts clients havien comprat un _Ratolí Surface Arc_ després de comprar un _Surface Book 3_ i un _Surface Pen_.
        - **Similitud amb el client**: un producte recomanat va ser comprat històricament per altres clients que mostren patrons de compra similars. Per exemple, es va recomanar a John _Surface Headphones 2_ perquè Jennifer i Brad van comprar recentment _Surface Headphones 2_. El model creu que John és similar a Jennifer i Brad perquè històricament han tingut patrons de compra similars.
        - **Similitud del producte**: un producte recomanat és similar a altres productes que el client havia comprat prèviament. El model considera que dos productes són similars si van ser comprats junts o per clients similars. Per exemple, algú rep una recomanació per a una _unitat d'emmagatzematge USB_ perquè prèviament ha comprat un _adaptador USB-C a USB_ i el model creu que la _unitat d'emmagatzematge USB_ és similar a l'_adaptador USB-C a USB_ basant-se en patrons de compra històrics.

        Cada recomanació de producte està influenciada per un o més d'aquests factors. El percentatge de recomanacions en què intervé cada factor d'influència es visualitza en un gràfic. En l'exemple següent, el 100% de les recomanacions van estar influenciades per transaccions passades, el 60% per similitud del client i el 22% per similitud del producte. Passeu el cursor per sobre de les barres del gràfic per veure el percentatge exacte amb què han intervingut els factors d'influència.

        > [!div class="mx-imgBorder"]
        > ![Factors clau de recomanació.](media/product-recommendation-keyrecommendationfactors.png "Factors clau de recomanació apresos pel model per generar recomanacions de producte")
       
     
   1. **Estadístiques de dades**: proporciona una visió general del nombre de transaccions, clients i productes que ha considerat el model. Es basa en les dades d'entrada que s'han utilitzat per aprendre patrons i generar recomanacions de productes.

      > [!div class="mx-imgBorder"]
      > ![Estadístiques de dades.](media/product-recommendation-datastatistics.png "Estadístiques de dades al voltant de les dades d'entrada utilitzades pel model per aprendre patrons")

      Aquesta secció mostra estadístiques al voltant dels punts de dades que ha utilitzat el model per aprendre patrons i generar recomanacions de productes. El filtratge, tal com està configurat en la configuració del model, s'aplicarà sobre la sortida generada pel model. No obstant això, el model utilitza totes les dades disponibles per aprendre patrons. Per tant, si utilitzeu el filtratge de productes a la configuració del model, en aquesta secció es mostrarà el nombre total de productes que el model ha analitzat per aprendre patrons, que poden diferir del nombre de productes que coincideixen amb els criteris de filtratge definits.

   1. **Recomanacions de productes d'alta seguretat:** mostra de recomanacions que es proporcionen als clients que el model creu amb seguretat que pot adquirir el client.    
      Si s'afegeix un catàleg de productes, els identificadors de producte se substitueixen per noms de producte. Els noms de producte proporcionen una informació més útil i intuïtiva sobre les prediccions.
       > [!div class="mx-imgBorder"]
       > ![Llista que mostra els suggeriments d'alta seguretat per a un conjunt de clients individuals seleccionat.](media/product-recommendation-highconfidence.PNG "Llista que mostra els suggeriments d'alta seguretat per a un conjunt de clients individuals seleccionat")

## <a name="manage-predictions"></a>Administrar prediccions

Es pot optimitzar, solucionar els problemes, actualitzar o suprimir predictions. Reviseu un informe d'ús de dades d'entrada per obtenir informació sobre com es pot realitzar una predicció més fiable més ràpidament. Per obtenir més informació, vegeu [Administrar prediccions](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
