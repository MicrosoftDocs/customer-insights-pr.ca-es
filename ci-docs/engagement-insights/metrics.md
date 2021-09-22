---
title: Visualitzar i crear mètriques
description: Com crear, editar i suprimir mètriques.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034257"
---
# <a name="view-and-create-metrics"></a>Visualitzar i crear mètriques

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Les mètriques ajuden a entendre el comportament dels visitants. Agreguen propietats d'incidències i mesuren les estadístiques i el rendiment de les vostres propietats web.  

Suposem que esteu executant una promoció de màrqueting al vostre lloc web. Podeu utilitzar les mètriques per fer el seguiment del nombre de visitants o usuaris únics que han vingut al vostre lloc web durant la promoció. Analitzar mètriques us ajuda a entendre millor el públic del lloc web. La combinació de mètriques amb [dimensions](dimensions.md) en un [informe personalitzat](custom-reports.md) us permet mesurar el comportament per comprendre els usuaris. Per exemple, podeu separar el procés de participació en categories noves i que retornen per identificar les diferències d'interès i intenció entre els grups.

## <a name="view-metrics"></a>Visualitzar mètriques

Els coneixements d'interacció inclouen agregacions freqüents de les propietats d'incidències com a mètriques del sistema: 

- Visitants
- Visites
- Visualitzacions de la pàgina
- Clics

Aquestes mètriques del sistema es basen en les propietats d'incidències existents a les incidències base.

1. Aneu a **Dades** a la subfinestra de navegació esquerra. 
1. Seleccioneu la pestanya **Mètriques** per veure una llista de totes les mètriques de l'àrea de treball. 
   > [!NOTE]
   > Les mètriques generades pel sistema són només de lectura. No les podeu canviar ni suprimir. Només podeu crear i editar mètriques personalitzades.

## <a name="create-a-metric"></a>Crear una mètrica

Els administradors de l'entorn i de l'àrea de treball poden crear mètriques. Les propietats de la incidència s'han d'enviar a l'àrea de treball abans de crear una mètrica. Podeu crear mètriques a partir de les propietats de la incidència enviades per incidències base o utilitzar l'SDK web per [enviar propietats d'incidències personalitzades](advanced-SDK-implementation.md).

1. Aneu a **Dades** > **Mètriques**.
1. Seleccioneu **Mètrica nova**.

   :::image type="content" source="media/new-metric.png" alt-text="Afegiu una mètrica a una incidència.":::

1. Pel format, seleccioneu el tipus de dades **Enter** o **Doble**. Enter és un nombre enter. Per a Doble, podeu triar entre una i tres posicions de decimals.
1. A la subfinestra **Biblioteca de recursos**, cerqueu la propietat de la incidència en la qual es basa la mètrica.
1. Seleccioneu el **signe més (+)** al costat de la propietat per utilitzar-lo a la fórmula. Només podeu crear una fórmula basada en una propietat. 
1. Trieu una de les funcions agregades següents. 

   - Suma: el total aritànhètic de tots els valors 
   - Mitjana: la mitjana de tots els valors
   - Recompte: el nombre total de valors
   - Recompte diferent: el nombre total de valors diferents

   Després de definir la mètrica, veureu una versió preliminar de l'activitat de la mètrica de la darrera hora.

1. Seleccioneu **Desa**. 
1. Introduïu un nom per a la mètrica i seleccioneu **Desa**.

Pot trigar un minut abans que pugueu utilitzar la mètrica per [crear informes personalitzats](custom-reports.md).

## <a name="edit-a-metric"></a>Editar una mètrica

1. Aneu a **Dades** > **Mètriques**.
1. Seleccioneu la mètrica a la llista.
1. Canviar la definició de la mètrica
1. Seleccioneu **Desa**.

## <a name="change-the-name-of-a-metric"></a>Canviar el nom d'una mètrica

1. Aneu a **Dades** > **Mètriques**.
1. Seleccioneu **Més [...]** per a una mètrica i trieu **Edita el nom**.
1. Canvieu-ne el nom. 
1. Seleccioneu **Canvia el nom**.

## <a name="delete-a-metric"></a>Suprimir una mètrica

1. Aneu a **Dades** > **Mètriques**.
1. Seleccioneu **Més [...]** per a una mètrica i trieu **Suprimeix**.

   :::image type="content" source="media/delete-metric.png" alt-text="Suprimiu una mètrica d'una incidència.":::

1. Seleccioneu **Suprimeix** per confirmar la supressió.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
