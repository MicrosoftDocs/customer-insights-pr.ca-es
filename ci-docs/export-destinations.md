---
title: Informació general sobre exportacions (versió preliminar)
description: Administrar les exportacions per compartir dades.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: fd234aff9021ded76d8226bf2f15e035cf75e7db
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245315"
---
# <a name="exports-preview-overview"></a>Informació general sobre exportacions (versió preliminar)

 Les exportacions us permeten compartir dades específiques amb diverses aplicacions. Poden incloure perfils de client, entitats, esquemes i detalls d'assignació. Cada exportació requereix una [connexió, configurada per un administrador, per administrar l'autenticació i l'accés](connections.md). A la pàgina **Exportacions** es mostren totes les exportacions configurades.

## <a name="export-types"></a>Tipus d'exportacions

Hi ha dos tipus principals d'exportacions:  

- **Exportacions de data-out: exporteu** qualsevol tipus d'entitat disponible al Customer Insights. Les entitats que seleccioneu per a l'exportació s'exporten amb tots els camps de dades, les metadades, els esquemes i els detalls de les assignacions.
- **Segmentar les exportacions: entitats del segment d'exportació des** del Customer Insights. Els segments representen una llista de perfils de client. En configurar l'exportació, seleccioneu els camps de dades inclosos, en funció del sistema de destinació al qual exporteu dades.

### <a name="export-segments"></a>Exportar segments

**Exportar segments en entorns per a comptes empresarials (d'empresa a empresa) o consumidors individuals (d'empresa a consumidor)**  
La majoria de les opcions d'exportació admeten els dos tipus d'entorns. L'exportació de segments a diversos sistemes de destinació té requisits específics. 

**Segmentar les exportacions en entorns per a consumidors individuals (d'empresa a consumidor)**  
- Els segments en el context dels entorns per a clients individuals estan integrats a l'entitat *perfil de client unificat*. Tots els segments que compleixen els requisits dels sistemes de destinació (per exemple, una adreça electrònica) es poden exportar.

**Segmentar entorns d'exportació per a comptes empresarials (d'empresa a empresa)**  
- Els segments en el context dels entorns de comptes empresarials estan integrats a l'entitat *compte*. Per exportar els segments de compte, és necessari que el sistema de destinació admeti segments de compte purs. Aquest és el cas del [LinkedIn](export-linkedin-ads.md) quan trieu l'opció **empresa** en definir l'exportació.
- La resta de sistemes de destinació requereixen camps de l'entitat contacte. Per garantir que els segments de compte poden recuperar dades de contactes relacionats, la definició del segment ha de projectar els atributs de l'entitat contacte. Més informació sobre com [configurar segments i atributs de projecte](segment-builder.md).

**Límits de les exportacions de segments**  
- Els sistemes de destinació de tercers poden limitar el nombre de perfils de client que podeu exportar. 
- Per als clients individuals, en seleccionar un segment per a l'exportació veureu el nombre real de membres del segment. Rebreu un advertiment si un segment és massa gran. 
- Per als comptes empresarials, veureu el nombre de comptes en un segment; tanmateix, el nombre de contactes que es poden projectar no es mostra. En alguns casos, podria fer que el segment exportat contingui realment més perfils de clients que els que accepta el sistema de destinació. Si se superen els límits del sistema de destinació, s'omet l'exportació.

## <a name="set-up-a-new-export"></a>Configurar una exportació nova

