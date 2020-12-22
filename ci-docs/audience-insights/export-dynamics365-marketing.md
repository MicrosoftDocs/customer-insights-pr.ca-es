---
title: Exportar dades del Customer Insights al Dynamics 365 Marketing
description: Més informació sobre com configurar la connexió al Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643761"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Connector per al Dynamics 365 Marketing (visualització prèvia)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilitzeu [segments](segments.md) per generar campanyes i posar-vos en contacte amb grups específics de clients amb el Dynamics 365 Marketing. Per obtenir més informació, vegeu [Utilitzar segments del Dynamics 365 Customer Insights amb el Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Requisit previ

Registres de contactes [del Dynamics 365 Marketing ingerits mitjançant el Common Data Service](connect-power-query.md).

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
