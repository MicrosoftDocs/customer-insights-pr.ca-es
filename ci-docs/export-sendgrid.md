---
title: Exportar segments a SendGrid (versió preliminar)
description: Apreneu a configurar la connexió i exportar a SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724836"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportar segments a SendGrid (versió preliminar)

Exporteu segments de perfils de client unificats a les llistes de contactes de SendGrid i utilitzeu-los per a les campanyes i el màrqueting per correu electrònic a SendGrid.

## <a name="prerequisites"></a>Requisits previs

- Un [compte](https://sendgrid.com/) SendGrid i les credencials d'administrador corresponents.
- [Llistes de contactes existents a SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) i els identificadors corresponents.
- Una [clau de l'API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segments configurats](segments.md) al Customer Insights.
- Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- No s'admet l'enllaç privat en combinació amb Bring your own storage (BYOS).
- Fins a 100,000 perfils de clients en total a SendGrid, que pot trigar fins a unes hores a completar-se. El nombre de perfils de client que podeu exportar a SendGrid depèn del vostre contracte amb SendGrid.
- Només segments.

## <a name="set-up-connection-to-sendgrid"></a>Configuració de la connexió a SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **SendGrid**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu la clau **de l'API** SendGrid.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Connecta** per inicialitzar la connexió.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció SendGrid. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Introduïu l'identificador **de la** llista SendGrid.

1. A la secció **Coincidència de dades**, al camp **Correu electrònic**, seleccioneu el camp que representa l'adreça electrònica d'un client.

1. Opcionalment, seleccioneu camps com **ara nom**, **cognom**, **País/Regió**, **Estat**, **Ciutat** i **Codi postal**.

1. Seleccioneu els segments que voleu exportar seguint les limitacions conegudes.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
