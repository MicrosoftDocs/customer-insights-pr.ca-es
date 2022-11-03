---
title: Exportar segments a Mailchimp (versió preliminar)
description: Apreneu a configurar la connexió i exportar a Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d74672768afec94e899ff0aec8c118c2afcde368
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725020"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportar segments a Mailchimp (versió preliminar)

Exporteu segments de perfils de client unificats a Mailchimp per crear butlletins i campanyes de correu electrònic.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://mailchimp.com/) de Mailchimp i les credencials d'administrador corresponents.
- [Públics existents a Mailchimp](https://mailchimp.com/help/create-audience/) i identificadors de públic [corresponents](https://mailchimp.com/help/find-audience-id/).
- [Segments configurats](segments.md).
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- No s'admet l'enllaç privat en combinació amb Bring your own storage (BYOS).
- Fins a 1 milió de perfils de clients per exportació a Mailchimp, que poden trigar fins a tres hores. El nombre de perfils de clients que podeu exportar a Mailchimp depèn del vostre contracte amb Mailchimp.
- Només segments.

## <a name="set-up-connection-to-mailchimp"></a>Configuració de la connexió a Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Mailchimp**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Autentica amb el Mailchimp** i indiqueu les vostres credencials de Mailchimp.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Mailchimp. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Introduïu el vostre **identificador** de públic de Mailchimp.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client.

1. Opcionalment, exporteu **nom** i **cognom** per crear correus electrònics més personalitzats. Seleccioneu **Afegeix un atribut** per assignar aquests camps.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
