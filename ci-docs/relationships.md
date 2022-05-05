---
title: Relacions entre entitats i camins d'entitats
description: Creeu i administreu relacions entre entitats procedents de diverses fonts de dades.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: a7b10d985d5cba64b25595a3d7c101d6cb5c62a5
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642410"
---
# <a name="relationships-between-entities"></a>Relacions entre entitats

Les relacions connecten entitats i defineixen una gràfica de les dades quan les entitats comparteixen un identificador comú, una externa. Es pot fer referència a aquesta clau externa d'una entitat a una altra. Les entitats connectades permeten definir segments i mesures segons diverses fonts de dades.

Hi ha tres tipus de relacions: 
- Relacions del sistema no editables creades pel sistema com a part del procés d'unificació de dades
- Relacions heretades no editables que es creen automàticament a partir de la ingesta de fonts de dades 
- Relacions personalitzades editables creades i configurades per usuaris

## <a name="non-editable-system-relationships"></a>Relacions del sistema no editables

Durant la unificació de dades, les relacions del sistema es creen automàticament a partir d'una coincidència intel·ligent. Aquestes relacions ajuden a relacionar els registres de perfil del client amb registres corresponents. El diagrama següent il·lustra la creació de tres relacions basades en el sistema. L'entitat de client es fa coincidir amb altres entitats per produir l'entitat *Client* unificada.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama amb rutes de relació de l'entitat de client amb tres relacions d'1 a n.":::

- Es crea una **relació *CustomerToContact*** entre l'entitat *Client* i l'entitat *Contacte*. L'entitat *Client* obté el camp clau **Contact_contactID** per relacionar-se amb el camp clau **contactID** de l'entitat *Contacte*.
- Es crea una **relació *CustomerToAccount*** entre l'entitat *Client* i l'entitat *Compte*. L'entitat *Client* obté el camp clau **Account_contactID** per relacionar-se amb el camp clau **accountID** de l'entitat *Compte*.
- Es crea una **relació *CustomerToWebAccount*** entre l'entitat *Client* i l'entitat *WebAccount*. L'entitat *Client* obté el camp clau **WebAccount_webaccountID** per relacionar-se amb el camp clau **webaccountID** de l'entitat *WebAccount*.

## <a name="non-editable-inherited-relationships"></a>Relacions heretades no editables

Durant el procés d'ingestió de dades, el sistema comprova les fonts de dades per si hi ha relacions existents. Si no hi ha cap relació, el sistema les crea automàticament. Aquestes relacions s'utilitzen també en processos descendents.

## <a name="create-a-custom-relationship"></a>Crear una relació personalitzada

La relació consisteix en una *entitat d'origen* que conté la clau externa i una *entitat de destinació* a la qual assenyala la clau externa de l'entitat d'origen. 

1. Aneu a **Dades** > **Relacions**.

2. Seleccioneu **Nova relació**.

3. A la subfinestra **Relació nova**, proporcioneu la informació següent:

   :::image type="content" source="media/relationship-add.png" alt-text="Subfinestra lateral de relació nova amb camps d'entrada buits.":::

   - **Nom de la relació**: nom que reflecteix la finalitat de la relació. Exemple: CustomerToSupportCase.
   - **Descripció**: descripció de la relació.
   - **Entitat d'origen**: entitat que s'utilitza com a origen a la relació. Exemple: SupportCase.
   - **Entitat d'arribada**: entitat que s'utilitza com a arribada de la relació. Exemple: Client.
   - **Cardinalitat d'origen**: especifiqueu la cardinalitat de l'entitat d'origen. La cardinalitat descriu el nombre d'elements possibles en un conjunt. Sempre es relaciona amb la cardinalitat de destinació. Podeu triar entre **Una** i **Diverses**. Només s'admeten les relacions de diversos a un i d'un a un.  
     - De diversos a un: diversos registres d'origen poden relacionar-se amb un registre de destinació. Exemple: diversos casos de suport d'un únic client.
     - Un a un: un registre d'origen únic està relacionat amb un registre de destinació. Exemple: un identificador de fidelitat d'un únic client.

     > [!NOTE]
     > Les relacions de diversos a diversos es poden crear amb dues relacions de diversos a un i una entitat que enllaça que connecta l'entitat d'origen i l'entitat de destinació.

   - **Cardinalitat de destinació**: seleccioneu la cardinalitat dels registres de l'entitat de destinació. 
   - **Camp clau d'origen**: camp clau d'origen de l'entitat d'origen. Exemple: SupportCase podria utilitzar CaseID com a camp clau extern.
   - **Camp de clau de destinació**: el camp de clau de l'entitat de destinació. Exemple: Client podria utilitzar el camp clau **CustomerID**.

