---
title: Unificar els camps de clients per a la unificació de dades
description: Combineu entitats per crear perfils de client unificats.
recommendations: false
ms.date: 07/27/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 7ebd6ab8fa6ae141f33295a5d7723e96c8dc70ca
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304001"
---
# <a name="unify-customer-fields"></a>Unificar els camps de clients

En aquest pas del procés d'unificació, trieu i excloeu els atributs per combinar-los a l'entitat del perfil unificat. Per exemple, si tres entitats tenien dades de correu electrònic, és possible que vulgueu conservar els tres camps de correu electrònic separats o combinar-los en un sol camp de correu electrònic per al perfil unificat. Alguns atributs es combinen automàticament amb el sistema. Podeu crear identificadors de client estables i únics. Per a clients individuals, podeu agrupar perfils relacionats en un clúster.

:::image type="content" source="media/m3_unify.png" alt-text="Unifiqueu la pàgina de camps de client en el procés d'unificació de dades que mostra la taula amb els camps fusionats que defineixen el perfil de client unificat.":::

## <a name="review-and-update-the-customer-fields"></a>Revisar i actualitzar els camps de clients

1. Reviseu la llista de camps que s'unificaran a la **pestanya Camps** del client de la taula. Feu qualsevol canvi, si escau.

   1. Per a qualsevol camp combinat, podeu:
      - [Edició](#edit-a-merged-field)
      - [Canvia el nom](#rename-fields)
      - [Separa](#separate-merged-fields)
      - [Exclou](#exclude-fields)
      - [Pujar o baixar](#change-the-order-of-fields)

   1. Per a qualsevol camp únic, podeu:
      - [Combina els camps](#combine-fields-manually)
      - [Combinar un grup de camps](#combine-a-group-of-fields)
      - [Canvia el nom](#rename-fields)
      - [Exclou](#exclude-fields)
      - [Pujar o baixar](#change-the-order-of-fields)

1. Opcionalment, [genereu la configuració](#configure-customer-id-generation) de l'ID de client.

1. Opcionalment per a B a C, [agrupar perfils en llars o clústers](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Pas següent: revisar la unificació](review-unification.md)

### <a name="edit-a-merged-field"></a>Editar un camp combinat

1. Seleccioneu un camp fusionat i trieu **Edita**. Es mostra la subfinestra Combina camps.

1. Especifiqueu com combinar els camps d'una de les tres opcions:
    - **Importància**: s'identifica el valor guanyador en funció de la classificació d'importància especificada per als camps participants. És l'opció de combinació per defecte. Seleccioneu **Desplaça amunt/avall** per definir la classificació d'importància.

      > [!NOTE]
      > El Customer Insights utilitza el primer valor no nul. Per exemple, donades les entitats A, B i C classificades en aquest ordre, si A.Name i B.Name són nul·les, s'utilitza el valor de C.Name.

      :::image type="content" source="media/importance-merge-option.png" alt-text="L'opció d'importància al quadre de diàleg de camps combinats.":::

    - **Més recents**: identifica el valor guanyador en funció del més recent. Requereix una data o un camp numèric per a cada entitat participants a l'àmbit dels camps combinats per definir el temps d'antiguitat.

      :::image type="content" source="media/recency-merge-option.png" alt-text="L'opció del temps d'antiguitat al quadre de diàleg de camps combinats.":::

    - **Menys recents**: identifica el valor guanyador en funció del menys recent. Requereix una data o un camp numèric per a cada entitat participants a l'àmbit dels camps combinats per definir el temps d'antiguitat.

1. Podeu afegir més camps per participar en el procés de combinació.

1. Podeu canviar el nom del camp combinat.

1. Seleccioneu **Fet** per aplicar els canvis.

### <a name="rename-fields"></a>Canviar el nom dels camps

Canvieu el nom de visualització dels camps fusionats o separats. No podeu canviar el nom de l'entitat de sortida.

1. Seleccioneu el camp i trieu **Canvia el nom**.

1. Introduïu el nom de visualització nou.

1. Seleccioneu **Fet**.

### <a name="separate-merged-fields"></a>Separar camps combinats

Per separar els camps combinats, cerqueu l'atribut a la taula. Els camps separats es mostren com a punts de dades individuals al perfil de client unificat.

1. Seleccioneu el camp fusionat i trieu **Camps separats**.

1. Confirmeu la separació.

### <a name="exclude-fields"></a>Excloure camps

Excloeu un camp combinat o separat del perfil de client unificat. Si el camp s'utilitza en altres processos, per exemple, en un segment, suprimiu-lo d'aquests processos abans d'excloure'l del perfil de client.

1. Seleccioneu un camp i trieu **Exclou**.

1. Confirmeu l'exclusió.

Per veure la llista de tots els camps exclosos, seleccioneu **Camps** exclosos. Si cal, podeu llegir el camp exclòs.

### <a name="change-the-order-of-fields"></a>Canviar l'ordre dels camps

Algunes entitats contenen més detalls que altres. Si una entitat inclou les dades més recents d'un camp, podeu prioritzar-la sobre altres entitats quan es combinen valors.

1. Seleccioneu el camp.
  
1. Trieu Mou **amunt/avall** per establir l'ordre o arrossegar-los i deixar-los anar a la posició desitjada.

### <a name="combine-fields-manually"></a>Combina els camps manualment

Combineu camps separats per crear un atribut fusionat.

1. Seleccioneu **Combina** > **camps**. Es mostra la subfinestra Combina camps.

1. Especifiqueu la política de guanyador de combinació al desplegable **Combina els camps segons**.

1. Seleccioneu **Afegeix un camp** per combinar més camps.

1. Proporcioneu un **Nom** i un **Nom de camp de sortida**.

1. Seleccioneu **Fet** per aplicar els canvis.

### <a name="combine-a-group-of-fields"></a>Combinar un grup de camps

Tractar un grup de camps com una sola unitat. Per exemple, si els nostres registres contenen els camps Adreça1, Adreça2, Ciutat, Estat i Zip, no volem fusionar-nos en l'Adreça2 d'un altre registre, pensant que faria que les nostres dades fossin més completes.

1. Seleccioneu **Combina** > **grup de camps**.

1. Especifiqueu la política de guanyador de la combinació als **grups de classificació per** menú desplegable.

1. Seleccioneu **Afegeix** i trieu si voleu afegir més camps o grups als camps.

1. Proporcioneu un **nom** i un **nom** de sortida per a cada camp combinat.

1. Proporcioneu un **nom** per al grup de camps.

1. Seleccioneu **Fet** per aplicar els canvis.

## <a name="configure-customer-id-generation"></a>Configurar la generació d'identificadors de client

Definiu com generar valors d'identificació de client, els identificadors únics del perfil de client. El pas unificar camps en el procés d'unificació de dades genera l'identificador únic del perfil de client. L'identificador és el *CustomerId* de l'entitat *Client* que resulta del procés d'unificació de dades.

El *CustomerId* es basa en un hash del primer valor de les claus primàries guanyadores no nul·les. Aquestes claus provenen de les entitats utilitzades en la unificació de dades i estan influenciades per l'ordre de coincidència.Per tant, l'identificador de client generat pot canviar quan canvia un valor clau principal a l'entitat principal de l'ordre de coincidència. És possible que el valor clau principal no sempre representi el mateix client.

Configurar un identificador de client estable us permet evitar aquest comportament.

1. Seleccioneu la pestanya **Claus**.

1. Passeu el cursor per la **fila CustomerId** i seleccioneu **Configura**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Control per personalitzar la generació d'ID.":::

1. Seleccioneu fins a cinc camps que formaran un identificador de client únic i que siguin més estables. Els registres que no coincideixen amb la configuració utilitzen un ID configurat pel sistema.  

1. Seleccioneu **Fet**.

## <a name="group-profiles-into-households-or-clusters"></a>Agrupar els perfils en domicilis o clústers

Per a clients individuals, podeu definir regles per agrupar perfils relacionats en un clúster. Actualment hi ha dos tipus de clústers disponibles: clústers de domicili i personalitzats. El sistema selecciona automàticament un domicili amb regles predefinides si l'entitat *Client* conté els camps semàntics *Person.LastName* i *Location.Address*. També podeu crear un clúster amb les vostres pròpies regles i condicions, de manera semblant a les [regles de coincidència](match-entities.md#define-rules-for-match-pairs).

1. Seleccioneu **Clúster de creació** > **avançada**.

   :::image type="content" source="media/create-cluster.png" alt-text="Control per crear un clúster nou.":::

1. Trieu entre un clúster **de Domicili** o un de **Personalitzat**. Si els camps semàntics *Person.LastName* i *Location.Address* existeixen a l'entitat *Client*, se selecciona automàticament el domicili.

1. Proporcioneu un nom del clúster i seleccioneu **Fet**.

1. Seleccioneu la pestanya **Clústers** per cercar el clúster que heu creat.

1. Especifiqueu les regles i les condicions per definir el clúster.

1. Seleccioneu **Fet**. El clúster es crea quan es completa el procés d'unificació. Els identificadors del clúster s'afegeixen com a camps nous a l'entitat *Client*.

> [!div class="nextstepaction"]
> [Pas següent: revisar la unificació](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
