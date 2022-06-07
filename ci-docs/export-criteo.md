---
title: Exporta les dades del Customer Insights a Criteo
description: Apreneu a configurar la connexió i exportar-la a Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 854f5f0c53f053fc5d742d69a045db1926fec00c
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808786"
---
# <a name="export-segments-to-criteo-preview"></a>Exporta segments a Criteo (previsualització)

Exportar segments de perfils de clients unificats per generar campanyes, proporcionar màrqueting per correu electrònic i utilitzar grups específics de clients amb Criteo.

## <a name="prerequisites-for-connection"></a>Requisits previs per a la connexió

-   Teniu un [compte](https://www.criteo.com/login/) de Criteo Dynamics Retargeting i les credencials d'administrador corresponents.
-   Teniu [segments configurats](segments.md).
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 1 milió de perfils de clients per exportació a Criteo.
- L'exportació a Criteo es limita a segments.
- L'exportació de segments amb un total de 1 milions de perfils de client pot trigar fins a 30 minuts. 
- El nombre de perfils de clients que pots exportar a Criteo depèn i es limita al teu contracte amb Criteo.

## <a name="set-up-connection-to-criteo"></a>Configura la connexió a Criteo

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Criteo** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccioneu **Accepto** confirmar la privadesa i el **compliment** de les dades i seleccioneu **Connecta't** per inicialitzar la connexió a Criteo.

1. Seleccioneu **AUTENTICA amb Criteo** i proporcioneu el vostre nom d'usuari i credencials d'administrador per a Criteo. 

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. **Al camp Connexió per a l'exportació**, trieu una connexió de la secció Criteo. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible. 

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. 

1. Opcionalment, podeu exportar l'identificador **i** el nom de l'anunciant **·**

1. Seleccioneu els segments que voleu exportar. 

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights transmetre dades a Criteo, permeteu la transferència de dades fora del límit Dynamics 365 Customer Insights de compliment de, incloses dades potencialment sensibles, com ara dades personals. Microsoft transferirà aquestes dades a les vostres instruccions, però sou responsable d'assegurar-vos que Criteo compleixi amb qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](includes/footer-banner.md)]
