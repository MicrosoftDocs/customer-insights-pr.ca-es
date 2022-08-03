---
title: Ingestió de dades en temps real (versió preliminar)
description: Informació general sobre les capacitats en temps real al Customer Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 403cc9dbd3bddcf67f59b5cb0be936af4d268fc2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195646"
---
# <a name="real-time-data-ingestion-preview"></a>Ingestió de dades en temps real (versió preliminar)

La funcionalitat gairebé en temps real us permet veure, en qüestió de segons, les darreres interaccions que els clients han fet amb els vostres productes o serveis.

Les [actualitzacions planificades](system.md#schedule-tab) inclouen grans quantitats de registres i diverses operacions complexes. En primer lloc, les dades s'extreuen de la font de dades. A continuació, les dades s'unifiquen i enriqueixen amb informació addicional. Cada execució d'aquest procés pot tardar de minuts a hores.

Aquesta funcionalitat en temps real proporciona dades immediatament per al consum fins que la següent actualització planificada extreu aquestes dades de la font de dades.

Les actualitzacions en temps real tenen un temps de venciment després del qual ja no poden substituir el valor de la font de dades:

- Les actualitzacions del perfil es conservaran durant quatre hores
- Les activitats es conservaran durant 30 dies

Aquests valors són paràmetres de trucada de l'API que podeu canviar. Pretenen assegurar--se que les dades d'origen segueixen sent el vostre origen en la veritat. Si voleu que les actualitzacions en temps real s'incloguin durant més temps, heu d'afegir-les a una font de dades perquè es puguin extreure durant la propera actualització planificada.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Actualització en temps real dels camps del perfil del client unificat

Els perfils actualitzats es mostraran al cap d'uns pocs segons a la visualització de la targeta del client o a qualsevol altra visualització.

Com que les operacions en temps real tenen lloc després que s'hagi produït la unificació de dades, només s'apliquen als perfils de client unificats. En conseqüència, els canvis de perfil en temps real no actualitzaran les mesures, la pertinença a segments o els enriquiments.

### <a name="limitations"></a>Limitacions

- Els perfils de client es poden actualitzar, però no crear o suprimir.
- L'exportació d'actualitzacions en temps real per a sistemes externs, com el Power BI, no és possible en aquest moment.

## <a name="real-time-creation-of-activities"></a>Creació d'activitats en temps real

L'API en temps real us permet publicar una activitat nova des del sistema d'origen (registre d'origen individual) en un perfil de client unificat. L'activitat nova estarà disponible com a activitat unificada a la cronologia unificada del perfil del client en segons. Podeu veure la cronologia a la visualització de targeta del client o qualsevol altra integració de cronologia que hagueu configurat.

> [!NOTE]
>
> - Les activitats són immutables. No canvien una vegada creades.
> - Actualment, els segments i les mesures no es mostraran en funció de la nova activitat.
> - Les activitats afegides només a través de l'API en temps real no formen part d'exportacions i no es mostraran al PowerBI.

Hi ha dues maneres de connectar-se a l'API en temps real:

- [indirectament](#connect-via-the-dynamics-365-customer-insights-connector), mitjançant el [connector del Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [directament](#connect-directly-to-the-real-time-api), amb el codi

Ambdues maneres comparteixen els requisits previs següents:

- Un entorn del Customer Insights
- Perfils de client unificats
- Activitats configurades i en execució
- Permisos de col·laborador o d'administrador per autenticar el compte

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Connectar-se amb el connector del Dynamics 365 Customer Insights

L'API en temps real pot ingerir dades d'un connector del Power Platform dedicat, el [connector del Dynamics 365 Customer Insights](/connectors/customerinsights/), sense haver d'escriure ni implementar cap codi.    
El connector pot fer les mateixes accions en temps real que l'API. Necessiteu una llicència vàlida per als connectors prèmium. Per obtenir més informació, vegeu [Preguntes freqüents de llicències del Power Apps i el Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps i/o Power Automate](/connectors/)
- [Aplicacions lògiques](/azure/connectors/apis-list) de l'Azure

Per obtenir informació detallada sobre la creació de fluxos, vegeu la [documentació del Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Connectar-se directament a l'API en temps real

Per utilitzar les capacitats en temps real, creeu el vostre propi pipeline i connecteu-vos directament a l'API en temps real.    
Podeu publicar una activitat en el format del vostre sistema d'origen o en el format UnifiedActivity. Obtenir el format fent una trucada de l'API a /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Els detalls d'aquesta API, incloent-hi els paràmetres i les respostes, es troben a la secció **EntityData** de la [referència de les API del Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Per obtenir més informació, vegeu [Treballar amb les API del Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Comprendre l'ús en temps real amb la telemetria

Obtingueu una visió general del volum de sol·licituds realitzades a l'API en temps real i la informació sobre els problemes que pot trobar el sistema. Podeu [accedir a la telemetria en temps real](system.md#api-usage-tab). 


[!INCLUDE [footer-include](includes/footer-banner.md)]
