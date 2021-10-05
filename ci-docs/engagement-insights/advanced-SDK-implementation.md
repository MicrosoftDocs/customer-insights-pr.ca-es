---
title: Escenaris avançats de l'SDK web
description: Escenaris avançats que cal tenir en compte a l'hora d'equipar el lloc web amb un SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558689"
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

A l'exemple següent es mostra una fragment de codi que envia informació d'usuari. On veieu les funcions precedides per un símbol d'asterisc *, substituïu la funció per la implementació personalitzada:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

També podeu especificar la informació de l'usuari cridant l'API `setUser(user: IUser)`. La telemetria enviada després de cridar l'API `setUser` contindrà la informació de l'usuari.

## <a name="adding-custom-properties-for-each-event"></a>Afegir propietats personalitzades per a cada incidència

L'SDK us permet especificar propietats personalitzades que es poden enviar amb cada incidència. Podeu especificar les propietats personalitzades com un objecte que conté parelles de valors clau (el valor pot ser de tipus `string | number | boolean`). Podeu afegir l'objecte en una propietat anomenada `props`, similar a `src`, `name` i a la configuració del fragment de codi `cfg`.

A l'exemple següent es mostra una fragment de codi que envia propietats personalitzades.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

També podeu especificar propietats personalitzades individualment cridant l'API `setProperty(name: string, value: string | number | boolean)`.

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
