---
title: Exportar segments a Marketo (versió preliminar)
description: Apreneu a configurar la connexió i exportar a Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724928"
---
# <a name="export-segments-to-marketo-preview"></a>Exportar segments a Marketo (versió preliminar)

Exporteu segments de perfils de client unificats per generar campanyes, proporcionar màrqueting per correu electrònic i utilitzar grups específics de clients amb Marketo.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://login.marketo.com/) de Marketo i les credencials d'administrador corresponents.
- Un [identificador de client de Marketo, secret del client i nom d'amfitrió del punt final REST](https://developers.marketo.com/rest-api/authentication/).
- [Llistes existents en Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) i els identificadors corresponents.
- [Segments configurats](segments.md).
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- No s'admet l'enllaç privat en combinació amb Bring your own storage (BYOS).
- Fins a 1 milió de perfils de clients per exportació a Marketo, que poden trigar fins a 3 hores. El nombre de perfils de clients que pots exportar a Marketo depèn del teu contracte amb Marketo.
- Només segments.

## <a name="set-up-connection-to-marketo"></a>Configuració de la connexió a Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Marketo**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el vostre **identificador de client de Marketo, el secret del client i el nom** d'amfitrió del punt final REST. El nom d'amfitrió de l'extrem REST és només el nom d'amfitrió, sense https://. Exemple: xyz-abc-123.mktorest.com.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Marketo. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Introduïu el vostre **identificador de llista** de Marketo. L'identificador de llista és un valor purament numèric. Per exemple, si el vostre identificador de llista de Marketo és ST12345A7, traieu el caràcter abans i després dels números i introduïu *12345*.

1. A la **secció Coincidència** de dades, seleccioneu almenys un camp que representi l'adreça electrònica d'un client o l'identificador de Marketo d'un client.

1. Opcionalment, exporteu **nom**, **cognom**, **ciutat**, **estat** i **país/regió** per crear correus electrònics més personalitzats. Seleccioneu **Afegeix un atribut** per assignar aquests camps.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

A Marketo, cerqueu els vostres segments a [llistes](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) de Marketo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
