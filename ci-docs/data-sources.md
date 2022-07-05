---
title: Informació general de les fonts de dades
description: Obteniu informació sobre com podeu importar o ingerir dades de diverses fonts.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051441"
---
# <a name="data-sources-overview"></a>Informació general de les fonts de dades

Dynamics 365 Customer Insights proporciona connexions per portar dades d'un ampli conjunt de fonts. La connexió a una font de dades sovint es coneix com el procés d'*ingesta de dades*. Després d'ingerir les dades, podeu [unificar](data-unification.md), generar estadístiques i activar les dades per crear experiències personalitzades.

## <a name="add-data-sources"></a>Afegir fonts de dades

Podeu adjuntar o importar orígens de dades al Customer Insights. Els enllaços següents proporcionen instruccions per afegir fonts de dades.

**Adjunta un font de dades**

Si teniu dades preparades en un dels serveis de dades de l'Azure de Microsoft, el Customer Insights es pot connectar fàcilment al font de dades sense haver de tornar a ingerir les dades. Seleccioneu una de les opcions següents:
- [Azure Data Lake Storage(fitxers CSV o parquet en una carpeta del Model de Dades Comú)](connect-common-data-model.md)
- [Azure Synapse Analytics(Bases de dades del llac)](connect-synapse.md)
- [Microsoft Dataverse llac de dades](connect-dataverse-managed-lake.md)

**Importa i transforma**

Si utilitzeu fonts de dades locals, dades de Microsoft o de tercers, importeu i transformeu les dades mitjançant Power Query connectors.
- [Power Query Connectors](connect-power-query.md)

## <a name="review-data-sources"></a>Revisa els orígens de dades

Si el vostre entorn s'ha configurat per utilitzar l'emmagatzematge del Customer Insights i utilitzeu orígens de dades locals, utilitzeu Power Platform els fluxos de dades. Amb Power Platform els fluxos de dades, podeu veure orígens de dades compartits i orígens de dades gestionats per altres persones. La **pàgina Orígens** de dades llista els orígens de dades en tres seccions:
- **Compartit**: orígens de dades que poden ser gestionats per tots els administradors del Customer Insights. Power Platform els fluxos de dades, el vostre propi compte d'emmagatzematge i l'adjunt a un Dataverse llac de dades gestionat són exemples de fonts de dades compartides.
- **Gestionat per mi**: Power Platform fluxs de dades creats i gestionats només per tu. Altres administradors del Customer Insights només poden veure aquests fluxos de dades, però no editar-los, actualitzar-los o suprimir-los.
- **Gestionat per altres**: Power Platform fluxos de dades creats per altres administradors. Només els podeu veure. Enumera el propietari del flux de dades per contactar per obtenir qualsevol ajuda.
> [!NOTE]
> Altres usuaris poden visualitzar i utilitzar totes les entitats. Tot i que les fonts de dades són propietat de l'usuari que les ha creat, totes les entitats resultants de la ingestió de dades poden ser utilitzades per tots els usuaris del Customer Insights.

Si l'entorn no utilitza Power Platform fluxos de dades, la **pàgina Orígens** de dades només conté una llista de tots els orígens de dades. No es mostra cap secció.

Aneu a **Orígens** > **de dades de dades** per visualitzar el nom de cada font de dades ingerit, el seu estat i l'última vegada que es van actualitzar les dades per a aquesta font. Podeu ordenar la llista de fonts de dades per cada columna.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Font de dades afegida":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

La càrrega de les dades pot tardar temps. Després d'una actualització correcta, les dades d'ingerides es poden revisar des de la pàgina **Entitats**. Per obtenir més informació, vegeu [Entitats](entities.md).

## <a name="refresh-data-sources"></a>Actualitzar les fonts de dades

Les fonts de dades es poden actualitzar seguint una planificació automàtica o bé manualment segons demanda. [Les fonts](connect-power-query.md#add-data-from-on-premises-data-sources) de dades locals s'actualitzen a les seves pròpies planificacions que es configuraran durant la ingestió de dades. Per a les fonts de dades adjuntes, la ingestió de dades consumeix les últimes dades disponibles d'aquest font de dades.

Aneu a **Planificació** > **del sistema** > [**d'administració**](system.md#schedule-tab) per configurar les actualitzaciós planificades pel sistema dels orígens de dades ingerits.

Per actualitzar una font de dades segons demanda, seguiu aquests passos:

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu l'el·lipsi vertical (&vellip;) al costat de la font de dades voleu actualitzar i seleccioneu **Actualitza** de la llista desplegable. S'inicia l'actualització manual de la font de dades en qüestió. En actualitzar una font de dades s'actualitza tan l'esquema d'entitat com les dades de totes les entitats especificades a la font de dades.

1. Seleccioneu **Para d'actualitzar** si voleu cancel·lar una actualització existent; la font de dades tornarà a l'últim estat d'actualització.

## <a name="delete-a-data-source"></a>Suprimir una font de dades

Un font de dades només es pot suprimir si les dades no s'utilitzen en cap processament, com ara la unificació, les estadístiques, les activacions o les exportacions.

1. Aneu a **Dades** > **Fonts de dades**.

2. Seleccioneu l'el·lipsi vertical (&vellip;) al costat de la font de dades voleu eliminar i seleccioneu **Suprimeix** al menú desplegable.

3. Confirmeu la supressió.


[!INCLUDE [footer-include](includes/footer-banner.md)]
