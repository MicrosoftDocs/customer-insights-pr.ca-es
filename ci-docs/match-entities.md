---
title: Condicions de coincidència per a la unificació de dades
description: Feu coincidir entitats per crear perfils de client unificats.
recommendations: false
ms.date: 10/07/2022
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
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721509"
---
# <a name="match-conditions-for-data-unification"></a>Condicions de coincidència per a la unificació de dades

Aquest pas en la unificació defineix l'ordre dels partits i les regles per a la coincidència entre entitats. Aquest pas requereix almenys dues entitats.

> [!NOTE]
> Un cop hàgiu creat les condicions de concordança i seleccioneu **Següent**, no podreu suprimir cap entitat o atribut seleccionats. Si cal, seleccioneu **Enrere** per revisar les entitats i els atributs seleccionats abans de continuar.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Incloure entitats enriquides (vista prèvia)

Si heu enriquit entitats del nivell font de dades per ajudar a millorar els resultats de la unificació, seleccioneu-les. Per obtenir més informació, vegeu [Enriquiment per a les fonts de dades](data-sources-enrichment.md). Si heu seleccionat entitats enriquides a la **pàgina Duplica els registres**, no cal que les torneu a seleccionar.

1. A la **pàgina Condicions de coincidència**, seleccioneu **Utilitza entitats** enriquides a la part superior de la pàgina.

1. Des del panell **Utilitza entitats** enriquides, trieu una o més entitats enriquides.

1. Seleccioneu **Fet**.

## <a name="specify-the-match-order"></a>Especificar l'ordre de coincidència

Cada coincidència unifica dues o més entitats en una única entitat consolidada. Al mateix temps, conserva els registres de client únics. L'ordre de coincidència indica l'ordre en què el sistema intenta igualar els registres.

> [!IMPORTANT]
> La primera entitat s'anomena entitat principal, que serveix de base per als vostres perfils unificats. A aquesta entitat s'afegiran entitats addicionals seleccionades.
>
> Consideracions importants:
>
> - Trieu l'entitat amb les dades de perfil més completes i fiables sobre els vostres clients com a entitat principal.
> - Trieu l'entitat que té diversos atributs en comú amb altres entitats (per exemple, el nom, el número de telèfon o l'adreça electrònica) com a entitat principal.

1. A la **pàgina Condicions** de coincidència, utilitzeu les fletxes moveu amunt i avall per moure les entitats en l'ordre que vulgueu o arrossegueu-les i deixeu-les anar. Per exemple, seleccioneu **eCommerceDuanes** com a entitat principal i **loyCustomers** com a segona entitat.

1. Per tenir tots els registres de l'entitat com a client únic independentment de si es troba una coincidència, seleccioneu **Inclou tots els registres**. Tots els registres d'aquesta entitat que no coincideixin amb els registres de cap altra entitat s'inclouen al perfil unificat. Els registres que no tenen partit s'anomenen singletons.
  
L'entitat *principal Contactes:eCommerce* coincideix amb la següent entitat *CustomerLoyalty:Loyalty*. El conjunt de dades que resulta del primer pas de coincidència coincideix amb l'entitat següent si teniu més de dues entitats.

:::image type="content" source="media/m3_match.png" alt-text="Captura de pantalla de l'ordre de coincidència seleccionat per a les entitats." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definir regles per a les parelles de coincidència

Les regles de coincidència especifiquen la lògica mitjançant la qual es farà coincidir un parell d'entitats específic. Una regla consisteix en una o més condicions.

L'advertiment que hi ha al costat d'un nom d'entitat significa que no es defineix cap regla de coincidència per a un parell de coincidències.

1. Seleccioneu **Afegeix una regla** per a un parell d'entitats per definir les regles de concordança.

