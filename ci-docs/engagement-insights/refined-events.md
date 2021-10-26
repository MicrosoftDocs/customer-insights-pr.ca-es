---
title: Crear i modificar esdeveniments
description: Com crear i modificar incidències.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606178"
---
# <a name="create-and-modify-events"></a>Crear i modificar esdeveniments

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Una incidència són dades que representen el comportament de l'usuari, com ara l'activitat a un lloc web.

- Una incidència *de base* registra quan un usuari visualitza una pàgina (incidència de visualització) o interactua amb el contingut (incidència d'acció).
- Una incidència *refinada* és una visualització virtual d'una incidència de base. Per definir incidències refinades, suprimiu i afegiu propietats o filtreu incidències basades en els valors de propietat.

## <a name="prerequisites"></a>Requisits previs

Per obtenir les incidències, les dades del lloc web s'han de connectar primer a les conclusions sobre les interaccions amb un fragment de codi. Per obtenir més informació, vegeu [Instal·lar l'SDK web en un lloc web](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Primer connecteu les dades.":::

## <a name="create-refined-events"></a>Crea esdeveniments refinats

Utilitzeu incidències refinades per reduir l'àmbit d'una incidència base per [exportar](export-events.md) o suprimir propietats que no són necessàries per a l'exposició.

> [!NOTE]
> Un cop afegiu l'SDK web al lloc web, podeu visualitzar les incidències base i crear incidències refinades. 

Per visualitzar les incidències base:

1. Aneu a **Dades** a la subfinestra de navegació esquerra.

1. Seleccioneu **Incidències** per veure una llista de totes les incidències a l'àrea de treball.

    :::image type="content" source="media/data-events.png" alt-text="Visualitzeu les incidències.":::

Per crear una incidència refinada a partir d'una incidència base: 

1. Aneu a **Dades** > **Incidències** i seleccioneu **+ Noves incidències** a la part superior de la pantalla.

1. Al quadre de diàleg **Incidències noves**, seleccioneu **Crea incidències refinades** i, a continuació, seleccioneu **Següent**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Assistent de creació d'incidències noves.":::
     
1. Al quadre de diàleg **Incidències noves**, introduïu la informació següent:

   - Seleccioneu una incidència al desplegable **Incidències base**.
   - Introduïu un nom al quadre **Nom de visualització de les incidències refinades**.
   - O bé, actualitzeu el **Nom real** suggerit sense utilitzar espais.

1. Seleccioneu **Crea** per aplicar la configuració.

La incidència refinada apareixerà ara a la llista **Incidències**.

### <a name="edit-event-name"></a>Editar el nom de la incidència

Podeu canviar el nom i les propietats d'una incidència base o refinada.

1. Aneu a **Dades** > **Incidències**. 

1. Seleccioneu **Més [...]** a una incidència i seleccioneu **Edita el nom**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Opcions per crear incidències refinades.":::

3. Actualitzeu el nom de la incidència i seleccioneu **Canvia el nom**.

### <a name="view-the-details-of-a-refined-event"></a>Visualitzeu els detalls d'una incidència refinada:

1. A la llista **Incidències**, seleccioneu la incidència base o refinada. 

1. Seleccioneu **Afegeix i suprimeix propietats** a la part superior de la pantalla per obrir la subfinestra **Edita les propietats**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Afegiu i suprimiu propietats.":::

1. Utilitzeu les caselles de selecció per seleccionar les propietats que voleu mostrar i les que voleu amagar. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Editar les propietats de les incidències refinades.":::

1. Seleccioneu **Confirma** per aplicar la selecció i, a continuació, seleccioneu **Desa**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Editar les propietats seleccionades per a una incidència refinada

1. Aneu a **Dades** > **Incidències** i seleccioneu les incidències refinades per obrir la visualització detallada.
1. Seleccioneu **Afegeix i suprimeix propietats**. 
1. Editeu la selecció de les caselles de selecció.
1. Seleccioneu **Confirma** i, a continuació, **Desa** per aplicar els canvis.

Per obtenir informació sobre l'exportació d'incidències, vegeu [Exportar incidències](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
