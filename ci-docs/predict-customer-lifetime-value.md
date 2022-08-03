---
title: Predicció del valor del cicle de vida del client (CLV)
description: Predieu el potencial d'ingressos per als clients actius en el futur.
ms.date: 07/21/2022
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
ms.openlocfilehash: b6f6665d906cc96688efe84035336f64d2a39303
ms.sourcegitcommit: 80d8436d8c940f1267e6f26b221b8d7ce02ed26b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186428"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Predicció del valor del cicle de vida del client (CLV)

Predieu el valor potencial (ingressos) que els clients actius individuals aportaran al vostre negoci en un període de temps futur definit. Aquesta característica us pot ajudar a aconseguir diversos objectius:

- Identificar clients d'alt valor i processar aquesta informació
- Crear segments de clients estratègics basats en el seu valor potencial per executar campanyes personalitzades amb objectius de vendes, màrqueting i assistència
- Guiar el desenvolupament de productes centrant-vos en característiques que augmentin el valor del client
- Optimitzar l'estratègia de vendes o màrqueting i assignar el pressupost de manera més precisa per arribar als clients
- Reconèixer i recompensar els clients d'alt valor a través de programes de fidelitat o recompenses

## <a name="prerequisites"></a>Requisits previs

Abans de començar, reflexioneu sobre què significa el CLV per al vostre negoci. Actualment admetem la predicció del CLV basada en transaccions. El valor previst d'un client es basa en l'historial de transaccions empresarials. Per crear la predicció, necessiteu com a mínim els permisos de [Col·laborador](permissions.md).

Com que la configuració i l'execució d'un model de CLV no triga gaire, penseu en la possibilitat de crear diversos models amb diferents preferències d'entrada i comparar els resultats dels models per veure quin escenari de model s'ajusta millor a les vostres necessitats empresarials.

### <a name="data-requirements"></a>Requisits de dades

Les dades següents són necessàries i, si es marquen com a opcionals, recomanades per augmentar el rendiment del model. Com més dades pugui processar el model, més precisa serà la predicció. Per tant, us animem a ingerir més dades d'activitats de client, si estan disponibles.

- Identificador de client: identificador únic per fer coincidir les transaccions amb un client individual

- Historial de transaccions: registre d'historial de transaccions amb l'esquema de dades semàntic següent
    - **ID de transacció**: identificador únic de cada transacció
    - **Data de la transacció**: data, preferiblement una marca de temps de cada transacció
    - **Import de la transacció**: valor monetari (per exemple, ingressos o marge de benefici) de cada transacció
    - **Etiqueta assignada a les devolucions** (opcional): valor booleà que indica si la transacció és una devolució 
    - **ID del producte** (opcional): identificador del producte implicat a la transacció

- Dades addicionals (opcional), per exemple
    - Activitats web: historial de visites de llocs web, historial de correus electrònics
    - Activitats de fidelitat: acumulació de punts de recompensa de fidelitat i historial de bescanvis
    - Registre del servei d'atenció al client, trucades de servei, queixes o historial de devolucions
    - Informació del perfil del client
