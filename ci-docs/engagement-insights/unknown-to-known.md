---
title: Reconèixer incidències web de visitants prèviament autenticats amb De desconegut a conegut
description: La característica De desconegut a conegut us permet associar incidències en un lloc web amb visitants que s'han autenticat prèviament.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230668"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Reconèixer incidències web de visitants prèviament autenticats

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La característica **De desconegut a conegut** en la capacitat de les conclusions d'interacció permet associar incidències en un lloc web amb visitants que s'han autenticat prèviament. Si la funció està inhabilitada, els visitants que es van autenticar durant una visita anterior i després van marxar no s'identifiquen si no tornen a autenticar-se quan tornen. 

Per exemple, una persona va visitar un lloc web la setmana passada, va iniciar sessió al seu compte d'usuari al lloc i va navegar pel catàleg de productes. La persona torna la setmana següent per navegar per més productes sense iniciar sessió al seu compte. El propietari del lloc, que utilitza la característica **De desconegut a conegut** sabria que la mateixa persona ha tornat i el que havia fet al lloc. Això permet un informe i anàlisi més precisos de les activitats del lloc web.

## <a name="enable-unknown-to-known"></a>Habilitar De desconegut a conegut

Necessitareu ser [administrador de l'àrea de treball](user-roles.md) per habilitar aquesta característica. 

1. A les conclusions d'interacció, aneu a **Administrador** > **Àrea de treball**. 
2. Seleccioneu la pestanya **Configuració**.
3. A la secció **De desconegut a conegut**, definiu el commutador com a **Habilitat**.

![Habilitar De desconegut a conegut](media/U2Ktoggle.png "Habilitar De desconegut a conegut")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Afegir codi JavaScript al fragment de seguiment del lloc

Un lloc web pot capturar **l'authId de l'usuari** amb la següent mostra de JavaScript utilitzant l'[SDK web de les conclusions d'interacció](advanced-SDK-implementation.md). Perquè funcioni la característica **De desconegut a conegut** heu de capturar authId *i* habilitar userMapping:True al fragment de JavaScript com a la mostra següent.

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
