---
title: Integrar dades web de les conclusions d'interacció amb les conclusions del públic
description: Incorporeu informació web sobre els clients de les conclusions d'interacció a les conclusions del públic.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597453"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrar dades web de les conclusions d'interacció amb les conclusions del públic

Els clients solen fer el dia a dia les transaccions en línia utilitzant llocs web. La funcionalitat de conclusions d'interacció del Dynamics 365 Customer Insights és una solució pràctica per integrar dades web com a font. A banda de les dades transaccionals, demogràfiques o de comportament, podem veure les activitats al web als perfils de client unificats. Podem utilitzar aquest perfil per obtenir informació addicional, com ara segments, mesures o prediccions per a l'activació del públic.

En aquest article es descriuen els passos per introduir les dades d'activitat web dels clients de les conclusions d'interacció a l'entorn de conclusions del públic existent.

En aquest exemple, suposem un entorn que conté perfils de client unificats. Els perfils s'han unificat amb fonts d'enquestes, vendes al detall i un sistema de venda d'entrades. També mostra les activitats relacionades dels clients. 

Ara volem saber si un client visita les nostres propietats web i comprendre les seves activitats. Les activitats inclouen, per exemple, llocs web visitats o pàgines de productes visualitzades des d'un enllaç rebut en un correu electrònic.

## <a name="prerequisites"></a>Requisits previs

Per integrar dades de les conclusions d'interacció, cal complir alguns requisits previs: 

- Integrar l'SDK de conclusions d'interacció amb el vostre lloc web. Per obtenir més informació, vegeu [Introducció a l'SDK web](../engagement-insights/instrument-website.md).
- Exportar esdeveniments web de les conclusions d'interacció requereix accés a un compte d'emmagatzematge de l'ADLS Gen 2 que s'utilitzarà per ingerir les dades d'esdeveniments web a les conclusions del públic. Per obtenir més informació, vegeu [Exportar esdeveniments](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Configurar esdeveniments refinats a les conclusions d'interacció

Després que un administrador instrumenti un lloc web amb l'SDK de conclusions d'interacció, els *esdeveniments base* es recopilen quan un usuari visualitza una pàgina web o fa clic en algun lloc. Els esdeveniments base tendeixen a oferir nombrosos detalls. Segons el cas d'ús, només cal un subconjunt de les dades d'un esdeveniment base. Les conclusions d'interacció us permeten crear *esdeveniments refinats* que només continguin les propietats d'un esdeveniment base que seleccioneu.     

Per obtenir més informació, vegeu [Crear i modificar esdeveniments refinats](../engagement-insights/refined-events.md).

Consideracions en crear esdeveniments refinats: 

- Proporcioneu un nom que tingui sentit per a l'esdeveniment refinat. S'utilitza com a nom d'activitat a les conclusions del públic.
- Seleccioneu com a mínim les propietats següents per crear una activitat a les conclusions del públic: 
    - Signal.Action.Name: indica els detalls de l'activitat
    - Signal.User.Id: s'utilitza per assignar-se amb l'identificador de client
    - Signal.View.Uri: s'utilitza com a adreça web com a base per a segments o mesures
    - Signal.Export.Id: per utilitzar-la com a clau principal per als esdeveniments <!-- system generated, do we need to list?-->
    - Signal.Timestamp: per determinar la data i l'hora de l'activitat

Seleccioneu els filtres en què us voleu centrar en els esdeveniments i les pàgines que importen per al cas d'ús. En aquest exemple, utilitzarem el nom de l'acció "Promoció per correu electrònic".

## <a name="export-the-refined-web-events"></a>Exportar els esdeveniments web refinats 

Després de definir l'esdeveniment refinat, heu de configurar l'exportació de les dades de l'esdeveniment a l'Azure Data Lake Storage, que es pot definir com a font de dades per a la ingesta a les conclusions del públic. Les exportacions tenen lloc constantment a mesura que flueixen els esdeveniments de la propietat web.

Per obtenir més informació, vegeu [Exportar esdeveniments](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Ingerir dades d'esdeveniments a les conclusions del públic

Ara que heu definit l'esdeveniment refinat i heu configurat la seva exportació, passarem a ingerir les dades a les conclusions del públic. Heu de crear una nova font de dades basada en una carpeta del Common Data Model. Introduïu els detalls del compte d'emmagatzematge al qual exporteu els esdeveniments. Al fitxer *default.cdm.json*, seleccioneu l'esdeveniment refinat que voleu ingerir i creeu l'entitat a les conclusions del públic.

Per obtenir més informació, vegeu [Connectar-se a una carpeta del Common Data Model mitjançant un compte de l'Azure Data Lake](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Relacionar dades d'esdeveniments refinats com a activitat d'un perfil de client

Un cop completada la ingesta d'entitats, podeu configurar l'activitat per al perfil de client.

Per obtenir més informació, vegeu [Activitats del client](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Pàgina Activitats amb la subfinestra Edita l'activitat ampliada i camps emplenats.":::

Configureu l'activitat nova amb l'assignació següent: 

- **Clau principal:** Signal.Export.Id, un identificador únic que està disponible per a cada registre d'esdeveniment a les conclusions d'interacció. Aquesta propietat es genera automàticament.

- **Marca de temps:** Signal.Timestamp a la propietat de l'esdeveniment.

- **Esdeveniment:** Signal.Name, el nom de l'esdeveniment del qual voleu fer el seguiment.

- **Adreça web:** Signal.View.Uri que fa referència a l'URI de la pàgina que ha creat l'esdeveniment.

- **Detalls:** Signal.Action.Name per representar la informació que s'associa a l'esdeveniment. La propietat seleccionada en aquest cas indica que l'esdeveniment és per a la promoció per correu electrònic.

- **Tipus d'activitat:** en aquest exemple, triem el tipus d'activitat existent WebLog. Aquesta selecció és una opció de filtre útil per executar models de predicció o crear segments basats en aquest tipus d'activitat.

- **Configuració de la relació:** aquesta configuració important relaciona l'activitat amb els perfils de client existents. **Signal.User.Id** és l'identificador configurat a l'SDK que cal recopilar i que està relacionat amb l'identificador d'usuari en altres fonts de dades que es configuren a les conclusions del públic. En aquest exemple, configurem la relació entre Signal.User.Id i RetailCustomers:CustomerRetailId, que és la clau principal definida en el pas d'assignació del procés d'unificació de dades.


Després de processar les activitats, podeu revisar els registres de client i obrir una targeta de client per veure les activitats de les conclusions d'interacció a la cronologia. 

> [!TIP]
> Per cercar un identificador de client que té una activitat de les conclusions d'interacció, aneu a **Entitats** i feu una visualització prèvia de les dades de l'entitat UnifiedActivity. ActivityTypeDisplay = WebLog conté l'activitat de les conclusions d'interacció configurada a l'exemple anterior. Copieu l'identificador de client d'un d'aquests registres i de l'identificador de la pàgina **Clients**.

## <a name="next-steps"></a>Passos següents

Ara podeu crear [segments](segments.md), [mesures](measures.md) i [prediccions](predictions.md) per fer una connexió significativa amb els clients.


[!INCLUDE[footer-include](../includes/footer-banner.md)]