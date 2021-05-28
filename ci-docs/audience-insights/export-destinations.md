---
title: Exportar dades del Customer Insights
description: Administrar les exportacions per compartir dades.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016602"
---
# <a name="exports-preview-overview"></a>Informació general sobre exportacions (versió preliminar)

A la pàgina **Exportacions** es mostren totes les exportacions configurades. Les exportacions comparteixen dades específiques amb diverses aplicacions. Poden incloure perfils de clients o entitats, esquemes i detalls d'assignació. Cada exportació requereix una [connexió, configurada per un administrador, per administrar l'autenticació i l'accés](connections.md).

Aneu a **Dades** > **Exportacions** per visualitzar la pàgina d'exportacions. Totes les funcions d'usuari tenen accés per visualitzar les exportacions configurades. Utilitzeu el camp de cerca a la barra d'ordres per cercar les exportacions pel seu nom, nom de connexió o tipus de connexió.

## <a name="set-up-a-new-export"></a>Configurar una exportació nova

Per configurar o editar una exportació, heu de tenir connexions disponibles. Les connexions depenen de la vostra [funció d'usuari](permissions.md):
- Els administradors tenen accés a totes les connexions. També poden crear connexions noves quan configuren una exportació.
- Els col·laboradors poden tenir accés a connexions específiques. Depenen dels administradors per configurar i compartir connexions. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Els visualitzadors només poden visualitzar les exportacions existents, però no les poden crear.

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació** per crear una destinació d'exportació nova.

1. A la subfinestra **Configura l'exportació**, seleccioneu la connexió que voleu utilitzar. Les [connexions](connections.md)les administren els administradors. 

1. Proporcioneu els detalls necessaris i seleccioneu **Desa** per crear l'exportació.

### <a name="edit-an-export"></a>Editar una exportació

1. Seleccioneu els punt suspensius verticals de la destinació d'exportació que voleu editar.

1. Al menú desplegable, seleccioneu **Edita**.

1. Canvieu els valors que voleu actualitzar i seleccioneu **Desa**.

## <a name="view-exports-and-export-details"></a>Visualitzar les exportacions i els detalls d'exportació

Un cop creades les destinacions d'exportació, es mostren a **Dades** > **Exportacions**. Tots els usuaris poden veure quines dades es comparteixen i el seu estat més recent.

1. Vés a **Dades** > **Exportacions**.

1. Els usuaris sense permisos d'edició seleccionen **Visualització** en lloc d'**Edició** per veure els detalls de l'exportació.

1. Aquesta subfinestra lateral mostra la configuració d'aquesta exportació. Sense permisos d'edició, els valors no es poden canviar. Seleccioneu **Tanca** per tornar a la pàgina d'exportacions.

## <a name="run-exports-on-demand"></a>Executar exportacions segons la demanda

Després de configurar una exportació, s'executarà amb cada [actualització planificada](system.md#schedule-tab) sempre que tingui una connexió que funcioni.

Per exportar dades sense esperar una actualització planificada, aneu a **Dades** > **Exportacions**. Teniu dues opcions:

- Per executar totes les exportacions, seleccioneu **Executa-ho tot** a la barra d'ordres. 
- Per executar una sola exportació, seleccioneu els punts suspensius (...) d'un element de llista i, a continuació, trieu **Executa**.

## <a name="remove-an-export"></a>Suprimir una exportació

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu els punt suspensius verticals de l'exportació que voleu suprimir.

1. Seleccioneu **Suprimeix** al menú desplegable.

1. Confirmeu la supressió seleccionant **Suprimeix** a la pantalla de confirmació.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
