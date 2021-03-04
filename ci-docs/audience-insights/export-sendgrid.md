---
title: Exportar dades del Customer Insights a SendGrid
description: Apreneu a configurar la connexió a SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268720"
---
# <a name="connector-for-sendgrid-preview"></a>Connector per a SendGrid (versió preliminar)

Exporteu segments de perfils de client unificats a les llistes de contactes de SendGrid i utilitzeu-los per a les campanyes i el màrqueting per correu electrònic a SendGrid. 

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte de SendGrid](https://sendgrid.com/) i les credencials d'administrador corresponents.
-   Hi ha llistes de contactes a SendGrid i els identificadors corresponents. Per obtenir més informació, vegeu [SendGrid: administració de contactes](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Teniu [segments configurats](segments.md) a les conclusions del públic.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="connect-to-sendgrid"></a>Connectar-se a SendGrid

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A **SendGrid**, seleccioneu **Configura**.

1. Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Subfinestra de configuració d'exportació a SendGrid.":::

1. Introduïu la **Clau de l'API de SendGrid** [Clau de l'API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Introduïu l'**[ID de la llista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a SendGrid.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Següent** per configurar l'exportació.

## <a name="configure-the-connector"></a>Configurar el connector

1. A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client. Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom**, el **Cognom**, el **País o regió**, l'**Estat**, la **Ciutat** i el **Codi postal**.

1. Seleccioneu els segments que voleu exportar. Es recomana **no exportar més de 100.000 perfils de clients en total** a SendGrid. 

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 100.000 perfils en total a SendGrid.
- L'exportació a SendGrid es limita als segments.
- L'exportació de fins a 100.000 perfils a SendGrid pot tardar unes hores a completar-se. 
- El nombre de perfils que podeu exportar a SendGrid és limitat i dependrà del contracte que tingueu amb SendGrid.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a SendGrid, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que SendGrid compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]