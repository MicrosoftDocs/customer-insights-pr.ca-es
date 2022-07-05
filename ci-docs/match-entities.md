---
title: Condicions de concordança per a la unificació de dades
description: Feu coincidir entitats per crear perfils de client unificats.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: 770a18f3a7471714a7e044ae034da168a2601010
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082402"
---
# <a name="match-conditions-for-data-unification"></a>Condicions de concordança per a la unificació de dades

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Aquest pas en la unificació defineix l'ordre de coincidència i les regles per a la coincidència entre entitats. Aquest pas requereix com a mínim dues entitats.

> [!NOTE]
> Un cop hàgiu creat les condicions de concordança i seleccioneu **Endavant**, no podeu suprimir una entitat o un atribut seleccionats. Si cal, seleccioneu **Endas per** revisar les entitats i els atributs seleccionats abans de continuar.

## <a name="include-enriched-entities-preview"></a>Inclou entitats enriquides (previsualització)

Si heu enriquit entitats al nivell font de dades per ajudar a millorar els resultats de la unificació, seleccioneu-les. Per obtenir més informació, vegeu [Enriquiment per a fonts de dades](data-sources-enrichment.md). Si heu seleccionat entitats enriquides a la **pàgina Registres duplicats**, no cal que les torneu a seleccionar.

1. A la **pàgina Condicions coincidents** **, seleccioneu** Utilitza entitats enriquides a la part superior de la pàgina.

1. A la **subfinestra** Utilitza les entitats enriquides, trieu una o més entitats enriquides.

1. Seleccioneu **Fet**.

## <a name="specify-the-match-order"></a>Especificar l'ordre de coincidència

Cada coincidència unifica dues o més entitats en una única entitat consolidada. Al mateix temps, conserva els registres de client únics. L'ordre de coincidència indica l'ordre en què el sistema intenta fer coincidir els registres.

> [!IMPORTANT]
> La primera entitat de la llista s'anomena entitat principal. L'entitat principal serveix de base per al conjunt de dades de perfils unificats. S'afegiran a aquesta entitat entitats addicionals seleccionades.
>
> Consideracions importants:
>
> - Trieu l'entitat amb les dades de perfil més completes i fiables sobre els vostres clients com a entitat principal.
> - Trieu l'entitat que té diversos atributs en comú amb altres entitats (per exemple, nom, número de telèfon o adreça electrònica) com a entitat principal.

1. A la **pàgina Condicions** coincidents, utilitzeu les fletxes mou amunt i avall per moure les entitats en l'ordre que vulgueu o arrossegueu-les i deixeu-les anar. Per exemple, seleccioneu **Contactes:comerç electrònic** com a entitat principal i **CustomerLoyalty:Loyalty** com a segona entitat.

1. Per tenir tots els registres de l'entitat com a client únic independentment de si es troba una coincidència, seleccioneu **Inclou tots els registres**. Tots els registres d'aquesta entitat que no coincideixin amb els registres de cap altra entitat s'inclouen al perfil unificat. Els registres que no tenen partit s'anomenen singletons.
  
L'entitat *principal Contactes:comerç electrònic* coincideix amb la següent entitat *CustomerLoyalty:Loyalty*. El conjunt de dades que resulta del primer pas de coincidència coincideix amb l'entitat següent si teniu més de dues entitats.

:::image type="content" source="media/m3_match.png" alt-text="Captura de pantalla de l'ordre de coincidència seleccionat per a les entitats." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definir regles per a les parelles de coincidència

Les regles de coincidència especifiquen la lògica mitjançant la qual es farà coincidir un parell d'entitats específic. Una regla consisteix en una o més condicions.

L'advertiment que hi ha al costat d'un nom d'entitat significa que no hi ha cap regla de concordança definida per a un parell de coincidències.

1. Seleccioneu **Afegeix una regla** per a un parell d'entitats per definir regles de concordança.

1. A la **subfinestra Afegeix regles**, configureu les condicions de la regla.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Captura de pantalla de la subfinestra Afegeix regles.":::

   - **Seleccioneu Entitat/Camp (primera fila)**: trieu una entitat relacionada i un atribut per especificar una propietat de registre que sigui probable que sigui única per a un client. Per exemple, un número de telèfon o una adreça electrònica. Eviteu la coincidència per atributs de tipus d'activitat. Per exemple, és probable que un ID de compra no trobi cap coincidència en altres tipus de registres.

   - **Seleccioneu Entitat/Camp (segona fila)**: Trieu un atribut relacionat amb l'atribut de l'entitat especificada a la primera fila.

   - **Normalitza**: seleccioneu les opcions de normalització següents per als atributs seleccionats.
     - **Numerals**: converteix altres sistemes numèrics, com ara els nombres romans, en nombres aràbics. *VIII* es converteix en *8*.
     - **Símbols**: elimina tots els símbols i caràcters especials. *Cap+espatlla* es converteix en *Capespatlla*.
     - **Text en minúscules**: converteix tot el caràcter en minúscules. *TOT MAJÚSCULES i títols* passa a ser *tot majúscules i títols*.
     - **Tipus (telèfon, nom, adreça, organització):** estandarditza els noms, els títols, els números de telèfon, les adreces i les organitzacions.
     - **Unicode a ASCII**: converteix la notació unicode en caràcters ASCII. */u00B2* es converteix en *2*.
     - **Espais en blanc**: elimina tots els espais. *Hola   món* es converteix en *Holamón*.

   - **Precisió**: definiu el nivell de precisió que voleu aplicar per a aquesta condició.
     - **Bàsic**: Tria entre *Baix (30%)*, *Mitjà (60%)*, *Alt (80%)*, i *Exacte (100%)*. Seleccioneu **Exacte** per coincidir només amb els registres que coincideixin amb el 100%.
     - **Personalitzat**: definiu un percentatge que han de complir els registres. El sistema només trobarà coincidències en els registres que compleixin aquest llindar.

   - **Nom**: Nom de la norma.

