---
title: Exportar segments a Facebook Ads Manager (previsualització) (conté vídeo)
description: Apreneu a configurar la connexió i exportar a Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724568"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exportar segments a Facebook Ads Manager (visualització prèvia)

Exporteu els segments de perfils unificats de client al Facebook Ads Manager per crear campanyes a Facebook i a Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Requisits previs

- Un [Facebook compte d'anuncis](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclogui un [Facebook compte d'empresa](https://business.facebook.com/).
- Privilegis d'administrador al compte d'Anuncis [Facebook](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Els Termes de públic personalitzats han de ser acceptats per l'usuari que configuri la connexió al Customer Insights.

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a 10 milions de perfils de clients per exportació a Facebook Ads Manager poden trigar fins a 90 minuts.
- Només segments.
- Facebook La integració d'anuncis no admet els usuaris amb més de 25 comptes d'anuncis.
- Facebook *tipus de llista* de clients només en [públics personalitzats](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > En alguns casos, és possible que vegeu públics personalitzats de diferents tipus a la llista desplegable. Si seleccioneu un altre tipus que no sigui la llista *de* clients, l'exportació falla.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configuració de la connexió a Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Facebook Gestor d'anuncis**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. [Permeteu que els col·laboradors utilitzin la connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentiqueu-vos a Facebook Ads Manager:

   1. Seleccioneu **Continua amb Facebook** per iniciar la sessió al compte de Facebook Ads.

   1. Activeu el permís **ads_management** un cop us hagueu autenticat amb el Facebook.

   1. Seleccioneu el **compte publicitari de Facebook** que voleu fer servir.

   1. Seleccioneu un **Públic personalitzat existent** de la llista desplegable o creeu un **Públic personalitzat nou**.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. **Al camp Connexió per a l'exportació**, trieu una connexió de la secció Administrador d'anuncis Facebook. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Al camp Connecta dades **, seleccioneu** Correu electrònic **,** Nom i adreça **o** Telèfon **per enviar-los al Gestor d'anuncis**.Facebook

1. Assigneu els atributs corresponents de l'entitat del client unificat per a l'identificador de clau seleccionat.
   > [!TIP]
   > Les millors oportunitats perquè hi hagi una coincidència es produeixen si seleccioneu **Correu electrònic** com a identificador de clau. L'addició d'identificadors addicionals podria millorar la coincidència.

1. Seleccioneu **Afegeix un atribut** per assignar més atributs per enviar-los a Facebook Ads Manager. Els atributs de Facebook Ads Manager s'assignen als noms de text descriptiu següents: **FN** = **Nom**, **LN** = **Cognom**, **FI** = **Primera inicial**, **PHONE** = **Telèfon**, **GEN** = **Gènere**, **DOB** = **Data de naixement**, **ST** = **Estat**, **CT** = **Ciutat**, **ZIP** = **Codi postal**, **COUNTRY** = **País/regió**

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
