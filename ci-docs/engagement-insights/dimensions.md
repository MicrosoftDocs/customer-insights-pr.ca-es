---
title: Visualitzar i crear dimensions
description: Com crear, editar i suprimir dimensions.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033985"
---
# <a name="view-and-create-dimensions"></a>Visualitzar i crear dimensions

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Una dimensió és un atribut d'una incidència que pot descriure, filtrar o agrupar dades. Si executeu una promoció de màrqueting al lloc web, podeu utilitzar dimensions per ordenar els visitants segons usuaris nous i retornats.  

Els coneixements d'interacció inclouen dimensions estàndard per a les propietats de la incidència. Els exemples inclouen:

- Nom del navegador
- Nom de la pàgina
- Model del dispositiu
- Sistema operatiu
- Country

## <a name="view-dimensions"></a>Dimensions de visualització

Les dimensions es basen en les propietats d'una incidència existent. Quan utilitzeu el codi de seguiment per als coneixements d'interacció, es creen automàticament les dimensions del sistema.

1. Aneu a **Dades** a la subfinestra de navegació esquerra. 
1. Seleccioneu **Dimensions** per veure una llista de totes les dimensions de l'àrea de treball. 
   > [!NOTE]
   > Les dimensions generades pel sistema són només de lectura. No les podeu editar. Només podeu crear i editar dimensions personalitzades.

## <a name="create-a-dimension"></a>Crea una dimensió

A banda de les dimensions generades pel sistema, els administradors de l'entorn i de l'àrea de treball poden crear dimensions personalitzades. Les dimensions personalitzades es basen en les propietats per defecte de les incidències base o poden utilitzar [les propietats personalitzades d'una incidència](advanced-SDK-implementation.md).

1. Aneu a **Dades** > **Dimensions**.
1. Seleccioneu **Afegeix una dimensió**.

   :::image type="content" source="media/add-dimension.png" alt-text="Afegiu una dimensió a una incidència.":::

1. A la subfinestra **Crea una dimensió**, seleccioneu una propietat per basar-hi la dimensió. La llista de propietats mostrarà totes les propietats de l'àrea de treball no assignades a cap dimensió.
1. Introduïu un nom al quadre **Nom de visualització**. De forma opcional, podeu afegir una descripció.
1. Seleccioneu **Crea** per crear la dimensió. Pot tardar un minut abans que pugueu utilitzar la dimensió a un [informe personalitzat](custom-reports.md) o a un [segment](segments.md). 

## <a name="edit-a-dimension"></a>Editar una dimensió

Podeu canviar el nom i la descripció d'una dimensió.

1. Aneu a **Dades** > **Dimensions**.
1. Seleccioneu la dimensió que voleu suprimir.
1. A la subfinestra **Edita la dimensió**, actualitzeu la dimensió.
1. Seleccioneu **Aplica** per desar els canvis.

## <a name="delete-a-dimension"></a>Suprimir una dimensió

Només podeu suprimir les dimensions creades per usuaris, però no podeu suprimir dimensions del sistema.

La supressió d'una dimensió és permanent. Els informes i els segments que utilitzin una dimensió suprimida ja no funcionaran. 

1. Aneu a **Dades** > **Dimensions**.
1. Seleccioneu la dimensió que voleu suprimir.
1. A la subfinestra **Edita la dimensió**, seleccioneu **Suprimeix la dimensió**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Suprimiu una dimensió a una incidència.":::

1. Introduïu **CONFIRMA LA SUPRESSIÓ** (en tots els límits) per confirmar la supressió. 
1. Seleccioneu **Suprimeix**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]