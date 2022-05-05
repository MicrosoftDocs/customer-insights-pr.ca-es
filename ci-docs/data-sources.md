---
title: Utilitzar fonts de dades per ingerir dades
description: Més informació sobre com importar dades de diverses fonts.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: bcc50c6fa8f8e2a66ef6164bfa9022e068c0e374
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642209"
---
# <a name="data-sources-overview"></a>Informació general de les fonts de dades



Dynamics 365 Customer Insights es connecta a les dades d'un ampli conjunt d'orígens. La connexió a una font de dades sovint es coneix com el procés d'*ingesta de dades*. Després d'ingerir les dades, les podeu [unificar](data-unification.md) i treballar-hi.

## <a name="add-a-data-source"></a>Afegeix un origen de dades

Consulteu els articles detallats sobre com afegir un font de dades, en funció de l'opció que trieu.

Podeu afegir els orígens de dades següents:

- [A través de desenes de Power Query connectors](connect-power-query.md)
- [Des d'una carpeta del Common Data Model](connect-common-data-model.md)
- [Des del vostre propi llac del Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [Des d'una Azure Synapse Analytics base de dades](connect-synapse.md)

> [!NOTE]
> Si utilitzeu la versió de prova, la secció Mètodes d'importació inclou una **opció de biblioteca** de dades del Customer Insights. Trieu aquesta opció per seleccionar un conjunt de dades d'exemple disponible per a diverses indústries. Per a més informació, vegeu [Dynamics 365 Customer Insights judici](trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Afegir dades des de fonts de dades locals

S'admet la ingestió de dades de fonts de dades local en funció dels Microsoft Power Platform fluxos de dades. Podeu habilitar Els fluxos de dades a l'Insights [del client proporcionant l'ADREÇA URL Microsoft Dataverse de l'entorn](create-environment.md) en configurar l'entorn.

Els orígens de dades que es creen després d'associar un Dataverse entorn amb el Customer Insights utilitzen [Power Platform els fluxos de](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) dades per defecte. Els fluxos de dades admeten la connectivitat local mitjançant l'ús de la passarel·la de dades. Podeu suprimir i recrear els orígens de dades que existien abans que s'associés Dataverse un [entorn mitjançant local passarel·les](/data-integration/gateway/service-gateway-app) de dades.

Les passarel·les de dades d'un entorn existent del Power BI o el Power Apps seran visibles i es poden reutilitzar al Customer Insights. La pàgina de fonts de dades mostra enllaços per anar a l'entorn del Microsoft Power Platform on podeu visualitzar i configurar passarel·les de dades locals.

> [!IMPORTANT]
> Assegureu-vos que les passarel·les s'actualitzin a la versió més recent. Podeu instal·lar una actualització i reconfigurar una passarel·la des d'un indicador que es mostra directament a la pantalla de la passarel·la o [descarregar la versió més recent](https://powerapps.microsoft.com/downloads/). Si no utilitzeu la versió més recent de la passarel·la, l'actualització del flux de dades falla amb missatges d'error com **La paraula clau no és compatible: propietats de configuració. Nom del paràmetre: paraula clau**.

## <a name="review-ingested-data"></a>Revisar les dades ingerides
Si l'entorn conté Power Platform fluxos de dades, la **pàgina Orígens** de dades enumera tres seccions: 
- **Compartit**: orígens de dades que poden ser gestionats per tots els administradors del Customer Insights. Power BI els fluxos de dades, el vostre propi compte d'emmagatzematge i l'adjunt a un Dataverse llac de dades gestionat són exemples de fonts de dades compartides.
- **Gestionat per mi**: Power Platform fluxs de dades creats i només poden ser gestionats per vostè. Altres administradors del Customer Insights només poden veure aquests fluxos de dades, però no editar-los, actualitzar-los o suprimir-los.
- **Gestionat per altres**: Power Platform fluxos de dades creats per altres administradors. Només els podeu veure. Enumera el propietari del flux de dades per contactar per obtenir qualsevol ajuda.
> [!NOTE]
> Altres usuaris poden visualitzar i utilitzar totes les entitats. La contextualització de l'usuari només s'aplica als orígens de dades i no a les entitats que resulten d'aquests fluxos de dades.

Si no s'utilitzen Power Platform fluxos de dades, no veureu cap grup ni cap secció. La **pàgina Orígens** de dades només conté una llista de tots els orígens de dades.

Veureu el nom de cada font de dades ingerida, el seu estat i l'última vegada que les dades s'han actualitzat per a aquesta font. Podeu ordenar la llista de fonts de dades per cada columna.

> [!div class="mx-imgBorder"]
> ![Font de dades afegida](media/configure-data-datasource-added.png "Font de dades afegida")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

La càrrega de les dades pot tardar temps. Després d'una actualització correcta, les dades d'ingerides es poden revisar des de la pàgina **Entitats**. Per obtenir més informació, vegeu [Entitats](entities.md).

## <a name="refresh-a-data-source"></a>Actualitzar una font de dades

Les fonts de dades es poden actualitzar seguint una planificació automàtica o bé manualment segons demanda. 

Per configurar les actualitzacions planificades de totes les fonts de dades ingerides, aneu a **Administració** > **Sistema** > [**Planificació**](system.md#schedule-tab).

Per actualitzar una font de dades segons demanda, seguiu aquests passos:

1. Aneu a **Dades** > **Fonts de dades**.

2. Seleccioneu els punts suspensius verticals al costat de la font de dades voleu actualitzar i seleccioneu **Actualitza** a la llista desplegable.

3. S'inicia l'actualització manual de la font de dades en qüestió. En actualitzar una font de dades s'actualitza tan l'esquema d'entitat com les dades de totes les entitats especificades a la font de dades.

4. Seleccioneu **Para d'actualitzar** si voleu cancel·lar una actualització existent; la font de dades tornarà a l'últim estat d'actualització.

## <a name="delete-a-data-source"></a>Suprimir una font de dades

1. Aneu a **Dades** > **Fonts de dades**.

2. Seleccioneu els punts suspensius verticals al costat de la font de dades voleu suprimir i seleccioneu **Suprimeix** al menú desplegable.

3. Confirmeu la supressió.


[!INCLUDE [footer-include](includes/footer-banner.md)]