1. A la **subfinestra Afegeix una regla**, configureu les condicions de la regla.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Captura de pantalla d'Afegeix una subfinestra de regles.":::

   - **Seleccioneu Entitat/Camp (primera fila):** trieu una entitat i un atribut que probablement siguin únics per a un client. Per exemple, un número de telèfon o una adreça electrònica. Eviteu la coincidència per atributs de tipus d'activitat. Per exemple, és probable que un ID de compra no trobi cap coincidència en altres tipus de registres.

   - **Seleccioneu Entitat/Camp (segona fila):** trieu un atribut relacionat amb l'atribut de l'entitat especificada a la primera fila.

   - **Normalitza**: seleccioneu les opcions de normalització següents per als atributs seleccionats.
     - **Numerals**: Converteix altres sistemes numèrics, com els nombres romans, a nombres aràbics. *VIII* es converteix en *8*.
     - **Símbols**: elimina tots els símbols i caràcters especials. *Cap+espatlla* es converteix en *Capespatlla*.
     - **Text en minúscula**: converteix tots els caràcters en minúscules. *TOT MAJÚSCULES i títols* passa a ser *tot majúscules i títols*.
     - **Tipus (Telèfon, Nom, Adreça, Organització)**: Estandarditza noms, títols, números de telèfon, adreces i organitzacions.
     - **Unicode a ASCII**: Converteix la notació unicode a caràcters ASCII. */u00B2* es converteix en *2*.
     - **Espai en blanc**: Elimina tots els espais. *Hola   món* es converteix en *Holamón*.

   - **Precisió**: definiu el nivell de precisió que voleu aplicar per a aquesta condició.
     - **Bàsic**: Tria entre *Baix (30%)*, *Mitjà (60%)*, *Alt (80%)*, Exacte *(100%)*. Seleccioneu **Exacte** perquè només coincideixin amb els registres que coincideixin amb el 100 per cent.
     - **Personalitzat**: definiu un percentatge que han de complir els registres. El sistema només trobarà coincidències en els registres que compleixin aquest llindar.

   - **Nom**: Nom de la regla.

1. Per fer coincidir entitats només si els atributs compleixen diverses condicions, seleccioneu **Afegeix una** > **condició** per afegir més condicions a una regla de coincidència. Les condicions estan connectades amb un operador AND lògic i, per tant, només s'executen si es compleixen totes les condicions.

