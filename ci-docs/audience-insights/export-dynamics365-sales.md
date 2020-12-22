---
title: Exportar dades del Customer Insights al Dynamics 365 Sales
description: Més informació sobre com configurar la connexió al Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643806"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Connector per al Dynamics 365 Sales (visualització prèvia)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilitzeu les dades dels vostres clients per crear llistes de màrqueting, fer un seguiment de fluxos de treball i enviar promocions amb el Dynamics 365 Sales.

## <a name="prerequisite"></a>Requisit previ

Registres de contactes [del Dynamics 365 Sales ingerits mitjançant el Common Data Service](connect-power-query.md).

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
