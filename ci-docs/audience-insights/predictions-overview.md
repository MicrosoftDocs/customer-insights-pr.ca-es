---
title: Informació general sobre les situacions de predicció admeses
description: Situacions i opcions de predicció cobertes per l'aplicació del Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095687"
---
# <a name="predictions-overview"></a><span data-ttu-id="be544-103">Informació general sobre les prediccions</span><span class="sxs-lookup"><span data-stu-id="be544-103">Predictions overview</span></span>

<span data-ttu-id="be544-104">El Dynamics 365 Customer Insights inclou diverses opcions que poden utilitzar l'IA i l'aprenentatge automàtic per predir dades.</span><span class="sxs-lookup"><span data-stu-id="be544-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="be544-105">Models de sèrie</span><span class="sxs-lookup"><span data-stu-id="be544-105">Out-of-box models</span></span>

<span data-ttu-id="be544-106">La manera més fàcil de començar amb la predicció de dades són els models predefinits, que sovint es coneixen com a models de sèrie.</span><span class="sxs-lookup"><span data-stu-id="be544-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="be544-107">Només necessiten determinades dades i estructura per generar informació ràpidament.</span><span class="sxs-lookup"><span data-stu-id="be544-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="be544-108">Actualment, hi ha disponibles els models següents:</span><span class="sxs-lookup"><span data-stu-id="be544-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="be544-109">[Valor de vida dels clients](predict-customer-lifetime-value.md): preveu els ingressos potencials d'un client durant tota la interacció amb una empresa.</span><span class="sxs-lookup"><span data-stu-id="be544-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="be544-110">[Recomanació de producte](predict-product-recommendation.md): suggereix conjunts de recomanacions de productes predictives a partir del comportament de compra i dels clients amb patrons de compra similars.</span><span class="sxs-lookup"><span data-stu-id="be544-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="be544-111">[Cancel·lació de subscripció](predict-subscription-churn.md): prediu si un client està en risc de deixar d'utilitzar els productes o serveis de subscripció de la vostra empresa.</span><span class="sxs-lookup"><span data-stu-id="be544-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="be544-112">[Cancel·lació de subscripció](predict-transactional-churn.md): prediu si un client ja no comprarà els vostres productes o serveis en un determinat període de temps.</span><span class="sxs-lookup"><span data-stu-id="be544-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="be544-113">Integració de l'aprenentatge automàtic de l'Azure</span><span class="sxs-lookup"><span data-stu-id="be544-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="be544-114">Si una organització ja utilitza escenaris d'aprenentatge automàtic basats en els experiments de d'aprenentatge automàtic de l'Azure, la característica de models personalitzats del Customer Insights ajuda a connectar els punts.</span><span class="sxs-lookup"><span data-stu-id="be544-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="be544-115">Creeu fluxos de treball que us ajudin a triar les dades a partir de les qual voleu generar informació i assigneu els resultats als perfils de client unificats.</span><span class="sxs-lookup"><span data-stu-id="be544-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="be544-116">Per obtenir més informació, vegeu [Models d'aprenentatge automàtic personalitzats](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="be544-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="be544-117">Predicció de l'AI Builder</span><span class="sxs-lookup"><span data-stu-id="be544-117">AI Builder prediction</span></span>

<span data-ttu-id="be544-118">De vegades, els conjunts de dades són incomplets i falten alguns valors.</span><span class="sxs-lookup"><span data-stu-id="be544-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="be544-119">El Customer Insights pot ajudar a predir els valors que falten per a l'entitat i els segments del client.</span><span class="sxs-lookup"><span data-stu-id="be544-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="be544-120">Per obtenir més informació, vegeu [Completar les dades parcials amb predictions](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="be544-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
