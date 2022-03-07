---
title: Combinar entitats a la unificació de dades
description: Combineu entitats per crear perfils de client unificats.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305612"
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

1. Seleccioneu el camp combinat.
  
1. Seleccioneu **Mostra'n més** i trieu **Exclou**.

1. Confirmeu l'exclusió.

1. Seleccioneu **Desa** i **Executa** per processar els canvis. 

A la pàgina **Combina**, seleccioneu **Camps exclosos** per veure la llista de tots els camps exclosos. Aquesta subfinestra us permet tornar a afegir camps exclosos.

## <a name="manually-combine-fields"></a>Combinar camps manualment

Especifiqueu un atribut combinat manualment. 

1. A la pàgina **Combina**, seleccioneu **Combina els camps**.

1. Proporcioneu un **Nom** i un **Nom de camp de sortida**.

1. Trieu un camp per afegir-lo. Seleccioneu **Afegeix camps** per combinar-ne més.

1. Confirmeu l'exclusió.

1. Seleccioneu **Desa** i **Executa** per processar els canvis. 

## <a name="change-the-order-of-fields"></a>Canviar l'ordre dels camps

Algunes entitats contenen més detalls que altres. Si una entitat inclou les dades més recents d'un camp, podeu prioritzar-la sobre altres entitats quan es combinen valors.

1. Seleccioneu el camp combinat.
  
1. Seleccioneu **Mostra'n més** i trieu **Edita**.

1. A la subfinestra **Combina els camps**, seleccioneu **Desplaça amunt/avall** per definir l'ordre o arrossegueu-los i deixeu-los anar a la posició desitjada.

1. Confirmeu el canvi.

1. Seleccioneu **Desa** i **Executa** per processar els canvis.

## <a name="run-your-merge"></a>Executar la combinació

Ja sigui si combineu els atributs manualment o deixeu que el sistema els combini, sempre podeu executar la combinació. A la pàgina **Combinació**, seleccioneu **Executa** per iniciar el procés.

> [!div class="mx-imgBorder"]
> ![Desa i executa la combinació de dades](media/configure-data-merge-save-run.png "Desa i executa la combinació de dades")

Trieu **Executa només la combinació** si només voleu veure la sortida reflectida a l'entitat de client unificada. Els processos descendents s'actualitzaran segons [ho defineixi la planificació d'actualització](system.md#schedule-tab).

Trieu **Executa la combinació i els processos descendents** per actualitzar el sistema amb els canvis. Tots els processos, incloent-hi l'enriquiment, els segments i les mesures, es tornaran a executar automàticament. Un cop completats tots els processos descendents, els perfils de client reflecteixen els canvis que heu fet.

Per fer més canvis i tornar a executar el pas, podeu cancel·lar una combinació en curs. Seleccioneu **S'està actualitzant...** i seleccioneu **Cancel·la la feina** a la subfinestra lateral que es mostra.

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.

## <a name="next-step"></a>Pas següent

Configureu [Activitats](activities.md), [Enriquiment](enrichment-hub.md) o [Relacions](relationships.md) per obtenir més informació sobre els clients.

Si ja heu configurat activitats, enriquiments o segments, es processaran automàticament per utilitzar les dades de client més recents.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
