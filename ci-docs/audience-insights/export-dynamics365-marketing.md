---
title: Exportar dades del Customer Insights al Dynamics 365 Marketing
description: Apreneu a configurar la connexió i exportar a Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: d3254bf13b843fe8e1b6e6db49dd6ee1dc22290c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353899"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Ús de segments al Dynamics 365 Marketing (versió preliminar)



Utilitzeu [segments](segments.md) per generar campanyes i posar-vos en contacte amb grups específics de clients amb el Dynamics 365 Marketing. Per obtenir més informació, vegeu [Utilitzar segments del Dynamics 365 Customer Insights amb el Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Si utilitzeu les noves funcionalitats del Dynamics 365 Marketing per a l'orquestració del recorregut del client en temps real en una organització del Dataverse, no cal que creeu una exportació estàndard al Dynamics 365 Marketing. Els contactes i els segments de les conclusions del públic estan disponibles directament al Dynamics 365 Marketing després de connectar el Marketing i el Customer Insights Abans de suprimir les exportacions existents, reviseu la documentació sobre [com connectar les conclusions del públic i l'orquestració del recorregut del client del Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Requisit previ per a la connexió

- Els registres de contacte han d'estar presents al Dynamics 365 Marketing per poder exportar un segment del Customer Insights al Marketing. Llegiu més informació sobre com ingerir contactes al [Dynamics 365 Marketing mitjançant el Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > L'exportació de segments de les conclusions del públic al Marketing no crearà registres de contacte nous a les instàncies del Marketing. Els registres de contacte del Marketing s'han d'ingerir a les conclusions del públic i s'han d'utilitzar com a font de dades. També s'han d'incloure a l'entitat Client unificada per assignar els identificadors de client als identificadors de contacte abans d'exportar els segments.

## <a name="set-up-connection-to-marketing"></a>Configuració de la connexió a Marketing

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Dynamics 365 Marketing** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu l'adreça URL del Marketing de l'organització al camp **Adreça del servidor**.

1. A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Marketing.

1. Assigneu el camp Contact ID de l'entitat Client a l'identificador de contacte del Dynamics 365.

1. Seleccioneu **Desa** per completar la connexió. 

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Dynamics 365 Marketing. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Trieu un o diversos segments.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
