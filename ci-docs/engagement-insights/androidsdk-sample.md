---
title: Exemple de l'SDK de l'Android
description: Projecte d'exemple per obtenir informació sobre l'SDK de l'Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229906"
---
# <a name="run-the-android-sdk-sample"></a>Executar l'exemple de l'SDK de l'Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Aquest projecte d'exemple de l'Android us ajuda a entendre com funciona l'SDK en una aplicació. No haureu d'escriure cap codi. Només heu d'afegir la clau d'ingestió i podeu veure els esdeveniments a l'àrea de treball immediatament.

## <a name="prerequisites"></a>Requisits previs

- [Android Studio](https://developer.android.com/studio)
- [Clau d'ingestió](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Baixar l'exemple de l'SDK de l'Android

1. [Baixeu l'exemple de l'SDK de l'Android de les conclusions d'interacció](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Descomprimiu el fitxer comprimit `ei-android-sample.zip`.
1. Obriu la carpeta descomprimida a l'Android Studio.
1. Al fitxer `AndroidManifest.xml`, substituïu la cadena `"Your-Ingestion-Key"` per la clau d'ingestió de l'àrea de treball de les conclusions d'interacció a **Administració** > **Àrea de treball** > **Guia d'instal·lació**. 

   > [!NOTE]
   > No cal que substituïu la secció `${applicationId}`. S'emplena automàticament.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Per iniciar el projecte d'exemple, seleccioneu **Executa**.
1. Visualitzeu els esdeveniments a l'àrea de treball.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
