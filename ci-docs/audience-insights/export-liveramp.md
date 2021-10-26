---
title: Connector del LiveRamp
description: Apreneu a configurar la connexió i exportar a LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f9a0a88fb58897e4d279c181f4cdb4f6c852da60
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618923"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportar segments a LiveRamp&reg; (versió preliminar)

Activeu les vostres dades a LiveRamp per connectar-vos amb més de 500 plataformes entre digital, social i televisió. Treballeu amb les dades de LiveRamp per orientar, suprimir i personalitzar les campanyes publicitàries.

## <a name="prerequisites-for-a-connection"></a>Requisits previs per a una connexió

- Es necessita una subscripció a LiveRamp per utilitzar aquest connector.
- Per obtenir una subscripció, [poseu-vos en contacte amb LiveRamp](https://liveramp.com/contact/) directament. [Més informació sobre la incorporació a LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Configuració de la connexió a LiveRamp

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **LiveRamp** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcioneu un **nom d'usuari** i una **contrasenya** per al vostre compte de FTP segur (SFTP) de LiveRamp.
Aquestes credencials poden ser diferents de les vostres credencials d'incorporació de LiveRamp.

1. Seleccioneu **Verifica** per provar la connexió amb LiveRamp.

1. Després de la verificació correcta, proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció LiveRamp. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Al camp **Trieu el vostre identificador de clau**, seleccioneu el **Correu electrònic**, **Nom i adreça** o **Telèfon** per enviar a LiveRamp per a la resolució de la identitat.
   > [!div class="mx-imgBorder"]
   > ![Connector de LiveRamp amb l'assignació d'atributs.](media/export-liveramp-segments.png "Connector de LiveRamp amb l'assignació d'atributs")

1. Assigneu els atributs corresponents de l'entitat *Client* per a l'identificador de clau seleccionat.

1. Seleccioneu **Afegeix un atribut** per assignar més atributs per enviar-los a LiveRamp.

   > [!TIP]
   > Si envieu més atributs d'identificador clau a LiveRamp, és possible que obtingueu una taxa de concordança més alta.

1. Seleccioneu els segments que voleu exportar a LiveRamp.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a LiveRamp, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que LiveRamp compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
