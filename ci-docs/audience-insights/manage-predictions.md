---
title: Tasques compartides per a situacions de predicció
description: Més informació sobre com administrar, solucionar problemes i millor les prediccions.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 4e7e21a610564b30463b27ab703c291275725895
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731976"
---
# <a name="manage-predictions"></a>Administrar prediccions

En aquest article es parla d'algunes tasques que la majoria de situacions de predicció comparteixen.

## <a name="troubleshoot-a-failed-prediction"></a>Resoldre problemes relacionats amb una predicció fallida

1. Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.

1. Seleccioneu els punts suspensius verticals que hi ha al costat de la predicció els registres d'error de la qual voleu visualitzar.

1. Seleccioneu **Registres**.

1. Reviseu tots els errors. Hi ha diversos tipus d'errors que es poden produir i que descriuen la condició que ha causat l'error. Per exemple, un error que indica que no hi ha prou dades per predir amb precisió se sol resoldre amb la càrrega de dades addicionals al Customer Insights.

## <a name="input-data-usability-report"></a>Informe de facilitat d'ús de les dades d'entrada

L'informe d'ús de dades d'entrada proporciona una visualització consolidada dels errors i advertiments que poden generar les previsions de sèrie. També recomana com millorar el rendiment del model.

L'informe està disponible quan un model ha finalitzat el procés d'entrenament. Es crea per a cada model per separat, independentment de si s'ha completat correctament o no.

### <a name="view-the-input-data-usability-report"></a>Visualitzar l'informe d'ús de dades d'entrada

Un cop un model de sèrie ha completat l'entrenament, vegeu-ne l'informe:
- Seleccioneu les el·lipsis del costat del nom del model i trieu **Informe d'ús de dades d'entrada**.
- Seleccioneu l'estat d'un model i seleccioneu **Mostra l'informe d'ús de dades d'entrada** a la subfinestra lateral.
- Seleccioneu un dels models de la llista i seleccioneu l'**informe d'ús de dades d'entrada** a la barra d'ordres.
- Obriu la pàgina de resultats del model i seleccioneu l'**informe d'ús de dades d'entrada** a la barra d'ordres.

### <a name="information-in-the-input-data-usability-report"></a>Informació de l'informe d'ús de dades d'entrada

Les columnes següents de l'informe contenen informació útil per millorar les dades del model.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemple d'un informe d'ús de dades d'entrada que mostra una taula amb errors, advertiments i recomanacions.":::

- **Nom:** Nom descriptiu de l'error, advertiment o recomanació.
- **Pas:** Model fase, tren o puntuació, a la qual es refereix la informació.
- **Estat:** Gravetat de la informació (error, avís, recomanació).
- **Nom de la columna:** columna en una entitat que s'ha de modificar per millorar el rendiment del model.
- **Nom** de l'entitat: Nom de l'entitat que s'ha de modificar per millorar el rendiment del model.
- **Detalls:** detalls sobre l'error, l'avís o la recomanació.

## <a name="refresh-a-prediction"></a>Actualitzar una predicció

Les prediccions s'actualitzaran automàticament amb la mateixa [planificació d'actualització de les dades](system.md#schedule-tab) definida a la configuració. Podeu actualitzar-les manualment també.

1. Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.

1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció que voleu actualitzar.

1. Seleccioneu **Actualitza**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Suprimir una predicció

La supressió d'una predicció també comporta la supressió de la seva entitat de sortida.

1. Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.

1. Seleccioneu els tres punts verticals que hi ha al costat de la predicció que voleu suprimir.

1. Seleccioneu **Suprimeix**.
