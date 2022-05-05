---
title: Exportar dades del Customer Insights a SendGrid
description: Apreneu a configurar la connexió i exportar a SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 38dd782fdf06d5970e79e6deb6e8fc94252da585
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642382"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportar segments a SendGrid (versió preliminar)

Exporteu segments de perfils de client unificats a les llistes de contactes de SendGrid i utilitzeu-los per a les campanyes i el màrqueting per correu electrònic a SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Requisits previs per a una connexió

-   Teniu un [compte de SendGrid](https://sendgrid.com/) i les credencials d'administrador corresponents.
-   Hi ha llistes de contactes a SendGrid i els identificadors corresponents. Per obtenir més informació, vegeu [SendGrid: administració de contactes](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Heu [configurat segments](segments.md) a Customer Insights.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 100.000 perfils de client en total a SendGrid.
- L'exportació a SendGrid es limita als segments.
- L'exportació de fins a 100.000 perfils de client a SendGrid pot trigar algunes hores a completar-se. 
- El nombre de perfils de client que podeu exportar a SendGrid depèn del vostre contracte amb SendGrid i pot estar limitat.

## <a name="set-up-connection-to-sendgrid"></a>Configuració de la connexió a SendGrid

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **SendGrid** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu la **Clau de l'API de SendGrid** [Clau de l'API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a SendGrid.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció SendGrid. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Introduïu l'**[ID de la llista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom**, el **Cognom**, el **País o regió**, l'**Estat**, la **Ciutat** i el **Codi postal**.

1. Seleccioneu els segments que voleu exportar. Es recomana **no exportar més de 100.000 perfils de clients en total** a SendGrid. 

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a SendGrid, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que SendGrid compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE [footer-include](includes/footer-banner.md)]
