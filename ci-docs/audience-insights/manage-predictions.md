---
title: Tasques compartides per a situacions de predicció
description: Més informació sobre com administrar, solucionar problemes i millor les prediccions.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095688"
---
# <a name="manage-predictions"></a><span data-ttu-id="6fd9e-103">Administrar prediccions</span><span class="sxs-lookup"><span data-stu-id="6fd9e-103">Manage predictions</span></span>

<span data-ttu-id="6fd9e-104">En aquest article es parla d'algunes tasques que la majoria de situacions de predicció comparteixen.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="6fd9e-105">Resoldre problemes relacionats amb una predicció fallida</span><span class="sxs-lookup"><span data-stu-id="6fd9e-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="6fd9e-106">Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="6fd9e-107">Seleccioneu els punts suspensius verticals que hi ha al costat de la predicció els registres d'error de la qual voleu visualitzar.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="6fd9e-108">Seleccioneu **Registres**.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-108">Select **Logs**.</span></span>

1. <span data-ttu-id="6fd9e-109">Reviseu tots els errors.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-109">Review all the errors.</span></span> <span data-ttu-id="6fd9e-110">Hi ha diversos tipus d'errors que es poden produir i que descriuen la condició que ha causat l'error.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="6fd9e-111">Per exemple, un error que indica que no hi ha prou dades per predir amb precisió se sol resoldre amb la càrrega de dades addicionals al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="6fd9e-112">Informe de facilitat d'ús de les dades d'entrada</span><span class="sxs-lookup"><span data-stu-id="6fd9e-112">Input data usability report</span></span>

<span data-ttu-id="6fd9e-113">L'informe d'ús de dades d'entrada proporciona una visualització consolidada dels errors i advertiments que poden generar les previsions de sèrie.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="6fd9e-114">També recomana com millorar el rendiment del model.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="6fd9e-115">L'informe està disponible quan un model ha finalitzat el procés d'entrenament.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="6fd9e-116">Es crea per a cada model per separat, independentment de si s'ha completat correctament o no.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="6fd9e-117">Actualment, aquesta característica només funciona per al model de cancel·lació de la transacció.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="6fd9e-118">Visualitzar l'informe d'ús de dades d'entrada</span><span class="sxs-lookup"><span data-stu-id="6fd9e-118">View the input data usability report</span></span>

<span data-ttu-id="6fd9e-119">Un cop un model de sèrie ha completat l'entrenament, vegeu-ne l'informe:</span><span class="sxs-lookup"><span data-stu-id="6fd9e-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="6fd9e-120">Seleccioneu les el·lipsis del costat del nom del model i trieu **Informe d'ús de dades d'entrada**.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="6fd9e-121">Seleccioneu l'estat d'un model i seleccioneu **Mostra l'informe d'ús de dades d'entrada** a la subfinestra lateral.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="6fd9e-122">Seleccioneu un dels models de la llista i seleccioneu l'**informe d'ús de dades d'entrada** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="6fd9e-123">Obriu la pàgina de resultats del model i seleccioneu l'**informe d'ús de dades d'entrada** a la barra d'ordres.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="6fd9e-124">Informació de l'informe d'ús de dades d'entrada</span><span class="sxs-lookup"><span data-stu-id="6fd9e-124">Information in the input data usability report</span></span>

<span data-ttu-id="6fd9e-125">Les columnes següents de l'informe contenen informació útil per millorar les dades del model.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemple d'un informe d'ús de dades d'entrada que mostra una taula amb errors, advertiments i recomanacions.":::

- <span data-ttu-id="6fd9e-127">Nom: nom descriptiu de l'error, advertiment o recomanació.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="6fd9e-128">Pas: fase, entrenament o puntuació del model, la informació a la qual fa referència.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="6fd9e-129">Estat: gravetat de la informació (error, advertiment, recomanació).</span><span class="sxs-lookup"><span data-stu-id="6fd9e-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="6fd9e-130">Nom de la columna: columna d'una entitat que cal modificar per millorar el rendiment del model.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="6fd9e-131">Nom de l'entitat: nom de l'entitat que cal modificar per millorar el rendiment del model.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="6fd9e-132">Detalls: detalls sobre l'error, l'advertiment o la recomanació.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="6fd9e-133">Actualitzar una predicció</span><span class="sxs-lookup"><span data-stu-id="6fd9e-133">Refresh a prediction</span></span>

<span data-ttu-id="6fd9e-134">Les prediccions s'actualitzaran automàticament amb la mateixa [planificació d'actualització de les dades](system.md#schedule-tab) definida a la configuració.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="6fd9e-135">Podeu actualitzar-les manualment també.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="6fd9e-136">Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="6fd9e-137">Seleccioneu els tres punts verticals que hi ha al costat de la predicció que voleu actualitzar.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="6fd9e-138">Seleccioneu **Actualitza**.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="6fd9e-139">Suprimir una predicció</span><span class="sxs-lookup"><span data-stu-id="6fd9e-139">Delete a prediction</span></span>

<span data-ttu-id="6fd9e-140">La supressió d'una predicció també comporta la supressió de la seva entitat de sortida.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="6fd9e-141">Aneu a **Intel·ligència** > **Prediccions** i seleccioneu la pestanya **Les meves prediccions**.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="6fd9e-142">Seleccioneu els tres punts verticals que hi ha al costat de la predicció que voleu suprimir.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="6fd9e-143">Seleccioneu **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="6fd9e-143">Select **Delete**.</span></span>
