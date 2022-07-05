---
title: Exporta segments a Braze (previsualització)
description: Obteniu informació sobre com configurar la connexió i exportar-la a Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082675"
---
# <a name="export-segments-to-braze-preview"></a>Exporta segments a Braze (previsualització)

Exporteu segments de perfils de clients unificats a Braze i utilitzeu-los per a activitats de màrqueting.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://www.braze.com/) de Braze i les credencials d'administrador corresponents.
- Segments existents [a Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Segments configurats](segments.md) a Customer Insights.
- Els perfils de clients unificats dels segments exportats contenen un camp que representa una adreça electrònica i un identificador de client de Braze.

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

1. **Al camp Connexió per a l'exportació**, trieu una connexió de la secció Braze. Si no veieu aquesta secció, no hi ha connexions d'aquest tipus disponibles.  

1. Afegiu un **nom de visualització** per a l'exportació.

1. Afegiu l'identificador de l'API del segment Braze al qual voleu exportar al camp Identificador de **l'API del** segment de braze. Podeu trobar l'identificador als detalls del segment a la plataforma Braze.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. **Al camp Customer ID**, seleccioneu el camp que representa l'identificador de braze del client. És necessari exportar segments a Braze. Podeu triar més camps opcionalment.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights transmetre dades a Braze, permeteu la transferència de dades fora del límit Dynamics 365 Customer Insights de compliment de, incloses dades potencialment sensibles, com ara dades personals. Microsoft transferirà aquestes dades a les vostres instruccions, però sou responsable d'assegurar-vos que Braze compleixi amb qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