4. Seleccioneu **Desa** per crear la connexió personalitzada.

## <a name="set-up-account-hierarchies"></a>Configurar jerarquies de comptes

Els entorns configurats per utilitzar comptes empresarials com a públic principal de destinació poden configurar jerarquies de comptes per als comptes empresarials relacionats. Per exemple, una empresa que té unitats de negoci independents. 

Les organitzacions creen jerarquies de comptes per administrar millor els comptes i les seves relacions entre si. El Customer Insights admet les jerarquies de comptes pare-fill que ja existeixen a les dades de clients ingerides. Per exemple, comptes del Dynamics 365 Sales. Aquestes jerarquies es poden configurar a la **pàgina Relacions**.

1. Aneu a **Dades** > **Relacions**.
1. Seleccioneu la pestanya **Jerarquia del compte**.
1. Seleccioneu **Nova jerarquia de comptes**. 
1. A la subfinestra **Jerarquia de comptes**, proporcioneu un nom per a la jerarquia. El sistema crea un nom per a l'entitat de sortida. Podeu canviar el nom de l'entitat de sortida.
1. Seleccioneu l'entitat que conté la jerarquia de comptes. Normalment és a la mateixa entitat que conté els comptes.
1. Seleccioneu l'**ID del compte** i l'**ID principal del compte** de l'entitat seleccionada 
1. Seleccioneu **Desa** per aplicar la configuració i finalitzar la jerarquia de comptes.

## <a name="view-relationships"></a>Visualitza relacions

A la pàgina Relacions s'enumeren totes les relacions que s'han creat. Cada fila representa una relació, que també inclou detalls sobre l'entitat d'origen, l'entitat de destinació i la cardinalitat. 

:::image type="content" source="media/relationships-list.png" alt-text="Llista de relacions i opcions de la barra d'accions de la pàgina Relacions.":::

