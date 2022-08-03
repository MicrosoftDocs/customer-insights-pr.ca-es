---
title: Exportar dades a Salesforce Marketing Cloud (visualització prèvia)
description: Més informació sobre com configurar la connexió i l'exportació a Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197026"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Exportar dades a Salesforce Marketing Cloud (visualització prèvia)

Utilitzeu les dades de clients a Salesforce Marketing Cloud exportant-les a través d'una ubicació del protocol Secure File Transfer Protocol (SFTP).

## <a name="prerequisites"></a>Requisits previs

- Un [amfitrió SFTP per a Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) i les credencials d'administrador corresponents.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Configurar la connexió amb Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Salesforce Marketing Cloud**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcioneu un **Nom d'usuari**, una **Contrasenya**, un **Nom de l'amfitrió** i una **Carpeta d'exportació** per al vostre compte SFTP.

1. Seleccioneu **Verifica** per provar la connexió.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció SFTP. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Trieu si voleu exportar les dades **Comprimides** o **Descomprimides** i el **delimitador de camp** per als fitxers exportats.

1. Seleccioneu les entitats, per exemple els segments, que voleu exportar.

   > [!NOTE]
   > Cada entitat seleccionada es dividirà en un màxim de cinc fitxers de sortida quan s'exporti.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importar dades del Customer Insights de la ubicació SFTP a Salesforce Marketing Cloud

1. Creeu [extensions de dades a Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) per importar el fitxer de dades del Customer Insights des de la ubicació SFTP.

2. [Importeu les dades de la ubicació SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) a l'extensió de dades de Salesforce Marketing Cloud.

3. Configureu l'automatització per importar les dades a les extensions de dades. Més informació sobre les [automatitzacions de supressió de fitxers i les automatitzacions planificades](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definiu una [automatització de supressió de fitxers](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) o una [automatització planificada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Aquí teniu un exemple d'una [automatització amb SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