1. Per fer coincidir entitats només si els atributs compleixen diverses condicions, seleccioneu **Afegeix** > **una condició** per afegir més condicions a una regla de concordança. Les condicions estan connectades amb un operador AND lògic i, per tant, només s'executen si es compleixen totes les condicions.

1. Opcionalment, tingueu en compte opcions avançades, com [ara excepcions o](#add-exceptions-to-a-rule) condicions [de](#specify-custom-match-conditions) concordança personalitzades.

1. Seleccioneu **Fet** per finalitzar la regla.

1. Opcionalment, [afegiu més regles](#add-rules-to-a-match-pair).

1. Feu clic a **Endavant**.

> [!div class="nextstepaction"]
> [Pas següent: Unifica els camps](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Afegir regles a una parella de coincidència

Les regles de coincidència representen conjunts de condicions. Per fer coincidir entitats per condicions basades en diversos atributs, afegiu més regles.

1. Seleccioneu **Afegeix una norma** a l'entitat a la qual voleu afegir regles.

1. Seguiu els passos de [Definir regles per a les parelles de coincidència](#define-rules-for-match-pairs).

> [!NOTE]
> L'ordre de les regles és important. L'algorisme de coincidència intenta fer coincidir un registre de client determinat sobre la base de la vostra primera regla i continua a la segona regla només si no s'identifica cap coincidència amb la primera regla.

## <a name="advanced-options"></a>Opcions avançades

### <a name="add-exceptions-to-a-rule"></a>Afegir excepcions a una regla

En la majoria dels casos, la coincidència de l'entitat condueix a perfils de clients únics amb dades consolidades. Per abordar dinàmicament casos rars de falsos positius i falsos negatius, podeu definir excepcions per a una regla de concordança. Les excepcions s'apliquen després de processar les regles del partit i evitar la coincidència de tots els registres, que compleixen els criteris d'excepció.

Per exemple, si la regla del partit combina cognom, ciutat i data de naixement, el sistema identificaria bessons amb la mateixa cognom que viuen a la mateixa ciutat que el mateix perfil. Podeu especificar una excepció que no coincideixi amb els perfils si la nom de les entitats que combineu no és la mateixa.

1. A la **subfinestra De regles** Edita, seleccioneu **Afegeix** > **una excepció**.

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

1. Seleccioneu **Personalitzar**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="botó Personalitzat":::

1. Trieu el **tipus** Personalitzat i seleccioneu **Baixa la plantilla**. Necessiteu una plantilla separada per a cada opció de partit.

1. Obriu el fitxer de plantilla baixat i empleneu els detalls. La plantilla conté camps per especificar l'entitat i els valors de clau principal de l'entitat que s'utilitzaran a la coincidència personalitzada. Per exemple, si voleu que la clau principal *12345* de l'entitat *Vendes* coincideixi sempre amb la clau principal *34567* de l'entitat *Contacte*, empleneu la plantilla:
    - Entity1: Vendes
    - Entity1Key: 12345
    - Entity2: Contacte
    - Entity2Key: 34567

   El mateix fitxer de plantilla pot especificar els registres de coincidència personalitzats des de diverses entitats.

   Si voleu especificar la coincidència personalitzada per a la desduplicació en una entitat, proporcioneu la mateixa entitat com a Entitat1 i Entitat2 i definiu els diferents valors de clau principal.

1. Després d'afegir totes les substitucions, deseu el fitxer de plantilla.

1. Aneu a **Dades** > **Fonts de dades** i ingeriu els fitxers de plantilla com a entitats noves.

1. Després de penjar els fitxers, torneu a seleccionar l'opció **Personalitzat**. Seleccioneu les entitats necessàries al menú desplegable i seleccioneu **Fet**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de pantalla del diàleg per triar les substitucions per a un escenari de coincidència personalitzada.":::

1. L'aplicació de la coincidència personalitzada depèn de l'opció de concordança que vulgueu utilitzar.

   - Per a **Sempre coincideixi** o **no coincideixi** mai, aneu al següent pas.
   - Per a **l'assignació** de bypass **o** Àlies, seleccioneu **Edita** en una regla de concordança existent o creeu una regla nova. Al menú desplegable Normalitzacions, trieu l'opció d'assignació **de** bypass **personalitzat o** àlies i seleccioneu **Fet**.

1. Seleccioneu **Fet** a la **subfinestra Personalitzada** per aplicar la configuració de concordança personalitzada.

> [!div class="nextstepaction"]
> [Pas següent: Unifica els camps](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
