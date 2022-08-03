---
title: Exportar segments al Dynamics 365 Marketing (visualització prèvia)
description: Apreneu a configurar la connexió i exportar a Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196612"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Exportar segments al Dynamics 365 Marketing (visualització prèvia)

Utilitzeu [segments](segments.md) per generar campanyes i contactar amb grups específics de clients amb [el Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Si utilitzeu les noves funcionalitats del Dynamics 365 Marketing per a l'orquestració del recorregut del client en temps real en una organització del Dataverse, no cal que creeu una exportació estàndard al Dynamics 365 Marketing. Els contactes i segments del Customer Insights estan disponibles directament al Dynamics 365 Marketing després de connectar el Marketing i el Customer Insights. Abans de suprimir les exportacions existents, reviseu la documentació sobre [com connectar el Customer Insights i el Dynamics 365 Marketing recorregut del client l'orquestració](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Requisit previ

Els registres de contacte han d'estar presents al Dynamics 365 Marketing per poder exportar un segment del Customer Insights al Marketing. Llegiu més informació sobre com ingerir contactes al [Dynamics 365 Marketing mitjançant el Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> L'exportació de segments del Customer Insights al Marketing no crearà registres de contacte nous a les instàncies de Marketing. Els registres de contacte del Marketing s'han d'ingerir al Customer Insights i s'han d'utilitzar com a font de dades. També s'han d'incloure a l'entitat Client unificada per assignar els identificadors de client als identificadors de contacte abans d'exportar els segments.

## <a name="set-up-connection-to-marketing"></a>Configuració de la connexió a Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Dynamics 365 Marketing**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu l'adreça URL del Marketing de l'organització al camp **Adreça del servidor**.

1. A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Marketing.

1. Assigneu el camp Identificador de contacte de l'entitat Client a l'identificador de contacte del Dynamics 365.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Dynamics 365 Marketing. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Seleccioneu el camp Contact ID a l'entitat Client que coincideix amb l'identificador de contacte del Dynamics 365.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
