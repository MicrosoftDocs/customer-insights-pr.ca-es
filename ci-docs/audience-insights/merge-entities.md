---
title: Combinar entitats a la unificació de dades
description: Combineu entitats per crear perfils de client unificats.
ms.date: 01/28/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: c7743104bf89d9a2a741f1b358a89ed0240be024
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355833"
---
# <a name="merge-entities"></a>Combinar entitats

La fase de combinació és l'última fase en el procés d'unificació de dades. La seva finalitat és la conciliació de dades contradictòries. Alguns exemples de dades contradictòries són un nom del client que es troba en dos dels vostres conjunts de dades, però apareix una mica diferent a cadascun d'ells ("Grant Marshall" o "Grant Marshal") o un número de telèfon que difereix en el format (617-803-091X versus 617803091X). La combinació d'aquests punts de dades conflictius es fa per atribut.

:::image type="content" source="media/merge-fields-page.png" alt-text="Combineu la pàgina al procés d'unificació de dades que mostra la taula amb camps combinats que defineixen el perfil de client unificat.":::

Després de completar la [fase de coincidència](match-entities.md), podeu iniciar la fase de combinació seleccionant la peça **Combinació** a la pàgina **Unifica**.

## <a name="review-system-recommendations"></a>Revisar les recomanacions del sistema

A **Dades** > **Unifica** > **Combina**, trieu i excloueu els atributs que es combinaran a l'entitat de perfil de client unificada. El perfil de client unificat és el resultat del procés d'unificació de dades. El sistema combina automàticament alguns atributs.

Per visualitzar els atributs que s'inclouen en un dels atributs combinats automàticament, seleccioneu aquest atribut combinat a la pestanya de la taula **Camps de client**. Els atributs que componen aquest atribut combinat es mostren en dues files noves sota l'atribut combinat.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Separar camps combinats, canviar-ne el nom, excloure'ls i editar-los

Podeu canviar com el sistema processa els atributs combinats per generar el perfil de client unificat. Seleccioneu **Mostra'n més** i trieu què voleu canviar.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opcions del menú desplegable Mostra més per administrar els atributs combinats.":::

Per obtenir més informació, vegeu les seccions següents.

## <a name="separate-merged-fields"></a>Separar camps combinats

Per separar els camps combinats, cerqueu l'atribut a la taula. Els camps separats es mostren com a punts de dades individuals al perfil de client unificat. 

1. Seleccioneu el camp combinat.
  
1. Seleccioneu **Mostra'n més** i trieu **Separa els camps**.
 
1. Confirmeu la separació.

1. Seleccioneu **Desa** i **Executa** per processar els canvis.

## <a name="rename-merged-fields"></a>Canviar el nom dels camps combinats

Canvieu el nom de visualització dels atributs combinats. No podeu canviar el nom de l'entitat de sortida.

1. Seleccioneu el camp combinat.
  
1. Seleccioneu **Mostra'n més** i trieu **Canvia'n el nom**.

1. Confirmeu el nom de visualització canviat. 

1. Seleccioneu **Desa** i **Executa** per processar els canvis.

## <a name="exclude-merged-fields"></a>Excloure camps combinats

Excloeu un atribut del perfil de client unificat. Si el camp s'utilitza en altres processos, per exemple, en un segment, suprimiu-lo d'aquests processos abans d'excloure'l del perfil de client. 

1. Seleccioneu un camp combinat.
  
1. Seleccioneu **Mostra'n més** i trieu **Exclou**.

1. Confirmeu l'exclusió.

1. Seleccioneu **Desa** i **Executa** per processar els canvis. 

A la pàgina **Combina**, seleccioneu **Camps exclosos** per veure la llista de tots els camps exclosos. Aquesta subfinestra us permet tornar a afegir camps exclosos.

## <a name="edit-a-merged-field"></a>Editar un camp combinat

1.  Seleccioneu un camp combinat.

1.  Seleccioneu **Mostra'n més** i trieu **Edita**.

