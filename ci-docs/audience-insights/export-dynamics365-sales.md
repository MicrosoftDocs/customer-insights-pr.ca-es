---
title: Exportar dades del Customer Insights al Dynamics 365 Sales
description: Apreneu a configurar la connexió i exportar a Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d8a35424f4271b350b8d84e72a01deb6d69652a0
ms.sourcegitcommit: 08a5dfcc4f9d293c8e7ac4fef604bc52985b1b78
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/04/2022
ms.locfileid: "8090911"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Ús de segments al Dynamics 365 Sales (versió preliminar)



Utilitzeu les dades dels vostres clients per crear llistes de màrqueting, fer un seguiment de fluxos de treball i enviar promocions amb el Dynamics 365 Sales.

## <a name="known-limitations"></a>Limitacions conegudes

- Les exportacions al Dynamics 365 Sales estan limitades a 100.000 membres per segment.
- Les exportacions de segments al Dynamics 365 Sales poden trigar fins a 3 hores a completar-se. 

## <a name="prerequisite-for-connection"></a>Requisit previ per a la connexió

1. Els registres de contacte han d'estar presents al Dynamics 365 Sales per poder exportar un segment del Customer Insights al Sales. Llegiu més informació sobre com ingerir contactes al [Dynamics 365 Sales mitjançant el Microsoft Dataverse](connect-power-query.md).

   > [!NOTE]
   > L'exportació de segments de les conclusions del públic al Sales no crearà registres de contacte nous a les instàncies del Sales. Els registres de contacte del Sales s'han d'ingerir a les conclusions del públic i s'han d'utilitzar com a font de dades. També s'han d'incloure a l'entitat Client unificada per assignar els identificadors de client als identificadors de contacte abans d'exportar els segments.

## <a name="set-up-the-connection-to-sales"></a>Configuració de la connexió a Sales

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Dynamics 365 Sales** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu l'adreça URL del Sales de l'organització al camp **Adreça del servidor**.

1. A la secció **Compte d'administració del servidor**, seleccioneu **Inicia la sessió** i trieu un compte del Dynamics 365 Sales.

1. Assigneu un camp d'ID de client a l'ID de contacte del Dynamics 365.

1. Seleccioneu **Desa** per completar la connexió. 

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Dynamics 365 Sales. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Trieu un o diversos segments.

1. Seleccioneu **Desa**

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
