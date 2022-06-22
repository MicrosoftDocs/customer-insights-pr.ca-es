---
title: Actualitza la configuració de la unificació
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
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844028"
---
# <a name="update-the-unification-settings"></a>Actualitza la configuració de la unificació

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Per revisar o canviar qualsevol configuració d'unificació un cop s'hagi creat un perfil unificat, realitzeu els passos següents.

1. Aneu a Unificació de **dades** > **·**.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla de la pàgina Unificació de dades després d'unificar les dades.":::

   > [!TIP]
   > La **peça Condicions coincidents** només es mostra si s'han seleccionat diverses entitats.

1. Trieu què voleu actualitzar:
   - [Camps](#edit-source-fields) d'origen per afegir entitats o atributs o canviar tipus d'atributs.
   - [Registres duplicats](#manage-deduplication-rules) per administrar regles de deduplicació o combinar preferències.
   - [Condicions coincidents](#manage-match-rules) per actualitzar les regles de coincidència en dues o més entitats.
   - [Camps de client](#manage-unified-fields) unificats per combinar o excloure camps. També podeu agrupar perfils relacionats en clústers.

1. Després de fer els canvis, trieu la següent opció:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Captura de pantalla de la pàgina Unifica les dades amb les opcions d'Unificar ressaltats.":::

   - [Executeu les condicions](#run-matching-conditions) de coincidència per avaluar ràpidament la qualitat de les condicions de coincidència (regles de deduplicació i coincidència) sense actualitzar el perfil unificat. L'opció **Executa les condicions coincidents** no es mostra per a una sola entitat.
   - [Unifiqueu els perfils](#run-updates-to-the-unified-customer-profile) de clients per executar condicions coincidents i actualitzar l'entitat de perfil de client unificada sense afectar dependències (com ara enriquiments, segments o mesures). Els processos dependents no s'executen, sinó que s'actualitzaran tal com [es defineix a la planificació](system.md#schedule-tab) d'actualització.
   - [Unifiqueu els perfils de clients i les dependències](#run-updates-to-the-unified-customer-profile) per executar condicions coincidents i actualitzar l'entitat de perfil de client unificat i totes les dependències (com ara enriquiments, segments o mesures). Tots els processos es tornen a executar automàticament.

## <a name="edit-source-fields"></a>Edita els camps d'origen

No podeu suprimir un atribut o una entitat si ja s'han unificat.

1. Seleccioneu **Edita** a la peça Camps d'origen **·**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de pantalla de la pàgina Camps d'origen que mostra el nombre de claus primàries, camps assignats i sense assignar":::

   El nombre de camps assignats i no assignats es mostra.

1. Seleccioneu **Selecciona entitats i camps** per afegir altres atributs o entitats. Utilitzeu la cerca o desplaçament per cercar i seleccionar els atributs i les entitats d'interès. Seleccioneu **Aplica**.

1. Opcionalment, podeu canviar la clau principal d'una entitat, els tipus d'atributs i commutar **l'assignació** intel·ligent encaire o desactiva. Per obtenir més informació, vegeu [Seleccionar la clau principal i el tipus semàntic per als atributs](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Seleccioneu **Endavant** per fer canvis a les regles de deduplicació o seleccioneu **Desa** i tanca [i torna a](#update-the-unification-settings) Actualitza la configuració de la unificació.

## <a name="manage-deduplication-rules"></a>Administra les regles de deduplicació

1. Seleccioneu **Edita** a la **peça Registres** duplicats.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de pantalla de la pàgina Registres duplicats que mostra el nombre de registres duplicats" lightbox="media/m3_duplicates_edit.png":::

   Nombre de registres duplicats trobats es mostra a **Duplicats**. La **columna deduplicada** Registres mostra quines entitats tenien registres duplicats i el percentatge de registres duplicats.

1. Si heu afegit una entitat enriquida, seleccioneu **Utilitza entitats** enriquides. Per obtenir més informació, vegeu [Enriquiment per a fonts](data-sources-enrichment.md) de dades.

1. Per gestionar les regles de deduplicació, trieu qualsevol de les opcions següents:
   - **Crear una norma** nova: seleccioneu **Afegeix una norma** a l'entitat adequada. Per obtenir més informació, vegeu [Definir regles](remove-duplicates.md#define-deduplication-rules) de deduplicació.
   - **Canviar les condicions de la** regla: selecciona la regla i després **Edita**. Canvieu camps, afegiu o suprimiu condicions o afegiu o suprimiu excepcions.
   - **Visualització prèvia**: seleccioneu la regla i, a continuació, **visualitzeu la visualització prèvia** per veure els resultats de l'última execució d'aquesta regla.
   - **Desactivar una regla**: seleccioneu la regla i desactiveu-la **per** conservar una regla de deduplicació mentre l'excloeu del procés de coincidència.
   - **Duplicar una regla**: selecciona la regla i duplica **per** crear una regla similar amb modificacions.
   - **Suprimir una regla**: selecciona la regla i **suprimeix**.

1. Per canviar les preferències de combinació, seleccioneu l'entitat. Només podeu canviar les preferències si es crea una regla.
   1. Seleccioneu **Edita les preferències** de combinació i canvieu l'opció **Registre per conservar-lo**.
   1. Per canviar les preferències de combinació en atributs individuals d'una entitat, seleccioneu **Avançat** i feu els canvis necessaris.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Captura de pantalla de les preferències avançades de combinació que mostren el correu electrònic més recent i l'adreça més completa":::

   1. Seleccioneu **Fet**.

1. Seleccioneu **Endavant** per fer canvis a les condicions coincidents o seleccioneu **Desa i tanca** i torna a [Actualitza la configuració de](#update-the-unification-settings) la unificació.

## <a name="manage-match-rules"></a>Administra les regles de coincidència

Podeu reconfigurar i ajustar la majoria dels paràmetres de coincidència. No podeu afegir ni suprimir entitats. Les regles de concordança no s'apliquen a una sola entitat.

1. Seleccioneu **Edita** a la **peça Condicions coincidents**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captura de pantalla de la pàgina Regles i condicions de concordança amb estadístiques." lightbox="media/m3_match_edit.png":::

   La pàgina mostra l'ordre de coincidència i les regles definides i les estadístiques següents:
   - A **Registres d'origen únics** es mostra el nombre de registres d'origen individuals que s'han processat a la darrera execució de coincidència.
   - A **Registres coincidents i no coincidents** es ressalta el nombre de registres únics que queden després de processar les regles de coincidència.
   - A **Només registres coincidents** es mostra el nombre de coincidències en totes les parelles de coincidència.

1. Per veure els resultats de totes les regles i les seves puntuacions, seleccioneu **Visualitza l'última execució**. Es mostren els resultats, inclosos els identificadors de contacte alternatius. Podeu descarregar-vos els resultats.

1. Per veure els resultats i les puntuacions d'una regla en particular, seleccioneu la regla i, a continuació, **Previsualitza.** Els resultats es mostren. Podeu descarregar-vos els resultats.

1. Per veure els resultats d'una condició particular en una regla, seleccioneu la regla i **editeu**. A la subfinestra Edició, seleccioneu **Previsualitza a** la condició. Podeu descarregar-vos els resultats.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Representació gràfica de registres coincidents i coincidents, inclosa una llista de les dades.":::

1. Si heu afegit una entitat enriquida, seleccioneu **Utilitza entitats** enriquides. Per obtenir més informació, vegeu [Enriquiment per a fonts](data-sources-enrichment.md) de dades.

1. Per gestionar les regles, trieu qualsevol de les opcions següents:
   - **Crear una norma** nova: seleccioneu **Afegeix una norma** a l'entitat adequada. Per obtenir més informació, vegeu [Definir regles per als parells](match-entities.md#define-rules-for-match-pairs) de partits.
   - **Canviar l'ordre de les regles** si has definit diverses regles: arrossega i deixa anar les regles en l'ordre que vulguis. Per obtenir més informació, vegeu [Especifiqueu l'ordre de coincidència](match-entities.md#specify-the-match-order).
   - **Canviar les condicions de la** regla: selecciona la regla i després **Edita**. Canvieu camps, afegiu o suprimiu condicions o afegiu o suprimiu excepcions.
   - **Desactivar una regla**: selecciona la regla i desactiva-la **per** conservar una regla de concordança mentre l'exclou del procés de coincidència.
   - **Duplicar una regla**: selecciona la regla i duplica **per** crear una regla similar amb modificacions.
   - **Suprimir una regla**: selecciona la regla i **suprimeix**.

1. Seleccioneu **Endavant** per fer canvis als camps unificats **o seleccioneu** Desa i tanca [i torna a](#update-the-unification-settings) Actualitza la configuració de la unificació.

## <a name="manage-unified-fields"></a>Administra els camps unificats

1. Seleccioneu **Edita** a la **peça Camps de client** unificats.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de pantalla dels camps de client unificats":::

1. Reviseu els camps combinats i exclosos i feu els canvis segons calgui. Afegiu o editeu la clau o els perfils de grup del CustomerID als clústers. Per obtenir més informació, vegeu [Unificar els camps](merge-entities.md) de client.

1. Seleccioneu **Endavant** per revisar la configuració d'unificació i [actualitzar el perfil unificat i les dependències, o seleccioneu](#run-updates-to-the-unified-customer-profile) Desa **i tanca** i torna a [Actualitza la configuració](#update-the-unification-settings) de la unificació per fer més canvis.

## <a name="run-matching-conditions"></a>Executa les condicions de coincidència

Les condicions coincidents només executen la deduplicació i les regles de concordança i actualitza les *entitats Deduplication_** i *ConflationMatchPair*.

1. A la **pàgina Unificació de** > **dades**, seleccioneu **Executa només** les condicions coincidents.

   Les **peces Registres** duplicats i **Condicions** coincidents mostren **l'estat de cua** o **actualització**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Quan finalitzi el procés de coincidència, seleccioneu **Edita** a la **peça Condicions coincidents**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de pantalla retallada de les mètriques clau de la pàgina Coincidència amb nombres i detalls.":::

1. Per fer canvis, consulta [Administrar les regles](#manage-deduplication-rules) de deduplicació o [Administrar les regles de concordança](#manage-match-rules).

1. Torneu a executar el procés de coincidència o [executeu actualitzacions al perfil](#run-updates-to-the-unified-customer-profile) del client.

## <a name="run-updates-to-the-unified-customer-profile"></a>Executa les actualitzacions del perfil de client unificat

1. A la **pàgina Unificació de** > **dades**, seleccioneu:

   - **Unificar perfils** de clients: executa condicions coincidents i actualitza l'entitat de perfil de client unificada sense afectar dependències (com ara enriquiments, segments o mesures). Els processos dependents no s'executen, sinó que s'actualitzaran tal com [es defineix a la planificació](system.md#schedule-tab) d'actualització.

   - **Unificar perfils de clients i dependències**: executa condicions coincidents i actualitza el perfil unificat i totes les dependències. Tots els processos es tornen a executar automàticament. Després que s'hagin completat tots els processos downstream, el perfil del client reflecteix les dades actualitzades.

   Els **registres** duplicats, **les condicions coincidents i** les **peces de camps** de client unificats mostren **l'estat de** cua o **actualització**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Els resultats d'una visualització d'execució correcta a la **pàgina Unify** que mostra el nombre de perfils de clients unificats.
