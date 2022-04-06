---
title: Informació general sobre les situacions de predicció admeses
description: Situacions i opcions de predicció cobertes per l'aplicació del Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: a5e4503cf9ce0cea562bab9389748d8ca1451f9d
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487487"
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
- [Anàlisi](sentiment-analysis.md) del sentiment: Analitzar el sentiment de retroalimentació dels clients i identificar els aspectes empresarials que s'esmenten amb freqüència.

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

- [Cancel·lació de subscripció](predict-transactional-churn.md): prediu si un client ja no comprarà els vostres productes o serveis en un determinat període de temps.

---

> [!TIP]
> Us recomanem que actualitzeu regularment els models fora de la caixa amb dades actualitzades per assegurar-vos que informin amb precisió el vostre cas d'ús empresarial. Les dades s'actualitzen ad hoc quan el sistema ingereix fonts de dades noves o actualitzades. No obstant això, els models només es tornaran a col·lamentar en aquest cas i continuaran utilitzant les dades d'entrenament existents.
> 
> Podeu configurar una planificació **d'actualització** establint la planificació de reciclatge del model a l'experiència de configuració. El model es tornarà a entrenar i tornarà a marcar en aquesta planificació, que podeu canviar en qualsevol moment.


## <a name="azure-machine-learning-integration"></a>Integració de l'aprenentatge automàtic de l'Azure

Si una organització ja utilitza escenaris d'aprenentatge automàtic basats en els experiments de d'aprenentatge automàtic de l'Azure, la característica de models personalitzats del Customer Insights ajuda a connectar els punts. Creeu fluxos de treball que us ajudin a triar les dades a partir de les qual voleu generar informació i assigneu els resultats als perfils de client unificats. Per obtenir més informació, vegeu [Models d'aprenentatge automàtic personalitzats](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder predicció

De vegades, els conjunts de dades són incomplets i falten alguns valors. El Customer Insights pot ajudar a predir els valors que falten per a l'entitat i els segments del client. Per obtenir més informació, vegeu [Completar les dades parcials amb predictions](predictions.md).
