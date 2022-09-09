---
title: Actualitzar la configuració d'unificació de clients, comptes o contactes
description: Actualitzeu regles duplicades, regles de concordança o camps unificats a la configuració d'unificació de clients o comptes.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392459"
---
# <a name="update-unification-settings"></a>Actualitzar la configuració d'unificació

Per revisar o canviar qualsevol configuració d'unificació un cop s'hagi creat un perfil unificat, seguiu els passos següents.

1. Aneu a **Unificar dades** > **·**.

   Per a clients individuals (de B a C), la **pàgina Unify** mostra el nombre de perfils de clients unificats i peces per a cadascun dels passos d'unificació.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla de la pàgina Unify de dades després d'unificar les dades." lightbox="media/m3_unified.png":::

   En el cas dels comptes d'empresa (B a B), la **pàgina Unify** mostra el nombre de perfils i peces de comptes unificades per a cadascun dels passos d'unificació del compte. Si els contactes s'han unificat, es mostra el nombre de perfils de contactes unificats i de peces per a cadascun dels passos d'unificació de contactes. Trieu la peça adequada a **Unificar comptes** o **Unificar contactes (visualització prèvia)** en funció del que vulgueu actualitzar.

   :::image type="content" source="media/b2b_unified.png" alt-text="Captura de pantalla de la pàgina Unificar dades després que les dades del compte i de contacte estiguin unificades." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > La **peça Condicions** de coincidència només es mostra si s'han seleccionat diverses entitats.

