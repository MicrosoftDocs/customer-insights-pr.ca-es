---
title: Informació general sobre les situacions de predicció admeses
description: Situacions i opcions de predicció cobertes per l'aplicació del Dynamics 365 Customer Insights.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 63e22bf9a457ea43c65132643681cffb295ae7e5
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673950"
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

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

- [Cancel·lació de subscripció](predict-transactional-churn.md): prediu si un client ja no comprarà els vostres productes o serveis en un determinat període de temps.

---


## <a name="azure-machine-learning-integration"></a>Integració de l'aprenentatge automàtic de l'Azure

Si una organització ja utilitza escenaris d'aprenentatge automàtic basats en els experiments de d'aprenentatge automàtic de l'Azure, la característica de models personalitzats del Customer Insights ajuda a connectar els punts. Creeu fluxos de treball que us ajudin a triar les dades a partir de les qual voleu generar informació i assigneu els resultats als perfils de client unificats. Per obtenir més informació, vegeu [Models d'aprenentatge automàtic personalitzats](custom-models.md).

## <a name="ai-builder-prediction"></a>Predicció de l'AI Builder

De vegades, els conjunts de dades són incomplets i falten alguns valors. El Customer Insights pot ajudar a predir els valors que falten per a l'entitat i els segments del client. Per obtenir més informació, vegeu [Completar les dades parcials amb predictions](predictions.md).
