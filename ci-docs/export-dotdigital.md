---
title: Exportar segments a DotDigital (versió preliminar)
description: Apreneu a configurar la connexió i exportar a DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724974"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportar segments a DotDigital (versió preliminar)

Exporteu els segments de perfils de client unificats a llibretes d'adreces de DotDigital i utilitzeu-los per a les campanyes, el màrqueting per correu electrònic i per crear segments de clients amb DotDigital.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://dotdigital.com/) DotDigital i un usuari de [l'API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Un identificador DotDigital d'una llibreta [d'adreces nova](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) o existent a DotDigital. L'identificador es troba a l'adreça URL quan seleccioneu i obriu una llibreta d'adreces.
- [Segments configurats](segments.md) al Customer Insights.
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- No s'admet l'enllaç privat en combinació amb Bring your own storage (BYOS).
- Fins a 1 milió de perfils de clients per exportació a DotDigital, que poden trigar fins a tres hores a completar-se a causa de les limitacions del proveïdor. El nombre de perfils de clients que podeu exportar a DotDigital depèn del vostre contracte amb DotDigital.
- Només segments.

## <a name="set-up-connection-to-dotdigital"></a>Configuració de la connexió a DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **DotDigital**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el **nom d'usuari i la contrasenya de l'API de DotDigital**.

1. Introduïu l'identificador **de la** llibreta d'adreces DotDigital.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció DotDigital. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client.

1. Opcionalment, exporta **nom**, **cognom**, **nom** complet, **sexe** i **codi postal**.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

A DotDigital, cerqueu els vostres segments a les llibretes [d'adreces](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) DotDigital.

[!INCLUDE [footer-include](includes/footer-banner.md)]
