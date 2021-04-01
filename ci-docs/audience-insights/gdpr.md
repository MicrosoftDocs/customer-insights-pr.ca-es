---
title: Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD | MicrosoftDocs
description: Responeu a les sol·licituds de subjecte de dades per a la capacitat de conclusions del públic del Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597499"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="02c6f-103">Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD</span><span class="sxs-lookup"><span data-stu-id="02c6f-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="02c6f-104">Respondre a les sol·licituds de supressió del subjecte de dades del RGPD per a la capacitat de conclusions del públic del Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="02c6f-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="02c6f-105">El "dret a suprimir" les dades personals de les dades del client d'una organització és una protecció clau del Reglament general de protecció de dades (RGPD).</span><span class="sxs-lookup"><span data-stu-id="02c6f-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="02c6f-106">L'eliminació de dades personals inclou l'eliminació de totes les dades personals i registres generats pel sistema, tret de la informació del registre d'auditoria.</span><span class="sxs-lookup"><span data-stu-id="02c6f-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="02c6f-107">Administrar les sol·licituds de supressió de subjectes de dades</span><span class="sxs-lookup"><span data-stu-id="02c6f-107">Manage data subject delete requests</span></span>

<span data-ttu-id="02c6f-108">Les conclusions del públic ofereixen la següent experiència dins del producte per suprimir les dades personals d'un client o usuari específic del Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="02c6f-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="02c6f-109">**Administrar les sol·licituds de supressió de dades de clients**: les dades dels clients del Customer Insights s'ingereixen des de les fonts de dades originals externes al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="02c6f-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="02c6f-110">Totes les sol·licituds de supressió de l'RGPD s'han de dur a terme a la font de dades original.</span><span class="sxs-lookup"><span data-stu-id="02c6f-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="02c6f-111">**Administrar les sol·licituds de supressió de dades d'usuari del Customer Insights**: el Customer Insights crea les dades per als usuaris.</span><span class="sxs-lookup"><span data-stu-id="02c6f-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="02c6f-112">Totes les sol·licituds de supressió de l'RGPD s'han de dur a terme al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="02c6f-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="02c6f-113">Administrar les sol·licituds de supressió de dades de clients</span><span class="sxs-lookup"><span data-stu-id="02c6f-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="02c6f-114">Un administrador del Customer Insights pot seguir aquests passos per suprimir les dades del client que s'havien suprimit a la font de dades:</span><span class="sxs-lookup"><span data-stu-id="02c6f-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="02c6f-115">Inicieu la sessió a Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="02c6f-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="02c6f-116">A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.</span><span class="sxs-lookup"><span data-stu-id="02c6f-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="02c6f-117">Per a cada font de dades de la llista que conté dades dels clients suprimides:</span><span class="sxs-lookup"><span data-stu-id="02c6f-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="02c6f-118">Seleccioneu (...) i després trieu **Actualitza**.</span><span class="sxs-lookup"><span data-stu-id="02c6f-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="02c6f-119">Consulteu l'estat de la font de dades a **Estat**.</span><span class="sxs-lookup"><span data-stu-id="02c6f-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="02c6f-120">Una marca de selecció significa que l'actualització s'ha realitzat correctament.</span><span class="sxs-lookup"><span data-stu-id="02c6f-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="02c6f-121">Un triangle d'advertiment significa que alguna cosa ha anat malament.</span><span class="sxs-lookup"><span data-stu-id="02c6f-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="02c6f-122">Si es mostra un triangle d'advertiment, poseu-vos en contacte amb D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="02c6f-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="02c6f-123">![Gestionar les sol·licituds de l'RGPD de supressió de dades de clients](media/gdpr-data-sources.png "Gestionar les sol·licituds de l'RGPD de supressió de dades de clients")</span><span class="sxs-lookup"><span data-stu-id="02c6f-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="02c6f-124">Administrar les sol·licituds de supressió de dades d'usuaris</span><span class="sxs-lookup"><span data-stu-id="02c6f-124">Manage delete requests for user data</span></span>

