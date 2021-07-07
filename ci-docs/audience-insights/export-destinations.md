---
title: Exportar dades del Customer Insights
description: Administrar les exportacions per compartir dades.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305466"
---
# <a name="exports-preview-overview"></a>Informació general sobre exportacions (versió preliminar)

A la pàgina **Exportacions** es mostren totes les exportacions configurades. Les exportacions comparteixen dades específiques amb diverses aplicacions. Poden incloure perfils de clients o entitats, esquemes i detalls d'assignació. Cada exportació requereix una [connexió, configurada per un administrador, per administrar l'autenticació i l'accés](connections.md).

Aneu a **Dades** > **Exportacions** per visualitzar la pàgina d'exportacions. Totes les funcions d'usuari poden veure les exportacions configurades. Utilitzeu el camp de cerca de la barra d'ordres per cercar exportacions pel seu nom, nom de connexió o tipus de connexió.

## <a name="set-up-a-new-export"></a>Configurar una exportació nova

Per configurar o editar una exportació, heu de tenir connexions disponibles. Les connexions depenen de la vostra [funció d'usuari](permissions.md):
- Els administradors tenen accés a totes les connexions. També poden crear connexions noves quan configuren una exportació.
- Els col·laboradors poden tenir accés a connexions específiques. Depenen dels administradors per configurar i compartir connexions. La llista d'exportacions mostra als contribuïdors si poden editar o només visualitzar una exportació a la columna **Els vostres permisos**. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Els visualitzadors només poden visualitzar les exportacions existents, però no les poden crear.

### <a name="define-a-new-export"></a>Definir una exportació nova

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació** per crear una exportació nova.

1. A la subfinestra **Configura l'exportació**, seleccioneu la connexió que voleu utilitzar. Les [connexions](connections.md)les administren els administradors. 

1. Proporcioneu els detalls necessaris i seleccioneu **Desa** per crear l'exportació.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definir una exportació nova basada en una exportació existent

1. Vés a **Dades** > **Exportacions**.

1. A la llista d'exportacions, seleccioneu l'exportació que vulgueu duplicar.

1. Seleccioneu **Crea un duplicat** a la barra d'ordres per obrir la subfinestra **Configura l'exportació** amb els detalls de l'exportació seleccionada.

1. Reviseu i adapteu l'exportació i seleccioneu **Desa** per crear una exportació nova.

### <a name="edit-an-export"></a>Editar una exportació

1. Vés a **Dades** > **Exportacions**.

1. A la llista d'exportacions, seleccioneu l'exportació que vulgueu editar.

1. Seleccioneu **Edita** a la barra d'ordres.

1. Canvieu els valors que voleu actualitzar i seleccioneu **Desa**.

## <a name="view-exports-and-export-details"></a>Visualitzar les exportacions i els detalls d'exportació

Un cop creades les destinacions d'exportació, es mostren a **Dades** > **Exportacions**. Tots els usuaris poden veure quines dades es comparteixen i el seu estat més recent.

1. Vés a **Dades** > **Exportacions**.

1. Els usuaris sense editar permisos seleccionen **Visualitza** en comptes d'**Edita** per veure els detalls de l'exportació.

1. A la subfinestra lateral es mostra la configuració d'una exportació. Sense permisos d'edició, els valors no es poden canviar. Seleccioneu **Tanca** per tornar a la pàgina d'exportacions.

## <a name="schedule-and-run-exports"></a>Planificar i executar exportacions

Cada exportació que configureu té una planificació d'actualització. Durant una actualització, el sistema cerca dades noves o actualitzades per incloure-les en una exportació. Per defecte, les exportacions s'executen com a part de cada [actualització del sistema planificada](system.md#schedule-tab). Podeu personalitzar la planificació d'actualització o desactivar-la per executar les exportacions manualment.

Les planificacions d'exportació depenen de l'estat del vostre entorn. Si hi ha actualitzacions en curs en [dependències](system.md#refresh-policies) quan s'hagi d'iniciar una exportació planificada, el sistema finalitzarà primer les actualitzacions i executarà l'exportació. Podeu veure quan s'ha actualitzat per darrer cop una exportació a la columna **Actualitzat**.

### <a name="schedule-exports"></a>Exportacions planificades

Podeu definir planificacions d'actualització personalitzades per a exportacions individuals o diverses exportacions alhora. La planificació definida actualment es mostra a la columna **Planificació** de la llista d'exportació. El permís per canviar la planificació és el mateix que per [editar i definir exportacions](export-destinations.md#set-up-a-new-export). 

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu l'exportació que voleu planificar.

1. Seleccioneu **Planifica** a la barra d'ordres.

1. A la subfinestra **Planifica l'exportació**, definiu l'**Execució planificada** com a **Activada** per executar l'exportació automàticament. Definiu-la com a **Desactivada** per actualitzar-la manualment.

1. Per actualitzar automàticament les exportacions, trieu un valor de **Periodicitat** i especifiqueu-ne els detalls. El temps definit s'aplica a totes les instàncies d'una periodicitat. És el moment en què una exportació hauria de començar a actualitzar-se.

1. Per aplicar i activar els canvis, seleccioneu **Desa**.

Quan editeu la planificació de diverses exportacions, heu de fer una selecció a **Conserva o substitueix les planificacions**:
- **Conserva planificacions individuals**: mantingueu la planificació definida prèviament per a les exportacions seleccionades i només les inhabiliteu o habiliteu.
- **Defineix una planificació nova per a totes les exportacions seleccionades**: substituïu les planificacions existents de les exportacions seleccionades.

### <a name="run-exports-on-demand"></a>Executar exportacions segons la demanda

Per exportar dades sense esperar una actualització planificada, aneu a **Dades** > **Exportacions**.

- Per executar totes les exportacions, seleccioneu **Executa-ho tot** a la barra d'ordres. Aquesta acció només executarà les exportacions que tenen una planificació activa.
- Per executar una única exportació, seleccioneu-la a la llista i seleccioneu **Executa** a la barra d'ordres. Així s'executen les exportacions sense planificacions actives. 

## <a name="remove-an-export"></a>Suprimir una exportació

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu l'exportació que voleu suprimir.

1. Seleccioneu **Elimina** a la barra d'ordres.

1. Confirmeu la supressió seleccionant **Suprimeix** a la pantalla de confirmació.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
