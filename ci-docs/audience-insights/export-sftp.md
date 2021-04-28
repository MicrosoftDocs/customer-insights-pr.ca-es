---
title: Exportar dades del Customer Insights a amfitrions d'SFTP
description: Apreneu a configurar la connexió i exportar a una ubicació SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760407"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a>Exportar llistes de segments i altres dades a SFTP (versió preliminar)

Utilitzeu les dades de client en aplicacions de tercers exportant-les a una ubicació de Protocol de transferència segura de fitxers (SFTP).

## <a name="prerequisites-for-connection"></a>Requisits previs per a la connexió

- Disponibilitat d'un amfitrió SFTP i les credencials corresponents.

## <a name="known-limitations"></a>Limitacions conegudes

- El temps d'execució d'una exportació depèn del rendiment del sistema. Us recomanem dos nuclis de CPU i 1 Gb de memòria com a configuració mínima del vostre servidor. 
- L'exportació d'entitats amb fins a 100 milions de perfils de clients pot tardar 90 minuts quan s'utilitza la configuració mínima recomanada de dos nuclis de CPU i 1 Gb de memòria. 

## <a name="set-up-connection-to-sftp"></a>Configuració de la connexió a SFTP

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **SFTP** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcioneu un **Nom d'usuari**, una **Contrasenya**, un **Nom de l'amfitrió** i una **Carpeta d'exportació** per al vostre compte SFTP.

1. Seleccioneu **Verifica** per provar la connexió.

1. Trieu si voleu exportar les dades **Comprimides** o **Descomprimides** i el **delimitador de camp** per als fitxers exportats.

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció SFTP. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Seleccioneu les entitats, per exemple, els segments que voleu exportar.

   > [!NOTE]
   > Cada entitat seleccionada es divideix en fins a cinc fitxers de sortida en exportar-se. 

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a través d'SFTP, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que la destinació de l'exportació compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
