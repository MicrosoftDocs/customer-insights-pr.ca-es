---
title: Predir el valor de vida del client (CLV)
description: Predieu el potencial d'ingressos per als clients actius en el futur.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610362"
---
# <a name="predict-customer-lifetime-value-clv"></a>Predir el valor de vida del client (CLV)

Predieu el valor potencial (ingressos) que els clients actius individuals aportaran al vostre negoci en un període de temps futur definit. Aquesta predicció t'ajuda a:

- Identifiqueu clients d'alt valor i processeu aquesta informació.
- Creeu segments de clients estratègics en funció del seu valor potencial per executar campanyes personalitzades amb esforços específics de vendes, màrqueting i suport.
- Guiar el desenvolupament del producte centrant-se en les funcions que augmenten el valor del client.
- Optimitzeu l'estratègia de vendes o màrqueting i assigneu el pressupost amb més precisió per a la difusió del client.
- Reconèixer i premiar els clients d'alt valor mitjançant programes de fidelització o recompenses.

Determineu què significa CLV per al vostre negoci. Donem suport a les predicció CLV basades en transaccions. El valor previst d'un client es basa en l'historial de transaccions comercials. Penseu en la possibilitat de crear diversos models amb diferents preferències d'entrada i compareu els resultats del model per veure quin escenari del model s'adapta millor a les necessitats del vostre negoci.

