---
title: Introducció al Dynamics 365 Customer Insights
description: Una visió general de customer insights ajuda els recursos a iniciar-se ràpidament.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011967"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Introducció al Dynamics 365 Customer Insights

Les estadístiques del client us poden ajudar a crear una comprensió més profunda dels vostres clients. Connecteu dades de diverses fonts transaccionals, conductuals i observacionals per crear una visualització del client de 360 graus. Utilitzeu aquests coneixements per utilitzar processos i experiències centrades en el client. Unifiqueu i analitzeu les dades dels clients i aprofiteu-les per prendre conclusions i mesures intel·ligents.

## <a name="step-1-create-an-environment"></a>Pas 1: crear un entorn

En primer lloc, crear un entorn per treballar. Si l'organització ja ha adquirit una llicència, vegeu [Crear un entorn](create-environment.md). Per iniciar una prova per al Customer Insights, consulta [Configurar un entorn de prova](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Pas 2: exploreu les estadístiques dels clients

La primera vegada que inicieu la sessió al Customer Insights, configureu la configuració i exploreu el producte.

1. [Inicieu la sessió al Customer Insights](https://home.ci.ai.dynamics.com) mitjançant el vostre compte d'usuari de Microsoft Azure Active Directory (AAD).

1. Canvieu l'entorn per veure les dades de demostració i [explorar les estadístiques del client](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Pas 3: ingerir, unificar i configurar relacions per a les dades

Els perfils unificats són els fonaments per obtenir informació i dur a terme accions sobre les dades. Introduïu dades de diversos orígens i executeu el procés d'unificació de dades per combinar perfils unificats. Especifiqueu les relacions entre les entitats ingerides i utilitzeu funcions d'enriquiment per afegir informació als perfils.

1. Ingeriu dades creant fonts de dades a partir de diverses opcions. Trieu entre [Azure Data Lake Storage, inclòs el Model](connect-common-data-model.md) de dades comú, [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) o [Power Query connectors](connect-power-query.md).

1. Executeu el procés d'unificació [de dades identificant els camps](data-unification.md) d'origen [, suprimint](map-entities.md) duplicats, [condicions](remove-duplicates.md) coincidents [i](match-entities.md) unificant camps [.](merge-entities.md)

1. Familiaritzeu-vos amb les [entitats que crea el sistema](entities.md) i [creeu relacions entre les entitats ingerides](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Pas 4: millorar els perfils unificats amb prediccions, activitats i mesures

Amb els perfils unificats configurats, milloreu les vostres dades i augmenteu encara més la informació que proporcionen.

1. Trieu entre una biblioteca que expandeix de proveïdors d'enriquiment per [enriquir les dades dels clients](enrichment-hub.md).

1. Utilitzeu [models estàndard](predictions-overview.md) per predir la probabilitat de cancel·lació o els ingressos previstos.

1. [Configureu les activitats](activities.md) a partir de dades ingerides i visualitzeu les interaccions amb els clients en una cronologia.

1. [Creeu mesures](measures.md) per mesurar els objectius i els KPI de l'empresa.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Pas 5: creeu segments i activeu les dades mitjançant diverses opcions d'exportació

Ara que les vostres dades s'han completat i contenen una àmplia gamma d'informació sobre els vostres clients, cerqueu maneres d'actuar sobre aquestes dades.

1. [Creeu segments](segments.md), subconjunts de la base de clients, per assegurar-vos que les accions siguin rellevants per als clients destinataris.

1. Navegueu pel catàleg ampliat d'[opcions d'exportació](export-destinations.md) on podeu utilitzar les dades dels clients. Per exemple, podeu utilitzar les dades per administrar promocions i contactes amb el màrqueting digital.

1. Reviseu les opcions d'integració, per exemple, a altres aplicacions del Dynamics 365 amb el complement de la [targeta de client](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
