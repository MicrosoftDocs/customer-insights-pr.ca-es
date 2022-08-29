---
title: Seleccioneu els camps d'origen per a la unificació de dades
description: El primer pas en el procés d'unificació és seleccionar entitats, atributs, claus primàries i tipus semàntics per assignar dades al perfil de client unificat.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304553"
---
# <a name="select-source-fields-for-data-unification"></a>Seleccioneu els camps d'origen per a la unificació de dades

El primer pas per a la unificació és seleccionar les entitats i els camps dels conjunts de dades que voleu unificar. Seleccioneu entitats que continguin detalls relacionats amb el client, com ara el nom, l'adreça, el número de telèfon i el correu electrònic. Podeu seleccionar una o més entitats.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Seleccioneu les entitats i els camps

1. Aneu a **Unificar dades** > **·**.

   Per a clients individuals (de B a C), es mostra la **pàgina de destinació Unify** que mostra **Comença** al primer pas, **els camps Origen**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Captura de pantalla d'unificar la pàgina de destinació per a la primera experiència d'execució per a clients concrets.":::

   En el cas dels comptes d'empresa (de B a B), la **pàgina de destinació Unify** mostra **els comptes** Unify que mostra **Comença** al primer pas, **els camps** Origen. Els passos d'Unify **contactes (visualització prèvia)** són opcionals i estan pendents de completar la unificació del compte.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Captura de pantalla d'unify landing page per a la primera experiència d'execució per a comptes d'empresa.":::

1. Seleccioneu **Introducció**.

1. A la pàgina Camps **d'origen**, seleccioneu **Seleccioneu entitats i camps**. Es mostra la **subfinestra Selecciona entitats i camps**.

1. Seleccioneu almenys una entitat.

1. Per a cada entitat seleccionada, identifiqueu els camps que voleu utilitzar perquè coincideixin amb els registres de client i els camps que voleu incloure al perfil unificat. Aquests camps s'anomenen *Atributs*. Podeu seleccionar els atributs requerits individualment d'una entitat o incloure tots els atributs d'una entitat seleccionant la casella de selecció del nivell d'entitat. Podeu fer cerques per paraules clau a tots els atributs i les entitats per seleccionar els atributs necessaris que voleu assignar.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Captura de pantalla de les entitats i atributs seleccionats.":::

   En aquest exemple, afegim les **entitats eCommerceContacts** i **loyCustomer**. En triar aquestes entitats, podeu derivar informació sobre els client de quina empresa en línia són membres del programa de fidelització.

1. Seleccioneu **Aplica** per confirmar les seleccions. Es mostren les entitats i els atributs seleccionats.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Seleccioneu la clau principal i el tipus semàntic per als atributs

   :::image type="content" source="media/m3_select_primary.png" alt-text="Captura de pantalla de les entitats seleccionades amb clau principal encara no seleccionada." lightbox="media/m3_select_primary.png":::

Per a cada entitat, seguiu els passos següents.

1. Trieu la **tecla** Principal. La clau principal és un atribut únic per a l'entitat. Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls. Els atributs de tipus de dades String, Integer i GUID s'admeten com a claus principals.

1. Per utilitzar models d'IA per a predicció intel·ligents de semàntica que estalvia temps i millora la precisió, assegureu-vos que **l'assignació** intel·ligent estigui activada. La cartografia intel·ligent proporciona recomanacions semàntiques basades en IA en el **camp Tipus**.

1. Per a cada atribut, trieu un tipus **semàntic** que descrigui millor aquest atribut, com ara el nom, la ciutat o l'adreça electrònica.

   > [!NOTE]
   > En B-to-C, un camp s'ha d'assignar al tipus *semàntic Person.FullName* per omplir el nom del client a la targeta de client. En B a B, el nom del compte s'ha d'assignar a *Organization.Name*. Altrament, les targetes del client apareixeran sense nom.

   1. Per substituir un tipus d'atribut identificat pel sistema, seleccioneu una altra opció. Si el tipus no existeix, creeu un tipus semàntic personalitzat seleccionant el camp Tipus **per a l'atribut** i introduint el vostre nom de tipus semàntic personalitzat.

   1. Per afegir un atribut que contingui una URL a les imatges de perfil o logotips disponibles públicament, seleccioneu l'entitat i el camp que conté l'URL. **Al camp Tipus**, introduïu el següent:
      - Per a una persona: Person.ProfileImage
      - Per a una organització: Organization.LogoImage

1. Revisar els atributs on s'identifica automàticament un tipus semàntic. Aquests atributs es llisten a **Revisar els camps** mapejats. Només es poden combinar atributs amb el mateix tipus al pas Unify **camps** de client. Els tipus semàntics s'utilitzen per suggerir automàticament informació. Assegureu-vos que els tipus que trieu siguin coherents en totes les entitats seleccionades.

1. Per als atributs que no s'assignen automàticament a un tipus semàntic, seleccioneu un camp de tipus semàntic, introduïu el nom del tipus d'atribut personalitzat o deixeu-los sense mapa. Aquests atributs es llisten a **Defineix les dades als camps** sense mapa.

1. Després de completar els passos de cada entitat, seleccioneu **Desa els camps** d'origen.

1. Seleccioneu **Següent**.

> [!div class="nextstepaction"]
> [Pas següent: suprimeix duplicats](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
