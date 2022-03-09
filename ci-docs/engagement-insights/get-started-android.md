---
title: Introducció a l'SDK de l'Android
description: Més informació sobre com personalitzar i executar l'SDK de l'Android
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: b06822b2c2d6a859bdf808f7800baef43c4ab874
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226157"
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

## <a name="integrate-the-sdk-into-your-application"></a>Integrar l'SDK a l'aplicació
Per iniciar el procés, seleccioneu una àrea de treball, seleccioneu la plataforma mòbil Android i descarregueu l'SDK de l'Android.

- Utilitzeu el commutador d'àrea de treball de la subfinestra de navegació esquerra per seleccionar l'àrea de treball.

- Si no teniu cap àrea de treball existent, seleccioneu **Nova àrea de treball** i seguiu els passos per crear una [àrea de treball nova](create-workspace.md).

- Després de crear una àrea de treball, aneu a **Administració** > **Àrea de treball** i seleccioneu **Guia d'instal·lació**.

## <a name="configure-the-sdk"></a>Configurar l'SDK

Un cop baixat l'SDK, podeu treballar-hi a Android Studio per habilitar i definir esdeveniments. Hi ha dues maneres de fer-ho:
### <a name="option-1-use-jitpack-recommended"></a>Opció 1: Utilitzeu JitPack (recomanat)
1. Afegiu el dipòsit JitPack al `build.gradle` arrel:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Afegiu la dependència:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Opció 2: utilitzeu l'enllaç de baixada
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

## <a name="enable-auto-instrumentation"></a>Habilitar la instrumentació automàtica

1. Afegiu permís per a la xarxa i Internet al fitxer `AndroidManifest.xml` ubicat a la carpeta `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Configureu la configuració de l'SDK de la informació d'interacció a través del fitxer `AndroidManifest.xml`.

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

   >[!NOTE]
   >`Action` els esdeveniments s'han d'afegir manualment.

1. (Opcional) Altres configuracions inclouen definir l'adreça URL del recopilador d'extrems. Es poden afegir a les metadades de la clau d'ingestió del `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Implementar esdeveniments personalitzats

Després d'inicialitzar l'SDK, podeu treballar amb esdeveniments i les seves propietats a l'entorn `MainActivity`.


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

## <a name="set-user-details-for-your-event-optional"></a>Definir els detalls de l'usuari per a l'esdeveniment (opcional)

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
