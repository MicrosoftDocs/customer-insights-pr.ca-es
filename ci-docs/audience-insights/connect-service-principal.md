---
title: Connectar-se a un compte de l'Azure Data Lake Storage mitjançant una entitat de seguretat de servei
description: Utilitzeu una entitat de seguretat de servei de l'Azure per connectar-vos al vostre llac de dades.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: faef3583337fd495e7baf40b0a208f1d9f10281a
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900231"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Connectar-se a un compte de l'Azure Data Lake Storage mitjançant una entitat de seguretat de servei de l'Azure

En aquest article es discuteix com connectar-se Dynamics 365 Customer Insights amb un compte mitjançant un principal de servei de Azure Data Lake Storage l'Azure en lloc de claus de compte d'emmagatzematge. 

Les eines automatitzades que utilitzen serveis de l'Azure sempre hauran de tenir permisos restringits. En comptes d'iniciar la sessió a les aplicacions com a usuari amb tots els privilegis, l'Azure ofereix entitats de servei. Podeu utilitzar els principis de servei per afegir o editar de manera segura [una carpeta del Model de dades comú com a font de dades o crear o actualitzar un](connect-common-data-model.md)[entorn](create-environment.md).

> [!IMPORTANT]
> - El compte del Data Lake Storage que utilitzarà l'entitat de servei ha de tenir [habilitat l'espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace).
> - Necessiteu permisos d'administració per a la vostra subscripció de l'Azure per crear un principal de servei.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crear una entitat de seguretat de servei de l'Azure per al Customer Insights

Abans de crear un nou principi de servei per al Customer Insights, comproveu si ja existeix a la vostra organització.

### <a name="look-for-an-existing-service-principal"></a>Cercar una entitat de servei existent

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com) i inicieu-hi la sessió a la vostra organització.

2. A **Serveis de l'Azure**, seleccioneu **Azure Active Directory**.

3. A **Administra**, seleccioneu **Aplicacions empresarials**.

4. Cerqueu l'ID de l'aplicació de Microsoft:
   - Conclusions del públic: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` amb el nom `Dynamics 365 AI for Customer Insights`
   - Conclusions d'interacció: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` amb el nom `Dynamics 365 AI for Customer Insights engagement insights`

5. Si trobeu un registre coincident, significa que l'entitat de seguretat de servei ja existeix. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que mostra un entitat de seguretat de servei existent.":::
   
6. Si no es retorna cap resultat, creeu una nova entitat de servei.

>[!NOTE]
>Per utilitzar totes les funcionalitats del Dynamics 365 Customer Insights, suggerim que afegiu ambdues aplicacions a l'entitat de seguretat de servei.

### <a name="create-a-new-service-principal"></a>Crear una nova entitat de servei

1. Instal·leu la versió més recent del PowerShell de l'Azure Active Directory per al Graph. Per obtenir més informació, aneu a [Instal·lació del PowerShell de l'Azure Active Directory per al Graph](/powershell/azure/active-directory/install-adv2).

   1. A l'ordinador, seleccioneu la tecla del Windows al teclat, cerqueu el **Windows PowerShell** i seleccioneu **Executa com a administrador**.
   
   1. A la finestra del PowerShell que s'obre, introduïu `Install-Module AzureAD`.

2. Creeu l'entitat de seguretat de servei per al Customer Insights amb el mòdul del PowerShell de l'Azure AD.

   1. A la finestra del PowerShell introduïu `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Substituïu l'*[identificador d'inquilí]* per l'identificador real del vostre inquilí on voleu crear l'entitat de servei. El paràmetre del nom de l'entorn, `AzureEnvironmentName`, és opcional.
  
   1. Introduïu `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Amb aquesta ordre es crea l'entitat de servei per a les conclusions del públic a l'inquilí seleccionat. 

   1. Introduïu `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Aquesta ordre crea l'entitat de servei de seguretat per a les conclusions d'interacció de l'inquilí seleccionat.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Concedir permisos a l'entitat de servei per accedir al compte d'emmagatzematge

Aneu al portal de l'Azure per concedir permisos a l'entitat de servei del compte d'emmagatzematge que voleu utilitzar a les conclusions del públic.

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com) i inicieu-hi la sessió a la vostra organització.

1. Obriu el compte d'emmagatzematge al qual voleu que tingui accés l'entitat de servei per a les conclusions del públic.

1. A la subfinestra esquerra, seleccioneu **Control d'accés (IAM)** i, a continuació, seleccioneu **Afegeix** > **Afegeix una assignació de funcions**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que mostra el portal de l'Azure mentre afegiu una assignació de funcions.":::

1. A la subfinestra **Afegeix una assignació de funcions**, definiu les propietats següents:
   - Funció: **Col·laborador de dades de Blob d'emmagatzematge**
   - Assignació d'accés a: **Usuari, grup o entitat de servei**
   - Seleccioneu **Dynamics 365 AI for Customer Insights** i **Dynamics 365 AI for Customer Insights engagement insights** (les dues [entitats de seguretat de servei](#create-a-new-service-principal) que heu creat abans en aquest procediment)

1.  Seleccioneu **Desa**.

La propagació dels canvis pot trigar fins a 15 minuts.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Introduïu l'identificador de recurs de l'Azure o els detalls de subscripció de l'Azure al fitxer adjunt del compte d'emmagatzematge de les conclusions del públic.

Podeu adjuntar un compte del Data Lake Storage a les conclusions del públic per [ emmagatzemar-hi dades de sortida](manage-environments.md) o [utilitzar-lo com a font de dades ](connect-common-data-service-lake.md). Aquesta opció us permet triar entre un mètode basat en recursos o un mètode basat en subscripció. Segons l'enfocament que trieu, seguiu el procediment d'una de les seccions següents.

### <a name="resource-based-storage-account-connection"></a>Connexió al compte d'emmagatzematge basat en recursos

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com), inicieu la sessió a la vostra subscripció i obriu el compte d'emmagatzematge.

1. A la subfinestra esquerra, aneu a **Configuració** > **Propietats**.

1. Copieu el valor de l'identificador de recurs del compte d'emmagatzematge.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copieu l'identificador de recurs del compte d'emmagatzematge.":::

1. A les conclusions del públic, inseriu l'ID del recurs al camp del recurs que es mostra a la pantalla de connexió del compte d'emmagatzematge.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduïu la informació de l'identificador de recurs del compte d'emmagatzematge.":::   

1. Continueu amb els passos restants a les conclusions del públic per adjuntar el compte d'emmagatzematge.

### <a name="subscription-based-storage-account-connection"></a>Connexió al compte d'emmagatzematge basat en subscripcions

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com), inicieu la sessió a la vostra subscripció i obriu el compte d'emmagatzematge.

1. A la subfinestra esquerra, aneu a **Configuració** > **Propietats**.

1. Reviseu la **Subscripció**, el **Grup de recursos** i el **Nom** del compte d'emmagatzematge per assegurar-vos de seleccionar els valors adequats a les conclusions del públic.

1. A les conclusions del públic, trieu els valors dels camps corresponents quan adjunteu el compte d'emmagatzematge.

1. Continueu amb els passos restants a les conclusions del públic per adjuntar el compte d'emmagatzematge.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
