---
title: Enriquir els perfils de client amb les dades d'ubicació de l'Azure Maps
description: Informació general sobre l'enriquiment principal de l'Azure Maps.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953616"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Enriquiment dels perfils de client amb l'Azure Maps (versió preliminar)

L'Azure Maps proporciona dades i serveis centrats en la ubicació per oferir experiències basades en dades geoespacials amb intel·ligència d'ubicació integrada. Els serveis d'enriquiment de dades de l'Azure Maps milloren la precisió de la informació d'ubicació dels vostres clients. Proporciona capacitats com ara la normalització d'adreces i l'extracció de latitud i longitud al Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisits previs

- Una subscripció activa de l'Azure Maps. Per obtenir una subscripció, [registreu-vos o obteniu una prova gratuïta](https://azure.microsoft.com/services/azure-maps/).

- Un administrador ha configurat una connexió [de](connections.md) [l'Azure Maps](#configure-the-connection-for-azure-maps).

## <a name="configure-the-connection-for-azure-maps"></a>Configurar la connexió per a l'Azure Maps

Heu de ser administrador [del](permissions.md#admin) Customer Insights i tenir una clau d'API activa de l'Azure Maps.

1. Seleccioneu **Afegeix una connexió** en configurar un enriquiment o aneu a **Administració** > **Connexions** i seleccioneu **Configura** a la peça de l'Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Pàgina de configuració de la connexió de l'Azure Maps.":::

1. Introduïu un nom per a la connexió i una clau d'API vàlida de l'Azure Maps.

1. Reviseu i proporcioneu el vostre consentiment per a la [Privadesa de les dades i conformitat](#data-privacy-and-compliance) seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

### <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan permeteu que el Dynamics 365 Customer Insights transmeti dades a l'Azure Maps, permeteu la transferència de dades fora del límit de conformitat per al Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals. Microsoft transferirà aquestes dades a les instruccions, però sou responsable d'assegurar-vos que l'Azure Maps compleixi amb les obligacions de privadesa o de seguretat que pugueu tenir. Per obtenir més informació, aneu a la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la **peça Ubicació** de Microsoft Azure Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Peça Azure Maps.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Seleccioneu **Següent**.

1. Seleccioneu el **conjunt de dades del client** i trieu el perfil o el segment que voleu enriquir amb les dades de Microsoft. L'entitat *Client* enriqueix tots els vostres perfils de clients, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Definiu quin tipus de camps dels perfils unificats s'utilitzaran per fer coincidir: l'adreça principal i/o secundària. Podeu especificar una assignació de camps per a ambdues adreces i enriquir els perfils de les dues adreces per separat. Per exemple, per a una adreça de casa i una adreça de l'empresa. Seleccioneu **Següent**.

1. Assigneu els camps a les dades d'ubicació de l'Azure Maps. Els camps **Carrer 1** i **Codi postal** són obligatoris per a l'adreça principal o secundària seleccionada. Per obtenir una precisió més alta de coincidència, afegiu més camps.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps attribute mapping.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Reviseu **Configuració** avançada que ofereixen la màxima flexibilitat per gestionar casos d'ús avançats. No obstant això, els valors per defecte següents normalment no cal canviar-los.

   - **Tipus d'adreces**: la millor coincidència d'adreces torna encara que estigui incompleta. Per obtenir només les adreces completes (per exemple, les adreces que inclouen el número de domicili), desactiveu totes les caselles de selecció excepte **Adreces de punts**.
   - **Idioma**: les adreces tornen en l'idioma en funció de la regió d'adreces. Per aplicar una llengua d'adreça estandarditzada, seleccioneu la llengua al menú desplegable. Per exemple, seleccionant l'anglès **torna** **Copenhaguen, Dinamarca** en lloc de **København, Danmark**.
   - **Nombre màxim de resultats**: Nombre de resultats per adreça.

1. Seleccioneu **Següent**.

1. Proporcioneu un **nom** per a l'enriquiment i el nom **de l'entitat** Sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o a prop per tornar a la **pàgina Enriquiments**.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **nombre de clients enriquits per camp** proporciona una desglossament en la cobertura de cada camp enriquit.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
