---
title: Enriquir els perfils de clients amb HERE Technologies (vista prèvia)
description: Informació general sobre l'enriquiment de tercers de HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237846"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Enriquir els perfils de clients amb HERE Technologies (vista prèvia)

HERE Technologies és una empresa de plataformes d'ubicació que proporciona dades i serveis centrats en la ubicació. Els serveis d'enriquiment de dades de HERE Technologies milloren la precisió de la informació d'ubicació sobre els vostres clients. Proporciona normalització d'adreces, extracció de latitud i longitud, i molt més.

## <a name="prerequisites"></a>Requisits previs

- Una subscripció activa a HERE Technologies. Per obtenir una subscripció, [registreu-vos aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [poseu-vos en contacte directament amb HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Més informació sobre l'enriquiment d'ubicació de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Un administrador configura una [connexió](connections.md)[HERE](#configure-the-connection-for-here-technologies).

## <a name="configure-the-connection-for-here-technologies"></a>Configurar la connexió per a HERE Technologies

Heu de ser [administrador](permissions.md#admin) al Customer Insights i tenir una clau de l'API HERE Technologies activa.

1. Seleccioneu **Afegeix connexió** en configurar un enriquiment o aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la peça HERE Technologies.

1. Introduïu un nom per a la connexió i una clau d'API here technologies vàlida.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Pàgina de configuració de la connexió de HERE Technologies.":::

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la **peça Ubicació** des d'HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Peça de HERE Technologies.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Seleccioneu **Següent**.

1. Seleccioneu el **conjunt** de dades de clients i trieu el perfil o segment que voleu enriquir amb les dades de HERE Technologies. L'entitat *Client* enriqueix tots els teus perfils de client, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Definiu quin tipus de camps dels perfils unificats voleu utilitzar per a la coincidència: l'adreça principal i/o secundària. Podeu especificar una assignació de camps per a ambdues adreces i enriquir els perfils de les dues adreces per separat. Per exemple, per a una adreça de casa i una adreça comercial. Seleccioneu **Següent**.

1. Assigneu els vostres camps a les dades de HERE Technologies. Els camps **Carrer 1** i **Codi postal** són obligatoris per a l'adreça principal o secundària seleccionada. Per obtenir una precisió de coincidència més alta, afegiu més camps.

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un **nom** per a l'enriquiment i el nom de l'entitat **de sortida**.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o tancar per tornar a la **pàgina Enriquiments**.

## <a name="view-enrichment-results"></a>Veure resultats d'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **Nombre de clients enriquits per camp** proporciona un desglossament de la cobertura de cada camp enriquit.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
