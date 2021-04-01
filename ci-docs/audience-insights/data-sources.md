---
title: Utilitzar fonts de dades per ingerir dades
description: Més informació sobre com importar dades de diverses fonts.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595935"
---
# <a name="data-sources-overview"></a>Informació general de les fonts de dades

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

La capacitat de conclusions del públic del Dynamics 365 Customer Insights connecta amb les dades d'un ampli conjunt de fonts. La connexió a una font de dades sovint es coneix com el procés d'*ingesta de dades*. Després d'ingerir les dades, les podeu [unificar](data-unification.md) i treballar-hi.

## <a name="add-a-data-source"></a>Afegeix un origen de dades

Consulteu els articles detallats sobre com afegir una font de dades, en funció de l'opció que trieu.

Podeu afegir una font de dades de tres maneres principals:

- [Mitjançant desenes de connectors del Power Query](connect-power-query.md)
- [Des d'una carpeta del Common Data Model](connect-common-data-model.md)
- [Des del vostre propi llac del Common Data Service](connect-common-data-service-lake.md)

> [!NOTE]
> Encara no podeu afegir dades de les fonts de dades locals.

## <a name="review-ingested-data"></a>Revisar les dades ingerides

Veureu el nom de cada font de dades ingerida, el seu estat i l'última vegada que les dades s'han actualitzat per a aquesta font. Podeu ordenar la llista de fonts de dades per cada columna.

> [!div class="mx-imgBorder"]
> ![Font de dades afegida](media/configure-data-datasource-added.png "Font de dades afegida")

|Estat  |Descripció  |
|---------|---------|
|Correcte   |La font de dades s'ha ingerit correctament si es mostra una hora a la columna **Actualitzat**.
|No s'ha iniciat   |La font de dades no té encara dades ingerides o encara es troben en mode d'esborrany.         |
|S'està actualitzant    |La ingestió de dades està en curs. Per cancel·lar aquesta operació, seleccioneu **Deixa d'actualitzar** a la columna **Accions**. Si atureu l'actualització d'una font de dades, es revertirà a l'últim estat d'actualització.       |
|Erroni     |L'ingestió de dades ha trobat errors.         |

Seleccioneu el valor de la columna **Estat** de qualsevol font de dades per revisar més detalls. A la subfinestra **Detalls del progrés**, expandiu **Fonts de dades**. Seleccioneu **Visualitza els detalls** per a més informació sobre l'estat d'actualització, incloent-hi els detalls dels errors i les actualitzacions dels processos derivats.

La càrrega de dades pot tardar una estona. Després d'una actualització correcta, les dades d'ingerides es poden revisar des de la pàgina **Entitats**. Per obtenir més informació, vegeu [Entitats](entities.md).

## <a name="refresh-a-data-source"></a>Actualitzar una font de dades

Les fonts de dades es poden actualitzar seguint una planificació automàtica o bé manualment segons demanda. 

Per configurar les actualitzacions planificades de totes les fonts de dades ingerides, aneu a **Administració** > **Sistema** > [**Planificació**](system.md#schedule-tab).

Per actualitzar una font de dades segons demanda, seguiu aquests passos:

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2. Seleccioneu els punts suspensius verticals que hi ha al costat de la font de dades que voleu actualitzar i seleccioneu **Actualitza** a la llista desplegable.

3. S'inicia l'actualització manual de la font de dades en qüestió. En actualitzar una font de dades, s'actualitza tant l'esquema de l'entitat com les dades de totes les entitats especificades a la font de dades.

4. Seleccioneu **Para d'actualitzar** si voleu cancel·lar una actualització existent; la font de dades tornarà a l'últim estat d'actualització.

## <a name="delete-a-data-source"></a>Suprimir una font de dades

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2. Seleccioneu els punts suspensius vertical que hi ha al costat de la font de dades que voleu suprimir i seleccioneu **Suprimeix** al menú desplegable.

3. Confirmeu la supressió.


[!INCLUDE[footer-include](../includes/footer-banner.md)]