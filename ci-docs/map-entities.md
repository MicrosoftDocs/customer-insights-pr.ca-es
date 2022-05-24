---
title: Seleccioneu els camps d'origen per a la unificació de dades
description: El primer pas del procés d'unificació és seleccionar entitats, atributs, claus primàries i tipus semàntics per assignar dades al perfil de client unificat.
recommendations: false
ms.date: 04/22/2022
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
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740983"
---
# <a name="select-source-fields-for-data-unification"></a>Seleccioneu els camps d'origen per a la unificació de dades

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

El primer pas de la unificació és seleccionar les entitats i els camps dels conjunts de dades que voleu unificar. Seleccioneu entitats que continguin detalls relacionats amb el client, com ara el nom, l'adreça, el número de telèfon i el correu electrònic. Podeu seleccionar una o més entitats.

## <a name="select-entities-and-fields"></a>Seleccioneu les entitats i els camps

1. Aneu a Unificació de **dades** > **·**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Captura de pantalla de la pàgina de destinació Unify per a l'experiència de la primera execució amb Comença a ressaltat.":::

1. Seleccioneu **Introducció**.

1. A la **pàgina Camps d'origen**, seleccioneu **Selecciona entitats i camps**. Es **visualitza la subfinestra Selecciona les entitats i els camps**.

1. Seleccioneu com a mínim una entitat.

1. Per a cada entitat seleccionada, identifiqueu els camps que voleu utilitzar perquè coincideixin amb els registres de clients i els camps que voleu incloure al perfil unificat. Aquests camps s'anomenen *atributs*. Podeu seleccionar els atributs necessaris individualment des d'una entitat o incloure tots els atributs d'una entitat marcant la casella de selecció al nivell d'entitat. Podeu fer cerques per paraules clau a tots els atributs i les entitats per seleccionar els atributs necessaris que voleu assignar.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Captura de pantalla de les entitats i atributs seleccionats.":::

   En aquest exemple, afegim les **entitats Contactes** i **CustomerLoyalty**. En triar aquestes entitats, podeu derivar informació sobre els client de quina empresa en línia són membres del programa de fidelització.

1. Seleccioneu **Aplica** per confirmar les seleccions. Es visualitzen les entitats i atributs seleccionats.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Seleccioneu la clau principal i el tipus semàntic per als atributs

   :::image type="content" source="media/m3_select_primary.png" alt-text="Captura de pantalla d'entitats seleccionades amb clau principal no seleccionada." lightbox="media/m3_select_primary.png":::

Per a cada entitat, realitzeu els passos següents.

1. Trieu la **clau principal**. La clau principal és un atribut únic a l'entitat. Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls. Els atributs de tipus de dades string, integer i GUID són compatibles com a claus principals.

1. Per utilitzar models d'intel·ligència IA per a predicció intel·ligents de semàntica, estalvieu temps i milloreu la precisió, assegureu-vos que **el mapatge** intel·ligent estigui encesos. L'assignació intel·ligent destaca la recomanació semàntica basada en IA en el camp **Tipus**. Podeu substituir la selecció suggerida escollint qualsevol tipus semàntic de la llista d'opcions disponibles.

1. Per a cada atribut, trieu un tipus **semàntic** que descrigui millor aquest atribut, com ara el nom, la ciutat o l'adreça electrònica.

   > [!NOTE]
   > Un camp s'ha d'assignar al tipus *semàntic Person.FullName* per emplenar el nom del client a la targeta de client. Altrament, les targetes del client apareixeran sense nom.

   1. Per canviar un tipus d'atribut identificat pel sistema, seleccioneu un altre tipus. Si el tipus no existeix, creeu un tipus semàntic personalitzat seleccionant el **camp Tipus** per a l'atribut i introduint el nom del tipus semàntic personalitzat.

   1. Per afegir un atribut que contingui un URL a imatges o logotips de perfil disponibles públicament, seleccioneu l'entitat i el camp que conté l'adreça URL. **Al camp Tipus**, introduïu el següent:
      - Per a una persona: Person.ProfileImage
      - Per a una organització: Organization.LogoImage

   1. Per obtenir un atribut de nom de compte, introduïu "Organization.Name" al **camp Tipus**.

1. Reviseu els atributs on s'identifica automàticament un tipus semàntic. Aquests atributs es mostren a **Revisa els camps** assignats. Només es poden combinar atributs amb el mateix tipus al pas Unificat de **camps** de client. Els tipus semàntics s'utilitzen per suggerir automàticament estadístiques. Assegureu-vos que els tipus que heu triat siguin coherents en totes les entitats seleccionades.

1. Per als atributs que no s'assignen automàticament a un tipus semàntic, seleccioneu un camp de tipus semàntic, introduïu el nom personalitzat del tipus d'atribut o deixeu-los sense assignar. Aquests atributs es mostren a **Defineix les dades dels camps** no assignats.

1. Després de completar els passos de cada entitat, seleccioneu **Desa els camps** d'origen.

1. Seleccioneu **Següent**.

> [!div class="nextstepaction"]
> [Pas següent: Suprimeix els duplicats](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
