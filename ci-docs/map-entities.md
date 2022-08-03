---
title: Seleccioneu els camps d'origen per a la unificació de dades
description: El primer pas en el procés d'unificació és seleccionar entitats, atributs, claus primàries i tipus semàntics per assignar dades al perfil de client unificat.
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
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139770"
---
# <a name="select-source-fields-for-data-unification"></a>Seleccioneu els camps d'origen per a la unificació de dades

El primer pas per a la unificació és seleccionar les entitats i els camps dels conjunts de dades que voleu unificar. Seleccioneu entitats que continguin detalls relacionats amb el client, com ara el nom, l'adreça, el número de telèfon i el correu electrònic. Podeu seleccionar una o més entitats.

## <a name="select-entities-and-fields"></a>Seleccioneu les entitats i els camps

1. Aneu a **Unificar dades** > **·**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Captura de pantalla d'unificar la pàgina de destinació per a la primera experiència d'execució amb El ressaltat de Començar.":::

1. Seleccioneu **Introducció**.

1. A la pàgina Camps **d'origen**, seleccioneu **Seleccioneu entitats i camps**. Es mostra la **subfinestra Selecciona entitats i camps**.

1. Seleccioneu almenys una entitat.

1. Per a cada entitat seleccionada, identifiqueu els camps que voleu utilitzar perquè coincideixin amb els registres de client i els camps que voleu incloure al perfil unificat. Aquests camps s'anomenen *Atributs*. Podeu seleccionar els atributs requerits individualment d'una entitat o incloure tots els atributs d'una entitat seleccionant la casella de selecció del nivell d'entitat. Podeu fer cerques per paraules clau a tots els atributs i les entitats per seleccionar els atributs necessaris que voleu assignar.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Captura de pantalla de les entitats i atributs seleccionats.":::

   En aquest exemple, afegim les **entitats Contactes** i **CustomerLoyalty**. En triar aquestes entitats, podeu derivar informació sobre els client de quina empresa en línia són membres del programa de fidelització.

1. Seleccioneu **Aplica** per confirmar les seleccions. Es mostren les entitats i els atributs seleccionats.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Seleccioneu la clau principal i el tipus semàntic per als atributs

   :::image type="content" source="media/m3_select_primary.png" alt-text="Captura de pantalla de les entitats seleccionades amb clau principal no seleccionada." lightbox="media/m3_select_primary.png":::

Per a cada entitat, seguiu els passos següents.

1. Trieu la **tecla** Principal. La clau principal és un atribut únic per a l'entitat. Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls. Els atributs de tipus de dades String, Integer i GUID s'admeten com a claus principals.

1. Per utilitzar models d'IA per a predicció intel·ligents de semàntica, estalviar temps i millorar la precisió, assegureu-vos que **l'assignació** intel·ligent estigui activada. L'assignació intel·ligent destaca la recomanació semàntica basada en IA en el camp **Tipus**. Podeu substituir la selecció suggerida triant qualsevol tipus semàntic de la llista d'opcions disponible.

1. Per a cada atribut, trieu un tipus **semàntic** que descrigui millor aquest atribut, com ara el nom, la ciutat o l'adreça electrònica.

   > [!NOTE]
   > Un camp s'ha d'assignar al tipus *semàntic Person.FullName* per omplir el nom del client a la targeta de client. Altrament, les targetes del client apareixeran sense nom.

   1. Per canviar un tipus d'atribut identificat pel sistema, seleccioneu-ne un altre tipus. Si el tipus no existeix, creeu un tipus semàntic personalitzat seleccionant el camp Tipus **per a l'atribut** i introduint el nom del vostre tipus semàntic personalitzat.

   1. Per afegir un atribut que contingui una URL a les imatges de perfil o logotips disponibles públicament, seleccioneu l'entitat i el camp que conté l'URL. **Al camp Tipus**, introduïu el següent:
      - Per a una persona: Person.ProfileImage
      - Per a una organització: Organization.LogoImage

   1. Per a un atribut de nom de compte, introduïu "Organization.Name" al **camp Tipus**.

1. Revisar els atributs on s'identifica automàticament un tipus semàntic. Aquests atributs es llisten a **Revisar els camps** mapejats. Només es poden combinar atributs amb el mateix tipus al **pas Camps** de client unificats. Els tipus semàntics s'utilitzen per suggerir automàticament informació. Assegureu-vos que els tipus que trieu siguin coherents en totes les entitats seleccionades.

1. Per als atributs que no s'assignen automàticament a un tipus semàntic, seleccioneu un camp de tipus semàntic, introduïu el nom personalitzat del tipus d'atribut o deixeu-los sense mapa. Aquests atributs es llisten a **Defineix les dades als camps** sense mapa.

1. Després de completar els passos de cada entitat, seleccioneu **Desa els camps** d'origen.

1. Seleccioneu **Següent**.

> [!div class="nextstepaction"]
> [Pas següent: suprimeix duplicats](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