> [!TIP]
> Proveu el CLV predicció utilitzant dades d'exemple: [valor del cicle de vida del client (CLV) predicció guia d'exemple](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Requisits previs

- Com a mínim permisos [de col·laborador](permissions.md)
- Almenys 100 clients únics, preferiblement més de 10.000 clients
- Identificador de client, un identificador únic per fer coincidir les transaccions amb un client concret
- Almenys un any d'historial de transaccions, preferiblement de dos a tres anys. Idealment, almenys dues o tres transaccions per identificador de client, preferiblement en diverses dates. L'historial de transaccions ha d'incloure:
  - **ID de transacció**: identificador únic de cada transacció
  - **Data de l'operació**: data o segell de temps de cada operació
  - **Import de la transacció**: valor monetari (per exemple, ingressos o marge de benefici) de cada transacció
  - **Etiqueta assignada a les devolucions**: valor vertader/fals booleà que indica si la transacció és una rendibilitat
  - **Identificador** de producte: identificador de producte del producte implicat en la transacció
- Dades sobre les activitats dels clients:
  - **Clau principal**: identificador únic d'una activitat
  - **Marca de** temps: data i hora de l'esdeveniment identificat per la clau principal
  - **Esdeveniment (nom de l'activitat):** nom de l'esdeveniment que voleu utilitzar
  - **Detalls (import o valor)**: detalls de l'activitat del client
- Dades addicionals com ara:
  - Activitats web: Historial de visites al lloc web o historial de correu electrònic
  - Activitats de fidelització: acumulació de punts de recompensa de fidelització i historial de bescanvis
  - Registre de servei d'atenció al client: historial de trucades, queixes o devolucions del servei
  - Informació del perfil del client
- Menys del 20% de valors que falten als camps obligatoris

> [!NOTE]
> Només es pot configurar una entitat de l'historial de transaccions. Si hi ha diverses entitats de compra o transacció, combineu-les abans de la Power Query ingestió de dades.

## <a name="create-a-customer-lifetime-value-prediction"></a>Crear una predicció del valor de vida del client

Seleccioneu **Desa l'esborrany** en qualsevol moment per desar el predicció com a esborrany. L'esborrany predicció es mostra a la **pestanya Les meves prediccions**.

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Crea**, seleccioneu **Utilitza el model** a la peça Valor **del cicle de vida del** client.

1. Seleccioneu **Introducció**.

1. **Anomeneu aquest model** i el **nom de l'entitat de sortida** per distingir-los d'altres models o entitats.

1. Seleccioneu **Següent**.

### <a name="define-model-preferences"></a>Definir les preferències del model

1. Definiu un **període de temps de predicció** per definir la distància en el futur en què voleu preveure el CLV. Per defecte, la unitat es defineix com a mesos.

   > [!TIP]
   > Per predir amb precisió clv per al període de temps establert, es requereix un període comparable de dades històriques. Per exemple, si voleu predir CLV per als propers mesos 12, teniu almenys entre 18 i 24 mesos de dades històriques.

1. Definiu el període de temps en què un client ha d'haver fet com a mínim una transacció per tenir-lo en compte com a actiu. El model només prediu CLV per a **clients** actius.
   - **Permet que el model calculi l'interval de compra (recomanat):** el model analitza les vostres dades i determina un període de temps en funció de l'historial de compres.
   - **Definiu l'interval manualment**: període de temps per a la definició d'un client actiu.

1. Definir el percentil del client **d'alt** valor.
    - **Càlcul del model (recomanat)**: El model utilitza la regla 80/20. El percentatge de clients que han aportat fins al 80% dels ingressos acumulats per al vostre negoci durant el període històric es considera de clients d'alt valor. Normalment, menys del 30 a 40% dels clients contribueixen a un 80% d'ingressos acumulats. Tanmateix, aquest nombre pot variar en funció del vostre negoci i del vostre sector.
    - **Percentatge de clients** actius principals: percentil específic per a un client d'alt valor. Per exemple, introduïu **25** per definir els clients d'alt valor com el 25% superior dels futurs clients que paguen.

    Si el vostre negoci defineix els clients d'alt valor d'una altra manera, [feu-nos-ho saber perquè ens agradaria saber-ho](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Seleccioneu **Següent**.

### <a name="add-required-data"></a>Addició de les dades necessàries

1. Seleccioneu **Afegeix dades** per a **l'historial de transaccions de clients**.

1. Seleccioneu el tipus d'activitat semàntica, **SalesOrder** o **SalesOrderLine**, que conté l'historial de transaccions. Si l'activitat no s'ha configurat, seleccioneu **aquí** i creeu-la.

1. A **Activitats**, si els atributs d'activitat es van assignar semànticament quan es va crear l'activitat, trieu els atributs o l'entitat específics en què voleu centrar-vos en el càlcul. Si l'assignació semàntica no s'ha produït, seleccioneu **Edita** i assigna les dades.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Afegiu les dades necessàries per al model CLV":::

1. Seleccioneu **Següent** i reviseu els atributs necessaris per a aquest model.

1. Seleccioneu **Desa**.

1. Afegiu més activitats o seleccioneu **Següent**.

### <a name="add-optional-activity-data"></a>Afegir dades d'activitat opcionals

Les dades que reflecteixen les interaccions clau dels clients (com ara el web, el servei d'atenció al client i els registres d'esdeveniments) afegeixen context als registres de transacció. Trobar més patrons a les dades de l'activitat de client pot millorar la precisió de les previsions.

1. Seleccioneu **Afegeix dades** a **Estadístiques del model d'boost amb dades** d'activitat addicionals.

1. Seleccioneu un tipus d'activitat que coincideixi amb el tipus d'activitat de client que afegiu. Si l'activitat no s'ha configurat, seleccioneu **aquí** i creeu-la.

1. A **Activitats**, si els atributs d'activitat es van assignar quan es va crear l'activitat, trieu els atributs o l'entitat específics en què voleu centrar-vos en el càlcul. Si no s'ha produït cap assignació, seleccioneu **Edita** i assigna les dades.

1. Seleccioneu **Següent** i reviseu els atributs necessaris per a aquest model.

1. Seleccioneu **Desa**.

1. Seleccioneu **Següent**.

1. [Afegiu dades de client opcionals](#add-optional-customer-data) o seleccioneu **Següent** i aneu a Defineix la [planificació d'actualitzacions](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Afegir dades de client opcionals

Seleccioneu entre 18 atributs de perfil de client d'ús comú per incloure'ls com a entrada al model. Aquests atributs poden conduir a resultats de models més personalitzats, rellevants i accionables per als casos d'ús de la vostra empresa.

Per exemple: Contoso Coffee vol predir el valor de la vida del client per dirigir-se a clients d'alt valor amb una oferta personalitzada relacionada amb el llançament de la seva nova màquina espresso. Contoso utilitza el model CLV i afegeix els 18 atributs del perfil de client per veure quins factors influeixen en els seus clients de més valor. Troben que la ubicació del client és el factor més influent per a aquests clients.
Amb aquesta informació, organitzen un esdeveniment local per al llançament de la màquina espresso i s'associen amb proveïdors locals per obtenir ofertes personalitzades i una experiència especial a l'esdeveniment. Sense aquesta informació, Contoso només podria haver enviat correus electrònics de màrqueting genèrics i haver perdut l'oportunitat de personalitzar per a aquest segment local dels seus clients d'alt valor.

1. Seleccioneu **Afegeix dades** a estadístiques **del model d'Boost encara més amb dades** de clients addicionals.

1. Per a **Entitat**, trieu **Client: CustomerInsights** per seleccionar el perfil de client unificat que s'assigna a les dades dels atributs del client. Per veure **l'identificador de** client, trieu **System.Customer.CustomerId**.

1. Assigneu més camps si les dades estan disponibles als vostres perfils de client unificats.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Exemple de camps mapejats per a dades de perfil de client.":::

1. Seleccioneu **Desa**.

1. Seleccioneu **Següent**.

### <a name="set-update-schedule"></a>Configurar la planificació d'actualització

1. Trieu la freqüència per reciclar el model en funció de les dades més recents. Aquesta configuració és important per actualitzar la precisió de les prediccions a mesura que s'ingereixen dades noves al Customer Insights. La majoria d'empreses poden tornar a entrenar un cop al mes i obtenir una bona precisió de les prediccions.

1. Seleccioneu **Següent**.

### <a name="review-and-run-the-model-configuration"></a>Revisar i executar la configuració del model

El **pas Revisa i executa** mostra un resum de la configuració i proporciona l'oportunitat de fer canvis abans de crear el predicció.

1. Seleccioneu **Edita** en qualsevol dels passos per revisar i fer qualsevol canvi.

1. Si esteu satisfet amb les vostres seleccions, seleccioneu **Desa i executa** per començar a executar el model. Seleccioneu **Fet**. La **pestanya Les meves prediccions** es mostra mentre es crea el predicció. El procés pot tardar unes quantes hores a completar-se en funció de la quantitat de dades que s'han utilitzat a la predicció.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Veure predicció resultats

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Les meves prediccions**, seleccioneu la predicció voleu visualitzar.

A la pàgina de resultats hi ha tres seccions principals de dades.

- **Rendiment del model de** formació: Els graus A, B o C indiquen el rendiment de la predicció i us poden ajudar a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imatge del quadre d'informació de puntuació del model amb la nota A.":::

  Customer Insights avalua el rendiment del model d'IA en la predicció dels clients d'alt valor en comparació amb un model de referència.

  Les qualificacions es determinen segons les regles següents:
  - **A** quan el model ha predit amb precisió almenys el 5 % de clients de més valor en comparació amb el model de base.
  - **B** quan el model ha predit amb precisió entre el 0 i el 5 % de clients de més valor en comparació amb el model de base.
  - **C** quan el model ha predit amb precisió menys clients de més valor en comparació amb el model de base.
  
  Seleccioneu [**Obtén informació sobre aquesta puntuació**](#learn-about-the-score) per obrir la subfinestra Classificació **del** model que mostra més detalls sobre el rendiment del model d'IA i el model de referència. Us ajudarà a entendre millor les mètriques de rendiment del model subjacent i com es va derivar la nota final de rendiment del model. El model de vase utilitza un enfocament sense IA per calcular el valor de vida dels clients basat principalment en les compres històriques fetes pels clients.

- **Valor dels clients per percentil**: els clients de baix valor i alt valor es mostren en un gràfic. Passeu el cursor per sobre de les barres de l'histograma per veure el nombre de clients de cada grup i el CLV mitjà d'aquest grup. Opcionalment, [creeu segments de clients](prediction-based-segment.md) basats en les seves prediccions de CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Valor dels clients per percentil per al model CLV":::

- **Factors més influents**: es tenen en compte diversos factors es consideren quan es crea la predicció de CLV a partir de les dades d'entrada proporcionades al model d'IA. Cadascun dels factors té la seva importància calculada per a les prediccions agregades que crea un model. Utilitzeu aquests factors per ajudar-vos a validar els resultats predicció. Aquests factors també proporcionen més informació sobre els factors més rellevants que han contribuït a preveure el CLV a tots els clients.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Factors més influents per al model CLV":::

### <a name="learn-about-the-score"></a>Més informació sobre la puntuació

La fórmula estàndard utilitzada per calcular el CLV pel model de base:

 _**CLV per a cada client** = Mitjana de compra mensual realitzada pel client en la finestra del client actiu * Nombre de mesos en el CLV període predicció * Taxa de retenció global de tots els clients_

El model d'IA es compara amb el model de base segons dues mètriques de rendiment del model.
  
- **Taxa d’èxit en la predicció de clients d’alt valor**

  Vegeu la diferència en la previsió de clients d'alt valor mitjançant el model d'IA en comparació amb el model de base. Per exemple, el 84% de taxa d'èxit significa que, de tots els clients d'alt valor de les dades d'entrenament, el model d'IA ha pogut capturar amb precisió el 84%. A continuació, comparem aquesta taxa d'èxit amb el percentatge d'èxit del model de base per indicar el canvi relatiu. Aquest valor s'utilitza per assignar una qualificació al model.

- **Mètriques d’error**

  Vegeu el rendiment global del model en termes d'error en la predicció de valors futurs. Per avaluar aquest error, utilitzem la mètrica Arrel de l'error quadràtic mitjà (RMSE). L'RMSE és una manera estàndard de mesurar l'error d'un model a l'hora de preveure dades quantitatives. L'RMSE del model d'IA es compara amb l'RMSE del model de base i s'indica la diferència relativa.

El model d'IA prioritza la classificació exacta dels clients segons el valor que aporta al vostre negoci. Per tant, només el percentatge d'èxit de la previsió de clients d'alt valor s'utilitza per obtenir la qualificació final del model. La mètrica RMSE és sensible als valors atípics. Als escenaris en què teniu un petit percentatge de clients amb valors de compra excepcionalment alts, pot ser que la mètrica global de l'RMSE no doni la imatge completa del rendiment del model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
