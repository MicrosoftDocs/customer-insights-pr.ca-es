---
title: Enriquir perfils de client unificats
description: Utilitzeu les capacitats disponibles per enriquir les dades dels clients.
ms.date: 03/29/2022
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
ms.openlocfilehash: abc1b6af80e8854ee3bc930453634ef67376c4af
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800593"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquiment per a perfils de clients (versió preliminar)

Utilitzeu dades de diverses fonts, com ara Microsoft i altres associats, per enriquir les dades dels clients.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pàgina del centre d'enriquiment.":::

Anar a **Enriquiment de** > **dades** per treballar amb opcions d'enriquiment.  

Heu de tenir permisos de col·laborador o administrador per crear o editar els enriquiments. Per obtenir més informació, vegeu [Permisos](permissions.md).

A la pestanya **Descobriu**, trobareu totes les opcions d'enriquiment admeses.

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

- [Marques](enrichment-microsoft.md) proporcionades per Microsoft
- [Interessos](enrichment-microsoft.md) proporcionats per Microsoft
- [Adreces millorades](enrichment-enhanced-addresses.md) proporcionades per Microsoft 
- [Dades demogràfiques](enrichment-experian.md) proporcionades per Experian
- [Dades personalitzades](enrichment-SFTP-custom-import.md) a través del protocol de transferència segura de fitxers (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) proporcionat per Microsoft
- [Dades d'ubicació](enrichment-here.md) proporcionades per HERE Technologies 
- [Identitat](enrichment-liveramp.md) proporcionada per LiveRamp AbiliTec

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

- [Dades de l'empresa](enrichment-leadspace.md) proporcionades per Leadspace
- [Adreces millorades](enrichment-enhanced-addresses.md) proporcionades per Microsoft 
- [Dades millorades de l'empresa](enrichment-enhanced-company-data.md) proporcionades per Microsoft
- [Dades d'ubicació](enrichment-here.md) proporcionades per HERE Technologies 
- [Dades personalitzades](enrichment-SFTP-custom-import.md) a través del protocol de transferència segura de fitxers (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) proporcionat per Microsoft
- [Dades de](enrichment-dnb.md) l'empresa proporcionades per Dun &Bradstreet
- [Dades d'interacció amb](enrichment-office.md) el compte proporcionades per Microsoft

---

A la pestanya **Els meus enriquiments** podeu veure els enriquiments que heu configurat i editar-ne les propietats.

## <a name="manage-existing-enrichments"></a>Administrar els enriquiments existents

Aneu a la pestanya **Els meus enriquiments** per veure tots els enriquiments configurats. Cada enriquiment es representa com una fila que inclou informació addicional sobre l'enriquiment.

Seleccioneu l'enriquiment per veure les opcions disponibles. També podeu seleccionar l'el·lipsi vertical (&vellip;) en un element de llista per veure les opcions. Si heu configurat diversos enriquiments, podeu utilitzar el quadre de cerca per trobar-lo ràpidament.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcions per administrar els enriquiments a la llista d'enriquiments.":::

- **Visualitzeu** els detalls de l'enriquiment amb el nombre de perfils de client enriquits.
- **Editeu** la configuració d'enriquiment.
- **Executeu** l'enriquiment per actualitzar els perfils dels clients amb les últimes dades.
- **Desactiveu** un enriquiment existent per impedir que s'actualitzi de manera automàtica amb cada actualització planificada. Les dades de l'última actualització correcta continuaran estaran disponibles. **Activeu** un enriquiment inactiu per reiniciar l'actualització automàtica amb cada actualització planificada.
- **Suprimeix** l'enriquiment.

Executeu o desactiveu diversos enriquiments alhora seleccionant-los a la llista. Les opcions de visualització i edició no estan disponibles com a acció massiva. Només funcionen per a un enriquiment alhora.

## <a name="enrichments-and-connections"></a>Enriquiments i connexions

Les millores de tercers es configuren mitjançant [connexions](connections.md), que un administrador configura amb credencials i proporciona el consentiment per a les transferències de dades. Els administradors i els col·laboradors poden utilitzar les connexions per configurar enriquiments.  

## <a name="multiple-enrichments-of-the-same-type"></a>Múltiples enriquiments del mateix tipus

L'entitat que s'ha d'enriquir s'especifica durant la configuració de l'enriquiment, la qual cosa us permet enriquir només un subconjunt dels vostres perfils. Per exemple, podeu enriquir només les dades d'un segment concret. Podeu configurar diversos enriquiments del mateix tipus i reutilitzar la mateixa connexió. Alguns enriquiments tindran límits pel que fa al nombre d'enriquiments del mateix tipus que es poden crear. Els límits i l'ús actual es poden veure a la pàgina **Enriquiment**.

## <a name="enrich-data-sources-before-unification"></a>Enriqueix els orígens de dades abans de la unificació

Podeu enriquir les dades dels clients abans de la unificació de dades per ajudar a augmentar la qualitat d'una coincidència de dades. Per a més informació, consulteu [font de dades enriquiment](data-sources-enrichment.md).

## <a name="see-the-progress-of-the-enrichment-process"></a>Veure el progrés del procés d'enriquiment

Podeu trobar detalls sobre el processament d'un enriquiment, incloent-hi l'estat i els possibles problemes mentre s'actualitza o després de l'actualització. Compreneu quins processos s'impliquen per actualitzar un enriquiment i el temps que ha trigat a executar els processos. L'estat d'enriquiment està admès per a Experian, Leadspace, HERE Technologies, SFTP Import i Azure Maps.

Per veure l'estat d'un enriquiment

1. Aneu a **Dades** > **Enriquiment**. 
1. A la pestanya **Els meus enriquiments**, seleccioneu l'estat d'un enriquiment per obrir una subfinestra lateral. 
1. A la subfinestra **Detalls del progrés**, expandiu la secció **Enriquiments**. 
1. A l'enriquiment del qual voleu veure el progrés, seleccioneu **Mostra els detalls**. 
1. A la subfinestra **Detalls de la tasca**, seleccioneu **Mostra els detalls** per veure els processos implicats en l'actualització de l'enriquiment i el seu estat. 

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Després d'una carrera d'enriquiment completa, podeu revisar els resultats de l'enriquiment.

1. Aneu a **Dades** > **Enriquiment**. 
1. Seleccioneu l'enriquiment sobre el qual voleu informació.

Tots els enriquiments mostren informació bàsica com el nombre de perfils enriquits, una vista prèvia de l'entitat d'enriquiment generada i el nombre de perfils enriquits al llarg del temps. Si està disponible, el **nombre de clients enriquits per camp** proporciona una desglossament de la cobertura de cada camp enriquit.

:::image type="content" source="media/enrichments-results.png" alt-text="Pàgina de resultats d'enriquiments.":::

Alguns enriquiments també mostren informació específica per al tipus d'enriquiment. Consulteu la documentació per a l'enriquiment pertinent per obtenir més informació.


[!INCLUDE [footer-include](includes/footer-banner.md)]