- Dades sobre les activitats del client (opcional):
    - Identificadors d'activitat per distingir les activitats del mateix tipus
    - Identificadors de clients per assignar activitats als clients
    - Informació d'activitat que conté el nom i la data de l'activitat
    - L'esquema de dades semàntic per a les activitats és el següent:
        - **Clau principal**: un identificador únic per a una activitat
        - **Data i hora**: la data i l'hora de l'esdeveniment identificats per la clau principal
        - **Esdeveniment (nom de l'activitat)**: nom de l'esdeveniment que voleu utilitzar
        - **Detalls (import o valor)**: detalls de l'activitat del client

- Característiques de les dades suggerides:
    - Dades històriques suficients: almenys un any de dades transaccionals. Preferentment de dos a tres anys de dades transaccionals per predir el CLV durant un any.
    - Múltiples compres per client: l'ideal és almenys entre dues i tres transaccions per identificador de client, preferentment en múltiples dates.
    - Nombre de clients: almenys 100 clients únics, preferentment més de 10.000 clients únics. El model fallarà amb menys de 100 clients i dades històriques insuficients
    - Integritat de les dades: falten menys del 20% de valors als camps obligatoris de les dades d'entrada

> [!NOTE]
> - El model requereix l'historial de transaccions dels clients. Actualment només es pot configurar una entitat de l'historial de transaccions. Si hi ha diverses entitats de compra/transacció, podeu unir-les abans de la Power Query ingestió de dades.
> - Per a dades addicionals d'activitat del client (opcionals), però, podeu afegir tantes entitats d'activitat del client com vulgueu que el model tingui en compte.

## <a name="create-a-customer-lifetime-value-prediction"></a>Crear una predicció del valor de vida del client

1. Aneu a Prediccions d'intel **·ligència** > **·**.

1. Seleccioneu la peça **Valor de vida del client** i seleccioneu **Utilitza el model**. 

1. A la subfinestra Valor **del cicle de vida del** client, seleccioneu **Comença**.

1. **Anomeneu aquest model** i el **nom de l'entitat de sortida** per distingir-los d'altres models o entitats.

1. Seleccioneu **Següent**.

### <a name="define-model-preferences"></a>Definir les preferències del model

1. Definiu un **període de temps de predicció** per definir la distància en el futur en què voleu preveure el CLV.    
   Per defecte, la unitat es defineix com a mesos. Podeu canviar-la a anys per consultar més endavant en el futur.

   > [!TIP]
   > Per preveure amb precisió el CLV durant el període de temps que definiu, necessiteu un període comparable de dades històriques. Per exemple, si voleu preveure el CLV durant els pròxims 12 mesos, es recomana que tingueu com a mínim 18 a 24 mesos de dades històriques.

1. Especifiqueu què signifiquen els **clients actius** per a la vostra empresa. Definiu el període de temps en què un client ha d'haver fet com a mínim una transacció per tenir-lo en compte com a actiu. El model només predirà el CLV per als clients actius. 
   - **Deixa que el model calculi l'interval de compra (recomanat)**: el model analitza les dades i determina un període de temps segons les compres històriques.
   - **Defineix manualment l'interval**: si teniu una definició empresarial específica d'un client actiu, trieu aquesta opció i definiu el període de temps segons correspongui.

1. Definiu el percentatge de **Client d'alt valor** per permetre que el model proporcioni resultats que s'ajustin a la definició de l'empresa.
    - **Càlcul del model (recomanat)**: el model analitza les dades i determina quin valor pot ser el client d'alt valor per a l'empresa segons l'historial de transaccions dels clients. El model utilitza una regla heurística (inspirada segons la regla 80/20 o el principi de Pareto) per trobar la proporció de clients d'alt valor. El percentatge de clients que han aportat fins al 80% dels ingressos acumulats per al vostre negoci durant el període històric es considera de clients d'alt valor. Normalment, menys del 30 a 40% dels clients contribueixen a un 80% d'ingressos acumulats. Tanmateix, aquest nombre pot variar en funció del vostre negoci i del vostre sector.    
    - **Percentatge de clients actius principals**: definiu els clients d'alt valor per a la vostra empresa com a percentatge dels clients de pagament més actius. Per exemple, podeu utilitzar aquesta opció per definir els clients d'alt valor com el 20% superior dels clients futurs de pagament.

    Si el vostre negoci defineix els clients d'alt valor d'una altra manera, [feu-nos-ho saber perquè ens agradaria saber-ho](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Seleccioneu **Següent** per continuar amb el pas següent.

### <a name="add-required-data"></a>Addició de les dades necessàries

1. Al pas **Dades obligatòries**, seleccioneu **Afegeix dades** per a l'**Historial de transaccions del client** i trieu l'entitat que proporciona la informació de l'historial de transaccions tal com es descriu als [requisits previs](#prerequisites).

1. Assigneu els camps semàntics als atributs de l'entitat d'historial de compres i seleccioneu **Següent**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Imatge del pas de configuració per assignar els atributs de dades per a les dades necessàries.":::
 
1. Si els següents camps no estan emplenats, configureu la relació des de l'entitat de l'historial de compres a l'entitat *Client* i seleccioneu **Desa**.
    1. Seleccioneu l'entitat de l'historial de transaccions.
    1. Seleccioneu el camp que identifica un client a l'entitat de l'historial de compres. S'ha de relacionar amb l'identificador del client principal de l'entitat Client.
    1. Seleccioneu l'entitat que coincideixi amb l'entitat de client principal.
    1. Introduïu un nom que descrigui la relació.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Imatge del pas de configuració per definir la relació amb l'entitat de client.":::

1. Seleccioneu **Següent**.

### <a name="add-optional-activity-data"></a>Afegir dades d'activitat opcionals

Les dades que reflecteixen les interaccions clau dels clients (com ara el web, el servei d'atenció al client i els registres d'esdeveniments) afegeixen context als registres de transacció. Trobar més patrons a les dades de l'activitat de client pot millorar la precisió de les previsions.

1. **Al pas Dades addicionals (opcional),** seleccioneu **Afegeix dades a** Estadístiques **del model d'impuls amb dades** d'activitat addicionals. Trieu l'entitat d'activitat del client que proporciona la informació de l'activitat del client tal com es descriu als [requisits previs](#prerequisites).

1. Assigneu els camps semàntics als atributs de l'entitat de l'activitat del client i seleccioneu **Següent**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Imatge del pas de configuració per assignar els camps per a les dades addicionals.":::

1. Seleccioneu un tipus d'activitat que coincideixi amb el tipus d'activitat de client que afegiu. Trieu entre els tipus d'activitats existents o afegiu un tipus d'activitat nou.

1. Configureu la relació des de l'entitat d'activitat de client a l'entitat *Client*.

    1. Seleccioneu el camp que identifica el client a la taula de l'activitat del client. Pot estar directament relacionat amb l'ID de client principal de l'entitat *Client*.
    1. Seleccioneu l'entitat *Client* que coincideixi amb l'entitat *Client* principal.
    1. Introduïu un nom que descrigui la relació.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Imatge del pas del flux de configuració per afegir dades addicionals i configurar l'activitat amb exemples emplenats.":::

1. Seleccioneu **Desa**.
    Afegiu més dades si hi ha altres activitats de client que voleu incloure.

1. Afegiu dades de client opcionals o seleccioneu **Següent**.

### <a name="add-optional-customer-data"></a>Afegir dades de client opcionals

Seleccioneu entre 18 atributs de perfil de client d'ús comú per incloure'ls com a entrada al model. Aquests atributs poden conduir a resultats de models més personalitzats, rellevants i accionables per als casos d'ús de la vostra empresa.

Per exemple: Contoso Coffee vol predir el valor de la vida del client per dirigir-se a clients d'alt valor amb una oferta personalitzada relacionada amb el llançament de la seva nova màquina espresso. Contoso utilitza el model CLV i afegeix els 18 atributs del perfil de client per veure quins factors influeixen en els seus clients de més valor. Troben que la ubicació del client és el factor més influent per a aquests clients.
Amb aquesta informació, organitzen un esdeveniment local per al llançament de la màquina espresso i s'associen amb proveïdors locals per obtenir ofertes personalitzades i una experiència especial a l'esdeveniment. Sense aquesta informació, Contoso només podria haver enviat correus electrònics de màrqueting genèrics i haver perdut l'oportunitat de personalitzar per a aquest segment local dels seus clients d'alt valor.

1. **Al pas Dades addicionals (opcional),** seleccioneu **Afegeix dades** a **Estadístiques del model d'impuls encara més amb dades** de clients addicionals.

1. Per a **Entitat**, trieu **Client: CustomerInsights** per seleccionar la taula de perfil de client unificada que s'assigna a les dades dels atributs del client. Per veure **l'identificador de** client, trieu **System.Customer.CustomerId**.

1. Assigneu més camps si les dades estan disponibles als vostres perfils de client unificats.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Exemple de camps mapejats per a dades de perfil de client.":::

1. Seleccioneu **Desa** després d'assignar els atributs que el model hauria d'utilitzar per ajudar a predir el valor del cicle de vida del client.

1. Seleccioneu **Següent**.

### <a name="set-update-schedule"></a>Configurar la planificació d'actualització

1. Al pas **Planificació de l'actualització de dades**, trieu la freqüència per tornar a entrenar el model segons les dades més recents. Aquesta configuració és important per actualitzar la precisió de les prediccions a mesura que s'ingereixen dades noves al Customer Insights. La majoria d'empreses poden tornar a entrenar un cop al mes i obtenir una bona precisió de les prediccions.

1. Seleccioneu **Següent**.

### <a name="review-and-run-the-model-configuration"></a>Revisar i executar la configuració del model

1. Al pas **Revisió dels detalls del model**, valideu la configuració de la predicció. Podeu tornar enrere en qualsevol part de la configuració de predicció. Per fer-ho, seleccioneu **Edita** sota el valor que es mostra. També podeu seleccionar un pas de configuració de l'indicador de progrés.

1. Si tots els valors es configuren correctament, seleccioneu **Desa i executa** per iniciar l'execució del model. A la pestanya **Les meves prediccions**, podeu veure l'estat del procés de predicció. El procés pot tardar unes quantes hores a completar-se en funció de la quantitat de dades que s'han utilitzat a la predicció.

## <a name="review-prediction-status-and-results"></a>Revisar l'estat i els resultats de la predicció

### <a name="review-prediction-status"></a>Revisar l'estat de la predicció

1.  Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.
2.  Seleccioneu la predicció que voleu revisar.

- **Nom de la predicció:** nom de la predicció que es proporcionarà en crear-la.
- **Tipus de predicció:** tipus de model utilitzat per a la predicció
- **Entitat de sortida:** nom de l'entitat per emmagatzemar els resultats de la predicció. Aneu a **Dades** > **Entitats** per cercar l'entitat amb aquest nom.
- **Camp predit:** aquest camp només s'emplena per a alguns tipus de prediccions i no es fa servir a la predicció del valor de vida del client.
- **Estat:** estat de l'execució de la predicció.
    - **En cua:** la predicció està esperant que es completin altres processos.
    - **S'està actualitzant:** la predicció s'està executant per crear resultats que passaran a l'entitat de sortida.
    - **Error:** s'ha produït un error en executar la predicció. Per obtenir més informació, [reviseu els registres](manage-predictions.md#troubleshoot-a-failed-prediction).
    - **Correcta:** la predicció s'ha realitzat correctament. Seleccioneu **Visualitza** a sota dels punts suspensius verticals per revisar els resultats de la predicció.
- **Editat:** la data en què es va canviar la configuració de la predicció.
- **Última actualització:** la data en què s'han actualitzat els resultats de la predicció a l'entitat de sortida.

### <a name="review-prediction-results"></a>Revisar els resultats de la predicció

1. Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.

1. Seleccioneu la predicció de la qual voleu revisar els resultats.

A la pàgina de resultats hi ha tres seccions principals de dades.

- **Rendiment del model d'entrenament**: A, B o C són les qualificacions possibles. Aquesta qualificació indica el rendiment de la predicció i us pot ajudar a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida. Seleccioneu **Més informació sobre aquesta puntuació** per comprendre millor les mètriques de rendiment del model subjacent i com s'ha generat la qualificació de rendiment del model final.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imatge del quadre d'informació de puntuació del model amb la nota A.":::

  Mitjançant la definició dels clients d'alt valor proporcionada en configurar la predicció, el sistema avalua com fa funcionat el model d'IA a l'hora de predir els clients d'alt valor en comparació amb el model de base.    

  Les qualificacions es determinen segons les regles següents:
  - **A** quan el model ha predit amb precisió almenys el 5 % de clients de més valor en comparació amb el model de base.
  - **B** quan el model ha predit amb precisió entre el 0 i el 5 % de clients de més valor en comparació amb el model de base.
  - **C** quan el model ha predit amb precisió menys clients de més valor en comparació amb el model de base.

  A la subfinestra **Classificació del model** es mostren més detalls sobre el rendiment del model d'IA i el model de base. El model de vase utilitza un enfocament sense IA per calcular el valor de vida dels clients basat principalment en les compres històriques fetes pels clients.     
  La fórmula estàndard utilitzada per calcular el CLV pel model de base:    

  _**CLV per a cada client** = compra mitjana mensual realitzada pel client a la finestra del client activa * nombre de mesos al període de predicció del CLV * taxa de retenció global de tots els clients*_

  El model d'IA es compara amb el model de base segons dues mètriques de rendiment del model.
  
  - **Taxa d’èxit en la predicció de clients d’alt valor**

    Vegeu la diferència en la previsió de clients d'alt valor mitjançant el model d'IA en comparació amb el model de base. Per exemple, el 84% de taxa d'èxit significa que, de tots els clients d'alt valor de les dades d'entrenament, el model d'IA ha pogut capturar amb precisió el 84%. A continuació, comparem aquesta taxa d'èxit amb el percentatge d'èxit del model de base per indicar el canvi relatiu. Aquest valor s'utilitza per assignar una qualificació al model.

  - **Mètriques d’error**
    
    Una altra mètrica us permet revisar el rendiment global del model quant a error en preveure valors futurs. Per avaluar aquest error, utilitzem la mètrica Arrel de l'error quadràtic mitjà (RMSE). L'RMSE és una manera estàndard de mesurar l'error d'un model a l'hora de preveure dades quantitatives. L'RMSE del model d'IA es compara amb l'RMSE del model de base i s'indica la diferència relativa.

  El model d'IA prioritza la classificació exacta dels clients segons el valor que aporta al vostre negoci. Per tant, només el percentatge d'èxit de la previsió de clients d'alt valor s'utilitza per obtenir la qualificació final del model. La mètrica RMSE és sensible als valors atípics. Als escenaris en què teniu un petit percentatge de clients amb valors de compra excepcionalment alts, pot ser que la mètrica global de l'RMSE no doni la imatge completa del rendiment del model.   

- **Valor dels clients per percentatge**: mitjançant la definició de clients d'alt valor, els clients s'agrupen en un valor baix i un valor alt, segons les seves previsions de CLV, i es mostren en un gràfic. En passar el ratolí per sobre de les barres de l'histograma, podeu veure el nombre de clients a cada grup i la mitjana de CLV del grup. Aquestes dades us poden ajudar si voleu [crear segments de clients](segments.md) segons les seves previsions de CLV.

- **Factors més influents**: es tenen en compte diversos factors es consideren quan es crea la predicció de CLV a partir de les dades d'entrada proporcionades al model d'IA. Cadascun dels factors té la seva importància calculada per a les prediccions agregades que crea un model. Podeu utilitzar aquests factors per ajudar a validar els resultats de la predicció. Aquests factors també proporcionen més informació sobre els factors més rellevants que han contribuït a preveure el CLV a tots els clients.

## <a name="manage-predictions"></a>Administrar prediccions

Es pot optimitzar, solucionar els problemes, actualitzar o suprimir predictions. Reviseu un informe d'ús de dades d'entrada per obtenir informació sobre com es pot realitzar una predicció més fiable més ràpidament. Per obtenir més informació, vegeu [Administrar prediccions](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
