---
title: Utilitzar fonts de dades per ingerir dades
description: Més informació sobre com importar dades de diverses fonts.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732115"
---
# <a name="data-sources-overview"></a>Informació general de les fonts de dades

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

La capacitat d'informació de l'audiència en Dynamics 365 Customer Insights es connecta amb dades d'un ampli conjunt de fonts. La connexió a una font de dades sovint es coneix com el procés d'*ingesta de dades*. Després d'ingerir les dades, les podeu [unificar](data-unification.md) i treballar-hi.

## <a name="add-a-data-source"></a>Afegeix un origen de dades

Consulteu els articles detallats sobre com afegir una font de dades, en funció de l'opció que trieu.

Podeu afegir una font de dades de tres maneres principals:

- [Mitjançant desenes de connectors del Power Query](connect-power-query.md)
- [Des d'una carpeta del Common Data Model](connect-common-data-model.md)
- [Des del teu propi llac Microsoft Dataverse](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Afegir dades des de fonts de dades locals

La ingesta de dades de fonts de dades local en els coneixements de l'audiència és compatible amb Microsoft Power Platform fluxos de dades. Els fluxos de dades es poden habilitar a l'insights del client [proporcionant l'adreça URL de l'entorn Microsoft Dataverse](create-environment.md) en configurar l'entorn.

Els orígens de dades que es creen després d'associar un entorn Dataverse amb els clients per obtenir informació utilitzaran [Power Platform fluxos de dades](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) per defecte. Els fluxos de dades admeten la connectivitat local mitjançant l'ús de la passarel·la de dades. Suprimiu i torneu a crear fonts de dades que existien abans que un entorn Dataverse s'associés per [utilitzar les passarel·les de dades local](/data-integration/gateway/service-gateway-app).

Les passarel·les de dades d'un entorn Power BI o Power Apps existent seran visibles i es podran reutilitzar a Customer Insights. La pàgina d'orígens de dades mostra enllaços per anar a l'entorn Microsoft Power Platform on podeu veure i configurar local passarel·les de dades.

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