1.  Especifiqueu com combinar els camps d'una de les tres opcions:
    - **Importància**: s'identifica el valor guanyador en funció de la classificació d'importància especificada per als camps participants. És l'opció de combinació per defecte. Seleccioneu **Desplaça amunt/avall** per definir la classificació d'importància.
    :::image type="content" source="media/importance-merge-option.png" alt-text="L'opció d'importància al quadre de diàleg de camps combinats."::: 
    - **Més recents**: identifica el valor guanyador en funció del més recent. Requereix una data o un camp numèric per a cada entitat participants a l'àmbit dels camps combinats per definir el temps d'antiguitat.
    :::image type="content" source="media/recency-merge-option.png" alt-text="L'opció del temps d'antiguitat al quadre de diàleg de camps combinats.":::
    - **Menys recents**: identifica el valor guanyador en funció del menys recent. Requereix una data o un camp numèric per a cada entitat participants a l'àmbit dels camps combinats per definir el temps d'antiguitat.

1.  Podeu afegir més camps per participar en el procés de combinació.

1.  Podeu canviar el nom del camp combinat.

1. Seleccioneu **Fet** per aplicar els canvis.

1. Seleccioneu **Desa** i **Executa** per processar els canvis. 

## <a name="combine-fields-manually"></a>Combina camps manualment

Especifiqueu un atribut combinat manualment.

1. A la **pàgina Combina**, seleccioneu **Combina**.

1. Trieu l'opció **Camps**.

1. Especifiqueu la política de guanyador de combinació al desplegable **Combina els camps segons**.

1. Trieu un camp per afegir-lo. Seleccioneu **Afegeix camps** per combinar-ne més.

1. Proporcioneu un **Nom** i un **Nom de camp de sortida**.

1. Seleccioneu **Fet** per aplicar els canvis.

1. Seleccioneu **Desa** i **Executa** per processar els canvis. 

## <a name="combine-a-group-of-fields"></a>Combina un grup de camps

Tracta un grup de camps com una sola unitat. Per exemple, quan els nostres registres contenen els camps Adreça1, Adreça2, Ciutat, Estat i Zip. És probable que no vulguem fusionar-nos a l'Adreça 2 d'un registre diferent, pensant que faria que les nostres dades siguin més completes

1. A la **pàgina Combina**, seleccioneu **Combina**.

1. Trieu l'opció **Agrupa de camps**.

1. Especifiqueu la política de combinació guanyadora als **grups de classificació per** menú desplegable.

1. Seleccioneu **Afegeix** i trieu si voleu afegir més camps o grups addicionals als camps.

1. Proporcioneu un **nom** i un **nom** de sortida per a cada camp combinat.

1. Proporcioneu un **nom** per al grup de camps. 

1. Seleccioneu **Fet** per aplicar els canvis.

1. Seleccioneu **Desa** i **Executa** per processar els canvis.

## <a name="change-the-order-of-fields"></a>Canviar l'ordre dels camps

Algunes entitats contenen més detalls que altres. Si una entitat inclou les dades més recents d'un camp, podeu prioritzar-la sobre altres entitats quan es combinen valors.

1. Seleccioneu el camp combinat.
  
1. Seleccioneu **Mostra'n més** i trieu **Edita**.

1. A la subfinestra **Combina els camps**, seleccioneu **Desplaça amunt/avall** per definir l'ordre o arrossegueu-los i deixeu-los anar a la posició desitjada.

1. Confirmeu el canvi.

1. Seleccioneu **Desa** i **Executa** per processar els canvis.

## <a name="configure-customer-id-generation"></a>Configuració de la generació de l'ID de client 

Després de configurar els camps de combinació, podeu definir com generar els valors CustomerId, els identificadors únics del perfil de client. El pas de combinació del procés d'unificació de dades genera l'identificador únic del perfil de client. L'identificador és CustomerId de l'entitat *Client* que resulta del procés d'unificació de dades. 

