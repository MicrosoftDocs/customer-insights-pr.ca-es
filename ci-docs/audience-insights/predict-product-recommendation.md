---
title: Predicció de recomanacions de productes
description: Predieu els productes que pot comprar o interactuar un client.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598051"
---
# <a name="product-recommendation-prediction-preview"></a>Predicció de recomanacions de productes (versió preliminar)

El model de recomanació de productes crea conjunts de recomanacions de producte predictives. Les recomanacions es basen en el comportament de compra anterior i els clients amb patrons de compra similars. Podeu crear noves predictions de recomanació de productes a la pàgina **Intel·ligència** > **Prediccions**. Seleccioneu **Les meves prediccions** per veure la resta de prediccions que heu creat.

Les recomanacions de productes poden estar subjectes a les lleis i normatives locals, així com a les expectatives del client, que el model no està dissenyat específicament per tenir en compte.  Com a usuari d'aquesta funcionalitat predictiva, **heu de revisar les recomanacions abans de proporcionar-les als clients** per assegurar-vos que compliu les lleis o normatives aplicables, així com les expectatives dels clients del que podeu recomanar. 

A més, la sortida d'aquest model us proporcionarà recomanacions basades en l'identificador del producte. El vostre mecanisme de lliurament haurà d'agafar els identificadors de producte previstos i assignar-los al contingut adequat per als vostres clients que tenint en compte la localització, el contingut d'imatge i altres continguts o comportaments específics de l'empresa.

## <a name="sample-guide"></a>Guia d'exemple

