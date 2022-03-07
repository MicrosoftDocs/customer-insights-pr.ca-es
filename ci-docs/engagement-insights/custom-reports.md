---
title: Quant als informes personalitzats
description: Apreneu a crear i personalitzar informes.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232136"
---
# <a name="create-and-edit-custom-reports"></a>Crear i editar informes personalitzats

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A banda dels informes estàndard (OOB), podeu crear un informe personalitzat amb visualitzacions de gràfics i taules que us ajudin a comprendre el comportament dels usuaris. En aquest article s'explica com crear un informe amb les dades que necessiteu mitjançant les visualitzacions de taules i gràfics. Per obtenir informació sobre els informes OOB, vegeu [Visualitzar informes](view-reports.md).

## <a name="create-a-custom-report"></a>Crear un informe personalitzat

1. Aneu a **Analitza** > **Personalitza** per accedir a la llista d'informes personalitzats.

1. Seleccioneu **Informe nou** per començar a crear un informe personalitzat.

   :::image type="content" source="media/new-custom-report.png" alt-text="Informes personalitzats nous.":::

1. Decidiu el tipus d'informe que voleu crear:

    - Seleccioneu **Afegeix visual** a la barra d'ordres per crear una visualització de taula per defecte.
    - O bé, seleccioneu una visualització de columna, barra, línia, àrea, circular, dònut o taula des de la subfinestra **Editor d'informes**.

1. A la secció **Dades** de la subfinestra **Editor de visualització**, trieu una de les opcions disponibles (per exemple, visualitzacions de pàgina) al desplegable **Mètriques**. També podeu afegir **Dimensions** (per exemple, país) per mostrar-les a la visualització. Per obtenir més informació, vegeu [Visualitzar i crear mètriques](metrics.md) i [Visualitzar i crear dimensions](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Trieu una mètrica per a l'informe.":::

1. Seleccioneu la secció **Disseny** de la subfinestra **Editor de visualització** per afegir **Text de títol** i activar i desactivar el **títol**.  També podeu canviar el tipus de visualització seleccionant un altre gràfic, com ara un **gràfic circular**.

1. Per canviar la mida i la posició d'una visualització:
   - Seleccioneu la visualització i arrossegueu una de les cantonades o les vores per ajustar-ne la mida.
   - Seleccioneu la visualització i desplaceu-la a una nova posició. També podeu utilitzar les tecles de fletxa per canviar la posició.
1. Per afegir una altra visualització, seleccioneu **Afegeix visual** a la barra d'ordres.
1. Després d'afegir les visualitzacions que voleu per a l'informe, seleccioneu **Desa** a la barra d'ordres.

1. Proporcioneu un nom per a l'informe personalitzat i seleccioneu **Desa** per crear-lo.
 
## <a name="filter-a-custom-report"></a>Filtrar un informe personalitzat

Podeu seleccionar el període de temps o l'interval de dates en un informe personalitzat per centrar-vos en un valor o un període de temps.

Per seleccionar un període de temps, a la part superior dreta de la visualització d'informe, seleccioneu un valor a la llista desplegable de l'informe. També podeu triar un *Interval de dates fix*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrar per hora o interval de dates.":::

Per a la majoria d'informes, seleccioneu **+ Afegeix una condició**, per triar una dimensió o un segment per filtrar l'informe. Per obtenir més informació, vegeu [Visualitzar i crear segments](segments.md).

## <a name="edit-a-custom-report"></a>Editar un informe personalitzat

1. Aneu a **Analitza** > **Personalitza** per accedir a la llista d'informes personalitzats.

1. A la llista d'informes personalitzats, seleccioneu **Més [...]** 

1. Trieu **Edita el nom** per canviar el nom de l'informe.

1. Seleccioneu el nom de l'informe i utilitzeu les opcions **+ Afegeix visual** i **Edita** per afegir, suprimir, canviar la posició o canviar la mida de les visualitzacions.

1. Per canviar les propietats d'una visualització, seleccioneu el visual, seleccioneu ... **i** i, després, **Edita el visual**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Edició de les propietats del gràfic per als informes personalitzats.":::

1. Després d'editar l'informe, seleccioneu **Desa** per aplicar els canvis. 

## <a name="delete-a-custom-report"></a>Suprimir un informe personalitzat

1. Aneu a **Analitza** > **Personalitza** per accedir a la llista d'informes personalitzats.

1. A la llista d'informes personalitzats, seleccioneu **...**

1. Trieu **Suprimeix** per suprimir l'informe.

1. Confirmeu la supressió per suprimir l'informe permanentment.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
