---
title: Connectar-se a un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei
description: Utilitzeu una entitat de servei de l'Azure per a les conclusions del públic per connectar-vos al vostre llac de dades propi quan l'adjunteu a les conclusions del públic.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267710"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Connectar-se a un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure per a les conclusions del públic

Les eines automatitzades que utilitzen serveis de l'Azure sempre hauran de tenir permisos restringits. En comptes d'iniciar la sessió a les aplicacions com a usuari amb tots els privilegis, l'Azure ofereix entitats de servei. Seguiu llegint per obtenir més informació sobre com connectar les conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage mitjançant una entitat de servei de l'Azure en comptes de les claus de compte d'emmagatzematge. 

Podeu utilitzar l'entitat de servei per [afegir o editar de manera segura una carpeta de Common Data Model com a font de dades](connect-common-data-model.md) o [crear un entorn nou o actualitzar-ne un d'existent](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - El compte d'emmagatzematge de l'Azure Data Lake Storage Gen2 que té com a objectiu utilitzar l'entitat de servei ha de tenir habilitat l'[Espai jeràrquic de noms (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).
> - Per poder crear l'entitat de servei, heu de tenir permisos d'administrador per a la vostra subscripció a l'Azure.

## <a name="create-azure-service-principal-for-audience-insights"></a>Crear l'entitat de servei de l'Azure per a les conclusions del públic

Abans de crear una nova entitat de servei per a les conclusions del públic, comproveu si aquesta ja existeix a l'organització.

### <a name="look-for-an-existing-service-principal"></a>Cercar una entitat de servei existent

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com) i inicieu-hi la sessió a la vostra organització.

2. Seleccioneu **Azure Active Directory** als serveis de l'Azure.

3. A **Administra**, seleccioneu **Aplicacions empresarials**.

4. Cerqueu l'identificador de l'aplicació principal de les conclusions del públic `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` o el nom `Dynamics 365 AI for Customer Insights`.

5. Si trobeu un registre coincident, vol dir que l'entitat de servei per a les conclusions del públic existeix. No cal que la torneu a crear.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla con es mostra l'entitat de servei existent.":::
   
6. Si no es retorna cap resultat, creeu una nova entitat de servei.

### <a name="create-a-new-service-principal"></a>Crear una nova entitat de servei

1. Instal·leu la versió més recent del **PowerShell de l'Azure Active Directory per al Graph**. Per obtenir més informació, vegeu [Instal·lar el PowerShell de l'Azure Active Directory per al Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - Al PC, seleccioneu la tecla de Windows al teclat, cerqueu **Windows PowerShell** i seleccioneu **Executa com un administrador**.
   
   - A la finestra del PowerShell que s'obre, introduïu `Install-Module AzureAD`.

2. Creeu l'entitat de servei per a les conclusions del públic amb el mòdul del PowerShell de l'Azure AD.
   - A la finestra del PowerShell introduïu `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Substituïu "l'identificador d'inquilí" per l'identificador real del vostre inquilí on voleu crear l'entitat de servei. El paràmetre del nom de l'entorn `AzureEnvironmentName` és opcional.
  
   - Introduïu `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Amb aquesta ordre es crea l'entitat de servei per a les conclusions del públic a l'inquilí seleccionat.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Concedir permisos a l'entitat de servei per accedir al compte d'emmagatzematge

Aneu al portal de l'Azure per concedir permisos a l'entitat de servei del compte d'emmagatzematge que voleu utilitzar a les conclusions del públic.

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com) i inicieu-hi la sessió a la vostra organització.

1. Obriu el compte d'emmagatzematge al qual voleu que tingui accés l'entitat de servei per a les conclusions del públic.

1. Seleccioneu **Control d'accés (IAM)** a la subfinestra de navegació i seleccioneu **Afegeix** > **Afegeix l'assignació de funcions**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla on es mostra el portal de l'Azure mentre s'afegeix una assignació de funcions.":::
   
1. A la subfinestra **Afegeix l'assignació de funcions**, definiu les propietats següents:
   - Funció: *Col·laborador de dades de Blob d'emmagatzematge*
   - Assignació d'accés a: *Usuari, grup o entitat de servei*
   - Seleccionar: *Dynamics 365 AI per a Customer Insights* (l'[entitat de servei que heu creat](#create-a-new-service-principal))

1.  Seleccioneu **Desa**.

La propagació dels canvis pot trigar fins a 15 minuts.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Introduïu l'identificador de recurs de l'Azure o els detalls de subscripció de l'Azure al fitxer adjunt del compte d'emmagatzematge de les conclusions del públic.

Adjunteu un compte d'emmagatzematge de l'Azure Data Lake a les conclusions del públic per [emmagatzemar dades de sortida](manage-environments.md) o [utilitzar-les com a font de dades](connect-common-data-service-lake.md). Si trieu l'opció de l'Azure Data Lake, podreu triar entre un mètode basat en recursos o un basat en subscripcions.

Seguiu els passos que es descriuen a continuació per proporcionar la informació necessària sobre el mètode seleccionat.

### <a name="resource-based-storage-account-connection"></a>Connexió al compte d'emmagatzematge basat en recursos

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com), inicieu-hi la sessió a la vostra subscripció i obriu el compte d'emmagatzematge.

1. Aneu a **Configuració** > **Propietats** a la subfinestra de navegació.

1. Copieu el valor de l'identificador de recurs del compte d'emmagatzematge.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copieu l'identificador de recurs del compte d'emmagatzematge.":::

1. A les conclusions del públic, inseriu l'identificador de recurs al camp de recurs que es mostra a la pantalla de connexió del compte d'emmagatzematge.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduïu la informació de l'identificador de recurs del compte d'emmagatzematge.":::   
   
1. Continueu amb els passos restants a les conclusions del públic per adjuntar el compte d'emmagatzematge.

### <a name="subscription-based-storage-account-connection"></a>Connexió al compte d'emmagatzematge basat en subscripcions

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com), inicieu-hi la sessió a la vostra subscripció i obriu el compte d'emmagatzematge.

1. Aneu a **Configuració** > **Propietats** a la subfinestra de navegació.

1. Reviseu la **Subscripció**, el **Grup de recursos** i el **Nom** del compte d'emmagatzematge per assegurar-vos de seleccionar els valors adequats a les conclusions del públic.

1. A les conclusions del públic, trieu els valors o els camps corresponents quan adjunteu el compte d'emmagatzematge.
   
1. Continueu amb els passos restants a les conclusions del públic per adjuntar el compte d'emmagatzematge.


[!INCLUDE[footer-include](../includes/footer-banner.md)]