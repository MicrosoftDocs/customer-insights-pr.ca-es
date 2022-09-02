---
title: Treballar amb les API del Customer Insights
description: Utilitzeu API i enteneu-ne les limitacions.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387328"
---
# <a name="work-with-customer-insights-apis"></a>Treballar amb les API del Customer Insights

El Dynamics 365 Customer Insights proporciona API per crear les vostres pròpies aplicacions basades en les vostres dades al Customer Insights.

> [!IMPORTANT]
> Els detalls d'aquestes API es mostren a la [referència de les API del Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Inclouen informació addicional sobre operacions, paràmetres i respostes.

Proveu API del Customer Insights, creeu un registre d'aplicacions de l'Azure i comenceu a utilitzar biblioteques client.

## <a name="get-started-trying-the-customer-insights-apis"></a>Començar a provar les API del Customer Insights

Activeu les API del Customer Insights i proveu-les. Un administrador del Customer Insights ha d'habilitar l'accés de l'API al Customer Insights. Un cop habilitat l'accés, qualsevol usuari pot utilitzar API amb la clau de subscripció.

1. [Inicieu la sessió](https://home.ci.ai.dynamics.com) al Customer Insights. Si encara no teniu cap subscripció, [registreu-vos per obtenir una versió de prova del Customer Insights](https://aka.ms/tryci).

1. Aneu a **Seguretat d'administració** > **i** seleccioneu la **pestanya API**.

1. Si l'accés de l'API a l'entorn no s'ha configurat, seleccioneu **Habilita**.

   En habilitar les API, es crea una clau de subscripció principal i secundària per a la instància que s'utilitza a les sol·licituds d'API. Per regenerar les claus, seleccioneu regenera primària **o Regenera secundària** a la **pestanya API**.**·**

1. Seleccioneu [**Explora les nostres API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) per provar les API.

1. Cerqueu i seleccioneu una operació d'API i seleccioneu **Prova-la**.

   :::image type="content" source="media/try-api.png" alt-text="Com es proven les API.":::

1. A la subfinestra lateral, definiu el valor al menú desplegable **Autorització** com a **implícita**. La capçalera `Authorization` s'afegeix amb un testimoni de portador. La clau de subscripció s'emplena automàticament.
  
1. També podeu afegir tots els paràmetres de consulta necessaris.

1. Desplaceu-vos fins a la part inferior de la subfinestra lateral i seleccioneu **Envia**.

   La resposta HTTP es mostra a la part inferior de la subfinestra.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Crear un nou registre d'aplicació al portal de l'Azure

Creeu un registre [d'aplicació nou](/graph/auth-register-app-v2) per utilitzar les API del Customer Insights en una aplicació de l'Azure mitjançant permisos delegats.

1. Completeu la [secció](#get-started-trying-the-customer-insights-apis) Introducció.

1. Inicieu la sessió al [portal de l'Azure](https://portal.azure.com) amb el compte que pugui accedir a les dades del Customer Insights.

1. Cerqueu i seleccioneu **Registres d'aplicacions**.

1. Seleccioneu **Nou registre**, proporcioneu un nom per a l'aplicació i trieu el tipus de compte.

   També podeu afegir una adreça URL de redirecció. http://localhost és suficient per desenvolupar una aplicació a l'ordinador local.

1. Seleccioneu **Registra**.

1. Al nou registre de l'aplicació, aneu a **Permisos de l'API**.

1. Seleccioneu **Afegeix un permís** i seleccioneu **Dynamics 365 AI for Customer Insights** a la subfinestra lateral.

1. Per a **Tipus de permís**, seleccioneu **Permisos delegats** i seleccioneu el permís **user_impersonation**.

1. Seleccioneu **Afegeix permisos**.

1. Seleccioneu **Atorga el consentiment de l'administrador per a...** per completar el registre de l'aplicació.

1. Per accedir a l'API sense que un usuari iniciï la sessió, aneu a [Permisos](#server-to-server-application-permissions) d'aplicacions de servidor a servidor.

Podeu utilitzar l'ID d'aplicació/client per a aquest registre d'aplicacions a la [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) per obtenir un testimoni portador per enviar-lo amb la vostra sol·licitud a l'API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Per obtenir informació sobre l'ús de les API de les nostres biblioteques de client, vegeu [Biblioteques de client del Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permisos d'aplicació entre servidors

Creeu un registre d'aplicacions que no necessiti interacció de l'usuari i que es pugui executar en un servidor.

1. Al registre d'aplicacions del portal de l'Azure, aneu a **Permisos de l'API**.

1. Seleccioneu **Afegeix un permís**.

1. Seleccioneu la pestanya **API que utilitza la meva organització** i trieu **IA del Dynamics 365 per al Customer Insights** de la llista.

1. Per a **Tipus de permís**, seleccioneu **Permisos d'aplicació** i seleccioneu el permís **CustomerInsights.Api.All**.

1. Seleccioneu **Afegeix permisos**.

1. Per al registre de l'aplicació, torneu a **Permisos de l'API**.

1. Seleccioneu **Atorga el consentiment de l'administrador per a...** per completar el registre de l'aplicació.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Afegiu el nom del registre de l'aplicació com a usuari al Customer Insights.

   1. Obriu Customer Insights, aneu a Seguretat d'administració **·** > **i** seleccioneu **Afegeix usuaris**.

   1. Cerqueu el nom del registre de l'aplicació, seleccioneu-lo als resultats de la cerca i seleccioneu **Desa**.

## <a name="sample-queries"></a>Consultes d'exemple

Per obtenir una llista breu de consultes d'exemple d'OData per treballar amb les API, vegeu [exemples](odata-examples.md) de consulta d'OData.

## <a name="customer-insights-client-libraries"></a>Biblioteques de client del Customer Insights

Comenceu a utilitzar les biblioteques client disponibles per a les API del Customer Insights. Totes les aplicacions de mostra i de codi font de la biblioteca es poden trobar a la [pàgina de GitHub de Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>NuGet del C#

Utilitzeu les biblioteques client C# de NuGet.org. Actualment, el paquet s'orienta als frameworks netstandard2.0 i netcoreapp2.0. Per obtenir més informació sobre el NuGet paquet, vegeu [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Afegir la biblioteca de client del C# a un projecte del C#

1. Al Visual Studio, obriu l'**Administrador del paquet del NuGet** corresponent al vostre projecte.

1. Cerqueu **Microsoft.Dynamics.CustomerInsights.Api**.

1. Seleccioneu **Instal·la** per afegir el paquet al projecte.

   També podeu executar aquesta ordre a la **consola de l'administrador del paquet del NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Utilitzar la biblioteca de client del C#

1. Utilitzeu la [biblioteca d'autenticació de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) per obtenir un `AccessToken` mitjançant el [registre de l'aplicació de l'Azure](#create-a-new-app-registration-in-the-azure-portal) existent.

1. Després d'autenticar i adquirir amb èxit un testimoni, creeu-ne un de nou o utilitzeu-ne un d'existent `HttpClient` amb l' **"Autorització"** defaultRequestHeaders definit com a **"testimoni d'accés"** i **Ocp-Apim-Subscription-Key** establert a la [**clau** de subscripció des del vostre entorn](#get-started-trying-the-customer-insights-apis) Customer Insights.   

   Restabliu la capçalera d'**Autorització** si escau. Per exemple, quan el testimoni ha caducat.

1. Passeu el `HttpClient` a la creació del client de `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Feu trucades amb el client als "mètodes d'extensió", per exemple `GetAllInstancesAsync`. Si es prefereix l'accés al subjacent `Microsoft.Rest.HttpOperationResponse` , utilitzeu els "mètodes del missatge http", per exemple, `GetAllInstancesWithHttpMessagesAsync`.

1. És probable que `object` la resposta sigui de tipus perquè el mètode pot retornar diversos tipus (per exemple, `IList<InstanceInfo>` i `ApiErrorResult`). Per comprovar el tipus de devolució, utilitzeu els objectes dels tipus de resposta especificats a la pàgina [de detalls de l'API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) per a aquesta operació.

   Si necessiteu més informació sobre la sol·licitud, utilitzeu els **mètodes de missatges http** per accedir a l'objecte de la resposta sense processar.

### <a name="nodejs-package"></a>Paquet NodeJS

Utilitzeu les biblioteques de client NodeJS disponibles a través d'NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paquet Python

Utilitzeu les biblioteques de client Python disponibles a través de Pypi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
