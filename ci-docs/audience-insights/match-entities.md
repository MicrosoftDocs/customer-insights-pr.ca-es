---
title: Fer coincidir entitats per a la unificació de dades
description: Feu coincidir entitats per crear perfils de client unificats.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50b11e7d6f62d7a25eb25a0f2b1c4ad7d859def1
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306016"
---
# <a name="match-entities"></a>Fer coincidir entitats

La fase de coincidència especifica com combinar els conjunts de dades en un conjunt de dades de perfil del client unificat. Un cop completat el [pas de l'assignació](map-entities.md) al procés d'unificació de dades, ja esteu a punt per aparellar-ho amb les entitats. La fase de coincidència requereix com a mínim dues entitats assignades.

La pàgina de coincidències consta de tres seccions: 
- Mètriques clau que resumeixen el nombre de registres coincidents
- Fer coincidir l'ordre i les regles per a la coincidència entre entitats
- Regles per desduplicació d'entitats coincidents

## <a name="specify-the-match-order"></a>Especificar l'ordre de coincidència

Aneu a **Dades** > **Unificació** > **Coincidència** i seleccioneu **Defineix l'ordre** per iniciar la fase de coincidència.

Cada coincidència unifica dues o més entitats en una única entitat consolidada. Al mateix temps, conserva els registres de client únics. Per exemple, hem seleccionat dues entitats: **eCommerce:eCommerceContacts** com a entitat principal i **LoyaltyScheme:loyCustomers** a segona entitat. L'ordre de les entitats especifica en quin ordre el sistema intentarà trobar coincidències en els registres.

:::image type="content" source="media/match-page.png" alt-text="Captura de pantalla de la pàgina Coincidències a l'àrea Unifica del procés d'unificació de dades.":::
  
L'entitat principal *eCommerce:eCommerceContacts* coincideix amb l'entitat següent *LoyaltyScheme:loyCustomers*. El conjunt de dades que resulta del primer pas de coincidència es fa coincidir amb l'entitat següent si teniu més de dues entitats.

> [!IMPORTANT]
> L'entitat que trieu com a entitat principal servirà com a base per al vostre conjunt de dades de perfils unificat. Les entitats addicionals que s'hagin seleccionat durant la fase de coincidència s'afegiran a aquesta entitat. Això no vol dir que l'entitat unificada inclogui *totes* les dades incloses en aquesta entitat.
>
> Hi ha dues consideracions que poden ajudar-vos a triar la jerarquia de les entitats:
>
> - Trieu l'entitat amb les dades de perfil més completes i fiables sobre els clients com a entitat principal.
> - Trieu l'entitat que tingui diversos atributs comuns amb altres entitats (per exemple, nom, número de telèfon o adreça electrònica) com a entitat principal.

Després d'especificar l'ordre de coincidència, veureu les parelles de coincidència definides a la secció **Detalls dels registres coincidents** de **Dades** > **Unifica** > **Coincidència**. Les mètriques clau seran buides fins que es completi el procés de coincidència.

## <a name="define-rules-for-match-pairs"></a>Definir regles per a les parelles de coincidència

Les regles de coincidència especifiquen la lògica mitjançant la qual es farà coincidir un parell d'entitats específic.

L'advertiment **Necessita regles** al costat d'un nom d'entitat suggereix que no hi ha cap regla de coincidència definida per a una parella de coincidència. 

:::image type="content" source="media/match-rule-add.png" alt-text="Captura de pantalla de la secció Detalls del registre coincident amb el control per afegir regles ressaltat.":::

1. Seleccioneu **Afegeix regles** a sota d'una entitat a la secció **Detalls dels registres coincidents** per definir regles de coincidència.

1. A la subfinestra **Crea una regla**, configureu les condicions de la regla.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Captura de pantalla d'una regla de coincidència oberta amb condicions afegides.":::

   - **Entitat o camp (primera fila)**: trieu una entitat relacionada i un atribut per especificar una propietat de registre que probablement sigui única per a un client. Per exemple, un número de telèfon o una adreça electrònica. Eviteu la coincidència per atributs de tipus d'activitat. Per exemple, és probable que un ID de compra no trobi cap coincidència en altres tipus de registres.

   - **Entitat/camp (segona fila)**: trieu un atribut que es relacioni amb l'atribut de l'entitat especificada a la primera fila.

   - **Normalitza**: seleccioneu les opcions de normalització següents per als atributs seleccionats. 
     - Espai en blanc: suprimeix tots els espais. *Hola   món* es converteix en *Holamón*.
     - Símbols: suprimeix tots els símbols i caràcters especials. *Cap+espatlla* es converteix en *Capespatlla*.
     - Text en minúscula: converteix tots els caràcters a minúscules. *TOT MAJÚSCULES i títols* passa a ser *tot majúscules i títols*.
     - Unicode a ASCII: converteix la notació unicode en caràcters ASCII. */u00B2* es converteix en *2*.
     - Numèrics: converteix altres sistemes numèrics, com ara els números romans, en números àrabs. *VIII* es converteix en *8*.
     - Tipus semàntics: estandarditza els noms, els títols, els números de telèfon, les adreces, etc. 

   - **Precisió**: definiu el nivell de precisió que voleu aplicar per a aquesta condició. 
     - **Bàsica**: trieu entre *Baixa*, *Mitjana*, *Alta* i *Exacta*. Seleccioneu **Exacta** per tal de fer coincidir només els registres que coincideixen en un 100 per cent. Seleccioneu un dels altres nivells perquè fer coincidir registres que no són 100 per cent idèntics.
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

Les regles de coincidència representen conjunts de condicions. Per fer coincidir les entitats per condicions en funció de diversos atributs, afegiu més regles.

1.  Aneu a **Dades** > **Unifica** > **Coincidència** i seleccioneu **Afegeix regla** a l'entitat a la qual voleu afegir regles.

2. Seguiu els passos de [Definir regles per a les parelles de coincidència](#define-rules-for-match-pairs).

> [!NOTE]
> L'ordre de les regles és important. L'algoritme coincident intenta trobar una coincidència amb la primera regla i continua amb la segona regla només si no s'han identificat coincidències amb la primera regla.

### <a name="change-the-entity-order-in-match-rules"></a>Canviar l'ordre de les entitats a les regles de coincidència

Podeu reordenar les entitats de les regles de coincidència per canviar l'ordre en què es processen. Les regles que entrin en conflicte a causa d'una comanda canviada se suprimiran. Cal tornar a crear les regles suprimides amb una configuració actualitzada.

1. Aneu a **Dades** > **Unifica** > **Coincidències** i seleccioneu **Edita**.

1. A la subfinestra **Edita la regla**, seleccioneu el control **Desplaça amunt/avall** o arrossegueu i deixeu anar les entitats per canviar l'ordre.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opcions per canviar en què es processen les entitats d'ordre a la fase de coincidència.":::

1. Seleccioneu **Fet** per desar la regla.

## <a name="define-deduplication-on-a-match-entity"></a>Definir la desduplicació en una entitat de coincidència

A banda de les [regles de coincidència entre entitats](#define-rules-for-match-pairs), també podeu especificar regles de desduplicació. La *desduplicació* és un altre procés per cercar registres coincidents. Identifica els registres duplicats i els combina en un sol registre. Els registres d'origen s'enllacen al registre combinat amb ID alternatius.

Els registres desduplicats s'utilitzaran al procés de coincidència entre entitats. La desduplicació es produeix en entitats individuals i es pot configurar cada entitat que s'utilitza en parelles de coincidència.

No és obligatori especificar regles de desduplicació. Si no es configura cap regla d'aquest tipus, s'aplicaran les regles definides pel sistema. Combinen tots els registres en un únic registre abans de passar les dades de l'entitat a la coincidència entre entitats per millorar el rendiment.

### <a name="add-deduplication-rules"></a>Afegir regles de desduplicació

1. Aneu a **Dades** > **Unifica** > **Coincidència**.

1. A la secció **Duplicats combinats**, seleccioneu **Defineix entitats**. En el cas que les regles de desduplicació ja estiguin creades, seleccioneu **Edita**.

1. A la subfinestra **Combina les preferències**, trieu les entitats a les quals voleu executar la desduplicació.

1. Especifiqueu com es combinaran els registres duplicats i trieu una de les tres opcions:
   - **Més emplenat**: identifica el registre amb els atributs més emplenats com el registre guanyador. És l'opció de combinació per defecte.
   - **Més recent**: identifica el registre més recent com el registre guanyador. Requereix una data o un camp numèric per definir la qualitat de recent.
   - **Menys recent**: identifica el registre menys recent com el registre guanyador. Requereix una data o un camp numèric per definir la qualitat de recent.
 
   > [!div class="mx-imgBorder"]
   > ![Pas 1 de les regles de desduplicació](media/match-selfconflation.png "Pas 1 de les regles de desduplicació")
 
1. Un cop seleccionades les entitats i definida la seva preferència de combinació, seleccioneu **Afegeix una regla** per definir les regles de desduplicació en el nivell d'entitat.
   - **Seleccioneu un camp** mostra tots els camps disponibles de l'entitat. Trieu el camp on voleu comprovar si hi ha duplicats. Trieu els camps que probablement siguin únics per a cada client. Per exemple, una adreça electrònica o la combinació de nom, ciutat i número de telèfon.
   - Especifiqueu la configuració de normalització i precisió.
   - Definiu més condicions seleccionant **Afegeix una condició**.
 
   > [!div class="mx-imgBorder"]
   > ![Pas 2 de les regles de desduplicació](media/match-selfconflation-rules.png "Pas 2 de les regles de desduplicació")

  Podeu crear diverses regles de desduplicació per a una mateixa entitat. 

1. En executar ara el procés de coincidència, els registres s'agruparan segons les condicions definides a la regles de desduplicació. Un cop agrupats els registres, s'aplicarà la norma de combinació per identificar el registre guanyador.

1. A continuació, aquest registre guanyador es passa a la coincidència entre entitats i els registres no guanyadors (per exemple, els ID alternatius) per millorar la qualitat de les coincidències.

1. Les regles de coincidència personalitzades definides sobreescriuen les regles de desduplicació. Si una regla de desduplicació identifica registres coincidents i s'ha definit una regla de coincidència personalitzada per no fer coincidir mai aquests registres, aquests dos registres no es faran coincidir.

1. Un cop [executat el procés de coincidència](#run-the-match-process), es mostraran les estadístiques de desduplicació a les peces de mètriques clau.

### <a name="deduplication-output-as-an-entity"></a>Sortida de la desduplicació com a entitat

El procés de desduplicació crea una entitat nova per a cada entitat de les parelles de coincidència per identificar els registres desduplicats. Aquestes entitats es poden trobar amb **ConflationMatchPairs:CustomerInsights** a la secció **Sistema** de la pàgina **Entitats**, amb el nom **Deduplication_DataSource_Entity**.

Una entitat de sortida de desduplicació conté la informació següent:
- ID / Claus
  - Camp de clau principal i el seu camp d'ID alternatius. El camp d'ID alternatius consisteix en tots els ID alternatius identificats per a un registre.
  - El camp Deduplication_GroupId mostra el grup o clúster identificat dins d'una entitat que agrupa tots els registres semblants en funció dels camps de desduplicació especificats. S'utilitza per al processament del sistema. Si no hi ha regles de desduplicació manuals especificades i s'apliquen regles de desduplicació definides pel sistema, potser no trobareu aquest camp a l'entitat de sortida de desduplicació.
  - Deduplication_WinnerId: aquest camp conté l'ID guanyador dels grups o clústers identificats. Si Deduplication_WinnerId és el mateix que el valor de la clau principal d'un registre, significa que el registre és el registre guanyador.
- Camps que s'utilitzen per definir les regles de desduplicació.
- Els camps Regla i Puntuació per denotar quines de les regles de desduplicació s'apliquen i la puntuació retornada per l'algorisme de coincidència.
   
## <a name="run-the-match-process"></a>Executar el procés de coincidència

Un cop configurades les regles de coincidència, incloses les regles de coincidència entre entitats i les de desduplicació, podreu executar el procés de coincidència. 

Aneu a **Dades** > **Unifica** > **Coincidència** i seleccioneu **Executa** per iniciar el procés. L'algoritme coincident triga una estona en completar-se i no podeu canviar la configuració fins que es completi. Per fer-hi canvis, cancel·leu l'execució. Seleccioneu l'estat de la feina i seleccioneu **Cancel·la la feina** a la subfinestra **Detalls del progrés**.

Trobareu el resultat d'una execució correcta, l'entitat del perfil de client unificada, a la pàgina **Entitats**. L'entitat de client unificada s'anomena **Clients** i és a la secció **Perfils**. La primera execució de coincidències correcta crea l'entitat *Client* unificada. Totes les execucions de coincidència posteriors amplien aquesta entitat.

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.

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

## <a name="specify-custom-match-conditions"></a>Especificar condicions de coincidència personalitzades

Podeu especificar condicions amb les que certs registres han de coincidir sempre o mai. Aquestes regles es poden carregar per substituir el procés de coincidència estàndard. Per exemple, si als registres hi ha en Joan Duran I i en Joan Duran II, el sistema podria trobar-los com a coincidències d'una mateixa persona. Les regles de coincidència personalitzades us permeten especificar que els seus perfils fan referència a diferents persones. 

1. Aneu a **Dades** > **Unifica** > **Coincidència** i seleccioneu **Coincidència personalitzada** a la secció **Detalls dels registres coincidents**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Captura de pantalla de la secció de regles de coincidència amb el control de Coincidència personalitzada ressaltat.":::

1. Si no teniu definides regles de coincidència personalitzades, veureu una nova subfinestra de **Coincidència personalitzada** amb més detalls.

1. Seleccioneu **Emplena la plantilla** per obtenir un fitxer de plantilla que pugui especificar els registres de les entitats que han de coincidir sempre o no coincidir mai. Haureu d'emplenar per separat els registres "coincideix sempre" i "no coincideixis mai" en dos fitxers diferents.

1. La plantilla conté camps per especificar l'entitat i els valors de clau principal de l'entitat que s'utilitzaran a la coincidència personalitzada. Per exemple, si voleu que la clau principal *12345* de l'entitat *Vendes* coincideixi sempre amb la clau principal *34567* de l'entitat *Contacte*, empleneu la plantilla:
    - Entity1: Vendes
    - Entity1Key: 12345
    - Entity2: Contacte
    - Entity2Key: 34567

   El mateix fitxer de plantilla pot especificar els registres de coincidència personalitzats des de diverses entitats.
   
   Si voleu especificar la coincidència personalitzada per a la desduplicació en una entitat, proporcioneu la mateixa entitat com a Entitat1 i Entitat2 i definiu els diferents valors de clau principal.

1. Després d'afegir totes les substitucions que voleu aplicar, deseu el fitxer de la plantilla.

1. Aneu a **Dades** > **Fonts de dades** i ingeriu els fitxers de plantilla com a entitats noves. Un cop ingerits, podeu utilitzar-los per especificar la configuració de la coincidència.

1. Després de carregar els fitxers i que les entitats estiguin disponibles, torneu a seleccionar l'opció **Coincidència personalitzada**. Veureu opcions per especificar les entitats que voleu incloure. Seleccioneu les entitats necessàries al menú desplegable.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de pantalla del diàleg per triar les substitucions per a un escenari de coincidència personalitzada.":::

1. Seleccioneu les entitats que voleu utilitzar per a **Coincideix sempre** i **No coincideixis mai** i seleccioneu **Fet**.

1. Seleccioneu **Desa** a la pàgina **Coincidència** per aplicar la configuració de coincidència personalitzada.

1. Seleccioneu **Executa** a la pàgina **Coincidència** per iniciar el procés de coincidència. La configuració de coincidència personalitzada substitueix altres regles de coincidència especificades.

> [!TIP]
> Aneu a **Dades** > **Entitats** i reviseu l'entitat **ConflationMatchPair** per confirmar que s'apliquen les substitucions.

## <a name="next-step"></a>Pas següent

Després de completar el procés de coincidència com a mínim per a un parell de coincidència, podeu resoldre les contradiccions possibles de les dades anant al tema [**Combinació**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
