---
title: Relacions entre entitats i camins d'entitats
description: Creeu i administreu relacions entre entitats procedents de diverses fonts de dades.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171152"
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

1. A les conclusions del públic, aneu a **Dades** > **Relacions**.

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

## <a name="view-relationships"></a>Visualitza relacions

A la pàgina Relacions s'enumeren totes les relacions que s'han creat. Cada fila representa una relació, que també inclou detalls sobre l'entitat d'origen, l'entitat de destinació i la cardinalitat. 

:::image type="content" source="media/relationships-list.png" alt-text="Llista de relacions i opcions de la barra d'accions de la pàgina Relacions.":::

Aquesta pàgina ofereix un conjunt d'opcions per a relacions existents i noves: 
- **Relació nova**: [Crea una relació personalitzada](#create-a-custom-relationship).
- **Visualitzador**: [Exploreu el visualitzador de relacions](#explore-the-relationship-visualizer) per veure un diagrama de xarxa de les relacions existents i de la seva cardinalitat.
- **Filtra per**: trieu el tipus de relacions que es mostraran a la llista.
- **Cerca relacions**: utilitzeu una cerca basada en text en les propietats de les relacions.

### <a name="explore-the-relationship-visualizer"></a>Explorar el visualitzador de relacions

El visualitzador de relacions mostra un diagrama de xarxa de les relacions existents entre les entitats connectades i la seva cardinalitat.

Per personalitzar la visualització, podeu canviar la posició dels quadres arrossegant-los al llenç.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de pantalla del diagrama de xarxa del visualitzador de relacions amb connexions entre entitats relacionades.":::

Opcions disponibles: 
- **Exporta com a imatge**: deseu la visualització actual com a fitxer d'imatge.
- **Canvia a la disposició horitzontal/vertical**: canvieu l'alineació de les entitats i les relacions.
- **Edita**: actualitzeu les propietats de les relacions personalitzades a la subfinestra d'edició i deseu els canvis.

## <a name="manage-existing-relationships"></a>Administrar le relacions existents 

A la pàgina Relacions, una fila representa cada relació. 

Seleccioneu una relació i trieu una de les opcions següents: 
 
- **Edita**: actualitzeu les propietats de les relacions personalitzades a la subfinestra d'edició i deseu els canvis.
- **Suprimeix**: suprimiu relacions personalitzades.
- **Visualitza**: visualitzeu relacions creades pel sistema i heretades. 

## <a name="next-step"></a>Pas següent

Les relacions de sistema i les personalitzades s'utilitzen per [crear segments](segments.md) basats en diverses fonts de dades que ja no estan aïllades.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
