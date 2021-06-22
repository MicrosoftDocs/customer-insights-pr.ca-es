---
title: Exportar dades del Customer Insights al Microsoft Advertising
description: Apreneu a configurar la connexió i exportar al Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124456"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportar segments al Microsoft Advertising (versió preliminar)

Exporteu els segments del Customer Insights al Microsoft Advertising per crear públics del Customer Match. Utilitzeu aquests públics per a les campanyes publicitàries.

## <a name="prerequisites"></a>Requisits previs

-   Un [compte del Microsoft Advertising](https://ads.microsoft.com/) i les credencials d'administrador corresponents.
-   Heu acceptat les condicions d'ús del Customer Match. 
-   [Segments configurats](segments.md) als coneixements del públic.
-   Els perfils de client unificats als segments exportats contenen un camp amb una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Podeu exportar fins a 500 000 perfils per exportació al Microsoft Advertising.
- L'exportació al Microsoft Advertising es limita als segments.
- L'exportació de fins a 500 000 perfils al Microsoft Advertising pot trigar fins a 10 minuts com a màxim. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Configurar la connexió amb el Microsoft Advertising

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Microsoft Advertising** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte són els administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió al Microsoft Advertising.

1. Seleccioneu **Autentica amb el Microsoft Advertising** i proporcioneu les vostres credencials d'administració per al Microsoft Advertising.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció del Microsoft Advertising. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Seleccioneu els segments que voleu exportar. Els públics del Customer Match al Microsoft Advertising es creen automàticament amb el nom dels segments seleccionats per a l'exportació. Cada segment serà un públic diferent al Customer Match. 

1. Introduïu **l'identificador de client i l'identificador de compte de Microsoft Advertising**. Podeu trobar l'identificador de client (`cid`) i l'identificador de compte (`aid`) als paràmetres de l'adreça URL quan inicieu la sessió al Microsoft Advertising.

1. A la secció **Coincidències de dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat amb l'adreça electrònica d'un client. Cal que exporteu segments al Microsoft Advertising.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan permeteu al Dynamics 365 Customer Insights transmetre dades al Microsoft Advertising, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals. Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que el Microsoft Advertising compleixi les obligacions de privadesa o de seguretat que pugueu teniu. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per aturar l'ús d'aquesta funcionalitat.
