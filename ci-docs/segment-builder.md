---
title: Creeu segments complexos amb el creador de segments
description: Utilitzeu el creador de segments per crear segments de clients complexos agrupant-los en funció de diversos atributs.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304737"
---
# <a name="create-complex-segments-with-segment-builder"></a>Creeu segments complexos amb el creador de segments

Definiu filtres complexos al voltant del client unificat o contacte unificat i les seves entitats relacionades. Cada segment, després del processament, crea un conjunt de registres de contactes o de clients que podeu exportar i dur a terme accions.

> [!TIP]
> Els segments basats en **clients individuals** inclouen automàticament la informació de contacte disponible per als membres del segment. Als **comptes** d'empresa, si heu [unificat](data-unification.md) tant els comptes com els contactes, trieu si el segment es basa en comptes o contactes empresarials. Per exportar a una destinació que espera informació de contacte, utilitzeu un segment de contactes. Per exportar a una destinació que espera informació del compte, utilitzeu un segment de comptes.

## <a name="segment-builder"></a>Creador de segments

La imatge següent il·lustra els diferents aspectes del creador de segments. Mostra un segment que resulta en un grup de clients. Els clients han demanat productes en un període de temps específic i han recollit punts de recompensa o han gastat una determinada quantitat de diners.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elements del creador de segments." lightbox="media/segment-builder-overview.png":::

1. Organitzeu el segment amb regles i subregles. Cada regla o subregles consta de condicions. Combineu les condicions amb operadors lògics.

1. Trieu el [camí de la relació](relationships.md) entre les entitats que s'apliquen a una regla. El camí de la relació determina quins atributs es poden utilitzar en una condició.

1. Administreu regles i subregles. Canvieu la posició d'una regla o suprimiu-la.

1. Afegiu condicions i creeu el nivell adequat d'imbricació amb subregles.

1. Apliqueu operacions de conjunt a les regles connectades.

1. Utilitzeu la subfinestra d'atributs per afegir atributs d'entitat disponibles o crear condicions segons els atributs. A la subfinestra es mostra la llista d'entitats i d'atributs, segons el camí de relació seleccionat, que estan disponibles per a la regla seleccionada.

1. Afegiu condicions basades en atributs a regles i subregles existents o afegiu-les a una regla nova.

1. Desfeu i refeu canvis en crear el segment.

L'exemple anterior il·lustra la capacitat de segmentació. Hem definit un segment per als clients que han comprat almenys 500 $ de béns en línia *i* tenen interès en el desenvolupament de programari.

## <a name="create-a-new-segment-with-segment-builder"></a>Creeu un segment nou amb el creador de segments

1. Aneu a **Segments**.