1. Tria què vols actualitzar:
   - [Camps](#edit-source-fields) d'origen per afegir atributs o entitats o canviar tipus d'atributs. Per suprimir un atribut, vegeu [Supressió d'un camp](#remove-a-unified-field) unificat. Per suprimir una entitat, vegeu [Supressió d'una entitat](#remove-a-unified-entity) unificada.
   - [Duplicar registres](#manage-deduplication-rules) per gestionar regles de deduplicació o combinar preferències.
   - [Condicions coincidents](#manage-match-rules) per actualitzar les regles de coincidència en dues o més entitats.
   - [Camps de client](#manage-unified-fields) unificats per combinar o excloure camps. També podeu agrupar perfils relacionats en clústers.
   - [Camps](#manage-semantic-fields-for-unified-contacts) semàntics per gestionar tipus semàntics per a camps de contacte unificats.
   - [Relacions](#manage-contact-and-account-relationships) per gestionar la relació contacte-compte.

1. Després de fer els canvis, trieu la següent opció:

   - [Executeu condicions](#run-matching-conditions) de coincidència per avaluar ràpidament la qualitat de les vostres condicions de coincidència (deduplicació i regles de concordança) sense actualitzar el perfil unificat. L'opció **Executa les condicions de coincidència només** no es mostra per a una sola entitat.
   - [Unifiqueu perfils](#run-updates-to-the-unified-profile) per executar condicions de coincidència i actualitzeu l'entitat del perfil unificat sense afectar les dependències (com ara enriquiments, segments o mesures). Els processos dependents no s'executen, sinó que s'actualitzaran tal com [es defineix a la planificació d'actualització](schedule-refresh.md).
   - [Unifiqueu perfils i dependències](#run-updates-to-the-unified-profile) per executar condicions de coincidència, actualitzeu l'entitat del perfil unificat i actualitzeu totes les dependències (com ara enriquiments, segments o mesures). Tots els processos es tornen a executar automàticament. En B a B, la unificació s'executa tant a les entitats de compte com de contacte que actualitzen els perfils unificats.

## <a name="edit-source-fields"></a>Editar els camps d'origen

1. Seleccioneu **Edita** a la **peça Camps** d'origen.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de pantalla de la pàgina Camps d'origen que mostra el nombre de claus principals, camps mapejats i sense mapa":::

   Es mostra el nombre de camps mapejats i sense mapa.

1. Per afegir altres atributs o entitats, seleccioneu **Selecciona entitats i camps**.

1. Opcionalment, podeu canviar la clau principal d'una entitat, els tipus d'atributs i activar o desactivar l'assignació **intel**·ligent. Per obtenir més informació, vegeu [Selecció de camps d'origen](map-entities.md).

1. Seleccioneu **Següent** per fer canvis a les regles de deduplicació, o bé Desa **i tanca** i torna a [Actualitzar la configuració](#update-unification-settings) d'unificació.

### <a name="remove-a-unified-field"></a>Suprimir un camp unificat

Per eliminar un camp que s'ha unificat, el camp s'ha d'eliminar de qualsevol dependència, com ara segments, mesures, enriquiments o relacions.

1. Un cop eliminades totes les dependències del camp, aneu a **Unificar** > **dades**.

1. Seleccioneu **Edita** a la **peça Camps** de client unificats.

1. Seleccioneu totes les ocurrències del camp i, a continuació, seleccioneu **Exclou**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Captura de pantalla de la pàgina Camps unificats que mostra els camps seleccionats i el botó Exclou":::

1. Seleccioneu **Fet** per confirmar i, a continuació, Seleccioneu **Desa i tanca**.

   > [!TIP]
   > Si veieu el missatge "No s'ha pogut desar unificar. El recurs especificat no es pot modificar ni suprimir a causa de dependències aigües avall", llavors el camp encara s'utilitza en una dependència aigües avall.

1. Si el camp s'utilitza en una regla per a registres duplicats o condicions de coincidència, seguiu els passos següents. En cas contrari, aneu al següent pas.
   1. Seleccioneu **Edita** a la **peça Duplica els registres**.
   1. Elimineu el camp de totes les regles en què s'utilitza, si n'hi ha, i, a continuació, seleccioneu **Següent**.
   1. A la **pàgina Condicions** de coincidència, traieu el camp de totes les regles en què s'utilitza, si n'hi ha, i, a continuació, seleccioneu **Desa i tanca**.
   1. Seleccioneu **Unificar** > **unificar perfils i dependències de** clients. Espereu que es completi la unificació abans d'anar al següent pas.

1. Seleccioneu **Edita** a la **peça Camps** d'origen.

1. Seleccioneu **Selecciona entitats i camps** i desmarqueu la casella de selecció situada al costat de cada ocurrència del camp.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Captura de pantalla del quadre de diàleg Selecciona entitats i camps que mostra les caselles de selecció esborrades":::

1. Seleccioneu **Aplica**.

1. Seleccioneu **Desa i tanca**.

1. Seleccioneu **Unificar** > **els perfils i les dependències** dels clients per actualitzar el perfil unificat.

### <a name="remove-a-unified-entity"></a>Suprimir una entitat unificada

Per eliminar una entitat que s'ha unificat, l'entitat s'ha d'eliminar de qualsevol dependència, com ara segments, mesures, enriquiments o relacions.

1. Un cop eliminades totes les dependències de l'entitat, aneu a **Unificar** > **dades**.

1. Seleccioneu **Edita** a la **peça Camps** de client unificats.

1. Seleccioneu tots els camps de l'entitat i, a continuació, seleccioneu **Exclou**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Captura de pantalla dels camps unificats amb tots els camps d'una entitat seleccionada i el botó Exclou":::

1. Seleccioneu **Fet** per confirmar i, a continuació, Seleccioneu **Desa i tanca**.

   > [!TIP]
   > Si veieu el missatge "No s'ha pogut desar unificar. El recurs especificat no es pot modificar ni suprimir a causa de dependències aigües avall", llavors l'entitat encara s'utilitza en una dependència aigües avall.

1. Seleccioneu **Edita** a la **peça Duplica els registres**.

1. Elimineu totes les regles de l'entitat, si n'hi ha, i seleccioneu **Següent**.

1. A la **pàgina Condicions** de coincidència, seleccioneu l'entitat i, a continuació, seleccioneu **Suprimeix**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Captura de pantalla de les condicions de coincidència amb l'entitat seleccionada i el botó Suprimeix":::

1. Seleccioneu **Desa i tanca**.

1. Seleccioneu **Edita** a la **peça Camps** d'origen.

1. Seleccioneu **Selecciona entitats i camps** i desmarqueu la casella de selecció situada al costat de l'entitat.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Captura de pantalla del quadre de diàleg Seleccioneu entitats i camps amb la casella de selecció d'entitat esborrada":::

1. Seleccioneu **Aplica**.

1. Seleccioneu **Desa i tanca**.

1. Seleccioneu **Unificar** > **els perfils i les dependències** dels clients per actualitzar el perfil unificat.

## <a name="manage-deduplication-rules"></a>Gestionar les regles de deduplicació

1. Seleccioneu **Edita** a la **peça Duplica els registres**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de pantalla de la pàgina Registres duplicats que mostra el nombre de registres duplicats" lightbox="media/m3_duplicates_edit.png":::

   El nombre de registres duplicats trobats es mostra a **Duplicats**. La **columna Registres deduplicats** mostra quines entitats tenien registres duplicats i el percentatge de registres duplicats.

1. Per utilitzar una entitat enriquida, seleccioneu **Utilitza entitats** enriquides. Per obtenir més informació, vegeu [Enriquiment per a les fonts de](data-sources-enrichment.md) dades.

1. Per gestionar les regles de deduplicació, trieu qualsevol de les opcions següents:
   - **Crear una regla** nova: seleccioneu **Afegeix una regla** a sota de l'entitat adequada. Per obtenir més informació, vegeu [Definir regles](remove-duplicates.md#define-deduplication-rules) de deduplicació.
   - **Canviar les condicions de la** regla: seleccioneu la regla i, a continuació, **Edita**. Canvieu camps, afegiu o suprimiu condicions o afegiu o suprimiu excepcions.
   - **Previsualització**: seleccioneu la regla i, a continuació, **previsualitzar** per veure els darrers resultats d'execució d'aquesta regla.
   - **Desactivar una regla**: seleccioneu la regla i, a continuació, **Desactiva** per retenir una regla de deduplicació mentre l'excloeu del procés de coincidència.
   - **Duplicar una regla**: selecciona la regla i duplica **per** crear una norma similar amb modificacions.
   - **Suprimir una regla**: selecciona la regla i, a continuació, **Suprimeix**.

1. Per canviar les preferències de combinació, seleccioneu l'entitat. Només podeu canviar les preferències si es crea una regla.
   1. Seleccioneu **Edita les preferències** de combinació i canvieu l'opció **Registre per conservar**.
   1. Per canviar les preferències de combinació dels atributs individuals d'una entitat, seleccioneu **Avançat** i feu els canvis necessaris.

   1. Seleccioneu **Fet**.

1. Seleccioneu **Següent** per fer canvis a les condicions coincidents o bé Desa **i tanca** i torna a Actualitzar la [configuració](#update-unification-settings) d'unificació.

## <a name="manage-match-rules"></a>Administra les regles de coincidència

Podeu reconfigurar i ajustar la majoria dels paràmetres de coincidència. No podeu afegir ni suprimir entitats. Les regles de coincidència no s'apliquen a una sola entitat.

1. Seleccioneu **Edita** a la **peça Condicions** de coincidència.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captura de pantalla de la pàgina Regles i condicions de la coincidència amb estadístiques." lightbox="media/m3_match_edit.png":::

   La pàgina mostra l'ordre de coincidència i les regles definides i les estadístiques següents:
   - **Els registres d'origen únics** mostren el nombre de registres d'origen individuals que es van processar en l'última execució de coincidència.
   - **Els registres coincidents i no coincidents ressalten** quants registres únics queden després de processar les regles del partit.
   - **Els registres coincidents només** mostren el nombre de partits en tots els parells de partits.

1. Per veure els resultats de totes les regles i les seves puntuacions, seleccioneu **Mostra l'última execució**. Es mostren els resultats, inclosos els identificadors de contacte alternatius. Podeu descarregar-vos els resultats.

1. Per veure els resultats i les puntuacions d'una regla concreta, seleccioneu la regla i, a continuació, **previsualitza**. La visualització de resultats. Podeu descarregar-vos els resultats.

1. Per veure els resultats d'una condició particular en una regla, seleccioneu la regla i, a continuació, **Edita**. A la subfinestra Edita, seleccioneu **Visualització prèvia** sota la condició. Podeu descarregar-vos els resultats.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Representació gràfica de registres inigualables i coincidents incloent una llista de les dades.":::

1. Si heu afegit una entitat enriquida, seleccioneu **Utilitza entitats** enriquides. Per obtenir més informació, vegeu [Enriquiment per a les fonts de](data-sources-enrichment.md) dades.

1. Per gestionar les regles, trieu qualsevol de les opcions següents:
   - **Crear una regla** nova: seleccioneu **Afegeix una regla** a sota de l'entitat adequada. Per obtenir més informació, vegeu [Definir regles per a parelles de coincidències](match-entities.md#define-rules-for-match-pairs).
   - **Canviar l'ordre de les regles** si has definit diverses regles: arrossega i deixa anar les regles en l'ordre que vulguis. Per obtenir més informació, vegeu [Especificar l'ordre](match-entities.md#specify-the-match-order) de coincidència.
   - **Canviar les condicions de la** regla: seleccioneu la regla i, a continuació, **Edita**. Canvieu camps, afegiu o suprimiu condicions o afegiu o suprimiu excepcions.
   - **Desactivar una regla**: seleccioneu la regla i, a continuació, **Desactiva** per conservar una regla de coincidència mentre l'excloeu del procés de coincidència.
   - **Duplicar una regla**: selecciona la regla i duplica **per** crear una norma similar amb modificacions.
   - **Suprimir una regla**: selecciona la regla i, a continuació, **Suprimeix**.

1. Seleccioneu **Següent** per fer canvis als camps unificats, o bé Desa **i tanca** i torna a Actualitzar la [configuració](#update-unification-settings) d'unificació.

## <a name="manage-unified-fields"></a>Gestionar camps unificats

1. Seleccioneu **Edita** a la **peça Camps** de client unificats.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de pantalla dels camps de client unificats":::

1. Reviseu els camps combinats i exclosos i feu els canvis que calguin. Afegiu o editeu la clau CustomerID o els perfils de grup en clústers. Per obtenir més informació, vegeu [Unificar els camps](merge-entities.md) del client.

1. Per a clients o comptes, seleccioneu **Següent** per revisar i [actualitzar el perfil i les dependències](#run-updates-to-the-unified-profile) unificades. O bé, seleccioneu **Desa i tanca** i torneu a Actualitza la [configuració](#update-unification-settings) d'unificació per fer més canvis.

   Per als contactes, seleccioneu **Següent** per gestionar els camps semàntics. O bé, seleccioneu **Desa i tanca** i torneu a Actualitza la [configuració](#update-unification-settings) d'unificació per fer més canvis.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Gestionar camps semàntics per a contactes unificats

1. Seleccioneu **Edita** a la **peça Camps** semàntics.

1. Per canviar el tipus semàntic d'un camp unificat, seleccioneu-ne un de nou. Per obtenir més informació, vegeu [Definir els camps semàntics per a contactes](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts) unificats.

1. Seleccioneu **Següent** per gestionar la relació de contacte i compte, o bé Desa **i tanca** i torna a [Actualitzar la configuració d'unificació](#update-unification-settings) per fer més canvis.

## <a name="manage-contact-and-account-relationships"></a>Gestionar les relacions entre contactes i comptes

1. Seleccioneu **Edita** a la **peça Relacions**.

1. Per canviar la relació de contactes i comptes, canvieu qualsevol de les dades següents:

   - **Clau externa de l'entitat** de contacte: trieu l'atribut que connecta l'entitat de contacte amb el compte.
   - **Per tenir en compte l'entitat**: trieu l'entitat del compte associada al contacte.

1. Seleccioneu **Següent** per revisar la configuració d'unificació i [actualitzar el perfil unificat i les dependències, o bé Desa](#run-updates-to-the-unified-profile)**i tanca** i torna a [Actualitzar la configuració d'unificació](#update-unification-settings) per fer més canvis.

## <a name="run-matching-conditions"></a>Executar condicions de coincidència

Executar les condicions de coincidència només executa la deduplicació i les regles de concordança i actualitza les *entitats Deduplication_** i *ConflationMatchPair*.

1. A la **pàgina Unificar** > **dades**, seleccioneu **Executa només** les condicions de coincidència.

   Les fitxes **Registres duplicats** i **Condicions de coincidència** mostren **l'estat en** cua o **Actualització**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Quan finalitzi el procés de coincidència, seleccioneu **Edita** a la **peça Condicions** de coincidència.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de pantalla retallada de les mètriques clau de la pàgina Coincidència amb nombres i detalls.":::

1. Per fer canvis, consulta [Administrar les regles de la deduplicació o](#manage-deduplication-rules) Administrar les [regles de concordança](#manage-match-rules).

1. Torneu a executar el procés de coincidència o [executeu actualitzacions al perfil](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Executar actualitzacions al perfil unificat

- Per executar les condicions de coincidència i actualitzar l'entitat *del perfil unificat sense* afectar les dependències (com ara targetes de client, enriquiments, segments o mesures), seleccioneu **Unifica els perfils de** client. Per als comptes, seleccioneu **Unificar comptes** > **Unificar perfils**. Per als contactes, selecciona **Unificar contactes (previsualització)** > **Unificar perfils**. Els processos dependents no s'executen, sinó que s'actualitzaran tal com [es defineix a la planificació d'actualització](schedule-refresh.md).
- Per executar les condicions de coincidència, actualitzeu el perfil unificat i executeu totes les dependències, seleccioneu **Unifica els perfils de client i les dependències**. Tots els processos es tornen a executar automàticament. Per a comptes i contactes, seleccioneu **Unificar comptes** > **Unificar perfils i dependències**. Les condicions de coincidència s'executen tant per als comptes com per als contactes actualitzant tant els perfils unificats com la resta de dependències.

Totes les fitxes, excepte **els camps** Font, mostren **la cua o** l'actualització **·**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Els resultats d'una visualització d'execució correcta a la **pàgina Unify** que mostra el nombre de perfils unificats.
