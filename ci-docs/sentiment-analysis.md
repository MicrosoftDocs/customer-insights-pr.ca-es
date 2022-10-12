---
title: Analitzar els sentiments dels comentaris dels clients (previsualització)
description: Aprendre a utilitzar un model d'anàlisi de sentiments sobre els comentaris dels clients a Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610446"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analitzar els sentiments als comentaris dels clients (previsualització)

L'anàlisi de sentiments permet sintetitzar el sentiment dels clients i identificar els aspectes empresarials com a oportunitats de millora. Aquesta funció del Customer Insights us ajuda a entendre què funciona bé i què heu d'abordar. Us pot ajudar a impulsar accions empresarials que permetin experiències que es tradueixin en una alta satisfacció i fidelització dels clients.

## <a name="overview"></a>Informació general

La funció d'anàlisi de sentiments genera dues estadístiques derivades per identificador de client. Una puntuació de sentiment (de -5 a 5) i una llista d'aspectes empresarials aplicables (àrees de negoci) que, en conjunt, us ajuden a entendre millor els comentaris dels clients.

Aquesta anàlisi us ajuda a:
- Obtenir una visió general dels sentiments dels clients cap a una marca o organització
- Identifiqueu els clients amb sentiment negatiu per centrar les vostres campanyes i interaccions i optimitzar-los per obtenir un retorn més alt  
- Identificar aspectes de negoci amb qüestions assenyalades pels clients  
- Segmenteu els clients en funció del seu sentiment per fer campanyes personalitzades amb vendes, màrqueting i esforços de suport específics
- Optimitzar les operacions comercials abordant àrees de preocupació o oportunitats esmentades pels clients
- Reconèixer els aspectes empresarials que ho estan fent bé i premiar els clients feliços mitjançant programes de fidelització i promoció

El model proporciona una llista de paraules que han afectat la decisió del model d'assignar una puntuació de sentiment o un aspecte empresarial concrets als comentaris dels comentaris.  

Utilitzem dos **models** de Processament del Llenguatge Natural (PNL): El primer assigna a cada comentari de retroalimentació una puntuació de sentiment. El segon model associa cada feedback amb tots els aspectes empresarials aplicables. Els models s'entrenen sobre dades públiques de fonts de xarxes socials, comerç al detall, restaurants, productes de consum i indústries de l'automòbil.
  
Els aspectes empresarials predefinits perquè el model s'associï a les dades de retroalimentació inclouen:
- Administració de comptes
- Caixa i pagament
- Servei tècnic per al client
- Recollida a la botiga
- Enviament i recuperació de paquets
- Pre-comanda
- Preu
- Privadesa i seguretat
- Promocions i recompenses
- Rebut i garantia
- Canvi i cancel·lació de la devolució
- Precisió del compliment
- Qualitat del lloc web o de l'aplicació

> [!NOTE]
> Actualment, només admetem l'anàlisi de sentiments sobre els comentaris dels clients en anglès. En el futur s'admetran més idiomes. Si es pengen comentaris en altres idiomes, el model continuarà retornant resultats. No obstant això, aquests resultats no seran precisos.

## <a name="prerequisites"></a>Requisits previs

