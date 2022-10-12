---
title: Predir recomanacions de productes
description: Predieu els productes que pot comprar o interactuar un client.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610270"
---
# <a name="predict-product-recommendations"></a>Predir recomanacions de productes

El model de recomanació de productes crea conjunts de recomanacions de producte predictives. Les recomanacions es basen en el comportament de compra anterior i els clients amb patrons de compra similars. Aquest model és per a consumidors individuals (B-to-C).

Has de tenir coneixements empresarials sobre els diferents tipus de productes per al teu negoci i com interactuen els teus clients amb ells. Admeten la recomanació de productes que ja han adquirit els vostres clients o recomanacions per a productes nous.

Les recomanacions de productes poden estar subjectes a les lleis i regulacions locals i a les expectatives dels clients, que el model no està construït per tenir específicament en compte. Per tant, **heu de revisar les recomanacions abans de lliurar-les als vostres clients** per assegurar-vos que compliu les lleis o regulacions aplicables i les expectatives dels clients sobre el que pugueu recomanar.

La sortida d'aquest model proporciona recomanacions basades en l'identificador del producte. El mecanisme de lliurament ha d'assignar els identificadors de producte previstos al contingut adequat perquè els clients tinguin en compte la localització, el contingut de la imatge i altres continguts o comportaments específics de l'empresa.

