---
title: Anàlisi de sentiments per a la retroalimentació dels clients
description: Obteniu informació sobre com podeu utilitzar un model d'anàlisi de sentiments sobre la retroalimentació dels clients a Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: e51225bbfcd445180b12661cba12256c3f042045
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642334"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analitzar el sentiment en els comentaris dels clients (Previsualització)

Els clients esperen productes, serveis i experiències d'alta qualitat en aquests dies. Especialment els clients que comparteixen els seus comentaris. És molt difícil per a les organitzacions analitzar un volum creixent de dades sense reduir la precisió i un major cost laboral. Dynamics 365 Customer Insights Ofereix un model d'anàlisi de sentiments per a la retroalimentació dels clients que permet a les organitzacions analitzar les seves dades amb més precisió i a un cost menor.

L'anàlisi de sentiments permet sintetitzar el sentiment del client i identificar els aspectes empresarials com a oportunitats de millora. Aquesta funció d'estadístiques del client us ajuda a entendre què funciona bé i què heu d'abordar. Centra't en les àrees de negoci més rellevants i impactants per millorar l'experiència dels teus clients. En última instància, us pot ajudar a impulsar accions empresarials que permetin experiències que resultin en una alta satisfacció i lleialtat del client.

## <a name="overview"></a>Informació general

La funció d'anàlisi de sentiments genera dues estadístiques derivades per identificador de client. Una puntuació de sentiment (de -5 a 5) i una llista d'aspectes empresarials aplicables (àrees de negoci) junts us ajuden a entendre millor els comentaris dels clients. 

Aquesta informació us pot ajudar a aconseguir els següents resultats: 
- Obtenir una visió general dels sentiments del client cap a una marca o organització
- Identificar clients amb sentiment negatiu per centrar les vostres campanyes i interaccions i optimitzar-los per obtenir un rendiment més alt  
- Identificar els aspectes empresarials amb les qüestions assenyalades pels clients  
- Segmentar els clients en funció del seu sentiment per executar campanyes personalitzades amb esforços de vendes, màrqueting i suport específics
- Optimitzar les operacions comercials abordant les àrees de preocupació o oportunitats que els clients han esmentat
- Reconèixer els aspectes empresarials que ho estan fent bé i premiar els clients feliços a través de programes de fidelització i promoció

Per assegurar-vos que podeu confiar en els resultats dels models, proporcionem informació transparent sobre com els models prenen decisions. Obtindreu una llista de paraules que van afectar la decisió dels models d'assignar una puntuació de sentiment o un aspecte empresarial concret als comentaris de comentaris.  

Utilitzem dos **models** de processament del llenguatge natural (PNL): el primer assigna a cada comentari de retroalimentació una puntuació de sentiment. El segon model associa cada retroalimentació amb tots els aspectes empresarials aplicables. Els models es formen en dades públiques de fonts de les xarxes socials, el comerç minorista, la restauració, els productes de consum i les indústries de l'automòbil.    
  
Els aspectes empresarials predefinits perquè el model s'associï amb les dades de retroalimentació inclouen:
-   Administració de comptes
-   Caixa i pagament
-   Servei tècnic per al client
-   Recollida a la botiga
-   Enviament i recuperació de paquets
-   Pre-comanda
-   Preu
-   Privadesa i seguretat
-   Promocions i recompenses
-   Rebut i garantia
-   Canvi i cancel·lació de la devolució
-   Precisió del compliment
-   Qualitat del lloc web o de l'aplicació

> [!NOTE]
> Actualment, només donem suport a l'anàlisi de sentiments sobre la retroalimentació dels clients en anglès. En el futur es donaran suport a més idiomes. Si es carrega comentaris en altres idiomes, el model continuarà retornant els resultats. No obstant això, aquests resultats no seran exactes. 

## <a name="prerequisites"></a>Requisits previs

