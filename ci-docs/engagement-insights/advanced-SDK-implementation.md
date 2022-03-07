---
title: Escenaris avançats de l'SDK web
description: Escenaris avançats que cal tenir en compte a l'hora d'equipar el lloc web amb un SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036316"
---
# <a name="advanced-web-sdk-instrumentation"></a>Equipació avançada de l'SDK de webs

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En aquest article s'expliquen diferents escenaris avançats que cal tenir en compte quan [equipeu el lloc web](instrument-website.md) amb un SDK amb la capacitat dels coneixements d'interacció del Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Definir detalls de l'usuari per a la incidència

L'SDK us permet definir informació d'usuari que es pot enviar amb cada incidència. Podeu especificar els detalls de l'usuari en una propietat anomenada `user` (les dades esperades per a aquesta propietat són l'objecte `IUser`), de manera semblant a `src`, `name` i `cfg` a la configuració del fragment de codi.

L'objecte `IUser` conté les propietats de cadena següents:

- **localId**: l'identificador local de l'usuari.
- **authId**: l'identificador d'usuari autenticat.
- **authType**: el tipus d'autenticació utilitzada per obtenir l'identificador d'usuari autenticat.
- **name**: el nom de l'usuari.
- **email**: l'adreça electrònica de l'usuari.
    
A l'exemple següent es mostra una fragment de codi que envia informació d'usuari. On vegeu funcions marcdes amb un *, substituïu-les per la implementació de trucades d'aquests valors:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

També podeu especificar la informació de l'usuari trucant a l'API `setUser(user: IUser)` a l'SDK. La telemetria enviada després de trucar `setUser API` contindrà la informació d'usuari.

## <a name="adding-custom-properties-for-each-event"></a>Afegir propietats personalitzades per a cada incidència

L'SDK us permet especificar propietats personalitzades que es poden enviar amb cada incidència. Podeu especificar les propietats personalitzades com un objecte que conté parelles de valors clau (el valor pot ser de tipus `string | number | boolean`). L'objecte es pot afegir a una propietat anomenada `props`, similar a `src`, `name` i `cfg` a la configuració del fragment de codi. 

A l'exemple següent es mostra una fragment de codi que envia propietats personalitzades.

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

També podeu especificar propietats personalitzades individualment trucant a l'API `setProperty(name: string, value: string | number | boolean)` a l'SDK.

## <a name="sending-custom-events"></a>Enviar incidències personalitzades

Podeu utilitzar l'SDK per enviar incidències personalitzades. Heu d'especificar un nom per a la incidència i les propietats que s'han d'enviar amb la incidència.

A l'exemple següent es mostra una fragment de codi que fa el seguiment d'una incidència personalitzada. El valor "NAME" és el valor de la clau `name` de la configuració del fragment de codi. També és el nom de la variable a l'objecte de la finestra on es carrega l'SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]