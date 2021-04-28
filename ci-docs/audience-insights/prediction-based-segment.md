---
title: Segments basats en la sortida de predicció
description: Crear segments basats en l'entitat de sortida d'un model de predicció.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741417"
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