L'anàlisi de sentiments es basa en dades de retroalimentació de text que han passat pel procés d'unificació de [dades](data-unification.md). Us recomanem que configureu [les entitats de dades de comentaris com a entitats](map-entities.md#select-primary-key-and-semantic-type-for-attributes) d'activitat de tipus semàntic (tipus de comentaris) per endavant. 

Per configurar un model d'anàlisi de sentiments, necessiteu com a mínim [permisos](permissions.md) de col·laborador.

Les estadístiques del client poden processar fins a 10 milions de registres de comentaris per a un sol model executat. El model pot analitzar comentaris de retroalimentació de fins a 128 paraules. Si un comentari de retroalimentació és més llarg, l'anàlisi només té en compte les primeres 128 paraules.

### <a name="data-requirements"></a>Requisits de dades
  
Es requereixen els atributs de dades següents:
- Identificador de client unificat (UCID) per fer coincidir els registres de dades de comentaris de text amb un client individual. Aquest identificador és el resultat del procés [d'unificació](data-unification.md) de dades.
- Id. dels comentaris
- Marca horària de retroalimentació
- Text dels comentaris   

> [!TIP]
> L'anàlisi de sentiments requereix la retroalimentació del text dels vostres clients. Actualment només es pot configurar una entitat de retroalimentació. Si hi ha diverses entitats de retroalimentació, podeu unir-les abans que Power Query comenci la ingestió de dades.

## <a name="configure-a-sentiment-analysis"></a>Configura una anàlisi de sentiments 

1. Al Customer Insights, aneu a **Intel·ligència** > **Prediccions**.

1. A la **peça Anàlisi** de sentiments del client, seleccioneu **Utilitza el model**.

1. A la **subfinestra Anàlisi de sentiment del client (previsualització),** seleccioneu **Comença**.

1. Al pas Nom del **model**, proporcioneu un **nom** per a l'anàlisi. 

1. Proporcioneu el nom de l'entitat **de sortida de l'aspecte empresarial i el nom** de l'entitat de sortida de puntuació **Sentiment i, a continuació, seleccioneu** Següent **.**

1. **Al pas Dades necessàries**, seleccioneu **Afegeix dades**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Afegiu flux de dades al model d'anàlisi de sentiments.":::

1. A la **subfinestra Afegeix dades**, trieu el tipus **semàntic Feedback** de la llista.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Pas de configuració per seleccionar activitats de retroalimentació per a l'anàlisi de sentiments.":::

1. Seleccioneu les activitats que s'utilitzaran per a aquesta anàlisi de sentiments i, a continuació, seleccioneu **Endavant**.
 
1. Assigneu els atributs de les dades als atributs del model. Seleccioneu **Desa** per aplicar les seleccions. 

1. Veureu l'estat de l'assignació de dades. Per continuar, feu clic a **Següent**. 

1. Al pas Revisa els detalls **del** model, valida la configuració de la teva anàlisi de sentiments. Podeu tornar a qualsevol part de la configuració de predicció. Seleccioneu **Desa i executa** per iniciar l'anàlisi. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Pas de revisió del model de sentiment que mostra tots els elements configurats.":::

1. Seleccioneu **Fet** per sortir de l'experiència de configuració. El procés pot trigar diverses hores a completar-se en funció de la quantitat de dades utilitzades. 

## <a name="review-analysis-status"></a>Revisa l'estat de l'anàlisi

1.  Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.
2.  Seleccioneu la predicció que voleu revisar.
- **Nom de la predicció:** nom de la predicció que es proporcionarà en crear-la.
- **tipus** predicció: Tipus de model utilitzat per a la predicció.
- **Entitat de sortida:** nom de l'entitat per emmagatzemar els resultats de la predicció. Aneu a **Dades** > **Entitats** per cercar l'entitat amb aquest nom.
- **Camp predit:** aquest camp només s'emplena per a alguns tipus de prediccions i no es fa servir a la predicció del valor de vida del client.
- **Estat:** estat de l'execució de la predicció.
  - **En cua:** la predicció està esperant que es completin altres processos.
  - **S'està actualitzant:** la predicció s'està executant per crear resultats que passaran a l'entitat de sortida.
  - **Error:** s'ha produït un error en executar la predicció. Per obtenir més informació, reviseu els registres.
  - **Correcta:** la predicció s'ha realitzat correctament. Seleccioneu Visualitza a sota dels punts suspensius verticals per revisar els resultats de la predicció.
- **Editat:** la data en què es va canviar la configuració de la predicció.
- **Darrera actualització**: la data en què el predicció havia actualitzat resulta en l'entitat de sortida.

## <a name="manage-sentiment-analysis"></a>Gestionar l'anàlisi de sentiments

Podeu optimitzar, resoldre problemes, actualitzar o suprimir prediccions. Reviseu un informe d'ús de dades d'entrada per obtenir informació sobre com es pot realitzar una predicció més fiable més ràpidament. Per obtenir més informació, vegeu [Administrar prediccions](manage-predictions.md).

## <a name="review-analysis-results"></a>Revisa els resultats de l'anàlisi
 
1. Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**. 
1. Seleccioneu el nom de la predicció per a la qual voleu revisar els resultats. En aquest cas, seleccioneu l'anàlisi de sentiment que voleu revisar. 

### <a name="summary-tab"></a>Pestanya de resum

Hi ha quatre seccions principals de dades a la pàgina de resultats. 

- **Puntuació** mitjana del sentiment: us ajuda a entendre el sentiment general de tots els clients. Les puntuacions de sentiment s'agrupen en tres categories: 
  1.    Negatiu (-5 > 2)
  2.    Neutral (-1 > 1)
  3.    Positiu (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representació visual del sentiment global del client.":::

- **Distribució dels clients per puntuació** de sentiment: Els clients es classifiquen en grups negatius, neutres i positius en funció de les seves puntuacions de sentiment. Passeu el cursor per sobre de les barres de l'histograma per veure el nombre de clients i la puntuació mitjana del sentiment a cada grup. Aquestes dades us [poden ajudar a crear segments de clients](segments.md) en funció de les seves puntuacions de sentiment.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Gràfic de barres que mostra el sentiment del client entre els tres grups de sentiment.":::

- **Puntuació mitjana del sentiment al llarg del temps**: el sentiment del client pot canviar amb el temps. Proporcionem tendències en els sentiments dels seus clients per a l'interval de temps de les seves dades. Aquesta visualització us pot ajudar a mesurar l'efecte de promocions estacionals, llançaments de productes o altres intervencions temporals sobre el sentiment del client. Consulteu el gràfic seleccionant l'any d'interès del menú desplegable. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Gràfic d'historial amb la puntuació de sentiment al llarg del temps representada com una línia.":::
 
- **Sentiment entre els aspectes empresarials**: aquesta taula mostra el sentiment mitjà entre els aspectes empresarials. Pot ajudar-te a mesurar quins aspectes del teu negoci ja satisfan clients o aspectes que requereixen més atenció. Els registres de retroalimentació que no s'alineen amb cap dels aspectes empresarials admesos es classifiquen a **Altres**. La taula s'ordena alfabèticament per defecte. Podeu modificar l'ordenació seleccionant una capçalera de taula.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Relació d'aspectes empresarials amb el valor de sentiment associat i el nombre de clients que l'esmenten.":::
 
  Seleccioneu el nom d'un aspecte empresarial per veure informació addicional sobre com el model identifica un aspecte empresarial. Hi ha dues parts en aquest panell: 

  - **Paraules influents**: mostra les paraules principals que han influït en la identificació d'un aspecte empresarial del model d'IA en els comentaris dels clients. 
    **Mostrar paraules** ofensives: permet incloure paraules ofensives a la llista a partir de dades originals de comentaris dels clients. Per defecte, està desactivat.  L'emmascarament de paraules ofensiu està impulsat per un model d'IA i pot no detectar totes les paraules ofensives. Seguim iterant i entrenant el classificador per a un rendiment òptim. Si detecteu una paraula ofensiva que no s'ha filtrat com s'esperava, feu-nos-ho saber. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Llista de paraules influents amb el commutador per mostrar o amagar paraules ofensives.":::
 
  - **Mostres** de comentaris: mostra registres de comentaris reals a les dades. Les paraules estan codificades per colors segons la seva influència en la identificació d'un aspecte empresarial. 


### <a name="influential-words-analysis-tab"></a>Pestanya Anàlisi de paraules influents

Hi ha tres seccions d'informació addicional que expliquen com funciona el model de sentiment.
  
1. **Paraules principals que contribueixen al sentiment** positiu: mostra les paraules principals que van influir en la identificació del sentiment positiu del model d'IA en la retroalimentació dels clients.  
2. **Paraules principals que contribueixen al sentiment** negatiu: mostra les paraules principals que van influir en la identificació del sentiment negatiu del model d'IA en la retroalimentació dels clients.  
3. **Mostres** de retroalimentació: Mostra registres de retroalimentació reals, un amb un sentiment negatiu i un altre amb un sentiment positiu. Les paraules dels registres de retroalimentació es ressalten d'acord amb la seva contribució a la puntuació de sentiment assignada. Les paraules que contribueixen a una puntuació de sentiment positiu es ressalten en verd. Les paraules que contribueixen a una puntuació negativa es ressalten en vermell.
   Seleccioneu **Mostra més** per carregar més mostres de retroalimentació que proporcionin més informació i context de com funciona el model de sentiment.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemples d'anàlisi de sentiments sobre la retroalimentació dels clients.":::
 
**Mostrar paraules** ofensives: permet incloure paraules ofensives a la llista a partir de dades originals de comentaris dels clients. Per defecte, està desactivat.  L'emmascarament de paraules ofensiu està impulsat per un model d'IA i pot no detectar totes les paraules ofensives. Seguim iterant i entrenant el classificador per a un rendiment òptim. Si detecteu una paraula ofensiva que no s'ha filtrat com s'esperava, feu-nos-ho saber. 

## <a name="act-on-analysis-results"></a>Actuar sobre els resultats de l'anàlisi

Podeu començar a crear fàcilment nous segments de clients a partir de la pàgina de resultats de l'anàlisi de sentiments seleccionant **Crea segments a la part superior de la pàgina de resultats** del model.

:::image type="content" source="media/create-segment-model.png" alt-text="Barra d'ordres amb opcions sobre predicció models.":::
 
## <a name="potential-bias"></a>Biaix potencial

Igual que amb qualsevol característica que utilitza intel·ligència artificial predictiva, heu de ser conscients del biaix potencial en les dades que utilitzeu per predir el sentiment del client. Per exemple, si només recopileu comentaris digitalment, podeu perdre els comentaris dels clients que principalment fan negocis amb vosaltres en persona, cosa que podria afectar la sortida de la funció.

Atès que aquesta característica utilitza mitjans automatitzats per avaluar dades i fer prediccions basades en aquestes dades, per tant, té la capacitat de ser utilitzada com a mètode d'elaboració de perfils, ja que aquest terme està definit pel Reglament General de Protecció de Dades ("RGPD"). L'ús d'aquesta característica per processar dades pot estar subjecte a l'RGPD o altres lleis o normatives. Vostè és responsable d'assegurar-se que l'ús de, inclosa l'anàlisi de Dynamics 365 Customer Insights sentiments, compleix amb totes les lleis i regulacions aplicables, incloses les lleis relacionades amb la privadesa, les dades personals, les dades biomètriques, la protecció de dades i la confidencialitat de les comunicacions.

[!INCLUDE [footer-include](includes/footer-banner.md)]