1. Seleccioneu **Crea** > **Crea'n un de propi**. A la pàgina del creador de segments, definiu o redacteu regles. Una regla consta d'una o més condicions que defineixen un conjunt de clients.

   > [!NOTE]
   > Per a entorns basats en comptes d'empresa, seleccioneu **Segment nou** > **de comptes** o **Segment de contactes (visualització prèvia)** en funció del tipus de segment que vulgueu crear. Si s'ha definit una [jerarquia](relationships.md#set-up-account-hierarchies) de comptes i voleu crear regles per filtrar les dades en funció de la relació entre els fills i els pares, seleccioneu **Utilitza la jerarquia? (vista prèvia),** seleccioneu la jerarquia i, a continuació **, aplica**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Subfinestra de selecció de segments de la jerarquia de comptes.":::

1. Seleccioneu **Edita els detalls** al costat del segment Sense títol. Proporcioneu un nom per al segment i actualitzeu el **Nom de l'entitat de sortida** suggerit per al segment. Opcionalment, afegiu una descripció i [etiquetes](work-with-tags-columns.md#manage-tags) al segment.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Edita els detalls del quadre de diàleg.":::

1. A la **secció Regla1**, trieu un atribut d'una entitat per la qual voleu filtrar els clients. Hi ha dues maneres de triar atributs:
   - Reviseu la llista d'entitats i atributs disponibles a la subfinestra **Afegeix a la regla** i seleccioneu la icona **+** que hi ha al costat de l'atribut que voleu afegir. Trieu si voleu afegir l'atribut a una regla existent o utilitzar-lo per crear una regla nova.
   - Escriviu el nom de l'atribut a la secció de la regla per veure els suggeriments coincidents.

1. Trieu els operadors per especificar els valors coincidents de la condició. L'atribut pot tenir un d'aquests quatre tipus de dades com a valor: numèric, cadena, data o booleà. Segons el tipus de dades de l'atribut, hi ha disponibles diferents operadors per especificar la condició.

1. Seleccioneu **Afegeix una condició** per afegir més condicions a una regla. Per crear una regla a sota de la regla actual, seleccioneu **Afegeix una subregla**.

1. Si una norma utilitza altres entitats que no siguin l'entitat Client (o *l'entitat* ContactProfile *per a la B a la B), seleccioneu* Defineix el camí de **relació per assignar l'entitat seleccionada a l'entitat client unificada.** Si només hi ha un camí de relació possible, el sistema el selecciona automàticament. Diferents [camins de](relationships.md#relationship-paths) relació poden donar resultats diferents. Cada regla pot tenir el seu propi camí de relació.

   :::image type="content" source="media/relationship-path.png" alt-text="Possible camí de relació en crear una regla basada en una entitat assignada a l'entitat de client unificada.":::

1. Si teniu diverses condicions en una regla, trieu quin operador lògic les connecta.  
   - Operador **I**: cal complir totes les condicions per incloure un registre al segment. Utilitzeu aquesta opció quan definiu condicions entre diferents entitats.
   - Operador **O**: cal complir una de les condicions per incloure un registre al segment. Utilitzeu aquesta opció quan definiu diverses condicions per a la mateixa entitat.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regla amb dues condicions I.":::

   Quan utilitzeu l'operador O, totes les condicions s'han de basar en entitats incloses al camí de la relació.

1. Per crear diferents conjunts de registres de clients, creeu diverses regles. Per incloure els clients necessaris per al teu cas d'empresa, combina grups. En concret, si no podeu incloure una entitat en una regla a causa del camí de relació especificat, creeu-ne una de nova per triar-ne els atributs.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Afegiu una regla nova a un segment i trieu l'operador de conjunt.":::

   1. Seleccioneu **Afegeix una regla**.
   1. Seleccioneu un dels operadors de conjunts: **Union**, **Intersect** o **Except**.

      - **Unió** uneix els dos grups.
      - **Intersecció** solapa els dos grups. Al grup unificat, només hi queden dades *comunes* a ambdós grups.
      - **Excepte** combina els dos grups. Només es conserven les dades del grup A que *no són comunes* a les dades del grup B.

1. Per defecte, l'entitat de sortida contindrà automàticament tots els atributs dels perfils de client que coincideixin amb els filtres definits. En B a B quan s'utilitza l'entitat *ContactProfile*, l'identificador de compte s'inclou automàticament. Si un segment es basa en altres entitats que no siguin l'entitat *Client* o per incloure més atributs del *ContactProfile*, seleccioneu **Atributs** de projecte per afegir més atributs d'aquestes entitats a l'entitat de sortida.
 
   Per exemple: un segment es basa en una entitat que conté dades de compra, que està relacionada amb l'entitat *Client*. El segment cerca tots els clients d'Espanya que han adquirit productes a l'any actual. Podeu afegir atributs com ara el preu dels productes o la data de compra a tots els registres de clients coincidents a l'entitat de sortida. Aquesta informació pot ser útil per analitzar correlacions de temporada en el total de la despesa.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemple d'atributs previstos seleccionats a la subfinestra lateral per afegir-se a l'entitat de sortida.":::
 
   Una sortida de mostra d'un segment basat en comptes empresarials amb atributs previstos de contactes podria tenir aquest aspecte:

   |ID  |Nom del compte  |Ingressos  |Nom del contacte  | Funció de contacte|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100 000 | [Abbie Moss, Ruth Soto]  | [Director general, cap del proveïment]

   > [!NOTE]
   > - **Els atributs** del projecte només funcionen per a entitats que tenen una relació d'un a molts amb l'entitat *Client* o *ContactProfile*. Per exemple, un client pot tenir diverses subscripcions.
   > - Si l'atribut que voleu projectar és a més d'un pas de l'entitat *Client* o *ContactProfile*, tal com es defineix per la relació, aquest atribut s'ha d'utilitzar en totes les regles de la consulta del segment que esteu construint.
   > - Si l'atribut que voleu projectar és a només un sol pas de l'entitat *Client* o *ContactProfile*, aquest atribut no ha d'estar present a totes les regles de la consulta del segment que esteu construint.
   > - Els **atributs projectats** es factoritzen quan s'utilitzen operadors de conjunts.

1. Seleccioneu **Executa** per crear el segment. Seleccioneu **Desa** si voleu mantenir la configuració actual i executar el segment més tard. Es **mostra la pàgina Segments**.

### <a name="segment-builder-tips"></a>Consells per al creador de segments

Quan creeu un segment amb el creador de segments, tingueu en compte els consells següents:

- El creador de segments no suggerirà valors vàlids de les entitats quan es configurin els operadors per a les condicions. Podeu anar a **Dades** > **Entitats** i baixar les dades de l'entitat per veure quins valors estan disponibles.
- Les condicions basades en dates us permeten canviar entre dates fixes i un interval de dates flotant.
- Si teniu diverses regles per al segment, la regla que esteu editant té una línia blava vertical al seu costat.
- Podeu desplaçar regles i condicions a altres llocs de la definició del segment. Seleccioneu l'el·lipsi vertical (&vellip;) al costat d'una regla o condició i trieu com i on moure-la.
- Els controls **Desfés** i **Refés** de la barra d'ordres us permeten desfer i refer els canvis.
- Després de crear un segment, alguns segments us permeten fer [un seguiment de l'ús del segment](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Passos següents

[Exporteu un segment](export-destinations.md) i exploreu la [integració amb la targeta de client](customer-card-add-in.md) per utilitzar segments en altres aplicacions.

[!INCLUDE [footer-include](includes/footer-banner.md)]
