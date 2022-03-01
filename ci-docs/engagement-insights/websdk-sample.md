---
title: Executar un exemple de l'SDK web
description: Apreneu a personalitzar i executar un exemple de l'SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036591"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Executar l'exemple de l'SDK web per a la capacitat dels coneixements d'interacció del Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La biblioteca de l'SDK web de la capacitat dels coneixements d'interacció és una biblioteca JavaScript amb codi d'exemple que podeu utilitzar al lloc web.

## <a name="prerequisites"></a>Requisits previs

- Instal·leu el [Visual Studio Code](https://code.visualstudio.com/).
- [Instal·leu l'extensió Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) al Visual Studio Code i familiaritzeu-vos amb l'execució del Live Server.
- Heu de tenir la [clau d'ingestió](instrument-website.md).

## <a name="run-sample"></a>Executa l'exemple

1. [Baixeu l'exemple de l'SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Descomprimiu el fitxer comprimit `ei_websdk_sample.zip`.

1. Obriu la carpeta descomprimida al Visual Studio Code.

1. Al fitxer `ei_websdk_sample.html`, substituïu la cadena "INGESTION_KEY" per la clau d'ingestió del portal de la capacitat dels coneixements d'interacció i la cadena "NAME" pel nom global en què voleu que l'SDK s'instanciï. Assegureu-vos de substituir totes les aparicions.

1. Per obrir el fitxer `ei_websdk_sample.html` amb el Live Server del Visual Studio Code, seleccioneu **Activa-ho** des de la barra d'estat.

1. Quan s'obri la pàgina, s'ha d'enviar automàticament una incidència de visualització. En fer clic en un dels botons de la pàgina, s'enviaran incidències d'acció. El botó **Seguiment d'incidències** també enviarà incidències personalitzades. Si seleccioneu el botó **Ves al Bing**, s'enviarà una incidència d'acció abans d'anar al lloc web del Bing.

1. Mireu les incidències que flueixen quan us desplaceu a l'àrea de treball. Aquesta àrea de treball s'associa amb la clau d'ingestió introduida al pas 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]