---
title: Introducció a la capacitat de coneixements d'interacció
description: Descripció general dels recursos d'ajuda per començar ràpidament.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3505c15c4319c8cc8823bcd89d3b8adc944a87dd
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623665"
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

1. Reviseu les **condicions d'ús** i la **declaració de privadesa** de les conclusions d'interacció (versió preliminar) i, a continuació, seleccioneu **Explora la demostració** per acceptar aquesta configuració.

1. Exploreu el producte mitjançant un conjunt de dades d'exemple.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Pas 3: configurar una àrea de treball i crear informes

Una àrea de treball és on podeu visualitzar l'activitat dels usuaris en temps real i emmagatzemar i administrar informes. Afegiu codi al lloc web per començar a recopilar *incidències*, les dades de l'activitat dels usuaris.

1. [Creeu una àrea de treball](create-workspace.md) i afegiu-hi membres.

1. Afegiu codi al [lloc web](instrument-website.md) o a l'[aplicació mòbil](developer-resources.md#capture-events-from-mobile-apps) per veure l'activitat dels usuaris que arriben a l'àrea de treball.

1. Visualitzeu un [informe en temps real](view-reports.md) que mostri els usuaris actius per navegador, dispositiu, sistema operatiu, ubicació i llengua. També podeu crear [informes personalitzats](custom-reports.md) per crear visualitzacions pròpies.

1. Creeu [dimensions](dimensions.md) per ordenar els visitants en nous i retornats, [mètriques](metrics.md) per ajudar a comprendre millor el comportament dels usuaris i [segments](segments.md) per identificar subconjunts de visitants segons les característiques o interaccions amb el lloc web.
    
## <a name="step-4-export-data-to-other-channels"></a>Pas 4: exportar dades a altres canals

Podeu crear *incidències refinades* (una visualització virtual) de les dades d'anàlisi web. A continuació, filtreu i exporteu les dades a Azure Data Lake Storage. Podeu ingerir les dades exportades com a font de dades.

1. [Creeu incidències refinades](refined-events.md) per a l'exportació.

1. [Exporteu les dades](export-events.md) a l'Azure Data Lake Storage.

1. [Creeu un enllaç entre la informació del públic i la informació d'interacció](integrate-audience-insights-engagement-insights.md) per compartir dades entre les dues capacitats.

1. [Reconeixeu incidències web d'usuaris prèviament autenticats](unknown-to-known.md) amb la característica **desconegut o conegut**.

1. Més informació sobre com [suprimir i exportar dades d'incidències que contenen informació personal](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Pas 5: crear i administrar informes d'embut

Un informe d'embut recopila informació sobre els passos que s'han produït durant un recorregut del client al lloc web o a l'aplicació mòbil. A banda de crear informes de perfil estàndard i informes personalitzats, podeu crear un informe d'embut per identificar els camins que agafen els clients abans de fer una compra. 

1. [Creeu un informe d'embut](funnel-reports.md) per informar de les decisions i identificar àrees per a l'optimització i la millora dels processos.

1. Creeu informes d'embut entre canals, un cop hàgiu instrumentat l'aplicació mòbil amb l'[SDK d'Android](get-started-android.md) o l'[SDK d'iOS](get-started-ios.md) de les conclusions d'interacció.

1. Utilitzeu les [conclusions de l'embut](funnel-reports.md#funnel-insights) per obtenir informació més detallada sobre el comportament dels clients en els passos de l'informe d'embut.
 
## <a name="step-6-stay-connected"></a>Pas 6: romangueu contactat

Agraïm la vostra participació activa i valorem tots els comentaris rellevants en el desenvolupament de versions futures. Compartiu els vostres comentaris i notifiqueu incidències per un d'aquests canals:
- [Comunitat](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Proporciona comentaris](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Sol·licitud d'assistència tècnica](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
