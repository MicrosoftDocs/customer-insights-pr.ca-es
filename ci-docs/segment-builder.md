---
title: Creeu segments complexos amb el creador de segments
description: Utilitzeu el creador de segments per crear segments de clients complexos agrupant-los en funció de diversos atributs.
ms.date: 03/25/2022
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
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170623"
---
# <a name="create-complex-segments-with-segment-builder"></a>Creeu segments complexos amb el creador de segments

Definiu filtres complexos per a l'entitat de client unificada i les entitats relacionades. Cada segment, després del processament, crea un conjunt de registres de client que podeu exportar i on podeu prendre mesures.

> [!TIP]
> Els segments basats en **clients individuals** inclouen automàticament la informació de contacte disponible per als membres del segment. En entorns de **comptes empresarials**, els segments es basen en comptes (empreses o filials). Per incloure informació de contacte en un segment, utilitzeu la funcionalitat **Atributs del projecte** al creador de segments. Assegureu-vos que les fonts de dades del contacte [s'assignen de manera semàntica a l'entitat ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

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

1. Seleccioneu **Edita els detalls** al costat del segment Sense títol. Proporcioneu un nom per al segment i actualitzeu el **Nom de l'entitat de sortida** suggerit per al segment. Opcionalment, afegiu una descripció i [etiquetes](work-with-tags-columns.md#manage-tags) al segment.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Edita els detalls del quadre de diàleg.":::

1. A la **secció Regla1**, trieu un atribut d'una entitat per la qual voleu filtrar els clients. Hi ha dues maneres de triar atributs:
   - Reviseu la llista d'entitats i atributs disponibles a la subfinestra **Afegeix a la regla** i seleccioneu la icona **+** que hi ha al costat de l'atribut que voleu afegir. Trieu si voleu afegir l'atribut a una regla existent o utilitzar-lo per crear una regla nova.
   - Escriviu el nom de l'atribut a la secció de la regla per veure els suggeriments coincidents.

1. Trieu els operadors per especificar els valors coincidents de la condició. L'atribut pot tenir un d'aquests quatre tipus de dades com a valor: numèric, cadena, data o booleà. Segons el tipus de dades de l'atribut, hi ha disponibles diferents operadors per especificar la condició. Per als segments amb comptes empresarials, hi ha dos operadors especials disponibles per incloure jerarquies potencials entre els comptes ingerits. Utilitzeu els operadors *secundari de* i *principal de* per incloure comptes relacionats.

1. Seleccioneu **Afegeix una condició** per afegir més condicions a una regla. Per crear una regla a sota de la regla actual, seleccioneu **Afegeix una subregla**.

1. Si una norma utilitza altres entitats que no siguin l'entitat Client *, seleccioneu* Defineix el **camí de** relació per assignar l'entitat seleccionada a l'entitat de client unificada. Si només hi ha un camí de relació possible, el sistema el selecciona automàticament. Diferents [camins de](relationships.md#relationship-paths) relació poden donar resultats diferents. Cada regla pot tenir el seu propi camí de relació.

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

1. Per defecte, l'entitat de sortida contindrà automàticament tots els atributs dels perfils de client que coincideixin amb els filtres definits. Si un segment es basa en altres entitats que no siguin l'entitat *client*, seleccioneu **Atributs** de projecte per afegir més atributs d'aquestes entitats a l'entitat de sortida.

   > [!IMPORTANT]
   > Per als segments basats en comptes d'empresa, s'han d'incloure al segment les dades d'un o més contactes de cada compte de l'entitat *ContactProfile* per permetre que aquest segment s'activi o s'exporti a destinacions que requereixin informació de contacte. Per obtenir més informació sobre l'entitat *ContactProfile*, vegeu [Assignacions semàntiques](semantic-mappings.md).
   > Una sortida de mostra d'un segment basat en comptes empresarials amb atributs previstos de contactes podria tenir aquest aspecte:
   >
   > |ID  |Nom del compte  |Ingressos  |Nom del contacte  | Funció de contacte|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 000 | [Abbie Moss, Ruth Soto]  | [Director general, cap del proveïment]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemple d'atributs previstos seleccionats a la subfinestra lateral per afegir-se a l'entitat de sortida.":::
  
   Per exemple: un segment es basa en una entitat que conté dades de compra, que està relacionada amb l'entitat *Client*. El segment cerca tots els clients d'Espanya que han adquirit productes a l'any actual. Podeu afegir atributs com ara el preu dels productes o la data de compra a tots els registres de clients coincidents a l'entitat de sortida. Aquesta informació pot ser útil per analitzar correlacions de temporada en el total de la despesa.

   > [!NOTE]
   > - Els **atributs de projecte** només funcionen per a les entitats que tenen una relació d'un a diversos amb l'entitat de client. Per exemple, un client pot tenir diverses subscripcions.
   > - Si l'atribut que voleu projectar és a més d'un salt de l'entitat *Client*, segons ho defineix la relació, aquest atribut s'ha d'utilitzar a cada regla de la consulta de segment que esteu creant.
   > - Si l'atribut que voleu projectar és a només un salt de l'entitat *Client*, aquest atribut no cal que estigui present a cada regla de la consulta de segment que esteu creant.
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
