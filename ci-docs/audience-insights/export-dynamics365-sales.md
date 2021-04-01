---
title: Exportar dades del Customer Insights al Dynamics 365 Sales
description: Més informació sobre com configurar la connexió al Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598097"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Connector per al Dynamics 365 Sales (visualització prèvia)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilitzeu les dades dels vostres clients per crear llistes de màrqueting, fer un seguiment de fluxos de treball i enviar promocions amb el Dynamics 365 Sales.

## <a name="prerequisite"></a>Requisit previ

1. Els registres de contacte han d'estar presents al Dynamics 365 Sales per poder exportar un segment del Customer Insights al Sales. Llegiu més informació sobre com ingerir contactes al [Dynamics 365 Sales mitjançant el Common Data Services](connect-power-query.md).

   > [!NOTE]
   > L'exportació de segments de les conclusions del públic al Sales no crearà registres de contacte nous a les instàncies del Sales. Els registres de contacte del Sales s'han d'ingerir a les conclusions del públic i s'han d'utilitzar com a font de dades. També s'han d'incloure a l'entitat Client unificada per assignar els identificadors de client als identificadors de contacte abans d'exportar els segments.

## <a name="configure-the-connector-for-sales"></a>Configurar el connector per al Sales

1. A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.

1. A **Dynamics 365 Sales**, seleccioneu **Configura**.

1. Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.

1. Introduïu l'adreça URL del Sales de l'organització al camp **Adreça del servidor**.

1. A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Sales.

1. Assigneu un camp d'ID de client a l'ID de contacte del Dynamics 365.

1. Seleccioneu **Següent**.

1. Trieu un o diversos segments.

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]