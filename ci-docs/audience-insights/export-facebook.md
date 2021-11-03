---
title: Exportar dades del Customer Insights a l'Administrador d'anuncis del Facebook
description: Apreneu a configurar la connexió i exportar a Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bb74e35799410b92b64e48e065b45efda82490ca
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/22/2021
ms.locfileid: "7672941"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Exportar una llista de segments a Facebook Ads Manager (versió preliminar)

Exporteu els segments de perfils unificats de client al Facebook Ads Manager per crear campanyes a Facebook i a Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Requisits previs per a la connexió

- Heu de tenir un [**compte de Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclogui un [**compte empresarial de Facebook**](https://business.facebook.com/)
- Heu de ser un administrador al [**compte de Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 10 milions de perfils de client per exportació a Facebook Ads Manager.
- L'exportació a Facebook Ads Manager es limita als segments.
- Creeu o actualitzeu públics personalitzats a Facebook només del tipus *llista de clients*.
- L'exportació de segments amb un total de 10 milions de perfils de client pot trigar fins a 90 minuts a completar-se.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configuració de la connexió a Facebook Ads Manager

Per poder crear una exportació, abans un administrador ha de configurar la connexió amb el servei i permetre que els usuaris utilitzin la connexió.

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Facebook Ads Manager** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentiqueu-vos a Facebook Ads Manager: 

   1. Seleccioneu **Continua amb Facebook** per iniciar la sessió al compte de Facebook Ads.

   1. Activeu el permís **ads_management** un cop us hagueu autenticat amb el Facebook.

   1. Seleccioneu el **compte publicitari de Facebook** que voleu fer servir.

   1. Seleccioneu un **Públic personalitzat existent** de la llista desplegable o creeu un **Públic personalitzat nou**. Per obtenir més informació, vegeu [**Públics al Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Només podeu crear o actualitzar públics personalitzats a Facebook del tipus *llista de clients* amb aquesta exportació. En alguns casos, a la llista desplegable veureu públics personalitzats de diferents tipus. Seleccionar un tipus diferent de *llista de clients* tindrà com a resultat una exportació fallada. 

1. Reviseu la **Privadesa de les dades i el compliment** i, a continuació, seleccioneu **Accepto**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**. 

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció **Facebook Ads Manager**. Si no veieu aquest nom de secció, no hi ha disponible cap connexió d'aquest tipus.

1. Al camp **Trieu el vostre identificador de clau**, seleccioneu **Correu electrònic**, **Nom i adreça** o **Telèfon** per enviar al Facebook Ads Manager. 

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**.

1. Assigneu els atributs corresponents de l'entitat del client unificat per a l'identificador de clau seleccionat.
   > [!TIP]
   > Les millors oportunitats perquè hi hagi una coincidència es produeixen si seleccioneu **Correu electrònic** com a identificador de clau. L'addició d'identificadors addicionals podria millorar la coincidència.

1. Seleccioneu **Afegeix un atribut** per assignar més atributs per enviar-los a Facebook Ads Manager. Els atributs de Facebook Ads Manager s'assignen als noms de text descriptiu següents: **FN** = **Nom**, **LN** = **Cognom**, **FI** = **Primera inicial**, **PHONE** = **Telèfon**, **GEN** = **Gènere**, **DOB** = **Data de naixement**, **ST** = **Estat**, **CT** = **Ciutat**, **ZIP** = **Codi postal**, **COUNTRY** = **País/regió**

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). 

També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a l'Administrador d'anuncis del Facebook, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Facebook Ads compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