El CustomerId de l'entitat Client es basa en un hash del primer valor de les claus principals guanyadores que no són nul·les. Aquestes tecles provenen de les entitats utilitzades a la fase de coincidència i combinació i estan influencides per l'ordre de la coincidència.Per tant, el CustomerID pot canviar quan canvia un valor clau principal a l'entitat principal de l'ordre de coincidència. Per tant, el valor clau principal no sempre representa el mateix client.

Configurar un identificador de client estable us permet evitar aquest comportament.

**Configuració d'un ID de client únic**

1. Aneu a **Unifica** > **Combina**.

1. Seleccioneu la pestanya **Claus**. 

1. Passeu el cursor per sobre de la fila **CustomerId** i seleccioneu l'opció **Configura**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Control per personalitzar la generació d'ID.":::

1. Seleccioneu fins a cinc camps que formaran un identificador de client únic i que siguin més estables. Els registres que no coincideixen amb la configuració utilitzen un ID configurat pel sistema.  

1. Seleccioneu **Fet** i executeu el procés de combinació per aplicar els canvis.

## <a name="group-profiles-into-households-or-clusters"></a>Agrupar els perfils en domicilis o clústers

Com a part del procés de configuració de la generació de perfils de client, podeu definir regles per agrupar els perfils relacionats en un clúster. Actualment hi ha dos tipus de clústers disponibles: clústers de domicili i personalitzats. El sistema selecciona automàticament un domicili amb regles predefinides si l'entitat *Client* conté els camps semàntics *Person.LastName* i *Location.Address*. També podeu crear un clúster amb les vostres pròpies regles i condicions, de manera semblant a les [regles de coincidència](match-entities.md#define-rules-for-match-pairs).

**Definir un domicili o un clúster**

1. Aneu a **Unifica** > **Combina**.

1. A la pestanya **Combinació**, seleccioneu **Avançat** > **Crea un clúster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Control per crear un clúster nou.":::

1. Trieu entre un clúster **de Domicili** o un de **Personalitzat**. Si els camps semàntics *Person.LastName* i *Location.Address* existeixen a l'entitat *Client*, se selecciona automàticament el domicili.

1. Proporcioneu un nom del clúster i seleccioneu **Fet**.

1. Seleccioneu la pestanya **Clústers** per cercar el clúster que heu creat.

1. Especifiqueu les regles i les condicions per definir el clúster.

1. Seleccioneu **Executa** per executar el procés de combinació i crear el clúster.

Un cop executat el procés de combinació, els identificadors de clúster s'afegeixen com a camps nous a l'entitat *Client*.

## <a name="run-your-merge"></a>Executar la combinació

Ja sigui si combineu els atributs manualment o deixeu que el sistema els combini, sempre podeu executar la combinació. A la pàgina **Combinació**, seleccioneu **Executa** per iniciar el procés.

> [!div class="mx-imgBorder"]
> ![Desa i executa la combinació de dades.](media/configure-data-merge-save-run.png "Desa i executa la combinació de dades")

Trieu **Executa només la combinació** si només voleu veure la sortida reflectida a l'entitat de client unificada. Els processos descendents s'actualitzaran segons [ho defineixi la planificació d'actualització](system.md#schedule-tab).

Trieu **Executa la combinació i els processos descendents** per actualitzar el sistema amb els canvis. Tots els processos, incloent-hi l'enriquiment, els segments i les mesures, es tornaran a executar automàticament. Un cop completats tots els processos descendents, els perfils de client reflecteixen els canvis que heu fet.

Per fer més canvis i tornar a executar el pas, podeu cancel·lar una combinació en curs. Seleccioneu **S'està actualitzant...** i seleccioneu **Cancel·la la feina** a la subfinestra lateral que es mostra.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Camí de desglossament per accedir als detalls del procés des de l'enllaç d'estat de la tasca.":::

## <a name="next-step"></a>Pas següent

Configureu [Activitats](activities.md), [Enriquiment](enrichment-hub.md) o [Relacions](relationships.md) per obtenir més informació sobre els clients.

Si ja heu configurat activitats, enriquiments o segments, es processaran automàticament per utilitzar les dades de client més recents.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
