---
title: Introducció a l'SDK de l'Android
description: Més informació sobre com personalitzar i executar l'SDK de l'Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036906"
---
# <a name="get-started-with-the-android-sdk"></a>Introducció a l'SDK de l'Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Aquest tutorial us guiarà pel procés d'instrumentació de la vostra aplicació de l'Android amb l'SDK de conclusions d'interacció del Dynamics 365 Customer Insights. Començareu a veure els esdeveniments al portal en cinc minuts o més aviat.

## <a name="configuration-options"></a>Opcions de configuració
Les opcions de configuració següents es poden enviar a l'SDK:

- **ingestionKey**: clau d'ingestió utilitzada per enviar esdeveniments a l'àrea de treball.

## <a name="prerequisites"></a>Requisits previs

- Android Studio

- Nivell d'API de l'Android mínim: 16 (Jelly Bean)

- Clau d'ingestió (consulteu les instruccions següents per obtenir-la)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Pas 1. Integrar l'SDK a l'aplicació
Per iniciar el procés, seleccioneu una àrea de treball, seleccioneu la plataforma mòbil Android i descarregueu l'SDK de l'Android.

- Utilitzeu el commutador d'àrea de treball de la subfinestra de navegació esquerra per seleccionar l'àrea de treball.

- Si no teniu cap àrea de treball existent, seleccioneu **Nova àrea de treball** i seguiu els passos per crear una [àrea de treball nova](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Pas 2. Configurar l'SDK

1. Després de crear una àrea de treball, aneu a **Administració** > **Àrea de treball** i seleccioneu **Guia d'instal·lació**. 

1. Baixeu l'[SDK de l'Android de les conclusions d'interacció](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) i col·loqueu el fitxer `eiandroidsdk-debug.aar` a la carpeta `libs`.

1. Obriu el fitxer `build.gradle` de nivell de projecte i afegiu els fragments següents:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Configureu la configuració de l'SDK de les conclusions d'interacció a través del fitxer `AndroidManifest.xml` ubicat a la carpeta `manifests`. 
1. Copieu el fragment de codi XML de la **Guia d'instal·lació**. `Your-Ingestion-Key` s'hauria d'emplenar automàticament.

   > [!NOTE]
   > No cal que substituïu la secció `${applicationId}`. S'emplena automàticament.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Habiliteu o inhabiliteu la captura automàtica dels esdeveniments `View` definint el camp `autoCapture` anterior com a `true` o `false`.

1. (Opcional) Altres configuracions inclouen definir l'adreça URL del recopilador d'extrems. Es poden afegir a les metadades de clau d'ingestió a `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Pas 3. Inicialitzeu l'SDK des de MainActivity 

Després d'inicialitzar l'SDK, podeu treballar amb esdeveniments i les seves propietats a l'entorn MainActivity.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Definir la propietat per a tots els esdeveniments (opcional)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Els tipus següents estan admesos per a les propietats d'esdeveniment de context:
- String
- Date
- Doble
- Long
- Boolean
- UUID

### <a name="track-an-event"></a>Fes el seguiment d'un esdeveniment

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Definir els detalls de l'usuari per a l'esdeveniment (opcional)

L'SDK us permet definir informació d'usuari que es pot enviar amb cada incidència. Podeu especificar la informació de l'usuari trucant a l'API `setUser(user: User)` al nivell `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

La classe de dades `User` conté les següents propietats de cadena:

- **localId**: l'identificador local de l'usuari.
- **authId**: l'identificador d'usuari autenticat.
- **authType**: tipus d'autenticació utilitzat per a l'identificador d'usuari autenticat.
- **name**: el nom de l'usuari.
- **email**: l'adreça electrònica de l'usuari.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
