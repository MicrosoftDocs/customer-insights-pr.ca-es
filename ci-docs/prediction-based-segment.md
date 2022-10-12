---
title: Crear un segment basat en un model de predicció
description: Crear segments basats en l'entitat de sortida d'un model de predicció.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610408"
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

1. Seleccioneu el model que voleu revisar i seleccioneu **Visualitza**.

1. A la pàgina de resultats, seleccioneu **Crea un segment**. Per obtenir més informació sobre la pàgina de resultats, reviseu l'article sobre el model.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de pantalla de la pàgina de predicció de resultats amb l'acció Crea un segment destacada.":::

1. Creeu un segment nou utilitzant atributs de l'entitat de sortida del model seleccionat. Per a més informació, vegeu [Crear i administrar segments](segments.md).

> [!TIP]
> També podeu crear un segment per a un model de predicció des de la **pàgina Segments** seleccionant **Crea des** d'Intel·ligència i triant **Crea des d'Intel** > **·ligència**. Per obtenir més informació, vegeu [Crear un segment nou amb segments ràpids](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
