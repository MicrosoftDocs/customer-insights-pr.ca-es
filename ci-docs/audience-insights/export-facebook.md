---
title: Exportar dades del Customer Insights a l'Administrador d'anuncis del Facebook
description: Més informació sobre com configurar la connexió al Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596664"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Connector per al Facebook Ads Manager (versió preliminar)

Exporteu els segments de perfils unificats de client al Facebook Ads Manager per crear campanyes a Facebook i a Instagram.

## <a name="prerequisites"></a>Requisits previs

- Heu de tenir un [**compte publicitari de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclogui un [**compte empresarial de Facebook**](https://business.facebook.com/).
- Heu de ser un administrador del [**compte publicitari de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Connectar-se al Facebook Ads Manager

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A **Facebook Ads Manager**, seleccioneu **Configura**.

1. Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.

1. Seleccioneu **Continua amb Facebook** per iniciar la sessió al vostre compte publicitari de Facebook.

1. Activeu el permís **ads_management** un cop us hagueu autenticat amb el Facebook.

1. Seleccioneu el **compte publicitari de Facebook** que voleu fer servir.

1. Seleccioneu un **Públic personalitzat existent** de la llista desplegable o creeu un **Nou públic personalitzat**. Per obtenir més informació, vegeu [**Públics al Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Següent** per configurar l'exportació.

## <a name="configure-the-connector"></a>Configurar el connector

1. Al camp **Trieu el vostre identificador de clau**, seleccioneu **Correu electrònic**, **Nom i adreça** o **Telèfon** per enviar al Facebook Ads Manager.

1. Assigneu els atributs corresponents de l'entitat del client unificat per a l'identificador de clau seleccionat.
   > [CONSELL] Les millors oportunitats perquè hi hagi una coincidència es produeixen si seleccioneu **Correu electrònic** com a identificador de clau. L'addició d'identificadors addicionals podria millorar la coincidència.

1. Seleccioneu **Afegeix un atribut** per assignar atributs addicionals per enviar al Facebook Ads Manager. Els atributs del Facebook Ads Manager s'assignen als noms amigables següents: **FN** = **Nom**, **LN** = **Cognom**, **FI** = **Primera inicial**, **PHONE** = **Telèfon**, **GEN** = **Gènere**, **DOB** = **Data de naixement**, **ST** = **Estat**, **CT** = **Ciutat**, **ZIP** = **Codi postal**, **COUNTRY** = **País/regió**

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 10 milions de perfils de client per exportació a l'Administrador d'anuncis de Facebook 
- L'exportació a l'Administrador d'anuncis de Facebook es limita als segments
- L'exportació de segments amb un total de 10 milions de perfils pot tardar fins a 90 minuts a completar-se

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a l'Administrador d'anuncis del Facebook, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Facebook Ads compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]