---
title: Exportar segments a Constant Contact (versió preliminar)
description: Apreneu a configurar la connexió i exportar a Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c0affd3ed45f462696850813bd50331061dde780
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724489"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportar segments a Constant Contact (versió preliminar)

Exporteu segments de perfils de client unificats a Constant Contact i utilitzeu-los per a activitats de màrqueting.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://www.constantcontact.com/account-home) de contacte constant i les credencials d'administrador corresponents.
- Un identificador [de llista de contactes constant](https://app.constantcontact.com/pages/contacts/ui#lists). Obriu una llista a Constant Contact per trobar l'identificador de llista a l'adreça URL.
- [Segments configurats](segments.md) al Customer Insights.
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- No s'admet l'enllaç privat en combinació amb Bring your own storage (BYOS).
- Fins a 1 milió de perfils de clients per exportació a Constant Contact, que poden trigar fins a una hora a completar-se. El nombre de perfils de clients que podeu exportar a Constant Contact depèn del vostre contracte amb Constant Contact.
- Només segments.

## <a name="set-up-connection-to-constant-contact"></a>Configuració de la connexió a Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Contacte constant**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Autentica amb Constant Contact** i proporcioneu les vostres credencials d'administrador per al Constant Contact.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Constant Contact. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Introduïu l'identificador **de la llista de contactes constants**.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client.

1. Opcionalment, exporteu **nom** i **cognom** com a camps addicionals per crear correus electrònics més personalitzats. Seleccioneu **Afegeix un atribut** per assignar aquests camps.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
