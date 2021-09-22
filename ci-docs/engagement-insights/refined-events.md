---
title: Creació i modificació d'esdeveniments refinats
description: Com crear i modificar esdeveniments refinats.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034762"
---
# <a name="create-and-modify-refined-events"></a>Creació i modificació d'esdeveniments refinats

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Una incidència són dades que representen el comportament de l'usuari, com ara l'activitat a un lloc web.

- Una incidència *de base* registra quan un usuari visualitza una pàgina (incidència de visualització) o interactua amb el contingut (incidència d'acció).
- Una incidència *refinada* és una visualització virtual d'una incidència de base. Per definir incidències refinades, suprimiu i afegiu propietats o filtreu incidències basades en els valors de propietat.

Utilitzeu incidències refinades per reduir l'àmbit d'una incidència base per [exportar](export-events.md) o suprimir propietats que no són necessàries per a l'exposició.

## <a name="create-refined-events"></a>Crear incidències millorades

Hi ha tres maneres de crear una incidència refinada a partir d'una incidència de base. 

1. Aneu a **Dades**> **Incidències** i trieu una de les opcions següents:
    - Seleccioneu **Incidències noves** i, a continuació, seleccioneu **Crea incidències refinades**.
    - Seleccioneu una incidència de base per obrir una visualització detallada i seleccioneu **Crea incidències refinades** al menú superior.
    - Seleccioneu **Més [...]** per obrir el menú de drecera d'una incidència de base. A continuació, seleccioneu **Crea incidències refinades**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Opcions per crear incidències refinades.":::

1. Al quadre de diàleg **Crea incidències refinades**, introduïu la informació següent:

- Seleccioneu una incidència al desplegable **Incidències de base** si esteu creant una incidència nova.
- Introduïu un nom al quadre **Nom de visualització de les incidències refinades**.
- O bé, actualitzeu el **Nom real** suggerit sense utilitzar espais.

3. Seleccioneu **Crea** per aplicar la configuració.

1. A la visualització detallada de la incidència refinada, seleccioneu **Afegeix i suprimeix propietats** per obrir la subfinestra **Edita les propietats**. 

1. Utilitzeu les caselles de selecció per seleccionar les propietats que voleu mostrar i les que voleu amagar. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Editar les propietats de les incidències refinades.":::

1. Seleccioneu **Confirma** per aplicar la vostra selecció.

1. Seleccioneu **Desa** per desar la configuració.

## <a name="edit-refined-events"></a>Editar incidències refinades

Podeu canviar el nom i les propietats d'una incidència refinada.

### <a name="edit-event-name"></a>Editar el nom de la incidència

1. Aneu a **Dades** > **Incidències**. 
1. Seleccioneu **Més [...]** a una incidència i seleccioneu **Edita el nom**.
1. Actualitzeu el nom de la incidència i seleccioneu **Canvia el nom**.

### <a name="edit-selected-properties"></a>Editar propietats seleccionades

1. Aneu a **Dades** > **Incidències** i seleccioneu les incidències refinades per obrir la visualització detallada.
1. Seleccioneu **Afegeix i suprimeix propietats**. 
1. Editeu la selecció de les caselles de selecció.
1. Seleccioneu **Confirma** i, a continuació, **Desa** per aplicar els canvis.

Per obtenir informació sobre l'exportació d'incidències, vegeu [Exportar incidències](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
