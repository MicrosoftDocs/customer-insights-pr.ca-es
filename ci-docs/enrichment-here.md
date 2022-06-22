---
title: Enriquiment amb l'enriquiment de tercers de HERE Technologies
description: Informació general sobre l'enriquiment de tercers de HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 171ead92427924083a13e2a3d52e7a7da417c801
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953661"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquiment de perfils de client amb HERE Technologies (versió preliminar)

HERE Technologies és una empresa de plataformes d'ubicació que proporciona dades i serveis centrats en la ubicació. Els serveis d'enriquiment de dades d'HERE Technologies milloren la precisió de la informació d'ubicació sobre els vostres clients. Proporciona normalització d'adreces, extracció de latitud i longitud, i molt més.

## <a name="prerequisites"></a>Requisits previs

- Una subscripció activa a HERE Technologies. Per obtenir una subscripció, [inscriviu-vos aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [poseu-vos en contacte directament amb HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Més informació sobre l'enriquiment d'ubicació de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Un administrador ha configurat [una connexió](connections.md)[AQUÍ](#configure-the-connection-for-here-technologies).

## <a name="configure-the-connection-for-here-technologies"></a>Configurar la connexió per a HERE Technologies

Heu de ser administrador [del](permissions.md#admin) Customer Insights i tenir una clau d'API HERE Technologies activa.

1. Seleccioneu **Afegeix una connexió** en configurar un enriquiment o aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la peça HERE Technologies.

1. Introduïu un nom per a la connexió i una clau d'API HERE Technologies vàlida.

1. Reviseu i proporcioneu el vostre consentiment per a la [Privadesa de les dades i conformitat](#data-privacy-and-compliance) seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Pàgina de configuració de la connexió de HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a HERE Technologies, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que HERE Technologies compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la ubicació **de la** peça HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Peça de HERE Technologies.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió. Poseu-vos en contacte amb un administrador si no n'hi ha cap disponible.

1. Seleccioneu **Següent**.

1. Seleccioneu el **conjunt de dades del client** i trieu el perfil o segment que voleu enriquir amb les dades de HERE Technologies. L'entitat *Client* enriqueix tots els vostres perfils de clients, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Definiu quin tipus de camps dels perfils unificats s'utilitzaran per fer coincidir: l'adreça principal i/o secundària. Podeu especificar una assignació de camps per a ambdues adreces i enriquir els perfils de les dues adreces per separat. Per exemple, per a una adreça de casa i una adreça de l'empresa. Seleccioneu **Següent**.

1. Assigneu els vostres camps a les dades d'HERE Technologies. Els camps **Carrer 1** i **Codi postal** són obligatoris per a l'adreça principal o secundària seleccionada. Per obtenir una precisió de concordança més alta, afegiu més camps.

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un **nom** per a l'enriquiment i el nom **de l'entitat** Sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o a prop per tornar a la **pàgina Enriquiments**.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **nombre de clients enriquits per camp** proporciona una desglossament en la cobertura de cada camp enriquit.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
