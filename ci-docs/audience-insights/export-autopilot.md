---
title: Exportar dades del Customer Insights a Autopilot
description: Apreneu a configurar la connexió a Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596114"
---
# <a name="connector-for-autopilot-preview"></a>Connector per a Autopilot (versió preliminar)

Exporteu segments de perfils de client unificats a Autopilot i utilitzeu-los per al màrqueting per correu electrònic a Autopilot. 

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte d'Autopilot](https://www.autopilothq.com/) i les credencials d'administrador corresponents.
-   Teniu [segments configurats](segments.md) a les conclusions del públic.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="connect-to-autopilot"></a>Connectar-se a Autopilot

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A **Autopilot**, seleccioneu **Configura**.

1. Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Subfinestra de configuració per a la connexió d'Autopilot.":::

1. Introduïu la **Clau de l'API d'Autopilot** [Clau de l'API d'Autopilot](https://autopilot.docs.apiary.io/#).

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a Autopilot.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Següent** per configurar l'exportació.

## <a name="configure-the-connector"></a>Configurar el connector

1. A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client. Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom** i el **Cognom**.

1. Seleccioneu els segments que voleu exportar. Es recomana **no exportar més de 100.000 perfils de clients en total** a Autopilot. 

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitacions conegudes

- Podeu exportar fins a un total de 100.000 perfils a Autopilot.
- L'exportació a Autopilot es limita als segments.
- L'exportació de fins a 100.000 perfils a Autopilot pot tardar unes hores a completar-se. 
- El nombre de perfils que podeu exportar a Autopilot és limitat i dependrà del contracte que tingueu amb Autopilot.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Autopilot, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Autopilot compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]