---
title: Utilitzar fonts de dades per ingerir dades
description: Més informació sobre com importar dades de diverses fonts.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 75d597158233f75f0eb5f94389f9dba199d81719f2bbe4e5cc58d2a3afc7dcf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032838"
---
# <a name="data-sources-overview"></a>Informació general de les fonts de dades

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

La capacitat de conclusions del públic del Dynamics 365 Customer Insights connecta amb les dades d'un ampli conjunt de fonts. La connexió a una font de dades sovint es coneix com el procés d'*ingesta de dades*. Després d'ingerir les dades, les podeu [unificar](data-unification.md) i treballar-hi.

## <a name="add-a-data-source"></a>Afegeix un origen de dades

Consulteu els articles detallats sobre com afegir una font de dades, en funció de l'opció que trieu.

Podeu afegir una font de dades de tres maneres principals:

- [Mitjançant desenes de connectors del Power Query](connect-power-query.md)
- [Des d'una carpeta del Common Data Model](connect-common-data-model.md)
- [Des del vostre propi llac del Microsoft Dataverse](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Afegir dades des de fonts de dades locals

La ingesta de dades de fonts de dades locals a les conclusions del públic està admesa als fluxos de dades del Microsoft Power Platform. Els fluxos de dades es poden habilitar al Customer Insights [proporcionant l'adreça URL de l'entorn del Microsoft Dataverse](get-started-paid.md) en configurar l'entorn.

Les fonts de dades que es creen després d'associar un entorn del Dataverse amb el Customer Insights utilitzaran [fluxos de dades del Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) per defecte. Els fluxos de dades admeten la connectivitat local mitjançant l'ús de la passarel·la de dades. Suprimiu i torneu a crear fonts de dades que hi havia abans a l'entorn del Dataverse que estava associat a [utilitzar les passarel·les de dades locals](/data-integration/gateway/service-gateway-app).

Les passarel·les de dades d'un entorn existent del Power BI o el Power Apps seran visibles i es poden reutilitzar al Customer Insights. La pàgina de fonts de dades mostra enllaços per anar a l'entorn del Microsoft Power Platform on podeu visualitzar i configurar passarel·les de dades locals.

## <a name="review-ingested-data"></a>Revisar les dades ingerides

Veureu el nom de cada font de dades ingerida, el seu estat i l'última vegada que les dades s'han actualitzat per a aquesta font. Podeu ordenar la llista de fonts de dades per cada columna.

> [!div class="mx-imgBorder"]
> ![Font de dades afegida](media/configure-data-datasource-added.png "Font de dades afegida")

|Estat d'execució  |Descripció  |
|---------|---------|
|Correcte   |La font de dades s'ha ingerit correctament si es mostra una hora a la columna **Actualitzat**.
|No s'ha iniciat   |La font de dades no té encara dades ingerides o encara es troben en mode d'esborrany.         |
|S'està actualitzant    |La ingestió de dades està en curs. Per cancel·lar aquesta operació, seleccioneu **Deixa d'actualitzar** a la columna **Accions**. Si atureu l'actualització d'una font de dades, es revertirà a l'últim estat d'actualització.       |
|Erroni     |L'ingestió de dades ha trobat errors.         |

Seleccioneu el valor de la columna **Estat** de qualsevol font de dades per revisar més detalls. A la subfinestra **Detalls del progrés**, expandiu **Fonts de dades**. Seleccioneu **Visualitza els detalls** per a més informació sobre l'estat d'actualització, incloent-hi els detalls dels errors i les actualitzacions dels processos derivats.

La càrrega de les dades pot tardar temps. Després d'una actualització correcta, les dades d'ingerides es poden revisar des de la pàgina **Entitats**. Per obtenir més informació, vegeu [Entitats](entities.md).

## <a name="refresh-a-data-source"></a>Actualitzar una font de dades

Les fonts de dades es poden actualitzar seguint una planificació automàtica o bé manualment segons demanda. 

Per configurar les actualitzacions planificades de totes les fonts de dades ingerides, aneu a **Administració** > **Sistema** > [**Planificació**](system.md#schedule-tab).

Per actualitzar una font de dades segons demanda, seguiu aquests passos:

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2. Seleccioneu els punts suspensius verticals al costat de la font de dades voleu actualitzar i seleccioneu **Actualitza** a la llista desplegable.

3. S'inicia l'actualització manual de la font de dades en qüestió. En actualitzar una font de dades s'actualitza tan l'esquema d'entitat com les dades de totes les entitats especificades a la font de dades.

4. Seleccioneu **Para d'actualitzar** si voleu cancel·lar una actualització existent; la font de dades tornarà a l'últim estat d'actualització.

## <a name="delete-a-data-source"></a>Suprimir una font de dades

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2. Seleccioneu els punts suspensius verticals al costat de la font de dades voleu suprimir i seleccioneu **Suprimeix** al menú desplegable.

3. Confirmeu la supressió.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
