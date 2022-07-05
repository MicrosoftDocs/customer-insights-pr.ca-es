---
title: Enriquir els perfils de client amb dades demogràfiques d'Experian (versió preliminar)
description: Informació general sobre l'enriquiment de tercers d'Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053009"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquir els perfils de client amb dades demogràfiques d'Experian (versió preliminar)

Experian és un líder global en informes de crèdit d'empreses i consumidors i serveis de màrqueting. Amb els serveis d'enriquiment de dades dels clients d'Experian, podeu entendre millor els vostres clients enriquint els perfils dels clients amb dades demogràfiques com ara la mida de la llar, els ingressos i més.

## <a name="supported-countriesregions"></a>Països o regions admesos

Actualment admetem l'enriquiment de perfils de clients només als Estats Units.

## <a name="prerequisites"></a>Requisits previs

- Una subscripció activa Experian. Per obtenir una subscripció, [poseu-vos en contacte directament amb Experian](https://www.experian.com/marketing-services/contact). [Obteniu més informació sobre l'enriquiment de dades d'Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Un Experian [administrador configura](connections.md) una [connexió](#configure-the-connection-for-experian).

- Experian Identificador d'usuari, identificador de partit i número de model per al compte de transport segur (ST) habilitat per sSH que Experian s'ha creat per a vosaltres.

## <a name="configure-the-connection-for-experian"></a>Configurar la connexió per a Experian

Heu de ser administrador [del](permissions.md#admin) Customer Insights i tenir un identificador d'usuari, un identificador de festa i un Experian número de model.

1. Seleccioneu **Afegeix una connexió** en configurar un enriquiment, aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la Experian peça.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Subfinestra de configuració de connexió a Experian":::

1. Introduïu un nom per a la connexió i un identificador d'usuari, un identificador de festa i un número de model vàlids per al Experian compte de transport segur.

1. Reviseu i proporcioneu el vostre consentiment per a la [Privadesa de les dades i conformitat](#data-privacy-and-compliance) seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

### <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan permeteu que el Dynamics 365 Customer Insights transmeti dades a Experian, permeteu la transferència de dades fora del límit de conformitat per al Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals. Microsoft transferirà aquestes dades segons la vostra instrucció, però sou responsable d'assegurar que Experian compleixi les obligacions de privadesa o seguretat que tingueu. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la **peça Dades demogràfiques** Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian a la pàgina visió general d'enriquiment.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió. Poseu-vos en contacte amb un administrador si no n'hi ha cap disponible.

1. Seleccioneu **Següent**.

1. Seleccioneu el **conjunt de dades de client** i trieu el perfil o segment del qual voleu enriquir amb les dades demogràfiques de Experian. L'entitat *Client* enriqueix tots els vostres perfils de clients, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. Definiu de quin tipus de camps dels perfils unificats s'utilitzaran per fer coincidir les dades demogràfiques de Experian. Cal com a mínim un dels camps **Nom i adreça**, **Telèfon** o **Correu electrònic**. Per obtenir una precisió més alta de la coincidència, afegiu altres camps. Seleccioneu **Següent**.

1. Assigneu els camps a les dades demogràfiques de Experian.

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un **nom** per a l'enriquiment i el nom **de l'entitat** Sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o a prop per tornar a la **pàgina Enriquiments**.

## <a name="view-enrichment-results"></a>Veure resultats d'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **nombre de clients enriquits per camp** proporciona una desglossament en la cobertura de cada camp enriquit.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