<span data-ttu-id="02c6f-125">Un administrador del Customer Insights pot seguir aquests passos per suprimir les dades d'usuari del Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="02c6f-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="02c6f-126">Inicieu la sessió a Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="02c6f-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="02c6f-127">A les conclusions del públic, aneu a **Administració** > **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="02c6f-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="02c6f-128">Activeu la casella de selecció de l'usuari que voleu suprimir.</span><span class="sxs-lookup"><span data-stu-id="02c6f-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="02c6f-129">Seleccioneu **Suprimeix**.</span><span class="sxs-lookup"><span data-stu-id="02c6f-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="02c6f-130">![Gestionar sol·licituds de l'RGPD de supressió de dades d'usuaris](media/gdpr-permissions.png "Gestionar sol·licituds de l'RGPD de supressió de dades d'usuaris")</span><span class="sxs-lookup"><span data-stu-id="02c6f-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="02c6f-131">Respondre a sol·licituds de l'RGPD d'exportació de subjecte de dades</span><span class="sxs-lookup"><span data-stu-id="02c6f-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="02c6f-132">Com a part del nostre compromís d'associar-nos en el vostre viatge cap a l'RGPD (Reglament general de protecció de dades), hem desenvolupat documentació per ajudar-vos a preparar-vos.</span><span class="sxs-lookup"><span data-stu-id="02c6f-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="02c6f-133">En aquesta documentació es descriuen els passos que podeu dur a terme actualment per garantir la conformitat amb el RGPD en utilitzar les conclusions del públic.</span><span class="sxs-lookup"><span data-stu-id="02c6f-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="02c6f-134">Administrar les sol·licituds d'exportació i visualització</span><span class="sxs-lookup"><span data-stu-id="02c6f-134">Manage export and view requests</span></span>

<span data-ttu-id="02c6f-135">El dret de portabilitat de les dades permet als subjectes de dades sol·licitar una còpia de les seves dades personals en un format electrònic (definit com a "format estructurat, d’ús comú, llegible per ordinador i interoperable”) que es pugui transmetre a un altre controlador de dades.</span><span class="sxs-lookup"><span data-stu-id="02c6f-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="02c6f-136">Exportar dades del client (administrador d'inquilins)</span><span class="sxs-lookup"><span data-stu-id="02c6f-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="02c6f-137">Un administrador d'inquilins pot seguir aquests passos per exportar dades:</span><span class="sxs-lookup"><span data-stu-id="02c6f-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="02c6f-138">Envieu un missatge de correu electrònic a D365CI@microsoft.com especificant l'adreça de correu electrònic del client a la sol·licitud.</span><span class="sxs-lookup"><span data-stu-id="02c6f-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="02c6f-139">L'equip del Customer Insights enviarà un missatge de correu electrònic a l'adreça electrònica de l'administrador de l'inquilí registrada demanant la confirmació per exportar les dades.</span><span class="sxs-lookup"><span data-stu-id="02c6f-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="02c6f-140">Reconeixeu la confirmació per exportar les dades del client sol·licitat.</span><span class="sxs-lookup"><span data-stu-id="02c6f-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="02c6f-141">Rebeu les dades exportades a través de l'adreça electrònica de l'administrador d'inquilins.</span><span class="sxs-lookup"><span data-stu-id="02c6f-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="02c6f-142">Exportar dades de l'usuari (administrador de l'inquilí)</span><span class="sxs-lookup"><span data-stu-id="02c6f-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="02c6f-143">Envieu un missatge de correu electrònic a D365CI@microsoft.com especificant l'adreça de correu electrònic de l'usuari a la sol·licitud.</span><span class="sxs-lookup"><span data-stu-id="02c6f-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="02c6f-144">L'equip del Customer Insights enviarà un missatge de correu electrònic a l'adreça electrònica de l'administrador de l'inquilí registrada demanant la confirmació per exportar les dades.</span><span class="sxs-lookup"><span data-stu-id="02c6f-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="02c6f-145">Reconeixeu la confirmació per exportar les dades de l'usuari sol·licitat.</span><span class="sxs-lookup"><span data-stu-id="02c6f-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="02c6f-146">Rebeu les dades exportades a través de l'adreça electrònica de l'administrador d'inquilins.</span><span class="sxs-lookup"><span data-stu-id="02c6f-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]