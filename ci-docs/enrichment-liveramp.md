---
title: Enriquiment de dades d'identitat LiveRamp
description: Enriqueix els perfils dels clients amb dades de LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e8a130865267b57c89157b44be3d4bba3dc2fb4e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953983"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enriquir els perfils dels clients amb dades d'identitat de LiveRamp (previsualització)

LiveRamp proporciona una resolució d'identitat fora de línia determinista i la consolidació de les dades dels clients. Podeu assignar identificadors personals a les vostres dades de client al gràfic d'identitat d'AbiliTec i rebre identificadors d'AbiliTec. A continuació, podeu utilitzar aquests identificadors per a una millor unificació de les dades dels clients.

## <a name="supported-countriesregions"></a>Països o regions admesos

Actualment admetem perfils de clients enriquidors només amb dades de LiveRamp als Estats Units.

## <a name="prerequisites"></a>Requisits previs

- Una subscripció activa a LiveRamp. Per obtenir una subscripció, poseu-vos en contacte amb l'equip del compte liveramp o per [dynamics@liveramp.com](mailto:dynamics@liveramp.com) obtenir més informació.

- Una subscripció activa d'AbiliTec amb un identificador de client i secret per accedir a l'API. Per obtenir més informació, vegeu [El centre de desenvolupadors de l'API d'AbiliTec](https://developers.liveramp.com/abilitec-api/).

- Un administrador configura [una connexió](connections.md)[LiveRamp](#configure-the-connection-for-liveramp).

## <a name="configure-the-connection-for-liveramp"></a>Configura la connexió per a LiveRamp

Heu de ser administrador [del](permissions.md#admin) Customer Insights i tenir un identificador i un secret de client liveRamp actiu.

1. Seleccioneu **Afegeix una connexió** en configurar un enriquiment, o aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la peça LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Subfinestra de configuració per configurar la connexió al servei LiveRamp AbiliTec.":::

1. Introduïu un nom per a la connexió i un identificador de client liveRamp vàlid i un secret.

1. Reviseu i proporcioneu el vostre consentiment per a la [Privadesa de les dades i conformitat](#data-privacy-and-compliance) seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

### <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights transmetre dades a LiveRamp, permeteu la transferència de dades fora del límit de compliment de Dynamics 365 Customer Insights, incloses dades potencialment sensibles, com ara dades personals. Microsoft transferirà aquestes dades a les instruccions, però sou responsable d'assegurar-vos que LiveRamp compleixi amb qualsevol obligació de privadesa o de seguretat que pugueu tenir. Per obtenir més informació, consulteu la [Declaració](https://go.microsoft.com/fwlink/?linkid=396732) de privadesa de Microsoft. L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la **peça Identitat** de LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Mosaic d'identitat a la pàgina visió general d'enriquiment.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió. Poseu-vos en contacte amb un administrador si no n'hi ha cap disponible.

1. Seleccioneu **Següent**.

1. Seleccioneu el **conjunt** de dades del client i trieu el perfil o segment que voleu enriquir amb les dades d'identitat de LiveRamp. L'entitat *Client* enriqueix tots els vostres perfils de clients, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Definiu quin tipus de camps dels perfils unificats s'utilitzaran per fer coincidir les dades d'identitat de LiveRamp. Cal com a mínim un dels camps **Nom i adreça**, **correu electrònic** o **Telèfon**. Per obtenir una precisió més alta de la coincidència, afegiu altres camps. Seleccioneu **Següent**.

1. Assigneu els camps a les dades d'identificació de LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opcions d'assignació de dades per a l'enriquiment liveRamp.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un **nom** per a l'enriquiment i el nom **de l'entitat** Sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o a prop per tornar a la **pàgina Enriquiments**.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **nombre de clients enriquits per camp** proporciona una desglossament en la cobertura de cada camp enriquit.

## <a name="next-steps"></a>Passos següents

Construïu a partir de les dades de clients enriquits. Utilitzeu els identificadors d'AbiliTec per consolidar perfils de clients en una visualització basada en persones.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
