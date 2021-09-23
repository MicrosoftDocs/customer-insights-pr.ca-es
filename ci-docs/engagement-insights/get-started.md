---
title: Introducció a la capacitat de coneixements d'interacció
description: Descripció general dels recursos d'ajuda per començar ràpidament.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494582"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Introducció a la capacitat de coneixements d'interacció del Dynamics 365 Customer Insights (versió preliminar pública)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La capacitat dels coneixements d'interacció us permet recopilar i mesurar el comportament del client al vostre lloc web. S'integra amb la capacitat dels coneixements del públic per tal que pugue veure anàlisis enriquides de comportament en temps real juntament amb els informes de perfil de client. Els enllaços d'aquest article us ajuden a configurar ràpidament el vostre entorn.

## <a name="step-1-review-prerequisites"></a>Pas 1: Revisar els requisits previs

Primer de tot, heu de tenir un compte d'usuari de Microsoft Azure Active Directory (AAD) actiu. A continuació, llegiu els articles següents abans de configurar una àrea de treball dels coneixements d'interacció.

- Reviseu i accepteu les [condicions del servei](terms-of-service.md) amb Microsoft.  
- Llegiu l'article [Administrar les galetes i el consentiment de l'usuari](user-consent-storage.md). Després, avalueu si heu d'actualitzar la notificació de consentiment de l'usuari. Si anteriorment no heu tingut galetes "no essencials", és probable que hàgiu d'actualitzar la política del lloc.
- Reviseu el [glossari](glossary.md) per veure una introducció ràpida als termes i conceptes clau.

## <a name="step-2-explore-engagement-insights"></a>Pas 2: explorar els coneixements d'interacció

La primera vegada que visiteu la informació d'interacció, podeu ajustar la configuració, revisar-ne la normativa i explorar la capacitat.

1. Inicieu la sessió al [portal de capacitats d'informació d'interacció](https://home.ci.ai.dynamics.com/app/engagement-insights) amb el vostre compte d'usuari (acadèmic o laboral) de Microsoft AAD.

1. Activeu la regió i marqueu la casella si voleu optar per rebre actualitzacions i ofertes per correu electrònic.

1. Reviseu les **condicions d'ús de la informació de la interacció (versió preliminar)** i la **declaració de privadesa** i, a continuació, seleccioneu **Explora la demostració** per acceptar aquesta configuració.

1. Exploreu el producte mitjançant un conjunt de dades d'exemple.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Pas 3: configureu una àrea de treball i afegiu codi al lloc web

Una àrea de treball és on podeu visualitzar l'activitat dels usuaris en temps real i emmagatzemar i administrar informes. Afegiu codi al lloc web per començar a recopilar *incidències*, les dades de l'activitat dels usuaris.

1. [Creeu una àrea de treball](create-workspace.md) i afegiu-hi membres.

1. [Afegiu codi al lloc web](instrument-website.md) o a [l'aplicació mòbil](developer-resources.md#capture-events-from-mobile-apps) per veure l'activitat dels usuaris que arriben a l'àrea de treball.

1. Visualitzeu un [informe en temps real](view-reports.md) que mostri els usuaris actius per navegador, dispositiu, sistema operatiu, ubicació i llengua. També podeu crear [informes personalitzats](custom-reports.md) per crear visualitzacions pròpies.
    
## <a name="step-4-export-data-to-other-channels"></a>Pas 4: exportar dades a altres canals

Podeu crear *incidències refinades* (una visualització virtual) de les dades d'anàlisi web. A continuació, filtreu i exporteu les dades a Azure Data Lake Storage. Podeu ingerir les dades exportades com a font de dades. Per obtenir-ne més informació, consulteu [Creació d'un enllaç entre les conclusions del públic i les conclusions d'interacció](integrate-audience-insights-engagement-insights.md).

1. [Creeu incidències refinades](refined-events.md) per a l'exportació.

1. [Exporteu les dades](export-events.md) al Data Lake Storage.

1. [Creeu un enllaç entre la informació del públic i la informació d'interacció](integrate-audience-insights-engagement-insights.md) per compartir dades entre les dues capacitats.

1. Més informació sobre com [suprimir i exportar dades d'incidències que contenen informació personal](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Pas 5: romangueu contactat

Agraïm la vostra participació activa i valorem tots els comentaris rellevants en el desenvolupament de versions futures. Compartiu els vostres comentaris i notifiqueu incidències per un d'aquests canals:
- [Comunitat](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Proporciona comentaris](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Sol·licitud d'assistència tècnica](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
