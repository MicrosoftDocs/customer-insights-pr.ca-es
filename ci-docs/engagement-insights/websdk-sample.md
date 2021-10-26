---
title: Executar un exemple de l'SDK web
description: Apreneu a personalitzar i executar un exemple de l'SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606180"
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
