---
title: Exportar dades del Customer Insights a DotDigital
description: Apreneu a configurar la connexió a DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644436"
---
# <a name="connector-for-dotdigital-preview"></a>Connector per a DotDigital (versió preliminar)

Exporteu els segments de perfils de client unificats a llibretes d'adreces de DotDigital i utilitzeu-los per a les campanyes, el màrqueting per correu electrònic i per crear segments de clients amb DotDigital. 

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte de DotDigital](https://dotdigital.com/) i les credencials d'administrador corresponents.
-   Hi ha llibretes d'adreces a DotDigital amb els identificadors corresponents. L'identificador es troba a l'adreça URL quan seleccioneu i obriu una llibreta d'adreces. Per obtenir més informació, vegeu [Llibretes d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Teniu [segments configurats](segments.md) a les conclusions del públic.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="connect-to-dotdigital"></a>Connectar-se a DotDigital

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A **DotDigital**, seleccioneu **Configura**.

1. Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Subfinestra de configuració de l'exportació a DotDigital.":::

1. Introduïu el **nom d'usuari i la contrasenya de DotDigital**.

1. Introduïu l'**[identificador de la llibreta d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a DotDigital.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Següent** per configurar l'exportació.

## <a name="configure-the-connector"></a>Configurar el connector

1. A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client. Repetiu els mateixos passos per a altres camps opcionals com ara el **Nom**, el **Cognom**, el **Nom complet**, el **Sexe** i el **Codi postal**.

1. Seleccioneu els segments que voleu exportar. Podeu exportar fins a un total d'un milió de perfils de client a DotDigital.

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab). A DotDigital, ara podeu cercar els vostres segments a les [llibretes d'adreces de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a un milió de perfils per exportació a DotDigital.
- L'exportació a DotDigital es limita als segments.
- L'exportació de segments amb un total d'un milió de perfils pot durar fins a 3 hores a causa de les possibles limitacions del proveïdor. 
- El nombre de perfils que podeu exportar a DotDigital és limitat i dependrà del contracte que tingueu amb DotDigital.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a DotDigital, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que DotDigital compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