> [!TIP]
> Proveu la recomanació de producte predicció utilitzant dades d'exemple: [Recomanació de producte predicció guia d'exemple](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Requisits previs

- Com a mínim permisos [de col·laborador](permissions.md)
- Almenys 100 clients, preferiblement més de 10.000 clients.
- Identificador de client, un identificador únic per fer coincidir les transaccions amb un client concret
- Almenys un any de dades transaccionals, preferiblement de dos a tres anys per incloure alguna estacionalitat. Idealment, almenys tres o més transaccions per identificador de client. L'historial de transaccions ha d'incloure:
  - **Identificador** de transacció: identificador únic d'una compra o transacció.
  - **Data** de l'operació: Data de la compra o operació.
  - **Valor de l'operació**: Valor numèric de la compra o transacció.
  - **Identificador** únic de producte: identificador del producte o servei adquirit si les vostres dades es troben al nivell d'un article de línia.
  - **Compra o devolució**: un valor vertader/fals booleà on *el true* identifica que una transacció era una rendibilitat. Si no es faciliten les dades de compra o devolució en el model i el **valor de la transacció** és negatiu, inferim una devolució.
- Una entitat de dades del catàleg de productes per utilitzar-la com a filtre de producte.

> [!NOTE]
> - El model requereix l'historial de transaccions dels vostres clients on la transacció és qualsevol dada que descrigui una interacció usuari-producte. Per exemple, comprar un producte, fer una classe o assistir a un esdeveniment.
> - Només es pot configurar una entitat de l'historial de transaccions. Si hi ha diverses entitats de compra, combineu-les abans de la Power Query ingestió de dades.
> - Si la comanda i els detalls de la comanda són entitats diferents, uniu-los abans d'utilitzar-los al model. El model no funciona amb un sol identificador de comanda o identificador de rebut en una entitat.

## <a name="create-a-product-recommendation-prediction"></a>Crear una predicció de recomanacions de productes

Seleccioneu **Desa l'esborrany** en qualsevol moment per desar el predicció com a esborrany. L'esborrany predicció es mostra a la **pestanya Les meves prediccions**.

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Crea**, seleccioneu **Utilitza el model** a la peça Recomanacions de **producte (visualització prèvia).**

1. Seleccioneu **Introducció**.

1. **Anomeneu aquest model** i el **nom de l'entitat de sortida** per distingir-los d'altres models o entitats.

1. Seleccioneu **Següent**.

### <a name="define-product-recommendation-preferences"></a>Definir les preferències de recomanació de productes

1. Definiu el **nombre de productes** que voleu recomanar a un client. Aquest valor depèn de com el mètode de lliurament emplena les dades.

1. Trieu si voleu incloure productes que els clients han comprat prèviament al camp Repeteix les **compres esperades**.

1. Configureu la **finestra** Mira enrere amb el període de temps que el model consideri abans de tornar a recomanar el producte a l'usuari. Per exemple, indica que un client compra un portàtil cada dos anys. El model analitza l'historial de compres dels darrers dos anys i, si troba un article, l'article es filtra de les recomanacions.

1. Seleccioneu **Següent**

### <a name="add-purchase-history"></a>Afegeix l'historial de compres

1. Seleccioneu **Afegeix dades** per a **l'historial de transaccions de clients**.

1. Seleccioneu el tipus **d'activitat semàntica SalesOrderLine** que conté la informació necessària de l'historial de transaccions o compres. Si l'activitat no s'ha configurat, seleccioneu **aquí** i creeu-la.

1. A **Activitats**, si els atributs d'activitat es van assignar semànticament quan es va crear l'activitat, trieu els atributs o l'entitat específics en què voleu centrar-vos en el càlcul. Si l'assignació semàntica no s'ha produït, seleccioneu **Edita** i assigna les dades.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Subfinestra lateral que mostra la tria d'activitats específiques sota el tipus semàntic.":::

1. Seleccioneu **Següent** i reviseu els atributs necessaris per a aquest model.

1. Seleccioneu **Desa**.

1. Seleccioneu **Següent**.

### <a name="add-product-information-and-filters"></a>Afegir informació i filtres del producte

De vegades, només certs productes són beneficiosos o adequats per al tipus de predicció que construïu. Utilitzeu filtres de producte per identificar un subconjunt de productes amb característiques específiques per recomanar als vostres clients. El model utilitzarà tots els productes disponibles per aprendre patrons, però només utilitzarà els productes que coincideixin amb el filtre de producte en la seva sortida.

1. Afegiu l'entitat del catàleg de productes que contingui informació per a cada producte. Assigneu la informació necessària i seleccioneu **Desa**.

1. Seleccioneu **Següent**.

1. Seleccioneu **Filtres de productes**:

   - **Sense filtres**: utilitzeu tots els productes de la predicció de recomanació de productes.

   - **Definir filtres de producte específics**: utilitzeu productes específics a la predicció de recomanació de productes. A la **subfinestra Atributs** del catàleg de productes, seleccioneu els atributs de l'entitat del catàleg de productes que voleu incloure al filtre.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Subfinestra lateral que es mostra atribuïda a l'entitat del catàleg de productes per seleccionar els filtres de producte.":::

1. Trieu si voleu que s'utilitzi **el filtre de productes o** **combinar** lògicament la vostra selecció d'atributs del catàleg de productes.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Configuració d'exemple de filtres de producte combinats amb connectors AND lògics.":::

1. Seleccioneu **Següent**.

### <a name="set-update-schedule"></a>Configurar la planificació d'actualització

1. Trieu una freqüència per reciclar el vostre model. Aquesta configuració és important per actualitzar la precisió de les prediccions a mesura que s'ingereixen dades noves al Customer Insights. La majoria d'empreses poden tornar a entrenar un cop al mes i obtenir una bona precisió de les prediccions.

1. Seleccioneu **Següent**.

### <a name="review-and-run-the-model-configuration"></a>Revisar i executar la configuració del model

El **pas Revisa i executa** mostra un resum de la configuració i proporciona l'oportunitat de fer canvis abans de crear el predicció.

1. Seleccioneu **Edita** en qualsevol dels passos per revisar i fer qualsevol canvi.

1. Si esteu satisfet amb les vostres seleccions, seleccioneu **Desa i executa** per començar a executar el model. Seleccioneu **Fet**. La **pestanya Les meves prediccions** es mostra mentre es crea el predicció. El procés pot tardar unes quantes hores a completar-se en funció de la quantitat de dades que s'han utilitzat a la predicció.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Veure predicció resultats

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Les meves prediccions**, seleccioneu la predicció voleu visualitzar.

Hi ha cinc seccions principals de dades a la pàgina de resultats.

- **Rendiment del model:** les qualificacions A, B o C indiquen el rendiment del predicció i us poden ajudar a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Imatge del resultat del rendiment del model amb la qualificació A.":::

  Les qualificacions es determinen segons les regles següents:
  - **A** quan la mètrica "Èxit @ K" és almenys un 10% més que la línia de base.
  - **B** quan la mètrica "Èxit @ K" és del 0% al 10% més que la línia de base.
  - **C** quan la mètrica "Èxit @ K" és inferior a la línia de base.
  - **Línia de base**: Els principals productes més recomanats per compra compten entre tots els clients + regles apreses identificades pel model = un conjunt de recomanacions per als clients. A continuació, les previsions es comparen amb els productes principals, segons el nombre de clients que havien adquirit el producte. Si un client té com a mínim un producte en els seus productes recomanats que també s'ha observat als productes que s'han adquirit més, es consideren part de la referència. Per exemple, si 10 d'aquests clients tenien un producte recomanat comprat sobre 100 clients totals, la línia de base és del 10%.
  - **Èxit @ K**: Es creen recomanacions per a tots els clients i es comparen amb el conjunt de validació del període de temps de les transaccions. Per exemple, en un període de 12 mesos, el mes 12 es reserva com a conjunt de dades de validació. Si el model preveu almenys un producte que adquiriríeu al mes 12 segons el que s'ha après dels 11 mesos anteriors, el client augmentaria la mètrica "Èxit @ K".

- **Productes més suggerits (amb recompte):** els cinc millors productes que es van predir per als vostres clients.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Gràfic que mostra els 5 productes més recomanats.":::

- **Factors clau de recomanació:** el model utilitza l'historial de transaccions dels clients per fer recomanacions de productes. Aprèn patrons basats en compres passades i troba similituds entre clients i productes. Aquestes similituds s'utilitzen per generar recomanacions de productes.
  Els següents factors podrien influir en una recomanació de producte generada pel model.
  - **Transaccions anteriors**: Un producte recomanat es basava en patrons de compra anteriors. Per exemple, el model pot recomanar un *Ratolí Surface Arc* si algú ha comprat recentment un *Surface Book 3* i un *Surface Pen*. El model ha après que històricament molts clients havien comprat un *Ratolí Surface Arc* després de comprar un *Surface Book 3* i un *Surface Pen*.
  - **Similitud amb el client**: un producte recomanat va ser comprat històricament per altres clients que mostren patrons de compra similars. Per exemple, es va recomanar a John *Surface Headphones 2* perquè Jennifer i Brad van comprar recentment *Surface Headphones 2*. El model creu que John és similar a Jennifer i Brad perquè històricament han tingut patrons de compra similars.
  - **Similitud del producte**: un producte recomanat és similar a altres productes que el client havia comprat prèviament. El model considera que dos productes són similars si van ser comprats junts o per clients similars. Per exemple, algú rep una recomanació per a una *unitat d'emmagatzematge USB* perquè prèviament ha comprat un *adaptador USB-C a USB* i el model creu que la *unitat d'emmagatzematge USB* és similar a l'*adaptador USB-C a USB* basant-se en patrons de compra històrics.

  Cada recomanació de producte està influenciada per un o més d'aquests factors. El percentatge de recomanacions en què intervé cada factor d'influència es visualitza en un gràfic. En l'exemple següent, el 100% de les recomanacions van estar influenciades per transaccions passades, el 60% per similitud del client i el 22% per similitud del producte. Passeu el cursor per sobre de les barres del gràfic per veure el percentatge exacte amb què han intervingut els factors d'influència.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Factors de recomanació clau apresos pel model per generar recomanacions de productes.":::

- **Estadístiques** de dades: una visió general del nombre de transaccions, clients i productes que el model considera. Es basa en les dades d'entrada que s'han utilitzat per aprendre patrons i generar recomanacions de productes.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Estadístiques de dades al voltant de les dades d'entrada que utilitza el model per aprendre patrons.":::
  
  El model utilitza totes les dades disponibles per aprendre patrons. Per tant, si utilitzeu el filtratge de productes a la configuració del model, aquesta secció mostra el nombre total de productes que el model analitzat per aprendre patrons, que poden diferir del nombre de productes que coincideixen amb els criteris de filtratge definits. El filtratge s'aplica a la sortida generada pel model.

- **Exemple de recomanacions de productes:** una mostra de recomanacions que el model creu que és probable que el client les compri. Si s'afegeix un catàleg de productes, els identificadors de producte se substitueixen per noms de producte.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Llista que mostra els suggeriments d'alta seguretat per a un conjunt de clients individuals seleccionat.":::

> [!NOTE]
> En l'entitat de sortida d'aquest model, *Score* mostra la mesura quantitativa de la recomanació. El model recomana productes amb una puntuació més alta abans que els productes amb una puntuació més baixa. Per visualitzar la puntuació, aneu a **Entitats** > **de dades** i visualitzeu la pestanya dades de l'entitat de sortida que heu definit per a aquest model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
