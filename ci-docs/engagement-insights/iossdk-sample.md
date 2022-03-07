---
title: Executar l'exemple de l'SDK de l'iOS
description: Projecte d'exemple per obtenir informació sobre l'SDK de l'iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232830"
---
# <a name="run-the-ios-sdk-sample"></a>Executar l'exemple de l'SDK de l'iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Aquest projecte d'exemple de l'iOS us ajuda a entendre com funciona l'SDK en una aplicació. No haureu d'escriure cap codi. Només heu d'afegir la clau d'ingestió i podeu veure els esdeveniments a l'àrea de treball immediatament.

## <a name="prerequisites"></a>Requisits previs

- [Xcode versió 9+](https://developer.apple.com/xcode/downloads/)
- [Clau d'ingestió](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Baixar l'exemple de l'SDK de l'iOS

1. [Baixeu l'exemple de l'SDK de l'iOS de les conclusions d'interacció](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Descomprimiu el fitxer comprimit `ei-ios-sample.zip`.
1. Obriu el projecte d'aplicació d'exemple a Xcode.
1. Al fitxer `EIConfig.plist`, substituïu la cadena `“YOUR-INGESTION-KEY”` al camp `ingestionKey` per la clau d'ingestió de l'àrea de treball de les conclusions d'interacció a **Administració** > **Àrea de treball** > **Guia d'instal·lació**.
1. Per iniciar el projecte d'exemple, seleccioneu **Executa**.
1. Visualitzeu els esdeveniments a l'àrea de treball.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
