---
title: Crear segments amb el creador de segments
description: Creeu segments de clients per agrupar-los segons diversos atributs.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494480"
---
# <a name="create-segments"></a>Crear segments

Definiu filtres complexos per a l'entitat de client unificada i les entitats relacionades. Cada segment, després del processament, crea un conjunt de registres de client que podeu exportar i on podeu prendre mesures. Els segments s'administren a la pàgina **Segments**. Podeu [crear segments nous](#create-a-new-segment) mitjançant el [creador de segments](#segment-builder) o [crear segments ràpids](#quick-segments) des d'altres àrees de l'aplicació.

## <a name="segment-builder"></a>Creador de segments

La imatge següent il·lustra els diferents aspectes del creador de segments. Mostra un segment que resulta en un grup de clients. Els clients han demanat béns en un període de temps específic i han recollit diversos punts de recompensa o han gastat una determinada quantitat de diners. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elements del creador de segments." lightbox="media/segment-builder-overview.png":::

1 - Organitzeu el segment amb regles i subregles. Cada regla o subregles consta de condicions. Combinar les condicions amb operadors lògics

2 - Trieu el [camí de la relació](relationships.md) entre les entitats que s'apliquen a una regla. El camí de la relació determina quins atributs es poden utilitzar en una condició.

3 - Administreu regles i subregles. Canvieu la posició d'una regla o suprimiu-la.

4 - Afegiu condicions i creeu el nivell adequat d'imbricació amb subregles

5- Apliqueu operacions de conjunt a les regles connectades.

6 - Utilitzeu la subfinestra d'atributs per afegir atributs d'entitat disponibles o crear condicions segons els atributs. A la subfinestra es mostra la llista d'entitats i d'atributs, segons el camí de relació seleccionat, que estan disponibles per a la regla seleccionada.

7 - Afegiu condicions basades en atributs a regles i subregles existents o afegiu-les a una regla nova.

8 - Desfés i refés canvis en crear el segment.

L'exemple anterior il·lustra la capacitat de segmentació. Hem definit un segment per als clients que han comprat almenys 500 $ de béns en línia *i* tenen interès en el desenvolupament de programari.

## <a name="create-a-new-segment"></a>Crear un segment nou

Hi ha diverses maneres de crear un segment nou. Aquesta secció descriu com crear el vostre propi segment de zero. També podeu crear un *segment ràpid* basat en entitats existents o utilitzar els models d'aprenentatge automàtic per obtenir *segments suggerits*. Més informació: [Informació general dels segments](segments.md).

En crear un segment, podeu desar un esborrany. Es desarà com un segment inactiu i no es podrà activar fins que s'hagi acabat amb una configuració vàlida.

1. Aneu a la pàgina **Segments**.

1. Seleccioneu **Crea** > **Crea'n un de propi**.

1. A la pàgina del creador de segments, definiu la primera regla. Una regla consta d'una o més condicions i defineix un conjunt de clients.

1. A la secció **Rule1**, trieu un atribut d'una entitat per a la qual voleu filtrar els clients. Hi ha dues maneres de triar atributs: 
   - Reviseu la llista d'entitats i atributs disponibles a la subfinestra **Afegeix a la regla** i seleccioneu la icona **+** que hi ha al costat de l'atribut que voleu afegir. Trieu si voleu afegir l'atribut a una regla existent o utilitzar-lo per crear una regla nova.
   - Escriviu el nom de l'atribut a la secció de la regla per veure els suggeriments coincidents.

1. Trieu els operadors per especificar els valors coincidents de la condició. L'atribut pot tenir un d'aquests quatre tipus de dades com a valor: numèric, cadena, data o booleà. Segons el tipus de dades de l'atribut, hi ha disponibles diferents operadors per especificar la condició. 

1. Seleccioneu **Afegeix una condició** per afegir més condicions a una regla. Per crear una regla a sota de la regla actual, seleccioneu **Afegeix una subregla**.

1. Si una regla utilitza entitats que no no són l'entitat *Client*, heu de definir el camí de la relació. El camí de la relació és necessari per a informar el sistema sobre quines relacions voleu que accedeixin a l'entitat de client unificada. Seleccioneu **Defineix el camí de la relació** per assignar l'entitat seleccionada a l'entitat de client unificada. Si només hi ha un camí de relació possible, el sistema el seleccionarà automàticament. Les diferents rutes de relació poden donar resultats diferents. Cada regla pot tenir el seu propi camí de relació.

   :::image type="content" source="media/relationship-path.png" alt-text="Possible camí de relació en crear una regla basada en una entitat assignada a l'entitat de client unificada.":::

   Per exemple, l'entitat *eCommerce_eCommercePurchases* de la captura de pantalla té quatre opcions per assignar a l'entitat *Client*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Client
   - eCommerce_eCommercePurchases > Client
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Client
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Client En triar l'última opció, podem incloure atributs de totes les entitats enumerades a les condicions de la regla. És probable que rebem menys resultats perquè els registres de client que coincideixin han de formar part de totes les entitats. En aquest exemple, ha d'haver adquirit béns mitjançant e-commerce(*eCommerce_eCommercePurchases*), en un punt de venda (*POS_posPurchases*), i participar en el nostre programa de fidelitat (*loyaltyScheme_loyCustomers*). Quan trieu la segona opció, només es poden triar els atributs d'*eCommerce_eCommercePurchases* i l'entitat *Client*. Això probablement troba més perfils de client.

1. Si teniu diverses condicions en una regla, podeu triar l'operador lògic que les connecta.

   - Operador **I**: cal complir totes les condicions per incloure un registre al segment. Aquesta opció és més útil quan definiu les condicions entre diverses entitats diferents.

   - Operador **O**: cal complir una de les condicions per incloure un registre al segment. Aquesta opció és més útil quan definiu diverses condicions per a la mateixa entitat.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regla amb dues condicions I.":::

   Quan utilitzeu l'operador O, totes les condicions s'han de basar en entitats incloses al camí de la relació.

   1. Podeu crear diverses regles per crear diferents conjunts de registres de client. Podeu combinar grups per incloure els clients necessaris per al cas empresarial. Per crear una regla nova, seleccioneu **Afegeix una regla**. En concret, si no podeu incloure cap entitat en una regla a causa del camí de relació especificat, heu de crear una regla nova per triar-ne els atributs.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Afegiu una regla nova a un segment i trieu l'operador de conjunt.":::

   1. Seleccioneu un dels operadors de conjunts: **Union**, **Intersect** o **Except**.

   - **Unió** uneix els dos grups.

   - **Intersecció** solapa els dos grups. Només es conserven al grup unificat les dades *que siguin comunes* a tots dos grups.

   - **Excepte** combina els dos grups. Només es conserven les dades del grup A que *no siguin comunes* a les dades del grup B.

1. Per defecte, els segments generen l'entitat de sortida que conté tots els atributs dels perfils de client que coincideixen amb els filtres definits. Si un segment es basa en entitats que no són l'entitat *Client*, podeu afegir més atributs d'aquestes entitats a l'entitat de sortida. Seleccioneu **Atributs del projecte** per triar els atributs que s'annexaran a l'entitat de sortida.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemple d'atributs previstos seleccionats a la subfinestra lateral per afegir-se a l'entitat de sortida.":::
  
   Exemple: un segment es basa en una entitat que conté dades de compra, que està relacionada amb l'entitat *Client*. El segment cerca tots els clients d'Espanya que han adquirit productes a l'any actual. Podeu triar annexar atributs, com el preu dels béns o la data de compra a tots els registres de client que coincideixin a l'entitat de sortida. Aquesta informació pot ser útil per analitzar correlacions de temporada en el total de la despesa.

   > [!NOTE]
   > - Els atributs previstos només funcionen per a les entitats que tenen una relació d'un a diversos amb l'entitat de client. Per exemple, un client pot tenir diverses subscripcions.
   > - Només podeu projectar els atributs d'una entitat que s'utilitzi a cada regla de consulta de segment que esteu creant.
   > - Els atributs previstos es factoritzen quan s'utilitzen operadors de conjunts.

1. Abans de desar i executar el segment, seleccioneu **Edita els detalls** al costat del nom del segment. Proporcioneu un nom per al segment i actualitzeu el **Nom de l'entitat de sortida** suggerit per al segment. També podeu afegir una descripció al segment.

1. Seleccioneu **Executa** per desar i processar el segment si es validen tots els requisits. Altrament, es desarà com a esborrany de segment inactiu.

1. Seleccioneu **Torna als segments** per tornar a la pàgina **Segments**.

> [!TIP]
> - El creador de segments no suggerirà valors vàlids de les entitats quan es configurin els operadors per a les condicions. Podeu anar a **Dades** > **Entitats** i baixar les dades de l'entitat per veure quins valors estan disponibles.
> - Les condicions segons les dates permeten canviar entre dates fixes i un interval de dates flotant.
> - Si teniu diverses regles per al segment, trobareu una barra blava al voltant de la regla que esteu editant.
> - Podeu desplaçar regles i condicions a altres llocs de la definició del segment. Seleccioneu [...] al costat d'una regla o condició i trieu com i on la voleu desplaçar.
> - Els controls **Desfés** i **Refés** de la barra d'ordres us permeten refer els canvis.

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

    > [!div class="mx-imgBorder"]
    > ![Nom i estimació per a un segment ràpid.](media/quick-segment-name.png "Nom i estimació per a un segment ràpid")

5. Proporcioneu un **Nom** per al segment. Opcionalment, proporcioneu un **Nom de visualització**.

6. Seleccioneu **Desa** per crear el segment.

7. Quan el segment s'hagi acabat de processar, podeu visualitzar-lo com qualsevol altre segment que hàgiu creat.

## <a name="next-steps"></a>Passos següents

[Exporteu un segment](export-destinations.md) i exploreu la [integració amb la targeta de client](customer-card-add-in.md) per utilitzar segments en altres aplicacions.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