Si esteu interessat a provar aquesta característica però no teniu dades per completar els requisits següents, podeu [crear una implementació d'exemple](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.
- Coneixements empresarials per comprendre diversos tipus de productes per a la vostra empresa i com interactuen els vostres clients. Admeten la recomanació de productes que ja han adquirit els vostres clients o recomanacions per a productes nous.
- Dades sobre les vostres transaccions, compres i historial:
    - Identificadors de transaccions per distingir compres o transaccions.
    - Identificadors de client per assignar les transaccions als vostres clients.
    - Dates dels esdeveniments de les transaccions que especifiquen les dates en què es van produir les transaccions.
    - (Opcional) Informació d'identificador de producte de la transacció.
    - (Opcional) Si una transacció és una devolució o no.
    - L'esquema de dades semàntiques requereix la següent informació:
        - **ID de transacció:** identificador únic de la compra o la transacció.
        - **Data de la transacció:** data de la compra o la transacció.
        - **Valor de la transacció:** valor numèric de la compra o la transacció.
        - **ID de producte únic:** identificador del producte o servei adquirit quan les dades es troben en el nivell d'element de línia.
        - (Opcional) **Compra o devolució:** camp cert o fals que identifica si la transacció ha estat una devolució o no. Si el **Valor de la transacció** és negatiu, també farem servir aquesta informació per inferir una devolució.


## <a name="create-a-product-recommendation-prediction"></a>Crear una predicció de recomanacions de productes

1. Al Customer Insights, aneu a **Intel·ligència** > **Prediccions**.

1. Seleccioneu la peça **Model de recomanacions de productes (versió preliminar)** i seleccioneu **Utilitza aquest model**.
   > [!div class="mx-imgBorder"]
   > ![Peça Model de recomanació de productes amb el botó Utilitza aquest model](media/product-recommendation-usethismodel.PNG "Peça Model de recomanació de productes amb el botó Utilitza aquest model")

1. Reviseu la informació sobre els requisits del model. Si teniu les dades necessàries, seleccioneu **Comença**.

### <a name="name-model"></a>Assignació d'un nom al model

1. Proporcioneu un nom per al model per diferenciar-lo de la resta de models.

1. Introduïu un nom per a l'entitat de sortida utilitzant només lletres i números, sense espais. Aquest és el nom que utilitzarà l'entitat del model. A continuació, seleccioneu **Següent**.

### <a name="define-product-recommendation-configuration"></a>Definir la configuració de recomanació de producte

1. Definiu el **nombre de productes** que voleu recomanar a un client. Aquest valor depèn de com el mètode de lliurament emplena les dades. Si podeu recomanar tres productes, definiu aquest valor segons això.
   
   >[!TIP]
   > Podeu seleccionar **Desa i tanca** en qualsevol moment per desar la predicció en forma d'esborrany. Trobareu l'esborrany de predicció a la pestanya **Les meves prediccions**.

1. Trieu si voleu **suggerir productes que els clients han comprat recentment**.

1. Si heu seleccionat que *no* recomaneu els productes adquirits recentment, definiu la **Finestra de cerca en el passat**. Aquesta configuració especifica el període de temps que el model té en compte abans de recomanar el producte a l'usuari un altre cop. Per exemple, indiqueu que un client compra un ordinador portàtil cada 2 anys. Aquesta finestra cercarà l'historial de compra dels darrers 2 anys i si troba un element, l'element es filtrarà de les recomanacions.

1. Seleccioneu **Següent**

### <a name="add-required-data"></a>Addició de les dades necessàries

1. Seleccioneu **Afegeix dades** per a l'**Historial de transaccions del client** i trieu l'entitat que proporciona la informació de l'historial de transaccions o compres tal com es descriu als [requisits previs](#prerequisites).

1. Assigneu els camps semàntics als atributs de l'entitat d'historial de compres i seleccioneu **Següent**. Per a les descripcions dels camps, consulteu els [requisits previs](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definir la relació d'entitat](media/product-recommendation-purchasehistorymapping.PNG "Pàgina de compra de l'historial que mostra els atributs administrats que estan assignats a camps de l'entitat de l'historial de compra seleccionat")

1. Si els següents camps no estan emplenats, configureu la relació des de l'entitat de l'historial de compres a l'entitat *Client*.
    1. Seleccioneu l'**Entitat de l'historial de compres**.
    1. Seleccioneu el **Camp** que identifica el client a l'entitat de l'historial de compres. S'ha de relacionar amb l'identificador del client principal de l'entitat *Client*.
    1. Seleccioneu l'**entitat Client** que coincideixi amb l'entitat Client principal.
    1. Introduïu un nom que descrigui la relació.
       > [!div class="mx-imgBorder"]
       > ![Pàgina Historial de compres que mostra la creació d'una relació amb el client](media/model-purchase-join.png "Pàgina Historial de compres que mostra la creació d'una relació amb el client")

1. Seleccioneu **Desa**.

1. Seleccioneu **Següent**.

### <a name="set-schedule-and-review-configuration"></a>Definir la planificació i revisar la configuració

1. Definiu una freqüència per tornar a entrenar el model. Aquesta configuració és important per actualitzar la precisió de les prediccions amb la importació de dades noves al Customer Insights. La majoria d'empreses poden tornar a entrenar un cop al mes i obtenir una bona precisió de les prediccions.

1. Seleccioneu **Següent**.

1. Reviseu la configuració. Podeu tornar enrere en qualsevol part de la configuració de predicció. Per fer-ho, seleccioneu **Edita** sota el valor que es mostra. O bé, podeu seleccionar un pas de configuració a l'indicador de progrés.

1. Si tots els valors s'han configurat correctament, seleccioneu **Desa i executa** per iniciar el procés de predicció. A la pestanya **Les meves prediccions**, podeu veure l'estat de les vostres prediccions. El procés pot tardar unes quantes hores a completar-se en funció de la quantitat de dades que s'han utilitzat a la predicció.

## <a name="review-a-prediction-status-and-results"></a>Revisar l'estat i els resultats de la predicció

1. Aneu a la pestanya **Les meves prediccions** a **Intel·ligència** > **Prediccions**.
   > [!div class="mx-imgBorder"]
   > ![Visualització de la pàgina Les meves prediccions](media/product-recommendation-mypredictions.PNG "Visualització de la pàgina Les meves prediccions")

1. Seleccioneu la predicció que voleu revisar.
   - **Nom de la predicció:** el nom de la predicció proporcionat en crear-la.
   - **Tipus de predicció:** el tipus de model utilitzat per a la predicció
   - **Entitat de sortida:** nom de l'entitat per emmagatzemar els resultats de la predicció. Podeu trobar una entitat amb aquest nom a **Dades** > **Entitats**.
   - **Camp predit:** aquest camp només s'emplena per a alguns tipus de prediccions i no es fa servir a la predicció de rotació.
   - **Estat:** l'estat actual de l'execució de la predicció.
        - **A la cua:** la predicció actualment està a l'espera de l'execució d'altres processos.
        - **S'està actualitzant:** la predicció està executant actualment la fase de processament "puntuació" per produir resultats que fluiran a l'entitat de sortida.
        - **Error:** s'ha produït un error en la predicció. Seleccioneu **Registres** per obtenir més informació.
        - **Ha reeixit:** la predicció s'ha dut a terme correctament. Seleccioneu **Visualitza** a sota dels tres punts verticals per revisar la predicció
   - **Editat:** la data en què es va canviar la configuració de la predicció.
   - **Última actualització:** la data en què s'han actualitzat els resultats de la predicció a l'entitat de sortida.

1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció de la qual voleu revisar els resultats i seleccioneu **Visualitza**.
   > [!div class="mx-imgBorder"]
   > ![Visualització d'opcions del menú dels tres punts verticals d'una predicció, que inclou l'edició, l'actualització, la visualització, els registres i la supressió](media/product-recommendation-verticalellipses.PNG "Visualització d'opcions del menú dels tres punts verticals d'una predicció, que inclou l'edició, l'actualització, la visualització, els registres i la supressió")

1. A la pàgina de resultats hi ha tres seccions principals de dades:
    1. **Rendiment del model d'entrenament:** A, B o C són les puntuacions possibles. Aquesta puntuació indica el rendiment de la predicció i pot ser que us ajudi a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida.
        - La puntuació es determina en funció de les regles següents:
            - **A** Un model es considerarà de qualitat **A** si la mètrica "Èxit @ K" és com a mínim un 10% superior a la línia de base. 
            - **B** Un model es considerarà de qualitat **B** si la mètrica "Èxit @ K" és d'un 0 a un 10% superior a la línia de base.
            - **C** Un model es considerarà de qualitat **C** si la mètrica "Èxit @ K" és inferior a la línia de base.
               
               > [!div class="mx-imgBorder"]
               > ![Visualització del resultat del rendiment del model](media/product-recommendation-modelperformance.PNG "Visualització del resultat del rendiment del model")
            - **Referència**: el model agafa els productes més recomanats pel nombre de compres de tots els clients i utilitza regles apreses identificades pel model per crear un conjunt de recomanacions per als clients. A continuació, les previsions es comparen amb els productes principals, segons el nombre de clients que havien adquirit el producte. Si un client té com a mínim un producte en els seus productes recomanats que també s'ha observat als productes que s'han adquirit més, es consideren part de la referència. Si hi havia 10 d'aquests clients que havien adquirit un producte recomanat de 100 clients totals, la referència seria del 10%.
            - **Èxit @ K**: mitjançant un conjunt de validació de període de temps de les transaccions, es creen recomanacions per a tots els clients i es comparen amb el conjunt de transaccions de validació. Per exemple, en un període de 12 mesos, el mes 12 es podria separar com a conjunt de dades de validació. Si el model preveu almenys un producte que adquiriríeu al mes 12 segons el que s'ha après dels 11 mesos anteriors, el client augmentaria la mètrica "Èxit @ K".
    
    1. **Productes més suggerits (amb recompte):** els 5 productes principals que s'han predit per als clients.
       > [!div class="mx-imgBorder"]
       > ![Gràfic que mostra els 5 productes més recomanats](media/product-recommendation-topproducts.PNG "Gràfic que mostra els 5 productes més recomanats")
    
    1. **Recomanacions de productes d'alta seguretat:** mostra de recomanacions que es proporcionen als clients que el model creu amb seguretat que pot adquirir el client.
       > [!div class="mx-imgBorder"]
       > ![Llista que mostra els suggeriments d'alta seguretat per a un conjunt de clients individuals seleccionat](media/product-recommendation-highconfidence.PNG "Llista que mostra els suggeriments d'alta seguretat per a un conjunt de clients individuals seleccionat")

## <a name="fix-a-failed-prediction"></a>Corregir una predicció errònia

1. Aneu a la pestanya **Les meves prediccions** a **Intel·ligència** > **Prediccions**.

1. Seleccioneu la predicció de la qual voleu visualitzar els registres d'error i seleccioneu **Registres**.

1. Reviseu tots els errors. Hi ha diversos tipus d'errors que es poden produir i que descriuen la condició que ha causat l'error. Per exemple, un error que indica que no hi ha prou dades per predir amb precisió se sol resoldre amb la càrrega de dades addicionals al Customer Insights.

## <a name="refresh-a-prediction"></a>Actualitzar una predicció

Les previsions s'actualitzen automàticament segons la mateixa [planificació que s'actualitzen les dades](system.md#schedule-tab) a la configuració.

1. Aneu a la pestanya **Les meves prediccions** a **Intel·ligència** > **Prediccions**.

1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció que voleu actualitzar.

1. Seleccioneu **Actualitza**.

## <a name="delete-a-prediction"></a>Suprimir una predicció

La supressió d'una predicció també comporta la supressió de la seva entitat de sortida.

1. Aneu a la pestanya **Les meves prediccions** a **Intel·ligència** > **Prediccions**.

1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció que voleu suprimir.

1. Seleccioneu **Suprimeix**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]