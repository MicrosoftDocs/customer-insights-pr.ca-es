---
title: Informació general de les fonts de dades
description: Obteniu informació sobre com podeu importar o ingerir dades de diverses fonts.
ms.date: 07/26/2022
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
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245637"
---
# <a name="data-sources-overview"></a>Informació general de les fonts de dades

Dynamics 365 Customer Insights proporciona connexions per portar dades d'un ampli conjunt de fonts. La connexió a una font de dades sovint es coneix com el procés d'*ingesta de dades*. Després d'ingerir les dades, podeu [unificar](data-unification.md), generar estadístiques i activar les dades per crear experiències personalitzades.

## <a name="add-or-edit-data-sources"></a>Afegir o editar fonts de dades

Podeu adjuntar o importar fonts de dades al Customer Insights. Els enllaços següents proporcionen instruccions per afegir i editar fonts de dades.

**Adjuntar una font de dades**

Si teniu dades preparades en un dels serveis de dades de l'Azure de Microsoft, el Customer Insights es pot connectar fàcilment al font de dades sense haver de tornar a ingerir les dades. Seleccioneu una de les opcions següents:
- [Azure Data Lake Storage(fitxers csv o parquet en una carpeta del Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(Bases de dades del llac)](connect-synapse.md)
- [Microsoft Dataverse llac de dades](connect-dataverse-managed-lake.md)

**Importar i transformar**

Si utilitzeu fonts de dades locals, Microsoft o dades de tercers, importeu i transformeu les dades mitjançant Power Query connectors.
- [Power Query Connectors](connect-power-query.md)

## <a name="review-data-sources"></a>Revisar les fonts de dades

Si el vostre entorn s'ha configurat per utilitzar l'emmagatzematge del Customer Insights i utilitzeu fonts de dades locals, utilitzeu Power Platform fluxos de dades. Amb Power Platform els fluxos de dades, podeu veure les fonts de dades compartides i les fonts de dades gestionades per altres persones. La **pàgina Fonts de** dades enumera les fonts de dades en tres seccions:
- **Compartits**: fonts de dades que poden gestionar tots els administradors del Customer Insights. Power Platform els fluxos de dades, el vostre propi compte d'emmagatzematge i la connexió a un Dataverse llac de dades gestionat són exemples de fonts de dades compartides.
- **Gestionat per mi**: Power Platform fluxos de dades creats i gestionats només per vosaltres. Altres administradors del Customer Insights només poden veure aquests fluxos de dades, però no editar-los, actualitzar-los ni suprimir-los.
- **Gestionat per altres:** Power Platform fluxos de dades creats per altres administradors. Només els podeu veure. Enumera el propietari del flux de dades amb el qual contactar per obtenir qualsevol ajuda.
> [!NOTE]
> Totes les entitats poden ser visualitzades i utilitzades per altres usuaris. Tot i que les fonts de dades són propietat de l'usuari que les ha creat, tots els usuaris del Customer Insights poden utilitzar les entitats resultants de la ingestió de dades.

Si el vostre entorn no utilitza Power Platform fluxos de dades, la **pàgina Fonts de** dades només conté una llista de totes les fonts de dades. No es mostren seccions.

## <a name="manage-existing-data-sources"></a>Gestionar les fonts de dades existents

Aneu a **Fonts de** > **dades** per veure el nom de cada font de dades ingerit, el seu estat i l'última vegada que es van actualitzar les dades per a aquesta font. Podeu ordenar la llista de fonts de dades per qualsevol columna o utilitzar el quadre de cerca per trobar la font de dades voleu gestionar.

Seleccioneu un font de dades per veure les accions disponibles.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Font de dades afegida":::

- [**Editeu**](#add-or-edit-data-sources) la font de dades per canviar-ne les propietats.
- [**Actualitzeu**](#refresh-data-sources) la font de dades per incloure les dades més recents.
- [**Enriquir**](data-sources-enrichment.md) el font de dades abans de la unificació.
- **Suprimiu** el font de dades. Una font de dades només es pot suprimir si les dades no s'utilitzen en cap processament, com ara la unificació, les estadístiques, les activacions o les exportacions.

## <a name="refresh-data-sources"></a>Actualitzar les fonts de dades

Les fonts de dades es poden actualitzar seguint una planificació automàtica o bé manualment segons demanda. [Les fonts](connect-power-query.md#add-data-from-on-premises-data-sources) de dades locals s'actualitzen segons les seves pròpies planificacions que es configuren durant la ingestió de dades. Per a les fonts de dades adjuntes, la ingestió de dades consumeix les últimes dades disponibles des d'aquest font de dades.

Aneu a **Planificació del sistema d'administració** > **·** > [**·**](schedule-refresh.md) per configurar actualitzacions programades pel sistema de les fonts de dades ingerides.

Per actualitzar un font de dades sota demanda:

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu la font de dades voleu actualitzar i seleccioneu **Actualitza**. S'inicia l'actualització manual de la font de dades en qüestió. En actualitzar una font de dades s'actualitza tan l'esquema d'entitat com les dades de totes les entitats especificades a la font de dades.

1. Seleccioneu l'estat per obrir la subfinestra Detalls **del** progrés i veure el progrés. Per cancel·lar la feina, seleccioneu **Cancel·la la feina** a la part inferior de la subfinestra.

[!INCLUDE [footer-include](includes/footer-banner.md)]
