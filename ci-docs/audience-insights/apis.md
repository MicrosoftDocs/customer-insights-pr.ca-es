---
title: Treballar amb API
description: Utilitzeu API i enteneu-ne les limitacions.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 4d41d7d328dfa6699b5f5e992d3a5bf3179490d8
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016580"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="343eb-103">Treballar amb les API del Customer Insights</span><span class="sxs-lookup"><span data-stu-id="343eb-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="343eb-104">Dynamics 365 Customer Insights inclou API per crear les vostres pròpies aplicacions basades en dades del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="343eb-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="343eb-105">Els detalls d'aquestes API es mostren a la [referència de les API del Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="343eb-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="343eb-106">Inclouen informació addicional sobre operacions, paràmetres i respostes.</span><span class="sxs-lookup"><span data-stu-id="343eb-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="343eb-107">Feu servir aquest article com a guia per accedir a les API del Customer Insights, crear un registre d'aplicacions de l'Azure i començar a utilitzar les biblioteques de client disponibles.</span><span class="sxs-lookup"><span data-stu-id="343eb-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="343eb-108">Començar a provar les API del Customer Insights</span><span class="sxs-lookup"><span data-stu-id="343eb-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="343eb-109">[Inicieu la sessió](https://home.ci.ai.dynamics.com) al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="343eb-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="343eb-110">Si encara no teniu cap subscripció, [registreu-vos per obtenir una versió de prova del Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="343eb-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="343eb-111">Per habilitar les API a l'entorn del Customer Insights, aneu a **Administració** > **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="343eb-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="343eb-112">Per poder fer-ho, necessitareu permisos d'administració.</span><span class="sxs-lookup"><span data-stu-id="343eb-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="343eb-113">Aneu a la pestanya **API** i seleccioneu el botó **Habilita**.</span><span class="sxs-lookup"><span data-stu-id="343eb-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="343eb-114">En habilitar les API, es crea una clau de subscripció principal i secundària per a la instància que s'utilitza a les sol·licituds d'API.</span><span class="sxs-lookup"><span data-stu-id="343eb-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="343eb-115">Per tornar a generar les claus, seleccioneu **Torna a generar la principal** o **Torna a generar la secundària** a **Administració** > **Permisos** > **API**.</span><span class="sxs-lookup"><span data-stu-id="343eb-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Habilitar API del Customer Insights":::

1. <span data-ttu-id="343eb-117">Seleccioneu **Exploreu les nostres API** per [provar les API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="343eb-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="343eb-118">Trieu una operació d'API i seleccioneu **Proveu-ho**.</span><span class="sxs-lookup"><span data-stu-id="343eb-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="343eb-119">A la subfinestra lateral, definiu el valor del menú desplegable **Autorització** com a **implícit**.</span><span class="sxs-lookup"><span data-stu-id="343eb-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="343eb-120">S'afegeix a un testimoni del portador a la capçalera `Authorization`.</span><span class="sxs-lookup"><span data-stu-id="343eb-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="343eb-121">La clau de subscripció s'emplenarà automàticament.</span><span class="sxs-lookup"><span data-stu-id="343eb-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="343eb-122">També podeu afegir tots els paràmetres de consulta necessaris.</span><span class="sxs-lookup"><span data-stu-id="343eb-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="343eb-123">Desplaceu-vos fins a la part inferior de la subfinestra lateral i seleccioneu **Envia**.</span><span class="sxs-lookup"><span data-stu-id="343eb-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="343eb-124">La resposta HTTP apareixerà aviat tot seguit.</span><span class="sxs-lookup"><span data-stu-id="343eb-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Gif animat que mostra com seleccionar les API de prova.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="343eb-126">Crear un nou registre d'aplicació al portal de l'Azure</span><span class="sxs-lookup"><span data-stu-id="343eb-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="343eb-127">Amb aquests passos, podreu començar a utilitzar les API del Customer Insights en una aplicació de l'Azure mitjançant els permisos delegats.</span><span class="sxs-lookup"><span data-stu-id="343eb-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="343eb-128">Assegureu-vos que heu completat primer la [secció Com començar](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="343eb-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="343eb-129">Inicieu la sessió al [portal de l'Azure](https://portal.azure.com) amb el compte que pugui accedir a les dades del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="343eb-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="343eb-130">A l'esquerra, seleccioneu **Registres de l'aplicació**.</span><span class="sxs-lookup"><span data-stu-id="343eb-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="343eb-131">Seleccioneu **Nou registre**, proporcioneu un nom per a l'aplicació i trieu el tipus de compte.</span><span class="sxs-lookup"><span data-stu-id="343eb-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="343eb-132">També podeu afegir una adreça URL de redirecció.</span><span class="sxs-lookup"><span data-stu-id="343eb-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="343eb-133">http://localhost és suficient per desenvolupar una aplicació a l'ordinador local.</span><span class="sxs-lookup"><span data-stu-id="343eb-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="343eb-134">Al nou registre de l'aplicació, aneu a **Permisos de l'API**.</span><span class="sxs-lookup"><span data-stu-id="343eb-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Gif animat per definir el permís de l'API al registre de l'aplicació.":::

1. <span data-ttu-id="343eb-136">Seleccioneu **Afegeix un permís** i seleccioneu **Customer Insights** a la subfinestra lateral.</span><span class="sxs-lookup"><span data-stu-id="343eb-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="343eb-137">Com a **Tipus de permís**, seleccioneu **Permisos delegats** i seleccioneu el permís **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="343eb-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="343eb-138">Seleccioneu **Afegeix permisos**.</span><span class="sxs-lookup"><span data-stu-id="343eb-138">Select **Add permissions**.</span></span> <span data-ttu-id="343eb-139">Si heu d'accedir a l'API sense que cap usuari iniciï la sessió, reviseu la secció [Permisos d'aplicació entre servidors](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="343eb-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="343eb-140">Seleccioneu **Atorga el consentiment de l'administrador per a...** per completar el registre de l'aplicació.</span><span class="sxs-lookup"><span data-stu-id="343eb-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="343eb-141">Podeu utilitzar l'identificador de l'aplicació o del client per a aquest registre de l'aplicació amb la biblioteca d'autenticació de Microsoft (MSAL) per obtenir un testimoni del portador que pugueu enviar amb la vostra sol·licitud a l'API.</span><span class="sxs-lookup"><span data-stu-id="343eb-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Gif animat per atorgar el consentiment d'administrador.":::

<span data-ttu-id="343eb-143">Per obtenir més informació sobre MSAL, vegeu la [informació general sobre la biblioteca d'autenticació de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="343eb-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="343eb-144">Per obtenir més informació sobre el registre d'aplicacions a l'Azure, vegeu [l'experiència de registre de noves aplicacions del portal de l'Azure](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="343eb-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="343eb-145">Per obtenir informació sobre com utilitzar les API de les biblioteques de client, vegeu [Biblioteques de client del Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="343eb-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="343eb-146">Permisos d'aplicació entre servidors</span><span class="sxs-lookup"><span data-stu-id="343eb-146">Server-to-server application permissions</span></span>

<span data-ttu-id="343eb-147">A la [secció de registre d'aplicacions](#create-a-new-app-registration-in-the-azure-portal) es descriu com registrar una aplicació que requereix que un usuari hi iniciï la sessió com a mètode d'autenticació.</span><span class="sxs-lookup"><span data-stu-id="343eb-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="343eb-148">Informeu-vos sobre com crear un registre d'aplicacions que no necessiti la interacció de l'usuari i que es pugui executar en un servidor.</span><span class="sxs-lookup"><span data-stu-id="343eb-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="343eb-149">Al registre d'aplicacions del portal de l'Azure, aneu a **Permisos de l'API**.</span><span class="sxs-lookup"><span data-stu-id="343eb-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="343eb-150">Seleccioneu **Afegeix un permís**.</span><span class="sxs-lookup"><span data-stu-id="343eb-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="343eb-151">Seleccioneu la pestanya **API que utilitza la meva organització** i trieu **IA del Dynamics 365 per al Customer Insights** de la llista.</span><span class="sxs-lookup"><span data-stu-id="343eb-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="343eb-152">Com a **Tipus de permís**, seleccioneu **Permisos de l'aplicació** i seleccioneu el permís **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="343eb-152">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="343eb-153">Seleccioneu **Afegeix permisos**.</span><span class="sxs-lookup"><span data-stu-id="343eb-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="343eb-154">Per al registre de l'aplicació, torneu a **Permisos de l'API**.</span><span class="sxs-lookup"><span data-stu-id="343eb-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="343eb-155">Seleccioneu **Atorga el consentiment de l'administrador per a...** per completar el registre de l'aplicació.</span><span class="sxs-lookup"><span data-stu-id="343eb-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Gif animat per atorgar el consentiment d'administrador.":::

1. <span data-ttu-id="343eb-157">Per acabar, cal afegir el nom del registre de l'aplicació com a usuari al Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="343eb-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="343eb-158">Obriu Customer Insights, aneu a **Administració** > **Permisos** i seleccioneu **Afegeix un usuari**.</span><span class="sxs-lookup"><span data-stu-id="343eb-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="343eb-159">Cerqueu el nom del registre de l'aplicació, seleccioneu-lo als resultats de la cerca i seleccioneu **Desa**.</span><span class="sxs-lookup"><span data-stu-id="343eb-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="343eb-160">Biblioteques de client del Customer Insights</span><span class="sxs-lookup"><span data-stu-id="343eb-160">Customer Insights client libraries</span></span>

<span data-ttu-id="343eb-161">Amb aquesta secció, podreu començar a utilitzar les biblioteques de client que hi ha disponibles per a les API del Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="343eb-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="343eb-162">Totes les aplicacions de mostra i de codi font de la biblioteca es poden trobar a la [pàgina de GitHub de Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="343eb-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="343eb-163">NuGet del C#</span><span class="sxs-lookup"><span data-stu-id="343eb-163">C# NuGet</span></span>

<span data-ttu-id="343eb-164">Per obtenir informació sobre com començar a utilitzar les biblioteques de client del C#, aneu a NuGet.org. Per obtenir més informació sobre el paquet de NuGet, vegeu [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="343eb-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="343eb-165">Actualment, aquest paquet té està destinat als marcs netstandard 2.0 i netcoreapp 2.0.</span><span class="sxs-lookup"><span data-stu-id="343eb-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="343eb-166">Afegir la biblioteca de client del C# a un projecte del C#</span><span class="sxs-lookup"><span data-stu-id="343eb-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="343eb-167">Al Visual Studio, obriu l'**Administrador del paquet del NuGet** corresponent al vostre projecte.</span><span class="sxs-lookup"><span data-stu-id="343eb-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="343eb-168">Cerqueu **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="343eb-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="343eb-169">Seleccioneu **Instal·la** per afegir el paquet al projecte.</span><span class="sxs-lookup"><span data-stu-id="343eb-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="343eb-170">També podeu executar aquesta ordre a la **consola de l'administrador del paquet del NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="343eb-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Afegir el paquet del NuGet al projecte del Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="343eb-172">Utilitzar la biblioteca de client del C#</span><span class="sxs-lookup"><span data-stu-id="343eb-172">Use the C# client library</span></span>

1. <span data-ttu-id="343eb-173">Utilitzeu la [biblioteca d'autenticació de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) per obtenir un `AccessToken` mitjançant el [registre de l'aplicació de l'Azure](#create-a-new-app-registration-in-the-azure-portal) existent.</span><span class="sxs-lookup"><span data-stu-id="343eb-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="343eb-174">Un cop us hagueu autenticat correctament i hagueu obtingut un testimoni, creeu un nou `HttpClient` o feu-ne servir un d'existent amb l'**"Autorització" de DefaultRequestHeaders** addicional definida com a **<access token> portador** i la **Ocp-Apim-Subscription-Key** definida com a [**clau de subscripció** des de l'entorn del Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="343eb-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="343eb-175">Restabliu la capçalera d'**Autorització** si escau.</span><span class="sxs-lookup"><span data-stu-id="343eb-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="343eb-176">Per exemple, quan el testimoni ha caducat.</span><span class="sxs-lookup"><span data-stu-id="343eb-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="343eb-177">Passeu el `HttpClient` a la creació del client de `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="343eb-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Exemple d'httpclient":::

1. <span data-ttu-id="343eb-179">Feu trucades amb el client als "mètodes d'extensió", per exemple `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="343eb-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="343eb-180">Si es preferia l'accés al subjacent `Microsoft.Rest.HttpOperationResponse`, utilitzeu els "mètodes de missatges http", per exemple `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="343eb-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="343eb-181">La resposta serà probablement de tipus `object` perquè el mètode pot retornar diversos tipus (per exemple, `IList<InstanceInfo>` i `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="343eb-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="343eb-182">Per comprovar el tipus de retorn, podeu convertir de manera segura els objectes en els tipus de resposta especificats a la [pàgina de detalls de l'API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) corresponent a aquesta operació.</span><span class="sxs-lookup"><span data-stu-id="343eb-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="343eb-183">Si necessiteu més informació sobre la sol·licitud, utilitzeu els **mètodes de missatges http** per accedir a l'objecte de la resposta sense processar.</span><span class="sxs-lookup"><span data-stu-id="343eb-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="343eb-184">Paquet NodeJS</span><span class="sxs-lookup"><span data-stu-id="343eb-184">NodeJS package</span></span>

<span data-ttu-id="343eb-185">Utilitzeu les biblioteques de client NodeJS disponibles a través d'NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="343eb-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="343eb-186">Paquet Python</span><span class="sxs-lookup"><span data-stu-id="343eb-186">Python package</span></span>

<span data-ttu-id="343eb-187">Utilitzeu les biblioteques de client Python disponibles a través de Pypi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="343eb-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
