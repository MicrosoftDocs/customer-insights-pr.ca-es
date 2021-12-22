---
title: Utilitzar fonts de dades per ingerir dades
description: Més informació sobre com importar dades de diverses fonts.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 6846c73cb156aaa049e2656c8e327bcba1f73abc
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900324"
---
# <a name="data-sources-overview"></a>Informació general de les fonts de dades

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

La capacitat de conclusions del públic del Dynamics 365 Customer Insights connecta amb les dades d'un ampli conjunt de fonts. La connexió a una font de dades sovint es coneix com el procés d'*ingesta de dades*. Després d'ingerir les dades, les podeu [unificar](data-unification.md) i treballar-hi.

## <a name="add-a-data-source"></a>Afegeix un origen de dades

Consulteu els articles detallats sobre com afegir un font de dades, en funció de l'opció que trieu.

Podeu afegir els orígens de dades següents:

- [connectors Power Query](connect-power-query.md)
- [Model de dades comú](connect-common-data-model.md)
- [Microsoft Dataverse llac](connect-dataverse-managed-lake.md)

> [!NOTE]
> Si utilitzeu la versió de prova, la secció Mètodes d'importació inclou una **opció de biblioteca de dades del Customer Insights.** Trieu aquesta opció per seleccionar un conjunt de dades d'exemple disponible per a diverses indústries. Per a més informació, vegeu [Dynamics 365 Customer Insights judici](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Afegir dades des de fonts de dades locals

La ingesta de dades de fonts de dades locals a les conclusions del públic està admesa als fluxos de dades del Microsoft Power Platform. Podeu habilitar Els fluxos de dades a l'Insights del client [proporcionant l'ADREÇA URL de Microsoft Dataverse l'entorn en configurar](create-environment.md) l'entorn.

Els orígens de dades que es creen després d'associar un Dataverse entorn amb el Customer Insights utilitzen els [Power Platform fluxos de dades per](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) defecte. Els fluxos de dades admeten la connectivitat local mitjançant l'ús de la passarel·la de dades. Podeu suprimir i tornar a crear els orígens de dades que existien abans que Dataverse s'associés un entorn [mitjançant local passarel·les de dades](/data-integration/gateway/service-gateway-app).

Les passarel·les de dades d'un entorn existent del Power BI o el Power Apps seran visibles i es poden reutilitzar al Customer Insights. La pàgina de fonts de dades mostra enllaços per anar a l'entorn del Microsoft Power Platform on podeu visualitzar i configurar passarel·les de dades locals.

## <a name="review-ingested-data"></a>Revisar les dades ingerides

Veureu el nom de cada font de dades ingerida, el seu estat i l'última vegada que les dades s'han actualitzat per a aquesta font. Podeu ordenar la llista de fonts de dades per cada columna.

> [!div class="mx-imgBorder"]
> ![Font de dades afegida](media/configure-data-datasource-added.png "Font de dades afegida")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

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
