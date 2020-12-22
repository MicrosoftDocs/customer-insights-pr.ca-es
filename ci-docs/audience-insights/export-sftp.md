---
title: Exportar dades del Customer Insights a amfitrions d'SFTP
description: Més informació sobre com configurar la connexió a un amfitrió SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643491"
---
# <a name="connector-for-sftp-preview"></a>Connector per a SFTP (versió preliminar)

Per utilitzar les dades dels vostres clients en aplicacions de tercers, exporteu-les a un amfitrió del protocol de transferència segura de fitxers (SFTP).

## <a name="prerequisites"></a>Requisits previs

- Disponibilitat d'un amfitrió SFTP i de les credencials corresponents.

## <a name="connect-to-sftp"></a>Connectar-se a SFTP

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A **SFTP**, seleccioneu **Configura**.

1. Doneu a la destinació un nom reconeixible al camp **Nom de visualització**.

1. Proporcioneu un **Nom d'usuari**, una **Contrasenya** i un **Nom de l'amfitrió** per al vostre compte d'SFTP. Exemple: Si la carpeta arrel del servidor d'SFTP és /root/folder, i voleu que les dades s'exportin a /root/folder/ci_export_destination_folder, l'amfitrió haurà de ser sftp://<adreça_del_servidor>/ci_export_destination_folder".

1. Seleccioneu **Verifica** per provar la connexió.

1. Després de la verificació correcta, trieu si voleu exportar les dades **Comprimides** o **Descomprimides** i seleccioneu el **delimitador de camp** per als fitxers exportats.

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Següent** per començar a configurar l'exportació.

## <a name="configure-the-connection"></a>Configurar la connexió

1. Seleccioneu els **atributs del client** que voleu exportar. Podeu exportar un o diversos atributs.

1. Seleccioneu **Següent**.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a través d'SFTP, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que la destinació de l'exportació compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
