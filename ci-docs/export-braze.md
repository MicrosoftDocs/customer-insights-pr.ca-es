---
title: Exporta les dades de Customer Insights a Braze
description: Obteniu informació sobre com configurar la connexió i exportar-la a Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642229"
---
# <a name="export-segment-lists-to-braze-preview"></a>Exporta les llistes de segments a Braze (visualització prèvia)

Exporteu segments de perfils de clients unificats a Braze i utilitzeu-los per a activitats de màrqueting.

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte](https://www.braze.com/) Braze i les credencials d'administrador corresponents.
-   Heu [configurat segments](segments.md) a Customer Insights.
-   Els perfils de clients unificats dels segments exportats contenen un camp que representa una adreça electrònica i un identificador de client de Braze. 

## <a name="known-limitations"></a>Limitacions conegudes

- L'exportació a Braze es limita a segments.
- Exportar fins a 1 milió de perfils de clients a Braze pot trigar fins a 40 minuts a completar-se. 
- El nombre de perfils de clients que podeu exportar a Braze depèn i es limita al vostre contracte amb Braze.

## <a name="set-up-connection-to-braze"></a>Configura la connexió a Braze

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Braze** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcioneu la [clau](https://www.braze.com/docs/api/basics/) de l'API Braze per continuar iniciant la sessió. 

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a Braze.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. **Al camp Connexió per a l'exportació**, trieu una connexió de la secció Braze. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.  

3. A la **secció Coincidència de** dades, al **camp Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client, al camp "Identificador de client", seleccioneu el camp que representa l'identificador de braze del client. És necessari exportar segments a Braze. Els segments de Braze es crearan amb el mateix nom del segment que a Dynamics 365 Customer Insights. Podeu triar camps opcionals addicionals per fer coincidir dades. 

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights transmetre dades a Braze, permeteu la transferència de dades fora del límit Dynamics 365 Customer Insights de compliment de, incloses dades potencialment sensibles, com ara dades personals. Microsoft transferirà aquestes dades a les vostres instruccions, però sou responsable d'assegurar-vos que Braze compleixi amb qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
