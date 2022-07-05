---
title: Exportar segments a Sendinblue (versió preliminar)
description: Més informació sobre com configurar la connexió i l'exportació a Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f6550b5c57866702631b4c294bb059279461bd6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083074"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportar segments a Sendinblue (versió preliminar)

Exporteu els segments de perfils de client unificats per generar campanyes, proporcionar contingut de màrqueting per correu electrònic i utilitzar grups específics de clients amb Sendinblue.

## <a name="prerequisites-for-connection"></a>Requisits previs per a la connexió

-   Teniu un [compte de Sendinblue](https://www.sendinblue.com/) i les credencials d'administrador corresponents.
-   Hi ha llistes existents a Sendinblue i els ID corresponents.
-   Teniu [segments configurats](segments.md).
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 1 milió de perfils de client per exportar a Sendinblue.
- L'exportació a Sendinblue es limita als segments.
- L'exportació de segments amb un total de 1 milions de perfils de client pot trigar fins a 90 minuts. 
- El nombre de perfils de client que podeu exportar a Sendinblue depèn del vostre contracte amb Sendinblue i pot estar limitat.

## <a name="set-up-connection-to-sendinblue"></a>Configuració de la connexió a Sendinblue

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Sendinblue** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu la **[clau de l'API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Seleccioneu **Accepta** per confirmar la **Privadesa de les dades i conformitat** i seleccioneu **Connecta** per inicialitzar la connexió a Sendinblue.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Sendinblue. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Introduïu l'**ID de llista de SendinBlue**. 

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. 

1. Opcionalment, podeu exportar el **nom**, **cognom** i **telèfon** per crear correus electrònics més personalitzats. Seleccioneu **Afegeix un atribut** per assignar aquests camps.

1. Seleccioneu els segments que voleu exportar. 

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan permeteu que el Dynamics 365 Customer Insights transmeti dades a Sendinblue, permeteu la transferència de dades fora del límit de conformitat per al Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals. Microsoft transferirà aquestes dades segons la vostra instrucció, però sou responsable d'assegurar que Sendinblue compleixi les obligacions de privadesa o seguretat que tingueu. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE [footer-include](includes/footer-banner.md)]
