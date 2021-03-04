---
title: Exportar dades del Customer Insights a amfitrions d'SFTP
description: Més informació sobre com configurar la connexió a un amfitrió SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267986"
---
# <a name="connector-for-sftp-preview"></a>Connector per a SFTP (versió preliminar)

Per utilitzar les dades dels vostres clients en aplicacions de tercers, exporteu-les a un amfitrió del protocol de transferència segura de fitxers (SFTP).

## <a name="prerequisites"></a>Requisits previs

- Disponibilitat d'un amfitrió SFTP i les credencials corresponents.

## <a name="connect-to-sftp"></a>Connecta a SFTP

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A **SFTP**, seleccioneu **Configura**.

1. Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.

1. Proporcioneu un **Nom d'usuari**, una **Contrasenya**, un **Nom de l'amfitrió** i una **Carpeta d'exportació** per al vostre compte SFTP.

1. Seleccioneu **Verifica** per provar la connexió.

1. Després d'haver realitzat una verificació correcta, trieu si voleu exportar les dades **Comprimides** o **Sense comprimir** i seleccioneu el **delimitador de camp** per als fitxers exportats.

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Següent** per començar a configurar l'exportació.

## <a name="configure-the-export"></a>Configurar l'exportació

1. Seleccioneu les entitats, per exemple, els segments que voleu exportar.

   > [!NOTE]
   > Cada entitat seleccionada tindrà fins a cinc fitxers de sortida en exportar-se. 

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitacions conegudes

- El temps d'execució d'una exportació depèn del rendiment del sistema. Us recomanem dos nuclis de CPU i 1 Gb de memòria com a configuració mínima del vostre servidor. 
- L'exportació d'entitats amb fins a 100 milions de perfils de clients pot tardar 90 minuts quan s'utilitza la configuració mínima recomanada de dos nuclis de CPU i 1 Gb de memòria. 

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a través d'SFTP, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que la destinació de l'exportació compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]