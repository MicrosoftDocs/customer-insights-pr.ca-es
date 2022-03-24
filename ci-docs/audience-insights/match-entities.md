---
title: Fer coincidir entitats per a la unificació de dades
description: Feu coincidir entitats per crear perfils de client unificats.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: ab4ab0dba1bd91b1893cd4b16b8d51381d5b6ef8
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376910"
---
# <a name="match-entities"></a>Fer coincidir entitats

La fase de coincidència especifica com combinar els conjunts de dades en un conjunt de dades de perfil del client unificat. Un cop completat el [pas de l'assignació](map-entities.md) al procés d'unificació de dades, ja esteu a punt per aparellar-ho amb les entitats. La fase de coincidència requereix com a mínim dues entitats assignades.

La pàgina de coincidències consta de tres seccions: 
- Mètriques clau que resumeixen el nombre de registres coincidents
- Fer coincidir l'ordre i les regles per a la coincidència entre entitats
- Regles per desduplicació d'entitats coincidents

## <a name="specify-the-match-order"></a>Especificar l'ordre de coincidència

Cada coincidència unifica dues o més entitats en una única entitat consolidada. Al mateix temps, conserva els registres de client únics. L'ordre de coincidència indica l'ordre en què el sistema intenta fer coincidir els registres.

> [!IMPORTANT]
> L'entitat que trieu com a entitat principal servirà com a base per al vostre conjunt de dades de perfils unificat. Les entitats addicionals que s'hagin seleccionat durant la fase de coincidència s'afegiran a aquesta entitat. Això no vol dir que l'entitat unificada inclogui *totes* les dades incloses en aquesta entitat.
>
> Hi ha dues consideracions que poden ajudar-vos a triar la jerarquia de les entitats:
>
> - Trieu l'entitat amb les dades de perfil més completes i fiables sobre els clients com a entitat principal.
> - Trieu l'entitat que té diversos atributs en comú amb altres entitats (per exemple, nom, número de telèfon o adreça electrònica) com a entitat principal.

1. Aneu a **Dades** > **Unificació** > **Coincidència** i seleccioneu **Defineix l'ordre** per iniciar la fase de coincidència.
1. Seleccioneu **l'ordre de l'entitat**. Per exemple, seleccioneu **eCommerce:eCommerceContacts** com a entitat principal i **LoyaltyScheme:loyCustomers** com a segona entitat. 
1. Per tenir tots els registres de l'entitat com a client únic i coincidir amb totes les entitats següents, seleccioneu **Inclou-ho tot**.
1. Seleccioneu **Fet**. 

Després d'especificar l'ordre de coincidència, els parells de concordança definits es mostren a la secció Detalls de registres coincidents del **DataUnifyMatch** **·** > **.** > **·** Les mètriques clau estan buides fins que es completa el procés de coincidència.

:::image type="content" source="media/match-page.png" alt-text="Captura de pantalla de la pàgina Coincidències a l'àrea Unifica del procés d'unificació de dades.":::
  
L'entitat principal *eCommerce:eCommerceContacts* coincideix amb l'entitat següent *LoyaltyScheme:loyCustomers*. El conjunt de dades que resulta del primer pas de coincidència coincideix amb l'entitat següent si teniu més de dues entitats.

## <a name="define-rules-for-match-pairs"></a>Definir regles per a les parelles de coincidència

Les regles de coincidència especifiquen la lògica mitjançant la qual es farà coincidir un parell d'entitats específic.

L'advertiment **Necessita regles** al costat d'un nom d'entitat suggereix que no hi ha cap regla de coincidència definida per a una parella de coincidència. 

:::image type="content" source="media/match-rule-add.png" alt-text="Captura de pantalla de la secció Detalls del registre coincident amb el control per afegir regles ressaltat.":::

1. Seleccioneu **Afegeix una norma** a una entitat de la **secció Detalls** dels registres coincidents per definir les regles de concordança.

1. A la subfinestra **Crea una regla**, configureu les condicions de la regla.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Captura de pantalla d'una regla de coincidència oberta amb condicions afegides.":::

   - **Entitat o camp (primera fila)**: trieu una entitat relacionada i un atribut per especificar una propietat de registre que probablement sigui única per a un client. Per exemple, un número de telèfon o una adreça electrònica. Eviteu la coincidència per atributs de tipus d'activitat. Per exemple, és probable que un ID de compra no trobi cap coincidència en altres tipus de registres.

   - **Entitat/camp (segona fila)**: trieu un atribut que es relacioni amb l'atribut de l'entitat especificada a la primera fila.

   - **Normalitza**: seleccioneu les opcions de normalització següents per als atributs seleccionats. 
     - Numèrics: converteix altres sistemes numèrics, com ara els números romans, en números àrabs. *VIII* es converteix en *8*.
     - Símbols: suprimeix tots els símbols i caràcters especials. *Cap+espatlla* es converteix en *Capespatlla*.
     - Text en minúscula: converteix tots els caràcters a minúscules. *TOT MAJÚSCULES i títols* passa a ser *tot majúscules i títols*.
     - Tipus (Telèfon, Nom, Adreça, Organització): estandarditza noms, títols, números de telèfon, adreces, etc. 
     - Unicode a ASCII: converteix la notació unicode en caràcters ASCII. */u00B2* es converteix en *2*.
     - Espai en blanc: suprimeix tots els espais. *Hola   món* es converteix en *Holamón*.

   - **Precisió**: definiu el nivell de precisió que voleu aplicar per a aquesta condició. 
     - **Bàsica**: trieu entre *Baixa*, *Mitjana*, *Alta* i *Exacta*. Seleccioneu **Exacte** per coincidir només amb els registres que coincideixin amb el 100%. Seleccioneu un dels altres nivells perquè fer coincidir registres que no són 100 per cent idèntics.
     - **Personalitzat**: definiu un percentatge que han de complir els registres. El sistema només trobarà coincidències en els registres que compleixin aquest llindar.

1. Proporcioneu un **Nom** per a la regla.

1. [Afegiu més condicions](#add-conditions-to-a-rule) o seleccioneu **Fet** per finalitzar la regla.

1. Opcionalment, [afegiu més regles](#add-rules-to-a-match-pair).

1. Seleccioneu **Desa** per aplicar els canvis.

### <a name="add-conditions-to-a-rule"></a>Afegir condicions a una regla

Per fer coincidir les entitats només si els atributs compleixen diverses condicions, afegiu més condicions a una regla de coincidència. Les condicions estan connectades amb un operador AND lògic i, per tant, només s'executen si es compleixen totes les condicions.

1. Aneu a **Dades** > **Unifica** > **Coincidència** i seleccioneu **Edició** a la regla a la qual voleu afegir condicions.

1. A la subfinestra **Edita la regla**, seleccioneu **Afegeix una condició**.

1. Seleccioneu **Fet** per desar la regla.

### <a name="add-rules-to-a-match-pair"></a>Afegir regles a una parella de coincidència

Les regles de coincidència representen conjunts de condicions. Per fer coincidir entitats per condicions basades en diversos atributs, afegiu més regles.

1.  Aneu a **Dades** > **Unifica** > **Coincidència** i seleccioneu **Afegeix regla** a l'entitat a la qual voleu afegir regles.

2. Seguiu els passos de [Definir regles per a les parelles de coincidència](#define-rules-for-match-pairs).

> [!NOTE]
> L'ordre de les regles és important. L'algoritme coincident intenta trobar una coincidència amb la primera regla i continua amb la segona regla només si no s'han identificat coincidències amb la primera regla.

### <a name="change-the-entity-order-in-match-rules"></a>Canviar l'ordre de les entitats a les regles de coincidència

Podeu reordenar les entitats de les regles de concordança per canviar l'ordre en què es processen. Les regles que entrin en conflicte a causa d'una comanda canviada se suprimiran. Cal tornar a crear les regles suprimides amb una configuració actualitzada.

1. Aneu a **Dades** > **Unifica** > **Coincidències** i seleccioneu **Edita**.

1. A la subfinestra **Edita la regla**, seleccioneu el control **Desplaça amunt/avall** o arrossegueu i deixeu anar les entitats per canviar l'ordre.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opcions per canviar en què es processen les entitats d'ordre a la fase de coincidència.":::

1. Seleccioneu **Fet** per desar la regla.

## <a name="define-deduplication-on-a-match-entity"></a>Definir la desduplicació en una entitat de coincidència

A banda de les [regles de coincidència entre entitats](#define-rules-for-match-pairs), també podeu especificar regles de desduplicació. La *desduplicació* és un altre procés per cercar registres coincidents. Identifica els registres duplicats i els combina en un sol registre. Els registres d'origen s'enllacen al registre combinat amb ID alternatius.

Els registres deduplicats s'utilitzen en el procés de coincidència entre entitats. La deduplicació es produeix en entitats individuals i es pot configurar per a cada entitat utilitzada en parelles de coincidències.

No és obligatori especificar regles de desduplicació. Si no es configura cap regla d'aquest tipus, s'aplicaran les regles definides pel sistema. Combinen tots els registres en un únic registre abans de passar les dades de l'entitat a la coincidència entre entitats per millorar el rendiment.

### <a name="add-deduplication-rules"></a>Afegir regles de desduplicació

1. Aneu a **Dades** > **Unifica** > **Coincidència**.

1. A la **secció Detalls** dels registres deduplicats, seleccioneu **Defineix les entitats**. En el cas que les regles de desduplicació ja estiguin creades, seleccioneu **Edita**.

1. A la subfinestra **Combina les preferències**, trieu les entitats a les quals voleu executar la desduplicació.

   1. Especifiqueu com es combinaran els registres duplicats i trieu una de les tres opcions:
      - **Més emplenat**: identifica el registre amb els atributs més emplenats com el registre guanyador. És l'opció de combinació per defecte.
      - **Més recent**: identifica el registre més recent com el registre guanyador. Requereix una data o un camp numèric per definir la qualitat de recent.
      - **Menys recent**: identifica el registre menys recent com el registre guanyador. Requereix una data o un camp numèric per definir la qualitat de recent.

   1. Opcionalment, per definir regles de deduplicació sobre atributs individuals d'una entitat, seleccioneu **Avançat**. Per exemple, podeu triar mantenir el correu electrònic més recent i l'adreça més completa de diferents registres. Expandiu l'entitat per veure tots els seus atributs i definir quina opció s'utilitzarà per a atributs individuals. Si trieu una opció basada en la recència, també heu d'especificar un camp data/hora que defineixi la recència. 
 
      > [!div class="mx-imgBorder"]
      > ![Pas 1 de les regles de desduplicació.](media/match-selfconflation.png "Pas 1 de les regles de desduplicació")

   1. Seleccioneu **Fet** per aplicar les preferències de combinació per a la deduplicació.
 
1. Un cop seleccionades les entitats i definida la seva preferència de combinació, seleccioneu **Afegeix una regla** per definir les regles de desduplicació en el nivell d'entitat.
   - **Seleccioneu un camp** mostra tots els camps disponibles de l'entitat. Trieu el camp on voleu comprovar si hi ha duplicats. Trieu els camps que probablement siguin únics per a cada client. Per exemple, una adreça electrònica o la combinació de nom, ciutat i número de telèfon.
   - Especifiqueu la configuració de normalització i precisió.
   - Definiu més condicions seleccionant **Afegeix una condició**.
 
   > [!div class="mx-imgBorder"]
   > ![Pas 2 de les regles de desduplicació.](media/match-selfconflation-rules.png "Pas 2 de les regles de desduplicació")

  Podeu crear diverses regles de desduplicació per a una mateixa entitat. 

1. En executar ara el procés de coincidència, els registres s'agruparan segons les condicions definides a la regles de desduplicació. Un cop agrupats els registres, s'aplicarà la norma de combinació per identificar el registre guanyador.

1. A continuació, aquest registre guanyador es passa a la coincidència entre entitats i els registres no guanyadors (per exemple, els ID alternatius) per millorar la qualitat de les coincidències.

1. Les regles de coincidència personalitzades definides sobreescriuen les regles de desduplicació. Si una regla de desduplicació identifica registres coincidents i s'ha definit una regla de coincidència personalitzada per no fer coincidir mai aquests registres, aquests dos registres no es faran coincidir.

1. Després [d'executar el procés](#run-the-match-process) de coincidència, veureu les estadístiques de deduplicació a les peces de mètriques clau.

### <a name="deduplication-output-as-an-entity"></a>Sortida de la desduplicació com a entitat

El procés de desduplicació crea una entitat nova per a cada entitat de les parelles de coincidència per identificar els registres desduplicats. Aquestes entitats es poden trobar amb **ConflationMatchPairs:CustomerInsights** a la secció **Sistema** de la pàgina **Entitats**, amb el nom **Deduplication_DataSource_Entity**.

Una entitat de sortida de desduplicació conté la informació següent:
- ID / Claus
  - Camp de clau principal i el seu camp d'ID alternatius. El camp d'ID alternatius consisteix en tots els ID alternatius identificats per a un registre.
  - El camp Deduplication_GroupId mostra el grup o clúster identificat dins d'una entitat que agrupa tots els registres semblants en funció dels camps de desduplicació especificats. S'utilitza per al processament del sistema. Si no hi ha regles de desduplicació manuals especificades i s'apliquen regles de desduplicació definides pel sistema, potser no trobareu aquest camp a l'entitat de sortida de desduplicació.
  - Deduplication_WinnerId: aquest camp conté l'ID guanyador dels grups o clústers identificats. Si Deduplication_WinnerId és el mateix que el valor de la clau principal d'un registre, significa que el registre és el registre guanyador.
- Camps que s'utilitzen per definir les regles de desduplicació.
- Els camps Regla i Puntuació per denotar quines de les regles de desduplicació s'apliquen i la puntuació retornada per l'algorisme de coincidència.
 
## <a name="include-enriched-entities-preview"></a>Inclou entitats enriquides (Visualització prèvia)

Si heu enriquit entitats al nivell font de dades, seleccioneu-les abans d'executar el procés de coincidència. Les entitats enriquides poden millorar els resultats de la unificació. Per obtenir més informació, vegeu [Enriquiment per a fonts](data-sources-enrichment.md) de dades. 

L'entitat enriquida conté els camps de font de dades originals i els camps enriquits. Per tant, si decidiu treballar amb l'entitat enriquida, la configuració existent no es veurà afectada. Tanmateix, és possible que hàgiu d'actualitzar les regles de concordança per utilitzar els camps enriquits.

1. Aneu a **DataUnifyMatch** > **·** > **i** seleccioneu **Utilitza entitats** enriquides a la part superior de la pàgina.

1. A la **subfinestra** Utilitza les entitats enriquides, trieu una o més entitats enriquides.

1. Seleccioneu **Fet**. Allà on s'utilitza l'entitat d'origen (com ara l'ordre de concordança o les regles), es canvia automàticament a l'entitat enriquida.
  
## <a name="run-the-match-process"></a>Executar el procés de coincidència

Un cop configurades les regles de coincidència, incloses les regles de coincidència entre entitats i les de desduplicació, podreu executar el procés de coincidència. 

Aneu a **Dades** > **Unifica** > **Coincidència** i seleccioneu **Executa** per iniciar el procés. L'algoritme coincident triga una estona en completar-se i no podeu canviar la configuració fins que es completi. Per fer-hi canvis, cancel·leu l'execució. Seleccioneu l'estat de la feina i seleccioneu **Cancel·la la feina** a la subfinestra **Detalls del progrés**.

Trobareu el resultat d'una execució correcta, l'entitat del perfil de client unificada, a la pàgina **Entitats**. L'entitat de client unificada s'anomena **Clients** i és a la secció **Perfils**. La primera execució de coincidències correcta crea l'entitat *Client* unificada. Totes les execucions de coincidència posteriors amplien aquesta entitat.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Revisar i validar les coincidències

Aneu a **Dades** > **Unifica** > **Coincidència** per avaluar la qualitat de les parelles de coincidència i refinar-les si cal.

Les peces de la part superior de la pàgina mostren mètriques clau que resumeixen el nombre de registres i duplicats coincidents.

:::image type="content" source="media/match-KPIs.png" alt-text="Captura de pantalla retallada de les mètriques clau de la pàgina Coincidència amb nombres i detalls.":::

- A **Registres d'origen únics** es mostra el nombre de registres d'origen individuals que s'han processat a la darrera execució de coincidència.
- A **Registres coincidents i no coincidents** es ressalta el nombre de registres únics que queden després de processar les regles de coincidència.
- A **Només registres coincidents** es mostra el nombre de coincidències en totes les parelles de coincidència.

Podeu avaluar els resultats de cada parella de coincidència i les seves regles a la taula **Detalls dels registres coincidents**. Compareu el nombre de registres que provenen d'una parella de coincidència amb el percentatge de registres amb coincidències correctes.

Reviseu les regles d'una parella de coincidència per veure el percentatge de registres amb coincidència correcta en el nivell de la regla. Seleccioneu els punts suspensius (...) i, a continuació, seleccioneu **Visualització prèvia de coincidència** per visualitzar tots aquests registres en el nivell de regla. Us recomanem que feu un cop d'ull a alguns registres per validar si s'han aparellat correctament.

Proveu diferents llindars de precisió a les condicions per trobar el valor òptim.

  1. Seleccioneu els punts suspensius (...) per a la regla amb la qual voleu experimentar i seleccioneu **Edita**.

  2. Canvieu els valors de precisió a les condicions que voleu revisar.

  3. Seleccioneu **Visualització prèvia** per veure el nombre de registres coincidents i no coincidents per a la condició seleccionada.

## <a name="manage-match-rules"></a>Administra les regles de coincidència

Podeu reconfigurar i ajustar la majoria dels paràmetres de coincidència.

:::image type="content" source="media/match-rules-management.png" alt-text="Captura de pantalla del menú desplegable amb les opcions de les regles de coincidència.":::

- **Canvieu l'ordre de les regles** si heu definit diverses regles. Per reordenar les regles de coincidència, seleccioneu les opcions **Desplaça amunt** i **Desplaça avall** o arrossegueu-les i deixeu-les anar.

- **Canvieu les condicions de les regles**, seleccionant **Edita** i triant camps diferents.

- **Desactiveu una regla** per conservar una regla de coincidència, excloent-la del procés de coincidència.

- **Dupliqueu les regles** si heu definit una regla de coincidència i voleu crear una regla semblant amb modificacions, seleccioneu **Duplicat**.

- **Suprimiu una regla** seleccionant el símbol **Suprimeix**.

## <a name="advanced-options"></a>Opcions avançades

### <a name="add-exceptions-to-a-rule"></a>Afegir excepcions a una regla

En la majoria dels casos, la coincidència de l'entitat condueix a perfils d'usuari únics amb dades consolidades. Per abordar dinàmicament casos rars de falsos positius i falsos negatius, podeu definir excepcions per a una regla de concordança. Les excepcions s'apliquen després de processar les regles del partit i evitar la coincidència de tots els registres, que compleixen els criteris d'excepció.

Per exemple, si la regla del partit combina cognom, ciutat i data de naixement, el sistema identificaria bessons amb la mateixa cognom que viuen a la mateixa ciutat que el mateix perfil. Podeu especificar una excepció que no coincideixi amb els perfils si la nom de les entitats que combineu no és la mateixa.

1. Aneu a **Dades** > **Unifica** > **Coincidència** i seleccioneu **Edició** a la regla a la qual voleu afegir condicions.

1. A la **subfinestra Edita**, seleccioneu **Afegeix una excepció**.

1. Especifiqueu els criteris d'excepció. 

1. Seleccioneu **Fet** per desar la regla.

### <a name="specify-custom-match-conditions"></a>Especificar condicions de coincidència personalitzades

Podeu especificar condicions que sobreescriuen la lògica de concordança per defecte. Hi ha quatre opcions disponibles: 

|Opció  |Descripció |Exemple  |
|---------|---------|---------|
|Coincidència     | Defineix els valors que sempre coincideixen.         |  Sempre coincideixen amb *Mike* i *MikeR*.       |
|No coincidència     | Defineix valors que mai coincideixen.        | Mai coincideixi amb *John* i *Jonathan*.        |
|Omissió personalitzada     | Defineix valors que el sistema sempre ha d'ignorar en la fase de coincidència. |  Ignora els valors *11111* i *Desconegut* durant el partit.        |
|Assignació d'àlies    | Definir valors que el sistema hauria de considerar com el mateix valor.         | Considereu que *Joe* és igual a *Josep*.        |

1. Aneu a **Dades** > **Unifica** > **Coincidència** i seleccioneu **Coincidència personalitzada** a la secció **Detalls dels registres coincidents**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Captura de pantalla de la secció de regles de coincidència amb el control de Coincidència personalitzada ressaltat.":::

1. A la **subfinestra Personalitzada**, aneu a la **pestanya Registres**.

1. Trieu l'opció de coincidència personalitzada del **menú desplegable Tipus** personalitzat i seleccioneu **Baixa la plantilla**. Necessiteu una plantilla separada per a cada opció de partit.

1. Obriu el fitxer de plantilla baixat i empleneu els detalls. La plantilla conté camps per especificar l'entitat i els valors de clau principal de l'entitat que s'utilitzaran a la coincidència personalitzada. Per exemple, si voleu que la clau principal *12345* de l'entitat *Vendes* coincideixi sempre amb la clau principal *34567* de l'entitat *Contacte*, empleneu la plantilla:
    - Entity1: Vendes
    - Entity1Key: 12345
    - Entity2: Contacte
    - Entity2Key: 34567

   El mateix fitxer de plantilla pot especificar els registres de coincidència personalitzats des de diverses entitats.
   
   Si voleu especificar la coincidència personalitzada per a la desduplicació en una entitat, proporcioneu la mateixa entitat com a Entitat1 i Entitat2 i definiu els diferents valors de clau principal.

1. Després d'afegir totes les substitucions, deseu el fitxer de plantilla.

1. Aneu a **Dades** > **Fonts de dades** i ingeriu els fitxers de plantilla com a entitats noves.

1. Després de carregar els fitxers i que les entitats estiguin disponibles, torneu a seleccionar l'opció **Coincidència personalitzada**. Veureu opcions per especificar les entitats que voleu incloure. Seleccioneu les entitats necessàries al menú desplegable i seleccioneu **Fet**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de pantalla del diàleg per triar les substitucions per a un escenari de coincidència personalitzada.":::

1. L'aplicació de la coincidència personalitzada depèn de l'opció de concordança que vulgueu utilitzar. 

   - Per a **Sempre coincideixi** o **no coincideixi** mai, aneu al següent pas.
   - Per a **l'assignació** personalitzada de bypass **o** àlies, seleccioneu **Edita** en una regla de concordança existent o creeu una regla nova. Al menú desplegable Normalitzacions, trieu l'opció d'assignació **de** bypass **personalitzat o** àlies i seleccioneu **Fet**.

1. Seleccioneu **Desa** a la pàgina **Coincidència** per aplicar la configuració de coincidència personalitzada.

1. Seleccioneu **Executa** a la pàgina **Coincidència** per iniciar el procés de coincidència. La configuració de coincidència personalitzada substitueix altres regles de coincidència especificades.

#### <a name="known-issues"></a>Problemes coneguts

- L'autocomunió no mostra les dades normalitzades en les entitats deduplicació. No obstant això, s'aplica la normalització internament durant la deduplicació. És per disseny per a totes les normalitzacions. 
- Si la configuració del tipus semàntic s'elimina a la **fase Mapa** quan una regla de concordança utilitza l'assignació d'àlies o el bypass personalitzat, no s'aplicarà la normalització. Només passa si esborreu el tipus semàntic després de configurar la normalització a la regla de coincidència perquè el tipus semàntic serà desconegut.


## <a name="next-step"></a>Pas següent

Després de completar el procés de coincidència per a almenys un parell de partits, continueu al [**pas Fusiona**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
