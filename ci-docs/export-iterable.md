---
title: Exporta segments a Iterable (previsualització)
description: Obteniu informació sobre com configurar la connexió i exportar-la a Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 98d5aeab6b0e932d291213053d509ec72da82e47
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052223"
---
# <a name="export-segments-to-iterable-preview"></a>Exporta segments a Iterable (previsualització)

Exporteu segments de perfils de clients unificats a Iterable i utilitzeu-los per a activitats de màrqueting.

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte](https://iterable.com/) iterable i les credencials d'administrador corresponents.
-   Heu [configurat segments](segments.md) a Customer Insights.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- L'exportació a Iterable es limita a segments.
- Exportar fins a 1 milió de perfils de clients a Iterable pot trigar fins a 30 minuts a completar-se. 
- El nombre de perfils de clients que podeu exportar a Iterable depèn i es limita al vostre contracte amb Iterable.

## <a name="set-up-connection-to-iterable"></a>Configura la connexió a Iterable

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Iterable** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcioneu la clau [de l'API](https://support.iterable.com/hc/en-us/articles/360043464871) iterable per continuar iniciant la sessió. 

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a l'Iterable.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. **Al camp Connexió per a l'exportació**, trieu una connexió de la secció Iterable. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

3. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. Cal exportar segments a Iterable.La llista creada a Iterable rebrà exactament el mateix nom que el nom del segment a Dynamics 365 Customer Insights.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights transmetre dades a Iterable, permeteu la transferència de dades fora del límit Dynamics 365 Customer Insights de compliment de, incloses dades potencialment sensibles, com ara dades personals. Microsoft transferirà aquestes dades a les vostres instruccions, però sou responsable d'assegurar-vos que Iterable compleixi amb qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
