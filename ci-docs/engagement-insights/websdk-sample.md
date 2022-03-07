---
title: Executar un exemple de l'SDK web
description: Apreneu a personalitzar i executar un exemple de l'SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225319"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Executar l'exemple de l'SDK web per a la capacitat dels coneixements d'interacció del Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La biblioteca de l'SDK web de la capacitat dels coneixements d'interacció és una biblioteca JavaScript amb codi d'exemple que podeu utilitzar al lloc web.

## <a name="prerequisites"></a>Requisits previs

- Instal·leu el [Visual Studio Code](https://code.visualstudio.com/).
- [Instal·leu l'extensió Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) al Visual Studio Code i familiaritzeu-vos amb l'execució del Live Server.
- Heu de tenir una [àrea de treball de conclusions d'interacció](create-workspace.md).

## <a name="run-sample"></a>Executa l'exemple

1. [Baixeu l'exemple de l'SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Descomprimiu el fitxer comprimit `ei_websdk_sample.zip`.

1. Obriu la carpeta descomprimida al Visual Studio Code.

1. Aneu al portal de conclusions d'interacció de l'espai de treball. Seleccioneu **Administració** > **Espai de treball** i després **Guia d'instal·lació**. Seguiu la primera opció i seleccioneu **Copia el codi** per copiar el fragment de codi de JavaScript.

1. Al fitxer `ei_websdk_sample.html`, enganxeu l fragment de codi que heu copiat en aquesta línia:

   - <-- ENGANXEU EL FRAGMENT DE CODI DE JAVASCRIPT DEL PORTAL DE CONCLUSIONS D'INTERACCIÓ AQUÍ PER SOTA D'AQUESTA LÍNIA -->

1. Per obrir el fitxer `ei_websdk_sample.html` amb el Live Server del Visual Studio Code, seleccioneu **Activa-ho** des de la barra d'estat.

1. Quan s'obri la pàgina, s'ha d'enviar automàticament una incidència de visualització. En fer clic en un dels botons de la pàgina, s'enviaran incidències d'acció. El botó **Seguiment d'incidències** també enviarà incidències personalitzades. Si seleccioneu el botó **Ves al Bing**, s'enviarà una incidència d'acció abans d'anar al lloc web del Bing.

1. Mireu les incidències que flueixen quan us desplaceu a l'àrea de treball. Aquesta àrea de treball s'associa amb la clau d'ingestió introduida al pas 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
