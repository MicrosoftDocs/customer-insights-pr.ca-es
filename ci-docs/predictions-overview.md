---
title: Informació general sobre les prediccions
description: Situacions i opcions de predicció cobertes per l'aplicació del Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 32240c8c43751d8514d38b392f23ef4138d50ee2
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411819"
---
# <a name="predictions-overview"></a>Informació general sobre les prediccions

El Dynamics 365 Customer Insights inclou diverses opcions que poden utilitzar l'IA i l'aprenentatge automàtic per predir dades. 

## <a name="out-of-box-models"></a>Models de sèrie

La manera més fàcil de començar amb la predicció de dades són els models predefinits, que sovint es coneixen com a models de sèrie. Només necessiten determinades dades i estructura per generar informació ràpidament. Actualment, hi ha disponibles els models següents: 

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

- [Valor de vida dels clients](predict-customer-lifetime-value.md): preveu els ingressos potencials d'un client durant tota la interacció amb una empresa.
- [Recomanació de producte](predict-product-recommendation.md): suggereix conjunts de recomanacions de productes predictives a partir del comportament de compra i dels clients amb patrons de compra similars.
- [Cancel·lació de subscripció](predict-subscription-churn.md): prediu si un client està en risc de deixar d'utilitzar els productes o serveis de subscripció de la vostra empresa.
- [Cancel·lació de subscripció](predict-transactional-churn.md): prediu si un client ja no comprarà els vostres productes o serveis en un determinat període de temps.
- [Anàlisi](sentiment-analysis.md) de sentiments: Analitzar el sentiment dels comentaris dels clients i identificar els aspectes empresarials que s'esmenten amb freqüència.

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

- [Cancel·lació de subscripció](predict-transactional-churn.md): prediu si un client ja no comprarà els vostres productes o serveis en un determinat període de temps.

---

> [!TIP]
> Us recomanem que actualitzeu regularment els models estàndard amb dades actualitzades per assegurar-vos que informin amb precisió el cas d'ús de la vostra empresa. Les dades s'actualitzen ad-hoc quan el sistema ingereix fonts de dades noves o actualitzades. No obstant això, els models només tornaran a aparèixer en aquest cas i continuaran utilitzant les dades d'entrenament existents.
>
> Podeu configurar una planificació **d'actualitzacions** establint la planificació de reciclatge del model a l'experiència de configuració. El model es reciclarà i es moderarà en aquest horari, que podeu canviar en qualsevol moment.

## <a name="azure-machine-learning-integration"></a>Integració de l'aprenentatge automàtic de l'Azure

Si una organització ja utilitza escenaris d'aprenentatge automàtic basats en els experiments de d'aprenentatge automàtic de l'Azure, la característica de models personalitzats del Customer Insights ajuda a connectar els punts. Creeu fluxos de treball que us ajudin a triar les dades a partir de les qual voleu generar informació i assigneu els resultats als perfils de client unificats. Per obtenir més informació, vegeu [Models d'aprenentatge automàtic personalitzats](custom-models.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
