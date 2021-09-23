---
title: Introducció a l'SDK de l'iOS
description: Més informació sobre com personalitzar i executar l'SDK de l'iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: f05929435eeee9cf3f891ab18842c5861e39d5ba
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494218"
---
# <a name="get-started-with-the-ios-sdk"></a>Introducció a l'SDK de l'iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Aquest tutorial us guiarà pel procés d'instrumentació de la vostra aplicació de l'iOS amb l'SDK de les conclusions d'interacció del Dynamics 365 Customer Insights. Començareu a veure els esdeveniments al portal en cinc minuts o més aviat.

## <a name="configuration-options"></a>Opcions de configuració

Les opcions de configuració següents es poden enviar a l'SDK mitjançant el fitxer `EIConfig.plist` proporcionat:

- **ingestionKey**: clau d'ingestió utilitzada per enviar esdeveniments al vostre projecte.
- **autocollectAction**: valor booleà per habilitar o inhabilitar la inactivitat automàtica de l'esdeveniment d'acció.
- **autocollectView**: valor booleà per habilitar o inhabilitar la inactivitat automàtica de l'esdeveniment de visualització.
- **endpointUrl** : adreça URL de l'extrem on es dirigiran els esdeveniments.

## <a name="prerequisites"></a>Requisits previs

- Xcode versió 9+
- iOS versió 8.2+
- Clau d'ingestió (consulteu les instruccions següents per obtenir-la)

## <a name="integrate-the-sdk-into-your-application"></a>Integrar l'SDK a l'aplicació

Per iniciar el procés, seleccioneu una àrea de treball on treballar, seleccioneu la plataforma mòbil iOS i descarregueu l'SDK.

- Utilitzeu el commutador d'àrea de treball de la subfinestra de navegació esquerra per seleccionar l'àrea de treball.

- Si no teniu cap àrea de treball existent, seleccioneu **Nova àrea de treball** i seguiu els passos per crear una [àrea de treball nova](create-workspace.md).

- Després de crear una àrea de treball, aneu a **Administració** > **Àrea de treball** i seleccioneu **Guia d'instal·lació**.

## <a name="configure-the-sdk"></a>Configurar l'SDK

Un cop baixat l'SDK, podeu treballar-hi a Xcode per habilitar i definir esdeveniments. Hi ha dues maneres de fer-ho

### <a name="option-1-using-cocoapods-recommended"></a>Opció 1: utilitzar CocoaPods (recomanat)
CocoaPods es un administrador de dependències per als projectes de Cocoa Swift i Objective-C. Amb això es facilita la integració de l'SDK de la informació d'interacció per a iOS. CocoaPods també us permet actualitzar a l'última versió de l'SDK de la informació d'interacció. A continuació, s'explica com cal utilitzar CocoaPods per integrar l'SDK de la informació d'interacció al vostre projecte Xcode. 

1. Instal·lar el CocoaPods. 

1. Creeu un fitxer nou anomenat Podfile dins del directori arrel del vostre projecte i afegiu-hi les declaracions següents.Substituïu YOUR_TARGET_PROJECT_NAME pel nom del vostre projecte Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
La configuració anterior conté les versions de depuració i de llançament de l'SDK. Trieu la que sigui millor per al vostre projecte.

1. Instal·leu-ho mitjançant l'execució de l'ordre següent: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Opció 2: utilitzar l'enllaç de baixada

1. Baixeu l'[SDK de l'iOS de les conclusions d'interacció](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) i col·loqueu el fitxer `EIObjC.xcframework` a la carpeta `Frameworks`.

1. Si no hi ha cap carpeta `Frameworks`, creeu-ne una a la carpeta de projectes.

## <a name="enable-auto-instrumentation"></a>Habilitar la instrumentació automàtica
 
Podeu habilitar fàcilment la instrumentació automàtica sense codi. Quan s'executa el projecte, es farà un seguiment automàtic dels esdeveniments `view` i `action` amb la clau d'ingestió configurada. 

1. Actualitzeu i incloeu el fitxer `EIConfig.plist` proporcionat a la carpeta de directori de projectes per als camps següents:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = SÍ
    - autocollectAction = SÍ

2. A continuació, afegiu el fitxer `EIConfig.plist` al vostre projecte a Xcode. 



Per inhabilitar la instrumentació automàtica, actualitzeu els camps següents al fitxer `EIConfig.plist` proporcionat a la carpeta de directori de projectes. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementar esdeveniments personalitzats

1. Obriu el projecte a Xcode i aneu a la configuració **General**. 
1. Afegiu `EIObjC.xcframework` al projecte a la secció "Marcs de treball, biblioteques i contingut incrustat".

1. Importeu el fitxer de capçalera del marc a AppDelegate.m amb el fragment següent:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicialitzeu l'SDK de les conclusions d'interacció des d'application:didFinishLaunchingWithOptions.
1. Copieu el fragment de codi XML de la **Guia d'instal·lació**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Fer el seguiment d'un esdeveniment:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Definir els detalls de l'usuari per a l'esdeveniment

L'SDK us permet definir informació d'usuari que es pot enviar amb cada incidència. Podeu especificar la informació de l'usuari trucant a l'API `setUser:(nonnull EIUser *)user` a l'SDK.

Especificar els detalls de l'usuari al nivell `Analytics` significa que totes les telemetries tindran aquesta informació. No obstant, si especifiqueu en el nivell d'esdeveniment trucant a l'API `setUser:(nonnull EIUser *)user` a l'objecte EIEvent, només aquesta esdeveniment específic inclourà la informació.

La classe de dades `EIUser` conté les següents propietats NSString:

- **localId**: l'identificador local de l'usuari.
- **authId**: l'identificador d'usuari autenticat.
- **authType**: el tipus d'autenticació utilitzada per obtenir l'identificador d'usuari autenticat.
- **name**: el nom de l'usuari.
- **email**: l'adreça electrònica de l'usuari.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
