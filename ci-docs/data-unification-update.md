---
title: Actualitzar la configuració d'unificació
description: Actualitzeu regles duplicades, regles de concordança o camps unificats a la configuració d'unificació.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: a7cf06c07e4b95b848a55dfe5fe0b09397fe744e
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245582"
---
# <a name="update-the-unification-settings"></a>Actualitzar la configuració d'unificació

Per revisar o canviar qualsevol configuració d'unificació un cop s'hagi creat un perfil unificat, seguiu els passos següents.

1. Aneu a **Unificar dades** > **·**.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla de la pàgina Unify de dades després d'unificar les dades.":::

   > [!TIP]
   > La **peça Condicions** de coincidència només es mostra si s'han seleccionat diverses entitats.

1. Tria què vols actualitzar:
   - [Camps](#edit-source-fields) d'origen per afegir entitats o atributs o canviar tipus d'atributs.
   - [Duplicar registres](#manage-deduplication-rules) per gestionar regles de deduplicació o combinar preferències.
   - [Condicions coincidents](#manage-match-rules) per actualitzar les regles de coincidència en dues o més entitats.
   - [Camps de client](#manage-unified-fields) unificats per combinar o excloure camps. També podeu agrupar perfils relacionats en clústers.

1. Després de fer els canvis, trieu la següent opció:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Captura de pantalla de la pàgina Unify de dades amb les opcions unificades ressaltades.":::

   - [Executeu condicions](#run-matching-conditions) de coincidència per avaluar ràpidament la qualitat de les vostres condicions de coincidència (deduplicació i regles de concordança) sense actualitzar el perfil unificat. L'opció **Executa les condicions de coincidència només** no es mostra per a una sola entitat.
   - [Unifiqueu els perfils de](#run-updates-to-the-unified-customer-profile) client per executar condicions de coincidència i actualitzeu l'entitat del perfil de client unificat sense afectar les dependències (com ara enriquiments, segments o mesures). Els processos dependents no s'executen, sinó que s'actualitzaran tal com [es defineix a la planificació d'actualització](schedule-refresh.md).
   - [Unifiqueu els perfils i les dependències](#run-updates-to-the-unified-customer-profile) dels clients per executar les condicions de coincidència i actualitzeu l'entitat unificada del perfil de client i totes les dependències (com ara enriquiments, segments o mesures). Tots els processos es tornen a executar automàticament.

## <a name="edit-source-fields"></a>Editar els camps d'origen

No podeu suprimir un atribut o una entitat si ja s'han unificat.

1. Seleccioneu **Edita** a la **peça Camps** d'origen.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de pantalla de la pàgina Camps d'origen que mostra el nombre de claus principals, camps mapejats i sense mapa":::

   Es mostra el nombre de camps mapejats i sense mapa.

1. Seleccioneu **Seleccioneu entitats i camps** per afegir altres atributs o entitats. Utilitzeu la cerca o desplaçament per cercar i seleccionar els atributs i les entitats d'interès. Seleccioneu **Aplica**.

1. Opcionalment, podeu canviar la clau principal d'una entitat, els tipus d'atributs i activar o desactivar l'assignació **intel**·ligent. Per obtenir més informació, vegeu [Selecció de claus primàries i tipus semàntic per als atributs](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Seleccioneu **Següent** per fer canvis a les regles de deduplicació, o bé Desa **i tanca** i torna a [Actualitzar la configuració](#update-the-unification-settings) d'unificació.

## <a name="manage-deduplication-rules"></a>Gestionar les regles de deduplicació

1. Seleccioneu **Edita** a la **peça Duplica els registres**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de pantalla de la pàgina Registres duplicats que mostra el nombre de registres duplicats" lightbox="media/m3_duplicates_edit.png":::

   El nombre de registres duplicats trobats es mostra a **Duplicats**. La **columna Registres deduplicats** mostra quines entitats tenien registres duplicats i el percentatge de registres duplicats.

1. Si heu afegit una entitat enriquida, seleccioneu **Utilitza entitats** enriquides. Per obtenir més informació, vegeu [Enriquiment per a les fonts de](data-sources-enrichment.md) dades.

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

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Captura de pantalla de les preferències avançades de combinació que mostra el correu electrònic més recent i l'adreça més completa":::

   1. Seleccioneu **Fet**.

1. Seleccioneu **Següent** per fer canvis a les condicions coincidents o bé Desa **i tanca** i torna a [Actualitzar la configuració](#update-the-unification-settings) d'unificació.

## <a name="manage-match-rules"></a>Administra les regles de coincidència

Podeu reconfigurar i ajustar la majoria dels paràmetres de coincidència. No podeu afegir ni suprimir entitats. Les regles de coincidència no s'apliquen a una sola entitat.

1. Seleccioneu **Edita** a la **peça Condicions** de coincidència.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captura de pantalla de la pàgina Regles i condicions de la coincidència amb estadístiques." lightbox="media/m3_match_edit.png":::

   La pàgina mostra l'ordre de coincidència i les regles definides i les estadístiques següents:
   - A **Registres d'origen únics** es mostra el nombre de registres d'origen individuals que s'han processat a la darrera execució de coincidència.
   - A **Registres coincidents i no coincidents** es ressalta el nombre de registres únics que queden després de processar les regles de coincidència.
   - A **Només registres coincidents** es mostra el nombre de coincidències en totes les parelles de coincidència.

1. Per veure els resultats de totes les regles i les seves puntuacions, seleccioneu **Mostra l'última execució**. Es mostren els resultats, inclosos els identificadors de contacte alternatius. Podeu descarregar-vos els resultats.

1. Per veure els resultats i les puntuacions d'una regla concreta, seleccioneu la regla i, a continuació, **previsualitza**. Es mostren els resultats. Podeu descarregar-vos els resultats.

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

1. Seleccioneu **Següent** per fer canvis als camps unificats, o bé Desa **i tanca** i torna a [Actualitzar la configuració](#update-the-unification-settings) d'unificació.

## <a name="manage-unified-fields"></a>Gestionar camps unificats

1. Seleccioneu **Edita** a la **peça Camps** de client unificats.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de pantalla dels camps de client unificats":::

1. Reviseu els camps combinats i exclosos i feu els canvis que calguin. Afegiu o editeu la clau CustomerID o els perfils de grup en clústers. Per obtenir més informació, vegeu [Unificar els camps](merge-entities.md) del client.

1. Seleccioneu **Següent** per revisar la configuració d'unificació i [actualitzar el perfil unificat i les dependències, o bé Desa](#run-updates-to-the-unified-customer-profile)**i tanca** i torna a [Actualitzar la configuració](#update-the-unification-settings) d'unificació per fer més canvis.

## <a name="run-matching-conditions"></a>Executar condicions de coincidència

Executar les condicions de coincidència només executa la deduplicació i les regles de concordança i actualitza les *entitats Deduplication_** i *ConflationMatchPair*.

1. A la **pàgina Unificar** > **dades**, seleccioneu **Executa només** les condicions de coincidència.

   Les fitxes **Registres duplicats** i **Condicions de coincidència** mostren **l'estat en** cua o **Actualització**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Quan finalitzi el procés de coincidència, seleccioneu **Edita** a la **peça Condicions** de coincidència.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de pantalla retallada de les mètriques clau de la pàgina Coincidència amb nombres i detalls.":::

1. Per fer canvis, consulta [Administrar les regles de la deduplicació o](#manage-deduplication-rules) Administrar les [regles de concordança](#manage-match-rules).

1. Torneu a executar el procés de coincidència o [executeu actualitzacions al perfil](#run-updates-to-the-unified-customer-profile) de client.

## <a name="run-updates-to-the-unified-customer-profile"></a>Executar actualitzacions al perfil de client unificat

1. A la **pàgina Unificar** > **dades**, seleccioneu:

   - **Unificar perfils de** client: executa les condicions de coincidència i actualitza l'entitat del perfil de client unificat sense afectar les dependències (com ara enriquiments, segments o mesures). Els processos dependents no s'executen, sinó que s'actualitzaran tal com [es defineix a la planificació d'actualització](schedule-refresh.md).

   - **Unificar perfils i dependències** de clients: Executa les condicions de coincidència i actualitza el perfil unificat i totes les dependències. Tots els processos es tornen a executar automàticament. Un cop finalitzats tots els processos aigües avall, el perfil del client reflecteix les dades actualitzades.

   Els **registres duplicats**, **les condicions de coincidència i** les peces **dels camps** de client unificat mostren **l'estat en cua** o **actualització**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Els resultats d'una visualització d'execució correcta a la **pàgina Unify** que mostra el nombre de perfils de clients unificats.
