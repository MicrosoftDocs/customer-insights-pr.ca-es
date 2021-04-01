---
title: Destinacions d'exportació
description: Exporteu dades i administreu destinacions d'exportació.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596073"
---
# <a name="export-destinations-preview-overview"></a>Informació general de les destinacions d'exportació (versió preliminar)

A la pàgina **Destinacions d'exportació** es mostren totes les ubicacions per a les quals heu configurat l'exportació de dades. També podeu afegir noves destinacions per a l'exportació. A més, mostra les opcions d'exportació que hi ha disponibles actualment. Obteniu una descripció general i breu, i esbrineu què podeu fer amb cada opció d'extensibilitat. Exporteu els perfils unificats, les mesures i els segments a les aplicacions admeses rellevants per a la vostra empresa.

Aneu a **Administració** > **Destinacions d'exportació** per trobar les següents opcions d'extensibilitat:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Experience Platform](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Emmagatzematge blob de l’Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Bot per al Microsoft Teams](export-teams-bot.md)
- [API del Customer Insights](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (complement de la targeta del client)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Centre de vendes del Dynamics 365 (complement de la targeta del client)](customer-card-add-in.md)
- [Administrador d'anuncis del Facebook](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

## <a name="add-a-new-export-destination"></a>Afegir una destinació d'exportació nova

Per afegir destinacions d'exportació, heu de tenir [permisos d'administrador](permissions.md). Si exporteu a serveis de Microsoft, assumim que els dos serveis es troben a la mateixa organització.

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. Canvieu a la pestanya **Les meves destinacions d'exportació**.

1. Seleccioneu **Afegeix una destinació** per crear una destinació d'exportació nova.

1. A la subfinestra **Afegeix una destinació**, seleccioneu el **tipus** de destinació d'exportació al menú desplegable.

1. Proporcioneu les dades necessàries i seleccioneu **Següent** per crear la destinació d'exportació.

També podeu seleccionar **Configura** en una peça de la pestanya **Descobreix**.

## <a name="view-export-destinations"></a>Visualitzar les destinacions d'exportació

Després de crear destinacions d'exportació, les trobareu en una taula de la pestanya **Les meves destinacions d'exportació**. Aquesta taula té tres columnes:

- **Nom de visualització**: el nom que heu introduït en crear la destinació.
- **Tipus**: el tipus de destinació d'exportació que definiu en crear la destinació.
- **Data de creació**: la data de creació de la destinació.

## <a name="edit-an-export-destination"></a>Editar una destinació d'exportació

1. Seleccioneu els punt suspensius verticals de la destinació d'exportació que voleu editar.

   > [!div class="mx-imgBorder"]
   > ![Punts suspensius verticals](media/export-destinations-page-ellipsis.png "Punts suspensius verticals")

1. Al menú desplegable, seleccioneu **Edita**.

1. Canvieu els valors que requereixin l'actualització i seleccioneu **Desa**.

## <a name="export-data-on-demand"></a>Exportar dades segons demanda

Després de configurar un connector per a una destinació d'exportació, les exportacions s'executaran amb cada [actualització planificada](system.md#schedule-tab).

Per exportar les dades sense haver d'esperar una actualització programada, aneu a la pestanya **Les meves destinacions d'exportació** a **Administració** > **Destinacions d'exportació**.

> [!div class="mx-imgBorder"]
> ![Punts suspensius verticals](media/export-destinations-page-ellipsis.png "Punts suspensius verticals")

- Seleccioneu **Exporta** sobre de la llista per executar l'exportació a totes les destinacions d'exportació simultàniament.
- Seleccioneu els punts suspensius (...) després d'un element de la llista i, a continuació, trieu l'opció **Exporta** per executar l'exportació per a una única destinació d'exportació.

## <a name="remove-an-export-destination"></a>Suprimir una destinació d'exportació

Per suprimir una destinació d'exportació, comenceu des de la pàgina principal **Destinacions d'exportació**.

1. Seleccioneu els punt suspensius verticals de la destinació d'exportació que voleu suprimir.

   > [!div class="mx-imgBorder"]
   > ![Punts suspensius verticals](media/export-destinations-page-ellipsis.png "Punts suspensius verticals")

2. Seleccioneu **Suprimeix** al menú desplegable.

3. Confirmeu la supressió seleccionant **Suprimeix** a la pantalla de confirmació.


[!INCLUDE[footer-include](../includes/footer-banner.md)]