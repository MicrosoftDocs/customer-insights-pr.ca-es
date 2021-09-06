---
title: Exportar dades del Customer Insights a Campaign Monitor
description: Apreneu a configurar la connexió i exportar a Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d2cc3ec944faa1d77ffb44e8abb422d753c5625d0ccef75cbb7efb14cb7c3741
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031875"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportar segments a Campaign Monitor (versió preliminar)

Exporteu segments de perfils de client unificats a Campaign Monitor i utilitzeu-los per a activitats de màrqueting.

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte de Campaign Monitor](https://www.campaignmonitor.com/) i les credencials d'administrador corresponents.
-   Teniu [segments configurats](segments.md) a les conclusions del públic.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Podeu exportar fins a 1 milió de perfils per exportació a Campaign Monitor.
- L'exportació a Campaign Monitor es limita als segments.
- L'exportació de fins a 1 milió de perfils a Campaign Monitor pot trigar fins a 20 minuts com a màxim. 
- El nombre de perfils que podeu exportar a Campaign Monitor depèn i està limitat pel contracte amb Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurar la connexió a Campaign Monitor

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Campaign Monitor** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a Campaign Monitor.

1. Seleccioneu **Autentica amb Campaign Monitor** i proporcioneu les vostres credencials d'administració per a Campaign Monitor.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Campaign Monitor. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Introduïu l'[**ID de llista de Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Genereu la clau de l'API](https://www.campaignmonitor.com/api/getting-started/) des de **Configuració del compte** a Campaign Monitor per visualitzar primer l'ID de la llista de l'API.  

3. A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client. Cal que exporteu segments a Campaign Monitor.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan permeteu al Dynamics 365 Customer Insights transmetre dades a Campaign Monitor, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals. Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que Campaign Monitor compleixi les obligacions de privadesa o de seguretat que pugueu teniu. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