Per configurar o editar una exportació, necessiteu les connexions adequades que teniu a la vostra disposició. Les connexions depenen de la vostra [funció d'usuari](permissions.md):
- Els **administradors** tenen accés a totes les connexions. També poden crear connexions noves quan configuren una exportació.
- Els **col·laboradors** poden tenir accés a connexions específiques. Depenen dels administradors per configurar i compartir connexions. La llista d'exportacions mostra als contribuïdors si poden editar o només visualitzar una exportació a la columna **Els vostres permisos**. Per obtenir més informació, aneu a [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Els **visualitzadors** només poden visualitzar les exportacions existents, no crear-les.

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació** per crear una exportació nova.

1. A la subfinestra Configura l'exportació **·**, seleccioneu quina [connexió](connections.md) voleu utilitzar.

1. Proporcioneu els detalls necessaris i seleccioneu **Desa** per crear l'exportació. Per obtenir els detalls necessaris, reviseu la documentació del Customer Insights per a l'exportació específica.

## <a name="manage-existing-exports"></a>Gestionar les exportacions existents

Aneu a **Exportacions** > **de dades** per veure les exportacions, el nom de connexió, el tipus de connexió i l'estat. Totes les funcions d'usuari poden veure les exportacions configurades. Podeu ordenar la llista d'exportacions per qualsevol columna o utilitzar el quadre de cerca per trobar l'exportació que voleu gestionar.

Seleccioneu una exportació per veure les accions disponibles.

:::image type="content" source="media/exports_showmore.png" alt-text="Pàgina d'exportacions.":::

- **Visualitzar** o **editar** l'exportació. Els usuaris sense editar permisos seleccionen **Visualitza** en comptes d'**Edita** per veure els detalls de l'exportació.
- **Executeu** l'exportació per exportar les dades més recents.
- **Crear duplicat** d'una exportació.
- **[Programeu](#schedule-and-run-exports)** l'exportació.
- **Desprengui la connexió** per eliminar la connexió d'aquesta exportació. Detach no elimina la connexió, sinó que desactiva l'exportació. La **columna Connexió utilitzada** mostra Sense connexió.
- **Traieu** l'exportació.

## <a name="schedule-and-run-exports"></a>Planificar i executar exportacions

Cada exportació que configureu té una planificació d'actualització. Durant una actualització, el sistema cerca dades noves o actualitzades per incloure-les en una exportació. Per defecte, les exportacions s'executen com a part de cada [actualització del sistema planificada](schedule-refresh.md). Podeu personalitzar la planificació d'actualització o desactivar-la per executar les exportacions manualment.

Les planificacions d'exportació depenen de l'estat del vostre entorn. Si hi ha actualitzacions en curs en [dependències](system.md#refresh-processes) quan s'hagi d'iniciar una exportació planificada, el sistema finalitzarà primer les actualitzacions i executarà l'exportació. La **columna Actualitza es** mostra quan es va actualitzar per última vegada una exportació.

### <a name="schedule-exports"></a>Exportacions planificades

Definiu planificacions d'actualització personalitzades per a exportacions individuals o diverses exportacions alhora. La planificació definida actualment es mostra a la columna **Planificació** de la llista d'exportació. El permís per canviar la planificació és el mateix [que editar i definir exportacions](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu l'exportació que voleu planificar.

1. Seleccioneu **Planifica**.

1. A la subfinestra **Planifica l'exportació**, definiu l'**Execució planificada** com a **Activada** per executar l'exportació automàticament. Definiu-la com a **Desactivada** per actualitzar-la manualment.

1. Per actualitzar automàticament les exportacions, trieu un valor de **Periodicitat** i especifiqueu-ne els detalls. El temps definit s'aplica a totes les instàncies d'una periodicitat. És el moment en què una exportació hauria de començar a actualitzar-se.

1. Seleccioneu **Desa**.

Quan editeu la planificació de diverses exportacions, feu una selecció a **Conserva o substituïu les planificacions**:

- **Mantenir planificacions individuals: mantén** la planificació definida prèviament per a les exportacions seleccionades i només les desactiva o activa.
- **Defineix una planificació nova per a totes les exportacions seleccionades**: substituïu les planificacions existents de les exportacions seleccionades.

### <a name="run-exports-on-demand"></a>Executar exportacions segons la demanda

Per exportar dades sense esperar una actualització planificada, aneu a **Dades** > **Exportacions**.

- Per executar totes les exportacions, seleccioneu **Executa-ho tot** a la barra d'ordres. Només s'executen les exportacions que tenen una planificació activa. Per executar una exportació que no estigui activa, executeu una única exportació.
- Per executar una única exportació, seleccioneu-la a la llista i seleccioneu **Executa** a la barra d'ordres.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
