---
title: Fer coincidir entitats per a la unificació de dades
description: Feu coincidir entitats per crear perfils de client unificats.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267466"
---
# <a name="match-entities"></a>Fer coincidir entitats

Després d'haver completat la fase d'assignació, ja esteu preparat per a la coincidència de les entitats. La fase de coincidència especifica com combinar els conjunts de dades en un conjunt de dades de perfil del client unificat. La fase de coincidència requereix com a mínim [dues entitats assignades](map-entities.md).

## <a name="specify-the-match-order"></a>Especificar l'ordre de coincidència

Aneu a **Dades** > **Unificació** > **Coincidència** i seleccioneu **Defineix l'ordre** per iniciar la fase de coincidència.

Cada coincidència unifica dues o més entitats en una entitat única alhora que es conserva cada registre de client únic. A l'exemple següent, seleccionem tres entitats: **ContactCSV: TestData** com a entitat **Principal**, **WebAccountCSV: TestData** com a **Entitat 2**, i **CallRecordSmall: TestData** com a **Entitat 3**. El diagrama que hi ha a sobre de les seleccions il·lustra com s'executarà l'ordre de coincidència.

> [!div class="mx-imgBorder"]
> ![Editar l'ordre de coincidència de dades](media/configure-data-match-order-edit-page.png "Editar l'ordre de coincidència de dades")
  
L'entitat **Principal** es fa coincidir amb l'**Entitat 2**. El conjunt de dades que es produeix a partir de la primera coincidència es fa coincidir amb l'**Entitat 3**.
En aquest exemple, només seleccionem dues coincidència, però el sistema pot admetre'n més.

> [!IMPORTANT]
> L'entitat que trieu com a entitat **Principal** servirà com a base per al vostre conjunt de dades mestre unificat. Les entitats addicionals que s'hagin seleccionat durant la fase de coincidència s'afegiran a aquesta entitat. Al mateix temps, això no vol dir que l'entitat unificada inclourà *totes* les dades incloses en aquesta entitat.
>
> Hi ha dues consideracions que poden ajudar-vos a triar la jerarquia de les entitats:
>
> - Quina entitat considereu que té les dades més completes i fiables sobre els vostres clients?
> - L'entitat que acabeu d'identificar té atributs que també comparteixen altres entitats (per exemple, el nom, el número de telèfon o l'adreça electrònica)? Si no és així, trieu la segona entitat més fiable.

Seleccioneu **Fet** per desar l'ordre de coincidència.

## <a name="define-rules-for-your-first-match-pair"></a>Definir regles per al primer parell de coincidència

Després d'especificar l'ordre de coincidència, veureu les coincidències definides a la pàgina **Coincidència**. Les peces de la part superior de la pantalla estaran buides fins que s'executi l'ordre de coincidència.

> [!div class="mx-imgBorder"]
> ![Definir regles](media/configure-data-match-need-rules.png "Definir regles")

L'avís **Necessita regles** suggereix que no s'ha definit cap regla de coincidència per a un parell de coincidència. Les regles de coincidència especifiquen la lògica mitjançant la qual es farà coincidir un parell d'entitats específic.

1. Per definir la primera regla, obriu la subfinestra **Definició de regla** seleccionant la fila de coincidència corresponent a la taula de coincidències (1) i, a continuació, seleccionant **Crea una nova regla** (2).

   > [!div class="mx-imgBorder"]
   > ![Crear una regla nova](media/configure-data-match-new-rule2.png "Crea un usuari nou")

2. A la subfinestra **Edita la regla**, configureu les condicions per a aquesta regla. Cada condició està representada per dues files que inclouen seleccions obligatòries.

   > [!div class="mx-imgBorder"]
   > ![Subfinestra Regla nova](media/configure-data-match-new-rule-condition.png "Subfinestra Regla nova")

   Entitat/Camp (primer): atribut que s'utilitzarà per a la coincidència de la primera entitat del parell de coincidència. Per exemple, un número de telèfon o una adreça electrònica. Trieu un atribut que és probable que sigui únic per al client.

   > [!TIP]
   > Eviteu fer coincidències en funció dels atributs de tipus d'activitat. En altres paraules, si un atribut sembla ser una activitat, pot ser que sigui un criteri pobre per a la coincidència.  

   Entitat/Camp (segon): atribut que s'utilitzarà per a la coincidència de la segona entitat del parell de coincidència.

   Normalitza - **mètode de normalització**: hi ha diverses opcions de normalització disponibles per als atributs seleccionats. Per exemple, eliminar la puntuació o els espais

   Per a la normalització del nom de l'organització (visualització prèvia), també podeu seleccionar **Tipus (telèfon, nom, organització)**

   > [!div class="mx-imgBorder"]
   > ![Normalització-B2B](media/match-normalization-b2b.png "Normalització-B2B")

   Nivell de precisió: el nivell de precisió que s'utilitzarà per a aquesta condició. La definició d'un nivell de precisió per a una condició de coincidència pot tenir dos tipus: **Bàsic** i **Personalitzat**.  
   - Bàsic: us proporciona quatre opcions per seleccionar: Baixa, Mitjana, Alta i Exacta. Seleccioneu **Exacta** per tal de fer coincidir només els registres que coincideixen en un 100 per cent. Seleccioneu un dels altres nivells perquè fer coincidir registres que no són 100 per cent idèntics.
   - Personalitzat: utilitzeu la barra lliscant per definir el percentatge personalitzat de coincidència dels registres o introduïu un valor al camp **Personalitzat**. El sistema només farà coincidir els registres que superin aquest llindar com a parells de coincidència combinats. Els valors de la barra lliscant estan entre 0 i 1. Per tant, 0,64 representa el 64 per cent.

3. Seleccioneu **Fet** per desar la regla.

### <a name="add-multiple-conditions"></a>Afegir diverses condicions

Per fer coincidir les entitats només si es compleixen diverses condicions, afegiu més condicions enllaçades mitjançant un operador AND.

1. A la subfinestra **Edita la regla**, seleccioneu **Afegeix una condició**. També podeu suprimir condicions seleccionant el botó Suprimeix que hi ha al costat d'una condició existent.

2. Seleccioneu **Fet** per desar la regla.

## <a name="add-multiple-rules"></a>Afegir diverses regles

Cada condició s'aplica a un únic parell d'atributs, mentre que les regles representen conjunts de condicions. Per tal que les entitats coincideixin amb diferents conjunts d'atributs, podeu afegir més regles.

1. A les conclusions del públic, aneu a **Dades** > **Unifica** > **Coincidència**.

2. Seleccioneu l'entitat que voleu actualitzar i seleccioneu **Afegeix regles**.

3. Seguiu el procediment que s'indica a [Definir regles per al primer parell de coincidència](#define-rules-for-your-first-match-pair).

> [!NOTE]
> L'ordre de les regles és important. L'algoritme de coincidència prova de coincidir segons la primera regla i continua a la segona regla només si no s'ha identificat cap coincidència en la primera regla.

## <a name="define-deduplication-on-a-match-entity"></a>Definir la desduplicació en una entitat de coincidència

A més d'especificar les regles de coincidència entre entitats que es descriuen a les seccions anteriors, també podeu especificar regles de desduplicació. La *desduplicació* és un procés. Identifica registres duplicats, els combina en un únic registre i enllaça tots els registres d'origen amb aquest registre combinat amb identificadors alternatius al registre combinat.

Un cop identificat un registre desduplicat, aquest registre s'utilitzarà al procés de coincidència entre entitats. La desduplicació s'implementa en el nivell d'entitat i es pot aplicar a cada entitat utilitzada en el procés de coincidència.

### <a name="add-deduplication-rules"></a>Afegir regles de desduplicació

1. A les conclusions del públic, aneu a **Dades** > **Unifica** > **Coincidència**.

1. A la secció **Duplicats combinats**, seleccioneu **Defineix entitats**.

1. A la secció **Combinació de les preferències**, seleccioneu les entitats a les quals voleu aplicar la desduplicació.

1. Especifiqueu com es combinaran els registres duplicats i trieu una de les tres opcions de combinació:
   - *Més emplenat*: identifica el registre amb els atributs més emplenats com el registre guanyador. Es tracta de l'opció de combinació per defecte.
   - *Més recent*: identifica el registre més recent com el registre guanyador. Requereix una data o un camp numèric per definir la qualitat de recent.
   - *Menys recent*: identifica el registre menys recent com el registre guanyador. Requereix una data o un camp numèric per definir la qualitat de recent.
 
   > [!div class="mx-imgBorder"]
   > ![Pas 1 de les regles de desduplicació](media/match-selfconflation.png "Pas 1 de les regles de desduplicació")
 
1. Un cop seleccionades les entitats i definida la seva preferència de combinació, seleccioneu **Crea una regla nova** per definir les regles de desduplicació en el nivell d'entitat.
   - **Seleccioneu un camp** mostra una llista amb tots els camps disponibles de l'entitat en la qual voleu desduplicar les dades d'origen.
   - Especifiqueu la configuració de precisió i normalització de manera semblant a la que s'especifica a la coincidència entre entitats.
   - Per definir altres condicions, seleccioneu **Afegeix una condició**.
 
   > [!div class="mx-imgBorder"]
   > ![Pas 2 de les regles de desduplicació](media/match-selfconflation-rules.png "Pas 2 de les regles de desduplicació")

  Podeu crear diverses regles de desduplicació per a una mateixa entitat. 

1. En executar ara el procés de coincidència, els registres s'agruparan segons les condicions definides a la regles de desduplicació. Un cop agrupats els registres, s'aplicarà la norma de combinació per identificar el registre guanyador.

1. A continuació, aquest registre guanyador es passa a la coincidència entre entitats i els registres no guanyadors (per exemple, els ID alternatius) per millorar la qualitat de les coincidències.

1. Les regles de coincidència personalitzades definides per fer coincidir sempre o no fer coincidir mai invalidaran les regles de desduplicació. Si una regla de desduplicació identifica registres coincidents i s'ha definit una regla de coincidència personalitzada per no fer coincidir mai aquests registres, aquests dos registres no es faran coincidir.

1. Un cop executat el procés de coincidència, es mostraran les estadístiques de desduplicació.
   
> [!NOTE]
> No és obligatori especificar regles de desduplicació. Si no es configura cap regla d'aquest tipus, s'aplicaran les regles definides pel sistema. Per tal de millorar el rendiment i garantir el funcionament del sistema, es combinaran tots els registres que comparteixen la mateixa combinació de valors (coincidència exacta) des de la clau principal i els camps de les regles de coincidència en un únic registre abans de passar les dades de la entitat a la coincidència entre entitats.

## <a name="run-your-match-order"></a>Executar l'ordre de coincidència

Un cop definides les regles de coincidència, incloses les regles de coincidència entre entitats i les de desduplicació, podreu executar l'ordre de coincidència. A la pàgina **Coincidència**, seleccioneu **Executa** per iniciar el procés. L'algoritme de coincidència pot tardar una estona a completar-se. No podeu canviar les propietats de la pàgina **Coincidència** fins que finalitzi el procés de coincidència. Trobareu l'entitat de perfil del client unificat que s'ha creat a la pàgina **Entitats**. L'entitat de client unificat s'anomena **ConflationMatchPairs : CustomerInsights**.

Per fer canvis addicionals i tornar a executar el pas, podeu cancel·lar una assignació en curs. Seleccioneu el text **S'està actualitzant...** i seleccioneu **Cancel·la la feina** a la part inferior de la subfinestra lateral que es mostra.

Quan el procés de concordança s'hagi completat, el text **S'està actualitzant...** canviarà a **Correcte** i podreu tornar a utilitzar tota la funcionalitat de la pàgina.

El primer procés de coincidència resulta en la creació d'una entitat mestra unificada. Totes les execucions posteriors resulten en l'expansió d'aquesta entitat.

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.

## <a name="deduplication-output-as-an-entity"></a>Sortida de la desduplicació com a entitat
A banda de l'entitat mestra unificada creada com a part de la coincidència entre entitats, el procés de desduplicació també genera una entitat nova per a cada entitat des de l'ordre de coincidència per identificar els registres desduplicats. Aquestes entitats es poden trobar amb **ConflationMatchPairs:CustomerInsights** a la secció **Sistema** de la pàgina **Entitats**, amb el nom **Deduplication_Datasource_Entity**.

Una entitat de sortida de desduplicació conté la informació següent:
- ID / Claus
  - Camp de clau principal i el seu camp d'ID alternatius. El camp d'ID alternatius consisteix en tots els ID alternatius identificats per a un registre.
  - El camp Deduplication_GroupId mostra el grup o clúster identificat dins d'una entitat que agrupa tots els registres semblants en funció dels camps de desduplicació especificats. S'utilitza per al processament del sistema. Si no hi ha regles de desduplicació manuals especificades i s'apliquen regles de desduplicació definides pel sistema, potser no trobareu aquest camp a l'entitat de sortida de desduplicació.
  - Deduplication_WinnerId: aquest camp conté l'ID guanyador dels grups o clústers identificats. Si Deduplication_WinnerId és el mateix que el valor de la clau principal d'un registre, significa que el registre és el registre guanyador.
- Camps que s'utilitzen per definir les regles de desduplicació.
- Els camps Regla i Puntuació per denotar quines de les regles de desduplicació s'apliquen i la puntuació retornada per l'algorisme de coincidència.

## <a name="review-and-validate-your-matches"></a>Revisar i validar les coincidències

Avalueu la qualitat dels parells de coincidència i refineu-la:

- A la pàgina **Coincidència**, trobareu dues peces que mostren informació inicial sobre les vostres dades.

  - **Clients únics**: mostra el nombre de perfils únics que ha identificat el sistema.
  - **Registres coincidents**: mostra el nombre de coincidències entre tots els vostres parells de coincidència.

- A la taula **Ordre de coincidència**, podeu avaluar els resultats de cada parell de coincidència comparant el nombre de registres que provenen d'aquesta entitat de parell de coincidència en relació amb el percentatge de registres que han coincidit correctament.

- A la secció **Regles** d'una entitat de la taula **Ordre de coincidència**, trobareu el percentatge de registres que han coincidit correctament al nivell de regla. Si seleccioneu el símbol de taula que hi ha al costat d'una regla, podeu visualitzar tots aquests registres al nivell de regla. Es recomana revisar un subconjunt dels registres per validar que han coincidit correctament.

- Experimenteu amb diversos llindars de precisió sobre les condicions per identificar el valor òptim.

  1. Seleccioneu els punts suspensius (...) per a la regla de parell de coincidència amb la qual voleu experimentar i seleccioneu **Edita**.

  2. Seleccioneu la condició amb la qual voleu experimentar. Cada criteri es representa per una fila a la subfinestra **Regla de coincidència**.

  3. El que veureu a la pàgina **Visualització prèvia dels criteris** depèn del nivell de precisió que hàgiu seleccionat per a una condició. Cerqueu el nombre de registres coincidents i no coincidents per a la condició seleccionada.

     Obteniu una rica comprensió dels efectes dels diferents nivells de llindar. Podeu comparar el nombre de registres que coincidiran en cadascun dels nivells de llindar i visualitzar els registres de cada opció. Seleccioneu cadascuna de les peces i reviseu les dades de la secció de taula.

## <a name="optimize-your-matches"></a>Optimitzar les coincidències

Augmenteu la qualitat tornant a configurar alguns dels paràmetres de coincidència:

- **Canvieu l'ordre de coincidència** seleccionant **Edita** i canvieu els camps d'ordre de coincidència.

  > [!div class="mx-imgBorder"]
  > ![Editar l'ordre de coincidència de dades](media/configure-data-match-order-edit.png "Editar l'ordre de coincidència de dades")

- **Canvieu l'ordre de les regles** si heu definit diverses regles. Per tornar a ordenar les regles de coincidència, seleccioneu les opcions **Mou amunt** i **Mou avall** a la quadrícula de regles de coincidència.

  > [!div class="mx-imgBorder"]
  > ![Canviar l'ordre de les regles](media/configure-data-change-rule-order.png "Canviar l'ordre de les regles")

- **Dupliqueu les regles** si heu definit una regla de coincidència i voleu crear una regla semblant amb modificacions. Per fer-ho, seleccioneu **Duplica**.

  > [!div class="mx-imgBorder"]
  > ![Duplicar una regla](media/configure-data-duplicate-rule.png "Duplicar una regla")

- **Desactiveu una regla** per conservar una regla de coincidència, excloent-la del procés de coincidència.

  > [!div class="mx-imgBorder"]
  > ![Desactivar una regla](media/configure-data-deactivate-rule.png "Desactivar una regla")

- **Editeu les regles** seleccionant el símbol **Edita**. Podeu aplicar els canvis següents:

  - Canviar els atributs d'una condició: seleccioneu atributs nous dins de la fila de condicions específica.
  - Canviar el llindar d'una condició: ajusteu el control lliscant de precisió.
  - Canviar el mètode de normalització d'una condició: actualitzeu el mètode de normalització.

## <a name="specify-your-custom-match-records"></a>Especificar registres de coincidència personalitzats

Podeu especificar condicions amb les que certs registres han de coincidir sempre o mai. Aquestes regles es poden carregar de manera massiva al procés de coincidència.

1. Seleccioneu l'opció **Coincidència personalitzada** a la pantalla **Ordre de coincidència**.

   > [!div class="mx-imgBorder"]
   > ![Crear una coincidència personalitzada](media/custom-match-create.png "Crear una coincidència personalitzada")

2. Si no teniu cap entitat carregada, veureu un nou quadre de diàleg **Coincidència personalitzada** que requereix que empleneu alguns detalls. Si heu proporcionat aquestes dades abans, passeu al pas 8.

   > [!div class="mx-imgBorder"]
   > ![Quadre de diàleg de coincidència personalitzada nova](media/custom-match-new-dialog-box.png "Quadre de diàleg de coincidència personalitzada nova")

3. Seleccioneu **Emplena la plantilla** per obtenir un fitxer de plantilla que pugui especificar els registres de les entitats que han de coincidir sempre o no coincidir mai. Haureu d'emplenar per separat els registres "coincideix sempre" i "no coincideixis mai" en dos fitxers diferents.

4. La plantilla conté camps per especificar l'entitat i els valors de clau principal de l'entitat que s'utilitzaran a la coincidència personalitzada. Per exemple, si voleu que la clau principal 12345 des de l'entitat Vendes sempre coincideixi amb la clau principal 34567 de l'entitat Contacte, haureu d'especificar-ho de la següent manera:
    - Entity1: Vendes
    - Entity1Key: 12345
    - Entity2: Contacte
    - Entity2Key: 34567

   El mateix fitxer de plantilla pot especificar els registres de coincidència personalitzats des de diverses entitats.
   
   Si voleu especificar la coincidència personalitzada per a la desduplicació en una entitat, proporcioneu la mateixa entitat com a Entitat1 i Entitat2 i definiu els diferents valors de clau principal.

5. Després d'afegir totes les substitucions que voleu aplicar, deseu el fitxer de la plantilla.

6. Aneu a **Dades** > **Fonts de dades** i ingeriu els fitxers de plantilla com a entitats noves. Un cop ingerits, podeu utilitzar-los per especificar la configuració de la coincidència.

7. Després de carregar els fitxers i que les entitats estiguin disponibles, torneu a seleccionar l'opció **Coincidència personalitzada**. Veureu opcions per especificar les entitats que voleu incloure. Seleccioneu les entitats necessàries al menú desplegable.

   > [!div class="mx-imgBorder"]
   > ![Substitucions de coincidència personalitzada](media/custom-match-overrides.png "Substitucions de coincidència personalitzada")

8. Seleccioneu les entitats que voleu utilitzar per a **Coincideix sempre** i **No coincideixis mai** i seleccioneu **Fet**.

9. Seleccioneu **Desa** a la pàgina **Coincidència** de la configuració de coincidència personalitzada que acabeu de configurar.

10. Seleccioneu **Executa** a la pàgina **Coincidència** per iniciar el procés de coincidència i la configuració de coincidència personalitzada entrarà en vigor. Totes les regles del sistema coincidents se substitueixen segons el conjunt d'opcions de configuració.

11. Una vegada que s'hagi completat la coincidència, podeu verificar l'entitat **ConflationMatchPair** per confirmar que les substitucions s'apliquen a les coincidències de combinació.

## <a name="next-step"></a>Pas següent

Després de completar el procés de coincidència com a mínim per a un parell de coincidència, podeu resoldre les contradiccions possibles de les dades anant al tema [**Combinació**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]