- Com a mínim permisos [de col·laborador](permissions.md)
- [Dades de retroalimentació de text unificades](data-unification.md). Us recomanem que configureu [les entitats de dades de retroalimentació com a entitats](map-entities.md#select-primary-key-and-semantic-type-for-attributes) d'activitat de tipus semàntic (tipus de retroalimentació).
- Identificador de client unificat (UCID) des de la unificació de dades per fer coincidir els registres de dades de comentaris de text amb un client concret.
- Id. dels comentaris
- Marca de temps dels comentaris
- Text dels comentaris

El Customer Insights pot processar fins a 10 milions de registres de comentaris per a una única execució de models. El model pot analitzar comentaris de retroalimentació de fins a 128 paraules. Si un comentari de retroalimentació és més llarg, l'anàlisi només considera les primeres 128 paraules.

> [!NOTE]
> Només es pot configurar una entitat de retroalimentació. Si hi ha diverses entitats de retroalimentació, combineu-les abans de la Power Query ingestió de dades.

## <a name="configure-a-sentiment-analysis"></a>Configurar una anàlisi de sentiment

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Crea**, seleccioneu **Utilitza el model** a la peça Anàlisi del **sentiment del client (visualització prèvia).**

1. Seleccioneu **Introducció**.

1. **Anomeneu** l'anàlisi i proporcioneu el nom de l'entitat de sortida de l'aspecte **empresarial i el nom** de l'entitat de sortida de la **puntuació de sentiment**.

1. Seleccioneu **Següent**.

1. Seleccioneu **Afegeix dades** per **als comentaris** dels clients.

1. Seleccioneu el tipus **d'activitat semàntica Retroalimentació** que conté les dades de retroalimentació. Si l'activitat no s'ha configurat, seleccioneu **aquí** i creeu-la.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Pas de configuració per seleccionar activitats de comentaris per a l'anàlisi de sentiments.":::

1. Seleccioneu les activitats que voleu utilitzar per a aquesta anàlisi de sentiment i, a continuació, seleccioneu **Següent**.

1. Assigneu els atributs de les dades als atributs del model. 

1. Seleccioneu **Desa**.

1. Seleccioneu **Següent**. El **pas Revisa i executa** mostra un resum de la configuració i proporciona l'oportunitat de fer canvis abans de crear l'anàlisi.

1. Seleccioneu **Edita** en qualsevol dels passos per revisar i fer qualsevol canvi.

1. Si esteu satisfet amb les vostres seleccions, seleccioneu **Desa i executa** per començar a executar el model. Seleccioneu **Fet**. La **pestanya Les meves prediccions** es mostra mentre es crea el predicció. El procés pot tardar unes quantes hores a completar-se en funció de la quantitat de dades que s'han utilitzat a la predicció.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Veure els resultats de l'anàlisi

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Les meves prediccions**, seleccioneu la predicció voleu visualitzar.

Hi ha dues pestanyes de resultats.

### <a name="sumary-tab"></a>Fitxa sumari

Hi ha quatre seccions principals de dades a la pàgina de resultats.

- **Puntuació mitjana de** sentiment: les puntuacions de sentiment us ajuden a entendre el sentiment general de tots els clients.
  - **Negatiu** (-5 > 2)
  - **Neutre** (-1 > 1)
  - **Positiu** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representació visual del sentiment global del client.":::

- **Distribució dels clients per puntuació** de sentiment: els clients es classifiquen en grups negatius, neutres i positius en funció de les seves puntuacions de sentiment. Passeu el cursor per sobre de les barres de l'histograma per veure el nombre de clients i la puntuació mitjana de sentiment de cada grup. Aquestes dades us [poden ajudar a crear segments de clients](prediction-based-segment.md) en funció de les seves puntuacions de sentiment.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Gràfic de barres que mostra el sentiment dels clients entre els tres grups de sentiment.":::

- **Puntuació mitjana de sentiment al llarg del temps**: el sentiment del client pot canviar amb el pas del temps. Proporcionem tendències en els sentiments dels vostres clients per a l'interval de temps de les vostres dades. Aquesta visualització us ajuda a avaluar l'efecte de les promocions estacionals, els llançaments de productes o altres intervencions limitades en el temps sobre el sentiment dels clients. Per veure el gràfic, seleccioneu l'any d'interès al menú desplegable.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Gràfic d'història amb la puntuació de sentiment al llarg del temps representada com una línia.":::

- **Sentiment en tots els aspectes** empresarials: el sentiment mitjà en tots els aspectes empresarials us ajuda a avaluar quins aspectes de la vostra empresa ja satisfan els clients o requereixen més atenció. Els registres de comentaris que no s'alineen amb cap dels aspectes empresarials admesos es classifiquen a **Altres**. Ordena les dades seleccionant qualsevol columna.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Llista d'aspectes empresarials amb el valor de sentiment associat i el nombre de clients que l'esmenten.":::

  Seleccioneu el nom d'un aspecte empresarial per veure com s'identifica un aspecte empresarial mitjançant el model:

  - **Paraules** influents: paraules principals que van influir en la identificació del model d'IA d'un aspecte empresarial en els comentaris dels clients.
    **Mostrar paraules** ofensives: permet incloure paraules ofensives a la llista a partir de les dades originals dels comentaris dels clients. Per defecte, està desactivat.  L'emmascarament ofensiu de paraules està impulsat per un model d'IA i és possible que no detecti totes les paraules ofensives. Si detecteu una paraula ofensiva que no s'ha filtrat com s'esperava, feu-nos-ho saber.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Llista de paraules influents amb el commutador per mostrar o amagar paraules ofensives.":::

  - **Mostres** de comentaris: registres de comentaris reals a les dades. Les paraules es codifiquen per colors segons la seva influència en la identificació d'un aspecte empresarial.

### <a name="influential-words-analysis-tab"></a>Pestanya d'anàlisi de paraules influents

Hi ha tres apartats d'informació addicional que expliquen com funciona el model de sentiment.
  
- **Paraules principals que contribueixen al sentiment** positiu: paraules principals que van influir en la identificació del model d'IA del sentiment positiu en els comentaris dels clients.  

- **Paraules principals que contribueixen al sentiment** negatiu: paraules principals que van influir en la identificació del model d'IA del sentiment negatiu en els comentaris dels clients.

- **Mostres de** comentaris: registres de retroalimentació reals, un amb un sentiment negatiu i un altre amb un sentiment positiu. Les paraules dels registres de comentaris es ressalten segons la seva contribució a la puntuació de sentiment assignada. Les paraules que contribueixen a una puntuació de sentiment positiva es ressalten en verd. Les paraules que contribueixen a una puntuació negativa es ressalten en vermell.
   Seleccioneu **Mostra'n més** per carregar més mostres de retroalimentació.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemples d'anàlisi de sentiments sobre els comentaris dels clients.":::

**Mostrar paraules** ofensives: permet incloure paraules ofensives a la llista a partir de les dades originals dels comentaris dels clients. Per defecte, està desactivat.  L'emmascarament ofensiu de paraules està impulsat per un model d'IA i és possible que no detecti totes les paraules ofensives. Si detecteu una paraula ofensiva que no s'ha filtrat com s'esperava, feu-nos-ho saber.

## <a name="act-on-analysis-results"></a>Actuar sobre els resultats de l'anàlisi

Per crear segments de clients nous a partir dels resultats de l'anàlisi de sentiment, seleccioneu **Crea segments** a la part superior de la pàgina de resultats del model.

## <a name="potential-bias"></a>Biaix potencial

Com passa amb qualsevol característica que utilitzi intel·ligència artificial predictiva, pot haver-hi un biaix potencial en les dades que utilitzeu per predir el sentiment dels clients. Per exemple, si només recopileu comentaris en format digital, és possible que us perdeu els comentaris dels clients que principalment realitzen negocis amb vós en persona, cosa que afecta la sortida de la funció.

Com que aquesta característica utilitza mitjans automatitzats per avaluar dades i fer prediccions basades en aquestes dades, per tant, té la capacitat de ser utilitzada com a mètode d'elaboració de perfils, ja que aquest terme està definit pel Reglament General de Protecció de Dades ("GDPR"). L'ús d'aquesta característica per processar dades pot estar subjecte a l'RGPD o altres lleis o normatives. Vostè és responsable d'assegurar-se que el seu ús, inclosa l'anàlisi de Dynamics 365 Customer Insights sentiments, compleix amb totes les lleis i regulacions aplicables, incloses les lleis relacionades amb la privacitat, les dades personals, les dades biomètriques, la protecció de dades i la confidencialitat de les comunicacions.

[!INCLUDE [footer-include](includes/footer-banner.md)]

