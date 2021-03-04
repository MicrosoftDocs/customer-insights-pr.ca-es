---
title: Connector del LiveRamp
description: Apreneu a exportar dades a LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270146"
---
# <a name="liverampreg-connector-preview"></a>Connector de LiveRamp&reg; (visualització prèvia)

Activeu les dades a LiveRamp per connectar-vos amb més de 500 plataformes en ecosistemes digitals, socials i de TV. Treballeu amb les dades de LiveRamp per orientar, suprimir i personalitzar les campanyes publicitàries.

## <a name="prerequisites"></a>Requisits previs

- Es necessita una subscripció a LiveRamp per utilitzar aquest connector.
- Per obtenir una subscripció, [poseu-vos en contacte amb LiveRamp](https://liveramp.com/contact/) directament. [Més informació sobre la incorporació a LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Connectar-se a LiveRamp

1. A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.

1. A la peça de **LiveRamp**, seleccioneu **Configura**.

1. Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.

1. Proporcioneu un **nom d'usuari** i una **contrasenya** per al vostre compte de FTP segur (SFTP) de LiveRamp.
Aquestes credencials poden ser diferents de les vostres credencials d'incorporació de LiveRamp.

1. Seleccioneu **Verifica** per provar la connexió amb LiveRamp.

1. Després de la verificació correcta, proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**.

1. Seleccioneu **Següent** per configurar el connector de LiveRamp.

## <a name="configure-the-connector"></a>Configurar el connector

1. Al camp **Trieu el vostre identificador de clau**, seleccioneu el **Correu electrònic**, **Nom i adreça** o **Telèfon** per enviar a LiveRamp per a la resolució de la identitat.

1. Assigneu els atributs corresponents de l'entitat del client unificat per a l'identificador de clau seleccionat.

1. Seleccioneu **Afegeix un atribut** per assignar atributs addicionals per enviar a LiveRamp.

   > [!TIP]
   > Si envieu més atributs d'identificador clau a LiveRamp, és possible que obtingueu una taxa de concordança més alta.

1. Seleccioneu els segments que voleu exportar a LiveRamp.

1. Seleccioneu **Desa**.

> [!div class="mx-imgBorder"]
> ![Connector de LiveRamp amb l'assignació d'atributs](media/export-liveramp-segments.png "Connector de LiveRamp amb l'assignació d'atributs")

## <a name="export-the-data"></a>Exportar les dades

L'exportació començarà en breu si tots els requisits previs per a l'exportació s'han completat. L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).
Una vegada que l'exportació s'hagi completat correctament, podeu iniciar la sessió a la incorporació de LiveRamp per activar i distribuir les dades.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a LiveRamp, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que LiveRamp compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

[!INCLUDE[footer-include](../includes/footer-banner.md)]