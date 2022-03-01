---
title: Visualitzar informes de dades
description: Utilitzeu els informes disponibles per veure l'activitat en temps real al vostre lloc.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036636"
---
# <a name="view-reports"></a>Visualitza els informes

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un informe és una col·lecció de visualitzacions de dades, amb les dades recopilades a través de l'SDK, que us ajuden a mesurar i comprendre el comportament dels usuaris. Les conclusions d'interacció del Dynamics 365 Customer Insights inclouen informes de fàbrica (OOB) per a projectes web i mòbils.  

## <a name="web-reports"></a>Informes web

Podeu accedir als informes web a **Descobriu** a la subfinestra de navegació esquerra.

:::image type="content" source="media/report-menu.png" alt-text="Navegació que mostra la llista d'informes disponibles.":::

### <a name="real-time-usage-report"></a>Informe d'ús en temps real

L'informe d'**ús en temps real** proporciona una descripció general de l'activitat actual del lloc que s'actualitza automàticament cada minut. Utilitzeu l'ús en temps real per supervisar l'impacte de les campanyes de màrqueting, esdeveniments de premsa i altres escenaris del trànsit del lloc.

### <a name="key-metrics-reports"></a>Informes de mètriques clau

- Les **visualitzacions de pàgina** enumeren les visualitzacions de pàgina per a pàgines individuals juntament amb el nombre de visualitzacions de pàgina totals durant el període de temps seleccionat.

- Les **visites** mostren informació sobre el nombre de visites i la durada de la visita.

- Els **visitants** indiquen els visitants nous i anteriors únics al vostre lloc.

### <a name="content-reports"></a>Informes de contingut

- Els **enllaços** mostren informació sobre el nombre i el tipus de clics.

- Les **pàgines de sortida** indiquen els enllaços en què han fet clic els visitants per sortir del lloc.

### <a name="traffic-sources-reports"></a>Informes de fonts del trànsit

- Les **referències** indiquen els dominis i les adreces URL que han portat visitants al vostre lloc.

- Els **codis de seguiment** proporcionen detalls sobre els codis de seguiment dels enllaços que han portat visitants al vostre lloc.

### <a name="visitor-profiles-reports"></a>Informes de perfils de visitant

- Els **dispositius** són una llista dels dispositius físics utilitzats per accedir al lloc.

- Els **SO i navegadors** proporcionen informació sobre els sistemes operatius i els navegadors que s'estan executant quan accedeixen al vostre lloc.

- Les **ubicacions** mostren informació sobre els visitants per país, regió i ciutat.

- Les **llengües** enumeren les visualitzacions de la pàgina segons les llengües preferides del visitant.

## <a name="mobile-reports"></a>Informes mòbils

Els informes mòbils s'agrupen en categories d'ús en temps real, aplicació i usuari. Podeu accedir als informes mòbils a **Descobriu** a la subfinestra de navegació esquerra.   

:::image type="content" source="media/mobile-reports.png" alt-text="Interfície d'usuari de les conclusions d'interacció que mostra l'informe d'ús en temps real que representa dades en gràfics i llistes.":::   

### <a name="real-time-usage"></a>Ús en temps real

L'**ús en temps real** proporciona una descripció general de l'activitat actual a l'aplicació mòbil que s'actualitza automàticament cada minut. Utilitzeu l'ús en temps real per supervisar el nombre d'usuaris i les sessions que hi ha actualment actius a l'aplicació i les principals visualitzacions de pantalla.

### <a name="app-reports"></a>Informes d'aplicació

- Les **visualitzacions de pantalla** enumeren visualitzacions de pantalla per a pantalles individuals en una aplicació i el nombre total de visualitzacions de pantalla durant un període de temps seleccionat. Podeu visualitzar les visualitzacions de pantalla per nom de pantalla o per títol de pantalla.

- Les **sessions** mostren informació sobre el nombre de sessions i la duració de la sessió.

- La **freqüència de retorn** agrupa els nombres de sessions pel nombre de dies des de l'última sessió.

- Els **usuaris** mostren els usuaris nous i anteriors a l'aplicació mòbil.

- Els **esdeveniments** inclouen tots els esdeveniments recopilats de l'aplicació i el recompte total de cada esdeveniment.

### <a name="user-reports"></a>Informes d'usuaris

- Les **versions de l'aplicació** enumeren les versions de l'aplicació mòbil que utilitza la base d'usuaris.

- Els **dispositius i versions del sistema operatiu** proporcionen informació sobre quins dispositius i sistemes operatius executen l'aplicació mòbil.

- Les **ubicacions** mostren informació sobre els usuaris de l'aplicació per país, regió i ciutat.

## <a name="filter-by-time-or-value"></a>Filtrar per hora o valor

Podeu seleccionar un període de temps o un valor en un informe web o mòbil per centrar-vos en un valor o un període de temps. 

- Per seleccionar un període de temps, seleccioneu **Més [...]** a la llista desplegable de l'informe. La selecció d'interval de temps està inhabilitada per a un informe d'ús en temps real; l'interval de temps d'un informe d'ús en temps real és "ara".

- A la majoria d'informes, seleccioneu un valor en un gràfic o una llista per filtrar l'informe segons el valor seleccionat.

[!INCLUDE[footer-include](../includes/footer-banner.md)]