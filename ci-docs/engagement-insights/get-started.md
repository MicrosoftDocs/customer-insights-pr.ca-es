---
title: Introducció a la capacitat de coneixements d'interacció
description: Descripció general dels recursos d'ajuda per començar ràpidament.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405346"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Introducció a la capacitat de coneixements d'interacció del Dynamics 365 Customer Insights (versió preliminar pública)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La capacitat dels coneixements d'interacció us permet recopilar i mesurar el comportament del client al vostre lloc web. S'integra amb la capacitat dels coneixements del públic per tal que pugue veure anàlisis enriquides de comportament en temps real juntament amb els informes de perfil de client. Els enllaços d'aquest article us ajuden a configurar ràpidament el vostre entorn.

## <a name="step-1-review-prerequisites"></a>Pas 1: Revisar els requisits previs

Primer de tot, heu de tenir un compte d'usuari de Microsoft Azure Active Directory actiu. A continuació, llegiu els articles següents abans de configurar una àrea de treball dels coneixements d'interacció.

- Reviseu i accepteu les [condicions del servei](terms-of-service.md) amb Microsoft.  
- Llegiu l'article [Administrar les galetes i el consentiment de l'usuari](user-consent-storage.md). Després de revisar aquest article, avalueu si heu d'actualitzar la notificació de consentiment de l'usuari. Si anteriorment no heu tingut galetes "no essencials", és probable que hàgiu d'actualitzar la política del lloc.
- Reviseu el [glossari](glossary.md) per veure una introducció ràpida als termes i conceptes clau.

## <a name="step-2-explore-engagement-insights"></a>Pas 2: explorar els coneixements d'interacció

La primera vegada que visiteu els coneixements d'interacció, podeu configurar la configuració, revisar les normes i explorar el producte.

1. Inicieu sessió al [portal de la capacitat dels coneixements d'interacció](https://pi.dynamics.com) amb el vostre compte d'usuari de Microsoft Azure Active Directory. (Pot ser el vostre compte acadèmic o laboral.)

1. Activeu la regió i utilitzeu la casella de selecció per indicar si voleu optar a rebre actualitzacions i ofertes per correu electrònic.

1. Reviseu les **condicions d'ús** i la **declaració de privadesa dels coneixements d'interacció** i, a continuació, seleccioneu **Explora la demo** per acceptar-les.

1. Exploreu el producte mitjançant un conjunt de dades d'exemple.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Pas 3: configureu una àrea de treball i afegiu codi al lloc web

L'àrea de treball és on podeu visualitzar l'activitat dels usuaris en temps real i emmagatzemar i administrar informes. Afegiu codi al lloc web per començar a recopilar *incidències*, les dades de l'activitat dels usuaris.

1. [Creeu una àrea de treball](create-workspace.md) i afegiu-hi membres.

1. [Afegiu codi al lloc web](instrument-website.md) o a [l'aplicació mòbil](developer-resources.md#capture-events-from-mobile-apps) per veure l'activitat dels usuaris que arriben a l'àrea de treball.

1. Visualitzeu un [informe en temps real](view-reports.md) que mostra els usuaris actius per navegador, dispositiu, sistema operatiu, ubicació i llengua. També podeu crear [informes personalitzats](custom-reports.md) per crear visualitzacions pròpies.
    
## <a name="step-4-export-data-to-other-channels"></a>Pas 4: exportar dades a altres canals

Podeu crear *incidències refinades* (una visualització virtual) de les dades d'anàlisi web. A continuació, filtreu i exporteu les dades a Azure Data Lake Storage. Podeu ingerir les dades exportades com a font de dades. Per obtenir-ne més informació, consulteu [Creació d'un enllaç entre les conclusions del públic i les conclusions d'interacció](integrate-audience-insights-engagement-insights.md).

1. [Creeu incidències refinades](refined-events.md) per a l'exportació.

1. [Exporteu les dades](export-events.md) al Data Lake Storage.

1. Més informació sobre com [suprimir i exportar dades d'incidències que contenen informació personal](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Pas 5: romangueu contactat

Agraïm la vostra participació activa i tenim previst tenir en compte tots els comentaris rellevants en el desenvolupament de versions futures. Compartiu els vostres comentaris i notifiqueu incidències per un d'aquests canals:
- [Comunitat](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Proporciona comentaris](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Sol·licitud d'assistència tècnica](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
