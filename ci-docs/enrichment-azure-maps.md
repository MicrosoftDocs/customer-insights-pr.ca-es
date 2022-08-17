---
title: Enriquir perfils de clients amb dades d'ubicació de l'Azure Maps (visualització prèvia)
description: Informació general sobre l'enriquiment principal de l'Azure Maps.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238030"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Enriquir perfils de clients amb dades d'ubicació de l'Azure Maps (visualització prèvia)

Els mapes de l'Azure proporcionen dades i serveis centrats en la ubicació per oferir experiències basades en dades geoespacials amb intel·ligència d'ubicació integrada. Els serveis d'enriquiment de dades de l'Azure Maps milloren la precisió de la informació d'ubicació dels vostres clients. Proporciona capacitats com ara la normalització d'adreces i l'extracció de latitud i longitud al Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisits previs

- Una subscripció activa de l'Azure Maps. Per obtenir una subscripció, [registreu-vos o obteniu una prova gratuïta](https://azure.microsoft.com/services/azure-maps/).

- Un administrador configura [una connexió](connections.md)[de l'Azure Maps](#configure-the-connection-for-azure-maps).

## <a name="configure-the-connection-for-azure-maps"></a>Configurar la connexió per a l'Azure Maps

Heu de ser [administrador](permissions.md#admin) al Customer Insights i tenir una clau de l'API de l'Azure Maps activa.

1. Seleccioneu **Afegeix una connexió** en configurar un enriquiment o aneu a **Administració** > **Connexions** i seleccioneu **Configura** a la peça de l'Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Pàgina de configuració de la connexió de l'Azure Maps.":::

1. Introduïu un nom per a la connexió i una clau de l'API de l'Azure Maps vàlida.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la **peça Ubicació** de Maps Microsoft Azure.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Peça Azure Maps.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Seleccioneu **Següent**.

1. Seleccioneu el **conjunt** de dades del client i trieu el perfil o segment que voleu enriquir amb les dades de Microsoft. L'entitat *Client* enriqueix tots els teus perfils de client, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Definiu quin tipus de camps dels perfils unificats voleu utilitzar per a la coincidència: l'adreça principal i/o secundària. Podeu especificar una assignació de camps per a ambdues adreces i enriquir els perfils de les dues adreces per separat. Per exemple, per a una adreça de casa i una adreça comercial. Seleccioneu **Següent**.

1. Assigneu els camps a les dades d'ubicació de l'Azure Maps. Els camps **Carrer 1** i **Codi postal** són obligatoris per a l'adreça principal o secundària seleccionada. Per obtenir una precisió més alta de la coincidència, afegiu més camps.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps attribute mapping.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Reviseu **Configuració** avançada que ofereix la màxima flexibilitat per gestionar casos d'ús avançats. Tanmateix, normalment no cal canviar els valors predeterminats següents.

   - **Tipus d'adreces**: retorna la millor coincidència d'adreces encara que estigui incompleta. Per obtenir només les adreces completes (per exemple, les adreces que inclouen el número de domicili), desactiveu totes les caselles de selecció excepte **Adreces de punts**.
   - **Idioma**: les adreces tornen en l'idioma en funció de la regió d'adreça. Per aplicar una llengua d'adreça estandarditzada, seleccioneu la llengua al menú desplegable. Per exemple, seleccionant **anglès retorna** Copenhaguen, Dinamarca **en lloc de** København, Danmark **·**.
   - **Nombre màxim de resultats**: Nombre de resultats per adreça.

1. Seleccioneu **Següent**.

1. Proporcioneu un **nom** per a l'enriquiment i el nom de l'entitat **de sortida**.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o tancar per tornar a la **pàgina Enriquiments**.

## <a name="view-enrichment-results"></a>Veure resultats d'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **Nombre de clients enriquits per camp** proporciona un desglossament de la cobertura de cada camp enriquit.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
