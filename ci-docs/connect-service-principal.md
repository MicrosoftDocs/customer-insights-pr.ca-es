---
title: Connectar-se a un compte de l'Azure Data Lake Storage mitjançant una entitat de seguretat de servei
description: Utilitzeu una entitat de seguretat de servei de l'Azure per connectar-vos al vostre llac de dades.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642275"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Connectar-se a un compte de l'Azure Data Lake Storage mitjançant una entitat de seguretat de servei de l'Azure

En aquest article es discuteix com connectar-se Dynamics 365 Customer Insights amb un Azure Data Lake Storage compte mitjançant un principal de servei de l'Azure en lloc de claus de compte d'emmagatzematge. 

Les eines automatitzades que utilitzen serveis de l'Azure sempre hauran de tenir permisos restringits. En comptes d'iniciar la sessió a les aplicacions com a usuari amb tots els privilegis, l'Azure ofereix entitats de servei. Podeu utilitzar els principals de servei per afegir o editar de manera [segura una carpeta del Model de dades comú com a font de dades](connect-common-data-model.md) o [crear o actualitzar un entorn](create-environment.md).

> [!IMPORTANT]
> - El compte d'emmagatzematge del llac de dades que utilitzarà el principal del servei ha de ser Gen2 i tenir [habilitat l'espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace). Els comptes d'emmagatzematge de l'Azure Data Lake Gen1 no són compatibles.
> - Necessiteu permisos d'administració per a la vostra subscripció de l'Azure per crear un principal de servei.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crear una entitat de seguretat de servei de l'Azure per al Customer Insights

Abans de crear un nou principi de servei per al Customer Insights, comproveu si ja existeix a la vostra organització.

### <a name="look-for-an-existing-service-principal"></a>Cercar una entitat de servei existent

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com) i inicieu-hi la sessió a la vostra organització.

2. A **Serveis de l'Azure**, seleccioneu **Azure Active Directory**.

3. A **Administra**, seleccioneu **Aplicacions empresarials**.

4. Cerqueu l'identificador `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` de l'aplicació de Microsoft amb el nom `Dynamics 365 AI for Customer Insights`.

5. Si trobeu un registre coincident, significa que l'entitat de seguretat de servei ja existeix. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que mostra un entitat de seguretat de servei existent.":::
   
6. Si no es retorna cap resultat, creeu una nova entitat de servei.

### <a name="create-a-new-service-principal"></a>Crear una nova entitat de servei

1. Instal·leu la versió més recent del PowerShell de l'Azure Active Directory per al Graph. Per obtenir més informació, aneu a [Instal·lació del PowerShell de l'Azure Active Directory per al Graph](/powershell/azure/active-directory/install-adv2).

   1. A l'ordinador, seleccioneu la tecla del Windows al teclat, cerqueu el **Windows PowerShell** i seleccioneu **Executa com a administrador**.
   
   1. A la finestra del PowerShell que s'obre, introduïu `Install-Module AzureAD`.

2. Creeu l'entitat de seguretat de servei per al Customer Insights amb el mòdul del PowerShell de l'Azure AD.

   1. A la finestra del PowerShell introduïu `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Substituïu *[el vostre identificador de directori]* per l'identificador de directori real de la vostra subscripció a l'Azure on voleu crear el principal de servei. El paràmetre del nom de l'entorn, `AzureEnvironmentName`, és opcional.
  
   1. Introduïu `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Aquesta ordre crea la principal de servei del Customer Insights a la subscripció seleccionada de l'Azure. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Concedir permisos a l'entitat de servei per accedir al compte d'emmagatzematge

Aneu al portal de l'Azure per concedir permisos al principal de servei del compte d'emmagatzematge que voleu utilitzar al Customer Insights.

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com) i inicieu-hi la sessió a la vostra organització.

1. Obriu el compte d'emmagatzematge al qual voleu que tingui accés el principal de servei del Customer Insights.

1. A la subfinestra esquerra, seleccioneu **Control d'accés (IAM)** i, a continuació, seleccioneu **Afegeix** > **Afegeix una assignació de funcions**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que mostra el portal de l'Azure mentre afegiu una assignació de funcions.":::

1. A la subfinestra **Afegeix una assignació de funcions**, definiu les propietats següents:
   - Funció: **Col·laborador de dades de Blob d'emmagatzematge**
   - Assignació d'accés a: **Usuari, grup o entitat de servei**
   - Seleccioneu membres: **Dynamics 365 AI for Customer Insights** (el principal de [servei](#create-a-new-service-principal) que heu creat anteriorment en aquest procediment)

1.  Seleccioneu **Revisa + assigna**.

La propagació dels canvis pot trigar fins a 15 minuts.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Introduïu l'identificador de recurs de l'Azure o els detalls de la subscripció de l'Azure al fitxer adjunt del compte d'emmagatzematge al Customer Insights

Podeu adjuntar un compte d'emmagatzematge del llac de dades a l'Insights del client per [emmagatzemar dades](manage-environments.md) de sortida o [utilitzar-les com a font de dades](connect-dataverse-managed-lake.md). Aquesta opció us permet triar entre un mètode basat en recursos o un mètode basat en subscripció. Segons l'enfocament que trieu, seguiu el procediment d'una de les seccions següents.

### <a name="resource-based-storage-account-connection"></a>Connexió al compte d'emmagatzematge basat en recursos

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com), inicieu la sessió a la vostra subscripció i obriu el compte d'emmagatzematge.

1. A la subfinestra esquerra, aneu a **Configuració** > **Propietats**.

1. Copieu el valor de l'identificador de recurs del compte d'emmagatzematge.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copieu l'identificador de recurs del compte d'emmagatzematge.":::

1. Al Customer Insights, inseriu l'identificador de recurs al camp de recursos que es mostra a la pantalla de connexió del compte d'emmagatzematge.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduïu la informació de l'identificador de recurs del compte d'emmagatzematge.":::   

1. Continueu amb els passos restants de Customer Insights per adjuntar el compte d'emmagatzematge.

### <a name="subscription-based-storage-account-connection"></a>Connexió al compte d'emmagatzematge basat en subscripcions

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com), inicieu la sessió a la vostra subscripció i obriu el compte d'emmagatzematge.

1. A la subfinestra esquerra, aneu a **Configuració** > **Propietats**.

1. Reviseu la subscripció, el **grup** de recursos i el **nom** del compte d'emmagatzematge per assegurar-vos que seleccioneu els valors adequats a l'Insights **del client.**

1. Al Customer Insights, trieu els valors dels camps corresponents en adjuntar el compte d'emmagatzematge.

1. Continueu amb els passos restants de Customer Insights per adjuntar el compte d'emmagatzematge.


[!INCLUDE [footer-include](includes/footer-banner.md)]