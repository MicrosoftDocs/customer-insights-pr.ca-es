---
title: Administrar les galetes i el consentiment de l'usuari per emmagatzemar les dades dels usuaris al Dynamics 365 Customer Insights
description: Enteneu com s'utilitzen les galetes i el consentiment de l'usuari per identificar els visitants de llocs web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228973"
---
# <a name="manage-cookies-and-user-consent"></a>Administrar les galetes i el consentiment de l'usuari

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La capacitat de conclusions d'interacció del Dynamics 365 Customer Insights utilitza galetes i claus (`localStorage`) per identificar els visitants del lloc web.

Les galetes són petits fitxers que emmagatzemen fragments d'informació sobre les interaccions d'un usuari amb el lloc web. S'emmagatzemen en navegadors web. Quan els usuaris visiten un lloc web per al qual els usuaris han emmagatzemat les galetes, el navegador envia aquesta informació al servidor, que retorna informació única de l'usuari. Aquesta és la tecnologia que permet, per exemple, que un carretó mantingui els articles seleccionats encara que un usuari marxi del lloc web.

## <a name="user-consent"></a>Consentiment de l'usuari

El [Reglament general de protecció de dades (RGPD)](/dynamics365/get-started/gdpr/) és un reglament de la Unió Europea (UE) que dicta com les organitzacions han de gestionar la privadesa i la seguretat dels seus usuaris. Les galetes emmagatzemen o recopilen sovint "dades personals", com ara un identificador en línia, que està cobert pel RGPD. Si el vostre negoci fa servir i/o ven a titulars de les dades de la UE, el RGPD us afecta. [Més informació sobre com Microsoft pot ajudar-vos a complir amb el RGPD](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Per permetre que l'SDK dels coneixements d'interacció emmagatzemin les galetes o altres dades confidencials, heu d'especificar si els usuaris han consentit. Això succeeix en la inicialització de l'SDK configurant un camp `userConsent` a la configuració.

Si indiqueu que no hi ha cap consentiment de l'usuari, l'SDK no emmagatzemarà cap dada i no enviarà incidències que es puguin utilitzar per fer el seguiment del comportament de l'usuari. Qualsevol dada emmagatzemada prèviament se suprimirà del navegador.

Si no s'especifica cap valor de consentiment de l'usuari, l'SDK suposarà que l'usuari ha donat el seu consentiment. Això significa que si vós (com a client) no especifiqueu cap valor per al consentiment de l'usuari a l'SDK, les dades es recopilaran. No obstant això, si especifiqueu que el valor del consentiment de l'usuari ha de ser "cert", no es recopilarà si un usuari rebutja o no mostra el consentiment explícit.

A continuació es mostra un fragment de codi per inicialitzar l'SDK web amb el consentiment de l'usuari:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Emmagatzematge de dades dels visitants a la capacitat dels coneixements d'interacció

### <a name="cookies"></a>Galetes

- _msei
    - Emmagatzema l'identificador d'usuari anònim. Aquesta galeta es defineix al domini del client i caduca en 365 dies.

### <a name="local-storage"></a>Emmagatzematge local

La capacitat de conclusions d'interacció també utilitza claus (`localStorage`) per fer el seguiment de les dades no confidencials. Aquestes dades s'emmagatzemen totalment en el mateix navegador, sense trànsit enviat a ni des dels vostres servidors.

- *EISession.Id*
    - Emmagatzema informació sobre la sessió de l'usuari en curs, com ara l'identificador de sessió, el moment en què comença i el moment en què caduca.
- *EISession.Previous*
    - Emmagatzema l'adreça URL de la pàgina prèviament visitada a la sessió actual.

Les claus de l'emmagatzematge local no caduquen automàticament i es restabliran durant la propera sessió de l'SDK.

## <a name="deleting-cookies"></a>Suprimir galetes

Els vostres clients poden suprimir manualment les galetes i les claus d'emmagatzematge local en qualsevol moment mitjançant la configuració dels seus navegadors.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
