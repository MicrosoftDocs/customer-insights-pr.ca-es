---
title: Exportar dades del Customer Insights a AdRoll
description: Apreneu a configurar la connexió a AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697062"
---
# <a name="connector-for-adroll-preview"></a>Connector per a AdRoll (versió preliminar)

Exporteu segments de perfils de client unificats a AdRoll i utilitzeu-los per a la publicitat. 

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte d'AdRoll](https://www.adroll.com/) i les credencials d'administrador corresponents.
-   Teniu [segments configurats](segments.md) a les conclusions del públic.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="connect-to-adroll"></a>Connecta a AdRoll

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A **AdRoll**, seleccioneu **Configura**.

1. Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Subfinestra de configuració per a la connexió d'AdRoll.":::

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a AdRoll.

1. Seleccioneu **Autenticació amb AdRoll** i indiqueu les vostres credencials d'administrador d'AdRoll. 

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Introduïu l'**Identificador de l'anunciant d'AdRoll** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Seleccioneu **Següent** per configurar l'exportació.

## <a name="configure-the-connector"></a>Configurar el connector

1. A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client. Cal que exporteu segments a AdRoll.

1. Seleccioneu els segments que voleu exportar. Seleccioneu un segment amb un mínim de 100 membres. No podeu exportar segments més petits. A més, la mida màxima d'un segment que s'ha d'exportar és de 250.000 membres per exportació. 

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitacions conegudes

- Podeu exportar fins a un total de 100.000 perfils per exportació a AdRoll.
- No podeu exportar segments amb menys de 100 perfils a AdRoll. 
- L'exportació a AdRoll es limita als segments.
- L'exportació de fins a 250.000 perfils a AdRoll pot trigar fins a 10 minuts com a completar-se. 
- El nombre de perfils que podeu exportar a AdRoll és limitat i dependrà del contracte que tingueu amb AdRoll.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a AdRoll, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que AdRoll compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
