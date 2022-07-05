---
title: Visió general de l'enriquiment de dades (vista prèvia)
description: Utilitzeu les capacitats de Microsoft i d'altres serveis de tercers per enriquir les vostres dades de clients.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053852"
---
# <a name="data-enrichment-preview-overview"></a>Visió general de l'enriquiment de dades (vista prèvia)

Utilitzeu dades de diverses fonts, com ara Microsoft i altres associats, per enriquir les dades dels clients. Les millores de tercers es configuren mitjançant [connexions](connections.md), que un administrador configura amb credencials i proporciona el consentiment per a les transferències de dades. Els administradors i els col·laboradors poden utilitzar les connexions per configurar enriquiments.  

## <a name="multiple-enrichments-of-the-same-type"></a>Múltiples enriquiments del mateix tipus

L'entitat que s'ha d'enriquir s'especifica durant la configuració de l'enriquiment, la qual cosa us permet enriquir només un subconjunt dels vostres perfils. Per exemple, podeu enriquir només les dades d'un segment concret. Podeu configurar diversos enriquiments del mateix tipus i reutilitzar la mateixa connexió. Alguns enriquiments tindran límits pel que fa al nombre d'enriquiments del mateix tipus que es poden crear. Els límits i l'ús actual es poden veure a cada peça de la **pestanya Descobreix** de la **pàgina Enriquiment**.

## <a name="enrich-data-sources-before-unification"></a>Enriqueix els orígens de dades abans de la unificació

Podeu enriquir les dades dels clients abans de la unificació de dades per ajudar a augmentar la qualitat d'una coincidència de dades. Per a més informació, consulteu [font de dades enriquiment](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Crea un enriquiment

Heu de tenir permisos [de col·laborador o administrador](permissions.md) per crear o editar enriquiments.

Aneu a **Dades** > **Enriquiment**. La **pestanya Descobreix** mostra totes les opcions d'enriquiment admeses.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pàgina del centre d'enriquiment.":::

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

