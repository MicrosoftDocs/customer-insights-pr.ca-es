---
title: Exportar dades del Customer Insights a Snapchat
description: Apreneu a configurar la connexió i exportar a Snapchat.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 171b8bf0f4a034c78e872b671602ae7653271da7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642364"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportar segments a Snapchat (versió preliminar)

Exporteu segments de perfils de client unificats a Snapchat i utilitzeu-los per a la publicitat. 

## <a name="prerequisites-for-a-connection"></a>Requisits previs per a una connexió

-   Teniu un [compte d'empresa de Snapchat](https://business.snapchat.com/), un [compte d'anuncis de Snapchat](https://ads.snapchat.com/) i les credencials d'administrador corresponents.
-   Heu [configurat segments](segments.md) a Customer Insights.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- L'exportació a Snapchat es limita als segments.
- L'exportació de fins a 1 milió de perfils de client a Snapchat pot trigar fins a 15 minuts a completar-se. 

## <a name="set-up-connection-to-snapchat"></a>Configuració de la connexió a Snapchat

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Snapchat** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a Snapchat.

1. Seleccioneu **Autentica amb Snapchat** i proporcioneu les vostres credencials d'administració per a Snapchat. 

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Snapchat. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Introduïu l'[**Identificador de públic de Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. Cal que exporteu segments a Snapchat.

1. Seleccioneu els segments que voleu exportar. 

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan permeteu al Dynamics 365 Customer Insights transmetre dades a Snapchat, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals. Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que Snapchat compleixi les obligacions de privadesa o de seguretat que pugueu teniu. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