Aquesta pàgina ofereix un conjunt d'opcions per a relacions existents i noves: 
- **Relació nova**: [Crea una relació personalitzada](#create-a-custom-relationship).
- **Visualitzador**: [Exploreu el visualitzador de relacions](#explore-the-relationship-visualizer) per veure un diagrama de xarxa de les relacions existents i de la seva cardinalitat.
- **Filtra per**: trieu el tipus de relacions que es mostraran a la llista.
- **Cerca relacions**: utilitzeu una cerca basada en text en les propietats de les relacions.

### <a name="explore-the-relationship-visualizer"></a>Explorar el visualitzador de relacions

El visualitzador de relacions mostra un diagrama de xarxa de les relacions existents entre les entitats connectades i la seva cardinalitat. També visualitza el camí de la relació.

Per personalitzar la visualització, podeu canviar la posició dels quadres arrossegant-los al llenç.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de pantalla del diagrama de xarxa del visualitzador de relacions amb connexions entre entitats relacionades.":::

Opcions disponibles: 
- **Exporta com a imatge**: deseu la visualització actual com a fitxer d'imatge.
- **Canvia a la disposició horitzontal/vertical**: canvieu l'alineació de les entitats i les relacions.
- **Edita**: actualitzeu les propietats de les relacions personalitzades a la subfinestra d'edició i deseu els canvis.

## <a name="relationship-paths"></a>Camins de relació

Un camí de relació descriu les entitats que estan connectades amb relacions entre una entitat d'origen i una entitat de destinació. S'utilitza quan es crea un segment o una mesura que inclou altres entitats que no són l'entitat de perfil unificada i hi ha diverses opcions per arribar a l'entitat de perfil unificada. 

Un camí de relació informa el sistema sobre quines relacions calen per accedir a l'entitat de perfil unificada. Les diferents rutes de relació poden donar resultats diferents.

Per exemple, l'entitat *eCommerce_eCommercePurchases* té les relacions següents amb l'entitat del *client* del perfil unificat:

- eCommerce_eCommercePurchases > Client
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Client
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Client 

Un camí de relació determina quines entitats podeu utilitzar quan creeu regles per a mesures o segments. Triar l'opció amb el camí de relació més llarg produirà menys resultats perquè els registres coincidents han de formar part de totes les entitats. En aquest exemple, un client ha d'haver adquirit béns mitjançant e-commerce(eCommerce_eCommercePurchases) en un punt de venda (POS_posPurchases) i participar en el nostre programa de fidelitat (loyaltyScheme_loyCustomers). Quan trieu la primera opció, és probable que rebeu més resultats perquè els clients només han d'existir en una entitat addicional.

### <a name="direct-relationship"></a>Relació directa

Una relació es classifica com una **relació directa** quan una entitat d'origen es relaciona amb una entitat de destinació amb només una relació.

Per exemple, si una entitat d'activitat anomenada *eCommerce_eCommercePurchases* connecta a una entitat de destinació *eCommerce_eCommerceContacts* només a través de *ContactId*, és una relació directa.

:::image type="content" source="media/direct_Relationship.png" alt-text="L'entitat d'origen es connecta directament a l'entitat de destinació.":::

#### <a name="multi-path-relationship"></a>Relació de diversos camins

Una **relació de diversos camins** és un tipus especial de relació directa que connecta una entitat d'origen a més d'una entitat de destinació.

Per exemple, si una entitat d'activitat anomenada *eCommerce_eCommercePurchases* es relaciona amb dues entitats de destinació, *eCommerce_eCommerceContacts* i *loyaltyScheme_loyCustomers*, és una relació de diversos camins.

:::image type="content" source="media/multi-path_relationship.png" alt-text="L'entitat d'origen es connecta directament a més d'una entitat de destinació a través d'una relació de diversos salts.":::

### <a name="indirect-relationship"></a>Relació indirecta

Una relació es classifica com una **relació indirecta** quan una entitat d'origen es relaciona amb un o més entitats addicionals abans de relacionar-se amb una entitat de destinació.

#### <a name="multi-hop-relationship"></a>Relació de diversos salts

Una *relació de diversos salts* és una *relació indirecta* que permet connectar una entitat d'origen a una entitat de destinació a través d'una o diverses entitats intermèdies.

Per exemple, si una entitat d'activitat anomenada *eCommerce_eCommercePurchasesWest* es connecta a una entitat intermèdia anomenada *eCommerce_eCommercePurchasesEast* i després es connecta a una entitat de destinació anomenada *eCommerce_eCommerceContacts*, es tracta d'una relació de diversos salts.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="L'entitat d'origen es connecta directament a una entitat de destinació amb una entitat intermèdia.":::

### <a name="multi-hop-multi-path-relationship"></a>Relació de diversos salts i de diversos camins

Les relacions de diversos salts i diversos camins es poden utilitzar per crear **relacions de diversos salts i diversos camins**. Aquest tipus especial combina les funcions de les **relacions de diversos salts** i les **relacions de diversos camins**. Us permet connectar-vos a més d'una entitat de destinació quan utilitzeu entitats intermèdies.

Per exemple, si una entitat d'activitat anomenada *eCommerce_eCommercePurchasesWest* es connecta a una entitat intermèdia anomenada *eCommerce_eCommercePurchasesEast* i després es connecta a dues entitats de destinació anomenades *eCommerce_eCommerceContacts* i *loyaltyScheme_loyCustomers*, es tracta d'una relació de diversos salts i diversos camins.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="L'entitat d'origen es connecta directament a una entitat de destinació i es connecta a una altra entitat de destinació a través d'una entitat intermèdia.":::

## <a name="manage-existing-relationships"></a>Administrar le relacions existents 

A la pàgina Relacions, una fila representa cada relació. 

Seleccioneu una relació i trieu una de les opcions següents: 
 
- **Edita**: actualitzeu les propietats de les relacions personalitzades a la subfinestra d'edició i deseu els canvis.
- **Suprimeix**: suprimiu relacions personalitzades.
- **Visualitza**: visualitzeu relacions creades pel sistema i heretades. 

## <a name="next-step"></a>Pas següent

Les relacions del sistema i personalitzades s'utilitzen per [crear segments](segments.md) i [mesures](measures.md) basades en diverses fonts de dades que no estan aïllades.

[!INCLUDE [footer-include](includes/footer-banner.md)]
