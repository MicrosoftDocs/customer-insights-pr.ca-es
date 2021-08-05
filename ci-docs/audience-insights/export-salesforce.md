---
title: Exportar dades del Customer Insights a Salesforce Marketing Cloud
description: Més informació sobre com configurar la connexió i l'exportació a Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8ce243918c2388e931a98df3bbe576ddf692f707
ms.sourcegitcommit: 4823684a1399fd66ffecfce21735f2bc90a1733c
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "6660255"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Exportar segments i altres dades a Salesforce Marketing Cloud (versió preliminar)

Utilitzeu les dades de clients a Salesforce Marketing Cloud exportant-les a través d'una ubicació del protocol Secure File Transfer Protocol (SFTP).

## <a name="prerequisites-for-connection"></a>Requisits previs per a la connexió

- Disponibilitat d'un amfitrió SFTP i les credencials d'administració corresponents. [Com configurar ubicacions SFTP per a Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Configurar la connexió a Salesforce Marketing Cloud

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Salesforce Marketing Cloud** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcioneu un **Nom d'usuari**, una **Contrasenya**, un **Nom de l'amfitrió** i una **Carpeta d'exportació** per al vostre compte SFTP.

1. Seleccioneu **Verifica** per provar la connexió.

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció SFTP. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Trieu si voleu exportar les dades **Comprimides** o **Descomprimides** i el **delimitador de camp** per als fitxers exportats.

1. Seleccioneu les entitats, per exemple, els segments que voleu exportar.

   > [!NOTE]
   > Cada entitat seleccionada es divideix en fins a cinc fitxers de sortida en exportar-se. 

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importar dades del Customer Insights de la ubicació SFTP a Salesforce Marketing Cloud

1. Creeu [extensions de dades a Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) per importar el fitxer de dades del Customer Insights des de la ubicació SFTP.

2. [Importeu les dades de la ubicació SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) a l'extensió de dades de Salesforce Marketing Cloud. 

3. Configureu l'automatització per importar les dades a les extensions de dades. Més informació sobre les [automatitzacions de supressió de fitxers i les automatitzacions planificades](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definiu una [automatització de supressió de fitxers](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) o una [automatització planificada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Aquí teniu un exemple d'una [automatització amb SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a través d'SFTP, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que la destinació de l'exportació compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
