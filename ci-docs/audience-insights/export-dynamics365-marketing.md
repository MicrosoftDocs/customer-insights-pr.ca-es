---
title: Exportar dades del Customer Insights al Dynamics 365 Marketing
description: Més informació sobre com configurar la connexió al Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269042"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Connector per al Dynamics 365 Marketing (visualització prèvia)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilitzeu [segments](segments.md) per generar campanyes i posar-vos en contacte amb grups específics de clients amb el Dynamics 365 Marketing. Per obtenir més informació, vegeu [Utilitzar segments del Dynamics 365 Customer Insights amb el Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Requisit previ

- Els registres de contacte han d'estar presents al Dynamics 365 Marketing per poder exportar un segment del Customer Insights al Marketing. Llegiu més informació sobre com ingerir contactes al [Dynamics 365 Marketing mitjançant el Common Data Services](connect-power-query.md).

  > [!NOTE]
  > L'exportació de segments de les conclusions del públic al Marketing no crearà registres de contacte nous a les instàncies del Marketing. Els registres de contacte del Marketing s'han d'ingerir a les conclusions del públic i s'han d'utilitzar com a font de dades. També s'han d'incloure a l'entitat Client unificada per assignar els identificadors de client als identificadors de contacte abans d'exportar els segments.

## <a name="configure-the-connector-for-marketing"></a>Configurar el connector per al Marketing

1. A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.

1. A **Dynamics 365 Marketing**, seleccioneu **Configura**.

1. Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.

1. Introduïu l'adreça URL del Marketing de l'organització al camp **Adreça del servidor**.

1. A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Marketing.

1. Assigneu un camp d'ID de client a l'ID de contacte del Dynamics 365.

1. Seleccioneu **Següent**.

1. Trieu un o diversos segments.

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]