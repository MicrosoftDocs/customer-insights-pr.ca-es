---
title: Exportar dades del Customer Insights a DotDigital
description: Apreneu a configurar la connexió i exportar a DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e3a79603f9f5746ee176d3d4299a30510c7459e
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618371"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportar segments a DotDigital (versió preliminar)

Exporteu els segments de perfils de client unificats a llibretes d'adreces de DotDigital i utilitzeu-los per a les campanyes, el màrqueting per correu electrònic i per crear segments de clients amb DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Requisits previs per a una connexió

-   Teniu un [compte de DotDigital](https://dotdigital.com/) i heu creat un [usuari de l'API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Necessitareu utilitzar les credencials d'usuari de l'API per crear una connexió
-   Hi ha llibretes d'adreces a DotDigital amb els identificadors corresponents. L'identificador es troba a l'adreça URL quan seleccioneu i obriu una llibreta d'adreces. Per obtenir més informació, vegeu [Llibretes d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Teniu [segments configurats](segments.md) a les conclusions del públic.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 1 milió de perfils de client per exportar a DotDigital.
- L'exportació a DotDigital es limita als segments.
- L'exportació de segments amb un total d'1 milió de perfils de client pot trigar fins a 3 hores a causa de les limitacions del proveïdor. 
- El nombre de perfils de client que podeu exportar a DotDigital depèn del vostre contracte amb DotDigital i pot estar limitat.

## <a name="set-up-connection-to-dotdigital"></a>Configuració de la connexió a DotDigital

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **DotDigital** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el **nom d'usuari i la contrasenya de l'API de DotDigital**. 

1. Introduïu l'**[identificador de la llibreta d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a DotDigital.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió. 

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció DotDigital. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.


1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client. Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom**, el **Cognom**, el **Nom complet**, el **Sexe** i el **Codi postal**.

1. Seleccioneu els segments que voleu exportar. Podeu exportar fins a un total d'un milió de perfils de client a DotDigital.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 
 
A DotDigital, ara podeu cercar els vostres segments a les [llibretes d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a DotDigital, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que DotDigital compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