1. Opcionalment, tingueu en compte opcions avançades, com [ara excepcions o](#add-exceptions-to-a-rule) condicions [de concordança personalitzades](#specify-custom-match-conditions).

1. Seleccioneu **Fet** per finalitzar la regla.

1. Opcionalment, [afegiu més regles](#add-rules-to-a-match-pair).

1. Feu clic a **Endavant**.

> [!div class="nextstepaction"]
> [Pas següent: unificar camps](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Afegir regles a una parella de coincidència

Les regles de coincidència representen conjunts de condicions. Per fer coincidir entitats per condicions basades en diversos atributs, afegiu més regles.

1. Seleccioneu **Afegeix una regla** a l'entitat a la qual voleu afegir regles.

1. Seguiu els passos de [Definir regles per a les parelles de coincidència](#define-rules-for-match-pairs).

> [!NOTE]
> L'ordre de les regles és important. L'algorisme de coincidència intenta fer coincidir un registre de client determinat sobre la base de la primera regla i continua fins a la segona regla només si no s'han identificat coincidències amb la primera regla.

## <a name="advanced-options"></a>Opcions avançades

### <a name="add-exceptions-to-a-rule"></a>Afegir excepcions a una regla

En la majoria dels casos, l'entitat que coincideix condueix a perfils de clients únics amb dades consolidades. Per abordar casos rars de falsos positius i falsos negatius, definiu excepcions per a una regla de coincidència. Les excepcions s'apliquen després de processar les regles de coincidència i eviten la coincidència de tots els registres, que compleixen els criteris d'excepció.

Per exemple, si la regla del partit combina cognom, la ciutat i la data de naixement, el sistema identificaria els bessons amb el mateix cognom que viuen al mateix poble que el mateix perfil. Podeu especificar una excepció que no coincideixi amb els perfils si les nom de les entitats que combineu no són les mateixes.

1. A la subfinestra Edita la **regla**, seleccioneu **Afegeix una** > **excepció**.

1. Especifiqueu els criteris d'excepció.

1. Seleccioneu **Fet** per desar la regla.

### <a name="specify-custom-match-conditions"></a>Especificar condicions de coincidència personalitzades

Especifiqueu les condicions que substitueixen la lògica de concordança per defecte. Hi ha quatre opcions disponibles:

|Opció  |Descripció |Exemple  |
|---------|---------|---------|
|Coincidència     | Defineix valors per a les claus primàries que sempre coincideixen.         |  Feu coincidir sempre la fila amb la clau *principal 12345* a la fila amb la clau *principal 54321*.       |
|No coincidència     | Defineix valors per a les claus primàries que mai coincideixen.        | No coincideixis mai la fila amb la clau *primària 12345* a la fila amb la clau *primària 54321*.        |
|Omissió            | Defineix valors que el sistema sempre ha d'ignorar en la fase de partit. |  Ignora els valors *11111* i *Desconegut* durant el partit.        |
|Assignació d'àlies    | Definició de valors que el sistema ha de considerar com el mateix valor.         | Considereu que *Joe* és igual a *Joseph*.        |

1. Seleccioneu **Personalitzar**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Botó personalitzat":::

1. Trieu el **Tipus** personalitzat i seleccioneu **Baixa la plantilla**. Canvieu el nom de la plantilla sense utilitzar espais. Utilitzeu una plantilla independent per a cada opció de coincidència.

1. Obriu el fitxer de plantilla descarregat i empleneu els detalls. La plantilla conté camps per especificar l'entitat i els valors de clau principal de l'entitat que s'utilitzaran a la coincidència personalitzada. Els noms de les entitats distingeixen entre majúscules i minúscules. Per exemple, si voleu que la clau principal *12345* de l'entitat *Vendes* coincideixi sempre amb la clau principal *34567* de l'entitat *Contacte*, empleneu la plantilla:
   - Entity1: Vendes
   - Entity1Key: 12345
   - Entity2: Contacte
   - Entity2Key: 34567

   El mateix fitxer de plantilla pot especificar els registres de coincidència personalitzats des de diverses entitats.

   > [!NOTE]
   > Si voleu especificar la coincidència personalitzada per a la desduplicació en una entitat, proporcioneu la mateixa entitat com a Entitat1 i Entitat2 i definiu els diferents valors de clau principal. Heu de definir com a mínim una regla de deduplicació a l'entitat per utilitzar la concordança personalitzada.

1. Després d'afegir totes les substitucions, deseu el fitxer de plantilla.

1. Aneu a **Dades** > **Fonts de dades** i ingeriu els fitxers de plantilla com a entitats noves.

1. Després de penjar els fitxers, torneu a seleccionar l'opció **Personalitzat**. Seleccioneu les entitats necessàries al menú desplegable i seleccioneu **Fet**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de pantalla del diàleg per triar les substitucions per a un escenari de coincidència personalitzada.":::

1. L'aplicació de la concordança personalitzada depèn de l'opció de coincidència que vulgueu utilitzar.

   - Per a **Always match** o **Never match**, procediu al següent pas.
   - A **l'assignació** Bypass **o** Alias, seleccioneu **Edita** en una regla de coincidència existent o creeu-ne una de nova. Al menú desplegable Normalitzacions, trieu l'opció **Bypass** personalitzat o **Assignació d'àlies** i seleccioneu **Fet**.

1. Seleccioneu **Fet** a la **subfinestra Personalitzat** per aplicar la configuració de concordança personalitzada.

   Cada fitxer de plantilla ingerit és el seu propi font de dades. Si es descobreixen registres que necessiten un tractament especial de coincidència, actualitzeu el font de dades adequat. L'actualització s'utilitzarà durant el proper procés d'unificació. Per exemple, identifiqueu bessons amb gairebé el mateix nom que viuen a la mateixa adreça que s'havia fusionat com una sola persona. Actualitzeu la font de dades per identificar els bessons com a registres únics i separats.

> [!div class="nextstepaction"]
> [Pas següent: unificar camps](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
