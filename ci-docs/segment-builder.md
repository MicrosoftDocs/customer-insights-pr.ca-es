---
title: Crear segments amb el creador de segments
description: Creeu segments de clients per agrupar-los segons diversos atributs.
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
ms.openlocfilehash: c8e9e4976ade36c1c3c4f688a667b329bfde6e3e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642341"
---
# <a name="create-segments"></a>Crear segments

Definiu filtres complexos per a l'entitat de client unificada i les entitats relacionades. Cada segment, després del processament, crea un conjunt de registres de client que podeu exportar i on podeu prendre mesures. Els segments s'administren a la pàgina **Segments**. Podeu [crear segments nous](#create-a-new-segment) mitjançant el creador de segments o [crear segments ràpids](#quick-segments) des d'altres àrees de l'aplicació.

> [!TIP]
> - Els segments ràpids només estan admesos als entorns per a **clients individuals**.
> - Els segments basats en **clients individuals** inclouen automàticament la informació de contacte disponible per als membres del segment. En entorns de **comptes empresarials**, els segments es basen en comptes (empreses o filials). Per incloure informació de contacte en un segment, utilitzeu la funcionalitat **Atributs del projecte** al creador de segments. Assegureu-vos que les fonts de dades del contacte [s'assignen de manera semàntica a l'entitat ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Creador de segments

La imatge següent il·lustra els diferents aspectes del creador de segments. Mostra un segment que resulta en un grup de clients. Els clients han demanat productes en un període de temps específic i han recollit punts de recompensa o han gastat una determinada quantitat de diners.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elements del creador de segments." lightbox="media/segment-builder-overview.png":::

1. Organitzeu el segment amb regles i subregles. Cada regla o subregles consta de condicions. Combinar les condicions amb operadors lògics

1. Trieu el [camí de la relació](relationships.md) entre les entitats que s'apliquen a una regla. El camí de la relació determina quins atributs es poden utilitzar en una condició.

1. Administreu regles i subregles. Canvieu la posició d'una regla o suprimiu-la.

1. Afegiu condicions i creeu el nivell adequat d'imbricació amb subregles.

1. Apliqueu operacions de conjunt a les regles connectades.

1. Utilitzeu la subfinestra d'atributs per afegir atributs d'entitat disponibles o crear condicions segons els atributs. A la subfinestra es mostra la llista d'entitats i d'atributs, segons el camí de relació seleccionat, que estan disponibles per a la regla seleccionada.

1. Afegiu condicions basades en atributs a regles i subregles existents o afegiu-les a una regla nova.

1. Desfeu i refeu canvis en crear el segment.

L'exemple anterior il·lustra la capacitat de segmentació. Hem definit un segment per als clients que han comprat almenys 500 $ de béns en línia *i* tenen interès en el desenvolupament de programari.

## <a name="create-a-new-segment"></a>Crear un segment nou

Hi ha diverses maneres de crear un segment nou. Aquesta secció descriu com crear el vostre propi segment de zero. També podeu crear un *segment ràpid* basat en entitats existents o utilitzar els models d'aprenentatge automàtic per obtenir *segments suggerits*. Per obtenir més informació, aneu a la [Informació general dels segments](segments.md).

En crear un segment, podeu desar un esborrany. A la fase d'esborrany, un segment es desa com a segment inactiu. Quan completeu la configuració del segment, executeu-la per activar-lo. També podeu **Activar** un segment des de la pàgina **Tots els segments**.

1. Aneu a la pàgina **Segments**.

1. Seleccioneu **Crea** > **Crea'n un de propi**.

1. A la pàgina del creador de segments, definiu o redacteu regles. Una regla consta d'una o més condicions que defineixen un conjunt de clients.

1. A la **secció Regla 1**, trieu un atribut d'una entitat per la qual voleu filtrar els clients. Hi ha dues maneres de triar atributs:
   - Reviseu la llista d'entitats i atributs disponibles a la subfinestra **Afegeix a la regla** i seleccioneu la icona **+** que hi ha al costat de l'atribut que voleu afegir. Trieu si voleu afegir l'atribut a una regla existent o utilitzar-lo per crear una regla nova.
   - Escriviu el nom de l'atribut a la secció de la regla per veure els suggeriments coincidents.

1. Trieu els operadors per especificar els valors coincidents de la condició. L'atribut pot tenir un d'aquests quatre tipus de dades com a valor: numèric, cadena, data o booleà. Segons el tipus de dades de l'atribut, hi ha disponibles diferents operadors per especificar la condició. Per als segments amb comptes empresarials, hi ha dos operadors especials disponibles per incloure jerarquies potencials entre els comptes ingerits. Utilitzeu els operadors *secundari de* i *principal de* per incloure comptes relacionats.

1. Seleccioneu **Afegeix una condició** per afegir més condicions a una regla. Per crear una regla a sota de la regla actual, seleccioneu **Afegeix una subregla**.

1. Si una regla utilitza entitats que no no són l'entitat *Client*, heu de definir el camí de la relació. El camí de la relació és necessari per a informar el sistema sobre quines relacions voleu que accedeixin a l'entitat de client unificada. Seleccioneu **Defineix el camí de la relació** per assignar l'entitat seleccionada a l'entitat de client unificada. Si només hi ha un camí de relació possible, el sistema el seleccionarà automàticament. Les diferents rutes de relació poden donar resultats diferents. Cada regla pot tenir el seu propi camí de relació.

   :::image type="content" source="media/relationship-path.png" alt-text="Possible camí de relació en crear una regla basada en una entitat assignada a l'entitat de client unificada.":::

   Per exemple, l'entitat *eCommerce_eCommercePurchases* de la captura de pantalla té quatre opcions per assignar a l'entitat *Client*:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Client
   - eCommerce_eCommercePurchases > Client
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Client
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Client En triar l'última opció, podem incloure atributs de totes les entitats enumerades a les condicions de la regla. És probable que rebeu menys resultats perquè els registres de client que coincideixen han de formar part de totes les entitats. En aquest exemple, ha d'haver adquirit béns mitjançant e-commerce(*eCommerce_eCommercePurchases*) en un punt de venda (*POS_posPurchases*) i participar en el nostre programa de fidelitat (*loyaltyScheme_loyCustomers*). Quan trieu la segona opció, només es poden triar els atributs d'*eCommerce_eCommercePurchases* i l'entitat *Client*. Això probablement troba més perfils de client.

1. Si teniu diverses condicions en una regla, podeu triar l'operador lògic que les connecta.  
   - Operador **I**: cal complir totes les condicions per incloure un registre al segment. Aquesta opció és més útil quan definiu les condicions entre diverses entitats diferents.
   - Operador **O**: cal complir una de les condicions per incloure un registre al segment. Aquesta opció és més útil quan definiu diverses condicions per a la mateixa entitat.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regla amb dues condicions I.":::

   Quan utilitzeu l'operador O, totes les condicions s'han de basar en entitats incloses al camí de la relació.

   - Podeu crear diverses regles per crear diferents conjunts de registres de client. Podeu combinar grups per incloure els clients necessaris per al cas empresarial. Per crear una regla nova, seleccioneu **Afegeix una regla**. En concret, si no podeu incloure cap entitat en una regla a causa del camí de relació especificat, heu de crear una regla nova per triar els atributs que la formen.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Afegiu una regla nova a un segment i trieu l'operador de conjunt.":::

   - Seleccioneu un dels operadors de conjunts: **Union**, **Intersect** o **Except**.

      - **Unió** uneix els dos grups.
      - **Intersecció** solapa els dos grups. Al grup unificat, només hi queden dades *comunes* a ambdós grups.
      - **Excepte** combina els dos grups. Només es conserven les dades del grup A que *no són comunes* a les dades del grup B.

1. Per defecte, els segments generen l'entitat de sortida que conté tots els atributs dels perfils de client que coincideixen amb els filtres definits. Si un segment es basa en entitats que no són l'entitat *Client*, podeu afegir més atributs d'aquestes entitats a l'entitat de sortida. Seleccioneu **Atributs del projecte** per triar els atributs que s'annexaran a l'entitat de sortida.

   > [!IMPORTANT]
   > Per als segments basats en comptes empresarials, s'han d'incloure detalls d'un o diversos contactes de cada compte de l'entitat *ContactProfile* al segment per permetre que aquest segment s'activi o s'exporti a destinacions que requereixin informació de contacte. Per obtenir més informació sobre l'entitat *ContactProfile*, vegeu [Assignacions semàntiques](semantic-mappings.md).
   > Una sortida de mostra d'un segment basat en comptes empresarials amb atributs previstos de contactes podria tenir aquest aspecte:
   >
   > |ID  |Nom del compte  |Ingressos  |Nom del contacte  | Funció de contacte|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 000 | [Abbie Moss, Ruth Soto]  | [Director general, cap del proveïment]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemple d'atributs previstos seleccionats a la subfinestra lateral per afegir-se a l'entitat de sortida.":::
  
   Per exemple: un segment es basa en una entitat que conté dades de compra, que està relacionada amb l'entitat *Client*. El segment cerca tots els clients d'Espanya que han adquirit productes a l'any actual. Podeu triar annexar atributs, com el preu dels béns o la data de compra a tots els registres de client que coincideixin a l'entitat de sortida. Aquesta informació pot ser útil per analitzar correlacions de temporada en el total de la despesa.

   > [!NOTE]
   > - Els **atributs de projecte** només funcionen per a les entitats que tenen una relació d'un a diversos amb l'entitat de client. Per exemple, un client pot tenir diverses subscripcions.
   > - Si l'atribut que voleu projectar és a més d'un salt de l'entitat *Client*, segons ho defineix la relació, aquest atribut s'ha d'utilitzar a cada regla de la consulta de segment que esteu creant.
   > - Si l'atribut que voleu projectar és a només un salt de l'entitat *Client*, aquest atribut no cal que estigui present a cada regla de la consulta de segment que esteu creant.
   > - Els **atributs projectats** es factoritzen quan s'utilitzen operadors de conjunts.

1. Seleccioneu **Edita els detalls** que hi ha al costat del segment Sense títol. Proporcioneu un nom per al segment i actualitzeu el **Nom de l'entitat de sortida** suggerit per al segment. Opcionalment, afegiu una descripció i [etiquetes](work-with-tags-columns.md#manage-tags) al segment.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Quadre de diàleg Edita els detalls.":::

1. Seleccioneu **Executa** per desar el segment, activeu-lo i comenceu a processar el segment basant-vos en totes les regles i condicions. Altrament, es desarà com a segment inactiu.

1. Seleccioneu **Torna als segments** per tornar a la pàgina **Segments**.

1. Per defecte, el segment es crea com a segment dinàmic. Això vol dir que el segment s'actualitzarà durant les actualitzacions del sistema. Per [aturar l'actualització automàtica](segments.md#manage-existing-segments), seleccioneu el segment i trieu l'opció **Converteix en estàtic**. Els segments estàtics es poden [actualitzar manualment](segments.md#refresh-segments) en qualsevol moment.

> [!TIP]
> - El creador de segments no suggerirà valors vàlids de les entitats quan es configurin els operadors per a les condicions. Podeu anar a **Dades** > **Entitats** i baixar les dades de l'entitat per veure quins valors estan disponibles.
> - Les condicions segons les dates permeten canviar entre dates fixes i un interval de dates flotant.
> - Si teniu diverses regles per al segment, la regla que esteu editant té una línia blava vertical al seu costat.
> - Podeu desplaçar regles i condicions a altres llocs de la definició del segment. Seleccioneu [...] al costat d'una regla o condició i trieu com i on la voleu desplaçar.
> - Els controls **Desfés** i **Refés** de la barra d'ordres us permeten desfer i refer els canvis.

## <a name="quick-segments"></a>Segments ràpids

Els segments ràpids us permeten crear segments senzills amb un sol operador ràpidament per obtenir informació més ràpida.

1. A la pàgina **Segments**, seleccioneu **Crea** > **Crea de**.
   - Seleccioneu l'opció **Perfils** per crear un segment que es basi en l'entitat de *client unificat*.
   - Seleccioneu l'opció **Mesures** per crear un segment en les mesures que heu creat anteriorment.
   - Seleccioneu l'opció **Intel·ligència** per crear un segment sobre una de les entitats de sortida que heu generat mitjançant les funcionalitats **Prediccions** o **Models personalitzats**.

2. Al quadre de diàleg **Crea un segment ràpid**, seleccioneu un atribut del desplegable **Camp**.

3. El sistema proporcionarà més informació per ajudar-vos a crear segments millorats dels vostres clients.
   - Per als camps categòrics, mostrarem 10 comptes de clients principals. Seleccioneu un **Valor** i seleccioneu **Revisa**.
   - Per a un atribut numèric, el sistema mostrarà quin valor de l'atribut queda en el percentil de cada client. Trieu un **Operador** i un **Valor** i, a continuació, seleccioneu **Revisa**.

4. El sistema us proporcionarà una **Mida de segment aproximada**. Podeu triar si voleu generar el segment que heu definit o, en primer lloc, tornar a examinar-lo per aconseguir una mida diferent del segment.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nom i estimació per a un segment ràpid.":::

5. Proporcioneu un nom **i** un **nom** d'entitat de sortida per al segment. Opcionalment, afegiu [etiquetes](work-with-tags-columns.md#manage-tags).

6. Seleccioneu **Desa** per crear el segment.

7. Quan el segment s'hagi acabat de processar, podeu visualitzar-lo com qualsevol altre segment que hàgiu creat.

## <a name="next-steps"></a>Passos següents

[Exporteu un segment](export-destinations.md) i exploreu la [integració amb la targeta de client](customer-card-add-in.md) per utilitzar segments en altres aplicacions.

[!INCLUDE [footer-include](includes/footer-banner.md)]