- [Identitat d'AbiliTec](enrichment-liveramp.md) proporcionada per LiveRamp AbiliTec
- [Marques](enrichment-microsoft.md) proporcionades per Microsoft
- [Dades demogràfiques](enrichment-experian.md) proporcionades per Experian
- [Adreces millorades](enrichment-enhanced-addresses.md) proporcionades per Microsoft
- [Interessos](enrichment-microsoft.md) proporcionats per Microsoft
- [Dades](enrichment-azure-maps.md) d'ubicació proporcionades per Microsoft Azure Maps
- [Dades d'ubicació](enrichment-here.md) proporcionades per HERE Technologies
- [Dades personalitzades](enrichment-SFTP-custom-import.md) SFTP mitjançant protocol de transferència segura de fitxers (SFTP)

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

- [Dades d'interacció amb](enrichment-office.md) el compte proporcionades per Microsoft
- [Dades de](enrichment-dnb.md) l'empresa proporcionades per Dun &Bradstreet
- [Dades de l'empresa](enrichment-leadspace.md) proporcionades per Leadspace
- [Adreces millorades](enrichment-enhanced-addresses.md) proporcionades per Microsoft
- [Dades millorades de l'empresa](enrichment-enhanced-company-data.md) proporcionades per Microsoft
- [Dades](enrichment-azure-maps.md) d'ubicació proporcionades per Microsoft Azure Maps
- [Dades d'ubicació](enrichment-here.md) proporcionades per HERE Technologies
- [Dades personalitzades](enrichment-SFTP-custom-import.md) SFTP mitjançant protocol de transferència segura de fitxers (SFTP)

---

## <a name="manage-existing-enrichments"></a>Administrar els enriquiments existents

Aneu a **Dades** > **Enriquiment**. A la **pestanya Els meus enriquiments**, consulteu els enriquiments configurats, el seu estat, el nombre de clients enriquits i l'última vegada que es van actualitzar les dades. Podeu ordenar la llista d'enriquiments per qualsevol columna o utilitzar el quadre de cerca per trobar l'enriquiment que voleu gestionar.

Seleccioneu l'enriquiment per visualitzar les accions disponibles.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcions per administrar els enriquiments a la llista d'enriquiments.":::

- **Visualitzeu** els detalls de l'enriquiment amb el nombre de perfils de client enriquits.
- **Editeu** la configuració d'enriquiment.
- [**Executeu**](#run-or-refresh-enrichments) l'enriquiment per actualitzar els perfils dels clients amb les dades més recents. Executeu diversos enriquiments alhora seleccionant-los a la llista.
- **Activar** o **desactivar** un enriquiment. Els enriquiments inactius no s'actualitzaran durant una [actualització](system.md#schedule-tab) programada.
- **Suprimeix** l'enriquiment.

També podeu crear [segments](segments.md) o [mesures a](measures.md) partir d'enriquiments.

## <a name="run-or-refresh-enrichments"></a>Executar o refrescar enriquiments

Un cop executat, els enriquiments es poden actualitzar en una planificació automàtica o actualitzar-se manualment sota demanda.

1. Per actualitzar manualment un o més enriquiments, seleccioneu-los i trieu **Executa**. Per [planificar una actualització](system.md#schedule-tab) automàtica, aneu a **Planificació** > **del sistema** > **d'administració**. El temps de processament depèn de la mida de les dades dels clients.

1. Opcionalment, [veure el progrés del procés](#see-the-progress-of-the-enrichment-process) d'enriquiment.

1. Un cop finalitzat el procés d'enriquiment, aneu a **Els meus enriquiments** per revisar les dades de perfils de clients recentment enriquits, el moment de l'última actualització i el nombre de perfils enriquits.

1. Seleccioneu l'enriquiment per veure [els resultats de l'enriquiment](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Veure el progrés del procés d'enriquiment

Podeu trobar detalls sobre el processament d'un enriquiment, incloent-hi l'estat i els possibles problemes mentre s'actualitza o després de l'actualització. Compreneu quins processos s'impliquen per actualitzar un enriquiment i el temps que ha trigat a executar els processos. L'estat d'enriquiment està admès per a Experian, Leadspace, HERE Technologies, SFTP Import i Azure Maps.

1. Aneu a **Dades** > **Enriquiment**.
1. A la **pestanya Els meus enriquiments**, seleccioneu l'estat de l'enriquiment per obrir una subfinestra lateral.
1. A la subfinestra **Detalls del progrés**, expandiu la secció **Enriquiments**.
1. A l'enriquiment del qual voleu veure el progrés, seleccioneu **Mostra els detalls**.
1. A la subfinestra **Detalls de la tasca**, seleccioneu **Mostra els detalls** per veure els processos implicats en l'actualització de l'enriquiment i el seu estat.

## <a name="view-enrichment-results"></a>Veure resultats d'enriquiment

Després d'una carrera d'enriquiment completa, reviseu els resultats de l'enriquiment.

1. Aneu a **Dades** > **Enriquiment**.
1. A la **pestanya Els meus enriquiments**, seleccioneu l'enriquiment que voleu veure.

Tots els enriquiments mostren informació bàsica com el nombre de perfils enriquits i el nombre de perfils enriquits al llarg del temps. La **peça de visualització prèvia de** clients enriquits mostra una mostra de l'entitat d'enriquiment generada. Per veure una visualització detallada, seleccioneu **Mostra'n més** i seleccioneu la **pestanya Dades**.

:::image type="content" source="media/enrichments-results.png" alt-text="Pàgina de resultats d'enriquiments.":::

Si està disponible, el **nombre de clients enriquits per camp** proporciona una desglossament de la cobertura de cada camp enriquit.

Alguns enriquiments també mostren informació específica per al tipus d'enriquiment. Per obtenir més informació, consulteu la documentació relacionada.

[!INCLUDE [footer-include](includes/footer-banner.md)]
