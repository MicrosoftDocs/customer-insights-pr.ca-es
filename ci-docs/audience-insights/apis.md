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
ms.openlocfilehash: 7201ed9e5315d73e6b9c25b4bc4c4e4ed839a215
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732252"
---
# <a name="work-with-customer-insights-apis"></a>Treballar amb les API del Customer Insights

Dynamics 365 Customer Insights proporciona API per construir les vostres pròpies aplicacions basades en les vostres dades a Customer Insights.

> [!IMPORTANT]
> Els detalls d'aquestes API es mostren a la [referència de les API del Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Inclouen informació addicional sobre operacions, paràmetres i respostes.

En aquest article es descriu com accedir a les API del Customer Insights, crear un registre de l'aplicació de l'Azure i començar a utilitzar les biblioteques de client disponibles.

## <a name="get-started-trying-the-customer-insights-apis"></a>Començar a provar les API del Customer Insights

1. [Inicieu la sessió](https://home.ci.ai.dynamics.com) al Customer Insights. Si encara no teniu cap subscripció, [registreu-vos per obtenir una versió de prova del Customer Insights](https://aka.ms/tryci).

1. Per habilitar les API a l'entorn del Customer Insights, aneu a **Administració** > **Permisos**. Per poder fer-ho, necessitareu permisos d'administració.

1. Aneu a la pestanya **API** i seleccioneu el botó **Habilita**.    
 
   En habilitar les API, es crea una clau de subscripció principal i secundària per a la instància que s'utilitza a les sol·licituds d'API. Per tornar a generar les claus, seleccioneu **Torna a generar la principal** o **Torna a generar la secundària** a **Administració** > **Permisos** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Habilitar API del Customer Insights.":::

1. Seleccioneu **Exploreu les nostres API** per [provar les API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Trieu una operació d'API i seleccioneu **Proveu-ho**.

1. A la subfinestra lateral, definiu el valor al menú desplegable **Autorització** com a **implícita**. La capçalera `Authorization` s'afegeix amb un testimoni de portador. La clau de subscripció s'emplenarà automàticament.
  
1. També podeu afegir tots els paràmetres de consulta necessaris.

1. Desplaceu-vos fins a la part inferior de la subfinestra lateral i seleccioneu **Envia**.

La resposta HTTP apareixerà aviat tot seguit.

   :::image type="content" source="media/try-apis.gif" alt-text="Com es proven les API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Crear un nou registre d'aplicació al portal de l'Azure

Aquests passos us ajuden a començar a utilitzar les API del Customer Insights en una aplicació de l'Azure utilitzant permisos delegats. Assegureu-vos de completar primer la [secció Introducció](#get-started-trying-the-customer-insights-apis).

1. Inicieu la sessió al [portal de l'Azure](https://portal.azure.com) amb el compte que pugui accedir a les dades del Customer Insights.

1. A l'esquerra, seleccioneu **Registres de l'aplicació**.

1. Seleccioneu **Nou registre**, proporcioneu un nom per a l'aplicació i trieu el tipus de compte.
 
   També podeu afegir una adreça URL de redirecció. http://localhost és suficient per desenvolupar una aplicació a l'ordinador local.

1. Al nou registre de l'aplicació, aneu a **Permisos de l'API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Com es defineixen els permisos de l'API al registre de l'aplicació.":::

1. Seleccioneu **Afegeix un permís** i seleccioneu **Customer Insights** a la subfinestra lateral.

1. Per a **Tipus de permís**, seleccioneu **Permisos delegats** i seleccioneu el permís **user_impersonation**.

1. Seleccioneu **Afegeix permisos**. Si heu d'accedir a l'API sense que cap usuari iniciï la sessió, reviseu la secció [Permisos d'aplicació entre servidors](#server-to-server-application-permissions).

1. Seleccioneu **Atorga el consentiment de l'administrador per a...** per completar el registre de l'aplicació.

Podeu utilitzar l'identificador de l'aplicació o del client per a aquest registre de l'aplicació amb la biblioteca d'autenticació de Microsoft (MSAL) per obtenir un testimoni del portador que pugueu enviar amb la vostra sol·licitud a l'API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Com atorgar el consentiment d'administració.":::

Per obtenir més informació sobre MSAL, vegeu la [informació general sobre la biblioteca d'autenticació de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Per obtenir més informació sobre el registre de l'aplicació a l'Azure, vegeu [Registrar una aplicació](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Per obtenir informació sobre l'ús de les API de les nostres biblioteques de client, vegeu [Biblioteques de client del Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permisos d'aplicació entre servidors

A la [secció de registre d'aplicacions](#create-a-new-app-registration-in-the-azure-portal) es descriu com registrar una aplicació que requereix que un usuari hi iniciï la sessió com a mètode d'autenticació. Informeu-vos sobre com crear un registre d'aplicacions que no necessiti la interacció de l'usuari i que es pugui executar en un servidor.

1. Al registre d'aplicacions del portal de l'Azure, aneu a **Permisos de l'API**.

1. Seleccioneu **Afegeix un permís**. 

1. Seleccioneu la pestanya **API que utilitza la meva organització** i trieu **IA del Dynamics 365 per al Customer Insights** de la llista. 

1. Per a **Tipus de permís**, seleccioneu **Permisos d'aplicació** i seleccioneu el permís **CustomerInsights.Api.All**.

1. Seleccioneu **Afegeix permisos**.

1. Per al registre de l'aplicació, torneu a **Permisos de l'API**.

1. Seleccioneu **Atorga el consentiment de l'administrador per a...** per completar el registre de l'aplicació.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Com atorgar el consentiment d'administració.":::

1. Per acabar, cal afegir el nom del registre de l'aplicació com a usuari al Customer Insights.  
   
   Obriu Customer Insights, aneu a **Administració** > **Permisos** i seleccioneu **Afegeix un usuari**.

1. Cerqueu el nom del registre de l'aplicació, seleccioneu-lo als resultats de la cerca i seleccioneu **Desa**.

## <a name="customer-insights-client-libraries"></a>Biblioteques de client del Customer Insights

Amb aquesta secció, podreu començar a utilitzar les biblioteques de client que hi ha disponibles per a les API del Customer Insights. Totes les aplicacions de mostra i de codi font de la biblioteca es poden trobar a la [pàgina de GitHub de Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Obteniu informació sobre com podeu començar a utilitzar les biblioteques de clients C# de NuGet.org. Per obtenir més informació sobre el paquet NuGet, vegeu [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Actualment, aquest paquet té està destinat als marcs netstandard 2.0 i netcoreapp 2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Afegir la biblioteca de client del C# a un projecte del C#

1. A Visual Studio, obriu el **gestor de paquets NuGet per al vostre** projecte.

1. Cerqueu **Microsoft.Dynamics.CustomerInsights.Api**.

1. Seleccioneu **Instal·la** per afegir el paquet al projecte.
 
   Alternativament, executeu aquesta ordre a la **consola gestora de paquets** NuGet:`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Afegiu NuGet paquet al projecte Visual Studio.":::

#### <a name="use-the-c-client-library"></a>Utilitzar la biblioteca de client del C#

1. Utilitzeu la [biblioteca d'autenticació de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) per obtenir un `AccessToken` mitjançant el [registre de l'aplicació de l'Azure](#create-a-new-app-registration-in-the-azure-portal) existent.

1. Després d'autenticar i adquirir amb èxit un testimoni, construir un nou o utilitzar un existent `HttpClient` amb **l'"Autorització" de DefaultRequestHeaders addicional** a **Bearer "testimoni d'accés"** i **Ocp-Apim-Subscription-Key** establert a la clau de [**subscripció** des de l'entorn Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Restabliu la capçalera d'**Autorització** si escau. Per exemple, quan el testimoni ha caducat.

1. Passeu el `HttpClient` a la creació del client de `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Exemple d'httpclient.":::

1. Feu trucades amb el client als "mètodes d'extensió", per exemple `GetAllInstancesAsync`. Si es preferia l'accés al subjacent `Microsoft.Rest.HttpOperationResponse`, utilitzeu els "mètodes de missatges http", per exemple `GetAllInstancesWithHttpMessagesAsync`.

1. La resposta serà probablement de tipus `object` perquè el mètode pot retornar diversos tipus (per exemple, `IList<InstanceInfo>` i `ApiErrorResult`). Per comprovar el tipus de retorn, podeu convertir de manera segura els objectes en els tipus de resposta especificats a la [pàgina de detalls de l'API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) corresponent a aquesta operació.    
   
   Si necessiteu més informació sobre la sol·licitud, utilitzeu els **mètodes de missatges http** per accedir a l'objecte de la resposta sense processar.

### <a name="nodejs-package"></a>Paquet NodeJS

Utilitzeu les biblioteques de client NodeJS disponibles a través d'NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paquet Python

Utilitzeu les biblioteques de client Python disponibles a través de Pypi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
