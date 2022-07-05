---
title: Crear un segment basat en un model de predicció
description: Crear segments basats en l'entitat de sortida d'un model de predicció.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: d67594f2467c1a0fde84b1ba0bd1afa4025e7b71
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082423"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Crear un segment basat en un model predicció (versió preliminar)

Els resultats de les previsions de vegades només s'apliquen a un subconjunt dels clients. Amplieu la personalització de les recomanacions creant segments a partir de resultats de models de predicció. Per exemple, pot ser que us calgui fer recomanacions específiques als clients que prefereixen un cert tipus de servei. 

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.

- Un model de recomanació de producte, cancel·lació transaccional, cancel·lació de subscripció o cicle de vida del client configurat al Customer Insights. Reviseu els requisits per configurar els diferents models:

  - [Model de recomanació de productes](predict-product-recommendation.md)
  - [Model de cancel·lació de la subscripció](predict-subscription-churn.md)
  - [Model de cancel·lació transaccional](predict-transactional-churn.md)
  - [Model de valor de vida del client](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Crear un segment de client basat en prediccions

1. Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.

1. Seleccioneu els punts suspensius verticals al costat del model que voleu revisar i seleccioneu **Visualitza**.

1. A la pàgina de resultats, seleccioneu **Crea un segment**. Per obtenir més informació sobre la pàgina de resultats, reviseu l'article sobre el model.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de pantalla de la pàgina de predicció de resultats amb l'acció Crea un segment destacada.":::

1. Crear un segment nou basat en l'entitat de sortida del model seleccionat. Per a més informació, vegeu [Crear i administrar segments](segments.md).