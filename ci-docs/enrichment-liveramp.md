---
title: Enriquir perfils de clients amb dades d'identitat de LiveRamp (visualització prèvia)
description: Enriquir perfils de clients amb dades de LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196336"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enriquir perfils de clients amb dades d'identitat de LiveRamp (visualització prèvia)

LiveRamp proporciona resolució determinista d'identitat fora de línia i consolidació de dades de clients. Podeu assignar els identificadors personals de les dades dels vostres clients al gràfic d'identitat d'AbiliTec i rebre els identificadors d'AbiliTec. A continuació, podeu utilitzar aquests identificadors per a una millor unificació de les dades dels vostres clients.

## <a name="supported-countriesregions"></a>Països o regions admesos

Actualment admetem perfils de clients enriquidors només amb dades de LiveRamp als Estats Units.

## <a name="prerequisites"></a>Requisits previs

- Una subscripció activa al LiveRamp. Per obtenir una subscripció, poseu-vos en contacte amb l'equip del vostre compte liveRamp o per obtenir [dynamics@liveramp.com](mailto:dynamics@liveramp.com) més informació.

- Una subscripció AbiliTec activa amb un identificador de client i secret per accedir a l'API. Per obtenir més informació, vegeu [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/).

- Un administrador configura una [connexió](connections.md)[LiveRamp](#configure-the-connection-for-liveramp).

## <a name="configure-the-connection-for-liveramp"></a>Configuració de la connexió per al LiveRamp

Heu de ser [administrador](permissions.md#admin) al Customer Insights i tenir un identificador de client i un secret actius del LiveRamp.

1. Seleccioneu **Afegeix connexió** en configurar un enriquiment o aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la peça LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Panell de configuració per configurar la connexió al servei LiveRamp AbiliTec.":::

1. Introduïu un nom per a la connexió i un identificador de client de LiveRamp vàlid i un secret.

1. Reviseu i proporcioneu el vostre consentiment per a la [Privadesa de les dades i conformitat](#data-privacy-and-compliance) seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

### <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights transmetre dades a LiveRamp, permeteu la transferència de dades fora del límit de compliment, Dynamics 365 Customer Insights incloses les dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons les vostres instruccions, però sou responsable de garantir que el LiveRamp compleixi les obligacions de privadesa o seguretat que pugueu tenir. Per obtenir més informació, consulteu la [Declaració](https://go.microsoft.com/fwlink/?linkid=396732) de privadesa de Microsoft. L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la **peça Identitat** del LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Rajola d'identitat a la pàgina de visió general de l'enriquiment.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Seleccioneu **Següent**.

1. Seleccioneu el **conjunt** de dades de clients i trieu el perfil o segment que voleu enriquir amb dades d'identitat del LiveRamp. L'entitat *Client* enriqueix tots els teus perfils de client, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Definiu quin tipus de camps dels perfils unificats voleu utilitzar per fer coincidir les dades d'identitat del LiveRamp. Es requereix almenys un dels camps **Nom i adreça**, **Correu electrònic** o **Telèfon**. Per obtenir una precisió de coincidència més alta, afegiu altres camps. Seleccioneu **Següent**.

1. Assigneu els vostres camps a les dades d'identificació del LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opcions d'assignació de dades per a l'enriquiment de LiveRamp.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un **nom** per a l'enriquiment i el nom de l'entitat **de sortida**.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o tancar per tornar a la **pàgina Enriquiments**.

## <a name="view-enrichment-results"></a>Veure resultats d'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **Nombre de clients enriquits per camp** proporciona un desglossament de la cobertura de cada camp enriquit.

## <a name="next-steps"></a>Passos següents

Construïu a partir de les dades de clients enriquits. Utilitzeu els identificadors AbiliTec per consolidar els perfils de client en una visualització basada en persones.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
