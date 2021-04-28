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
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="e92cf-103">Crear un segment basat en un model predicció (versió preliminar)</span><span class="sxs-lookup"><span data-stu-id="e92cf-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="e92cf-104">Els resultats de les previsions de vegades només s'apliquen a un subconjunt dels clients.</span><span class="sxs-lookup"><span data-stu-id="e92cf-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="e92cf-105">Amplieu la personalització de les recomanacions creant segments a partir de resultats de models de predicció.</span><span class="sxs-lookup"><span data-stu-id="e92cf-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="e92cf-106">Per exemple, pot ser que us calgui fer recomanacions específiques als clients que prefereixen un cert tipus de servei.</span><span class="sxs-lookup"><span data-stu-id="e92cf-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e92cf-107">Requisits previs</span><span class="sxs-lookup"><span data-stu-id="e92cf-107">Prerequisites</span></span>

- <span data-ttu-id="e92cf-108">Com a mínim, [Permisos de col·laborador](permissions.md) al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e92cf-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="e92cf-109">Un model de recomanació de producte, cancel·lació transaccional, cancel·lació de subscripció o cicle de vida del client configurat al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e92cf-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="e92cf-110">Reviseu els requisits per configurar els diferents models:</span><span class="sxs-lookup"><span data-stu-id="e92cf-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="e92cf-111">Model de recomanació de productes</span><span class="sxs-lookup"><span data-stu-id="e92cf-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="e92cf-112">Model de cancel·lació de la subscripció</span><span class="sxs-lookup"><span data-stu-id="e92cf-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="e92cf-113">Model de cancel·lació transaccional</span><span class="sxs-lookup"><span data-stu-id="e92cf-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="e92cf-114">Model de valor de vida del client</span><span class="sxs-lookup"><span data-stu-id="e92cf-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="e92cf-115">Crear un segment de client basat en prediccions</span><span class="sxs-lookup"><span data-stu-id="e92cf-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="e92cf-116">Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.</span><span class="sxs-lookup"><span data-stu-id="e92cf-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e92cf-117">Seleccioneu els punts suspensius verticals al costat del model que voleu revisar i seleccioneu **Visualitza**.</span><span class="sxs-lookup"><span data-stu-id="e92cf-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="e92cf-118">A la pàgina de resultats, seleccioneu **Crea un segment**.</span><span class="sxs-lookup"><span data-stu-id="e92cf-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="e92cf-119">Per obtenir més informació sobre la pàgina de resultats, reviseu l'article sobre el model.</span><span class="sxs-lookup"><span data-stu-id="e92cf-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de pantalla de la pàgina de predicció de resultats amb l'acció Crea un segment destacada.":::

1. <span data-ttu-id="e92cf-121">Crear un segment nou basat en l'entitat de sortida del model seleccionat.</span><span class="sxs-lookup"><span data-stu-id="e92cf-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="e92cf-122">Per a més informació, vegeu [Crear i administrar segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e92cf-122">For more information, see [Create and manage segments](segments.md).</span></span>