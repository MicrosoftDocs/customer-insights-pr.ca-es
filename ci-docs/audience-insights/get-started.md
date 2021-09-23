---
title: Començar a utilitzar la capacitat d'informació del públic al Dynamics 365 Customer Insights
description: Informació general sobre la informació del públic que ajuda els recursos a començar ràpidament.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466565"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Començar a utilitzar la capacitat d'informació del públic del Dynamics 365 Customer Insights

Les conclusions del públic us ajuden a comprendre millor els clients. Connecteu dades de diverses fonts transaccionals, conductuals i observacionals per crear una visualització del client de 360 graus. Utilitzeu aquests coneixements per utilitzar processos i experiències centrades en el client. Unifiqueu i analitzeu les dades dels clients i aprofiteu-les per prendre conclusions i mesures intel·ligents.

## <a name="step-1-create-an-environment"></a>Pas 1: crear un entorn

Per començar, primeu heu de crear un entorn per a treballar-hi. Si l'organització ja ha adquirit una llicència, vegeu [Comença amb una subscripció de pagament](get-started-paid.md). Per iniciar una versió de prova per a la informació del públic, vegeu [Configurar un entorn de prova](get-started-trial.md). 

## <a name="step-2-explore-audience-insights"></a>Pas 2: explorar la informació del públic

La primera vegada que inicieu sessió a la informació del públic, podeu ajustar la configuració i explorar el producte.

1. [Inicieu sessió a la informació del públic](https://home.ci.ai.dynamics.com) amb el compte d'usuari de Microsoft Azure Active Directory (AAD).

1. [Canvieu l'entorn](manage-environments.md#switch-environments) per veure les dades de demostració i [explorar la informació del públic](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Pas 3: ingerir, unificar i configurar relacions per a les dades

Els perfils unificats són els fonaments per obtenir informació i dur a terme accions sobre les dades. Introduïu dades de diversos orígens i executeu el procés d'unificació de dades per combinar perfils unificats. Especifiqueu relacions entre les entitats ingerides utilitzant característiques d'enriquiment per afegir informació als perfils. 

1. Ingeriu dades creant fonts de dades a partir de diverses opcions. Trieu entre els [connectors Power Query](connect-power-query.md), una [carpeta del Model de dades comú](connect-common-data-model.md) o el [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Executeu el [procés d'unificació de dades](data-unification.md) passant per les fases d'[assignació](map-entities.md), [coincidència](match-entities.md) i [combinació](merge-entities.md).

1. Familiaritzeu-vos amb les [entitats que crea el sistema](entities.md) i [creeu relacions entre les entitats ingerides](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Pas 4: millorar els perfils unificats amb prediccions, activitats i mesures

Havent configurat els perfils unificats, podeu millorar les dades i augmentar encara més la informació que proporcionen.

1. Trieu entre una biblioteca que expandeix de proveïdors d'enriquiment per [enriquir les dades dels clients](enrichment-hub.md).

1. Utilitzeu [models estàndard](predictions-overview.md) per predir la probabilitat de cancel·lació o els ingressos previstos.

1. [Configureu les activitats](activities.md) a partir de dades ingerides i visualitzeu les interaccions amb els clients en una cronologia. 

1. [Creeu mesures](measures.md) per mesurar els objectius i els KPI de l'empresa.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Pas 5: creeu segments i activeu les dades mitjançant diverses opcions d'exportació

Ara que les dades estan completes i contenen molta informació quant als vostres clients, és hora de cercar maneres d'actuar en aquestes dades. 

1. [Creeu segments](segments.md), subconjunts de la base de clients, per assegurar-vos que les accions siguin rellevants per als clients destinataris.

1. Navegueu pel catàleg ampliat d'[opcions d'exportació](export-destinations.md) on podeu utilitzar les dades dels clients. Per exemple, podeu utilitzar les dades per administrar promocions i contactes amb el màrqueting digital.

1. Reviseu les opcions d'integració, per exemple, amb la [connexió directa a la informació d'interacció](../engagement-insights/integrate-audience-insights-engagement-insights.md) o amb altres aplicacions del Dynamics 365 amb el [complement Targeta de client](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
