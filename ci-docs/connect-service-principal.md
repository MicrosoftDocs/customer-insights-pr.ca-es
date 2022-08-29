---
title: Connectar-se a un compte de l'Azure Data Lake Storage mitjançant una entitat de seguretat de servei de l'Azure
description: Utilitzeu una entitat de seguretat de servei de l'Azure per connectar-vos al vostre llac de dades.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304185"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Connectar-se a un compte de l'Azure Data Lake Storage mitjançant una entitat de seguretat de servei de l'Azure

Dynamics 365 Customer Insights proporciona una opció per connectar-se a un compte mitjançant un Azure Data Lake Storage principal de servei de l'Azure en lloc de claus de compte d'emmagatzematge.

Les eines automatitzades que utilitzen els serveis de l'Azure han de tenir permisos restringits. En comptes d'iniciar la sessió a les aplicacions com a usuari amb tots els privilegis, l'Azure ofereix entitats de servei. Utilitzeu els principis de servei per afegir o editar de manera [segura una carpeta del Common Data Model com a font de dades](connect-common-data-model.md) o [crear o actualitzar un entorn](create-environment.md).

## <a name="prerequisites"></a>Requisits previs

- El compte del Data Lake Storage que utilitzarà el principal del servei ha de ser Gen2. Els comptes d'emmagatzematge de l'Azure Data Lake Gen1 no són compatibles.
- El compte del Data Lake Storage té [habilitat l'espai jeràrquic de noms](/azure/storage/blobs/data-lake-storage-namespace).
- Permisos d'administració per a la vostra inquilí de l'Azure, si heu de crear un director de servei nou.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crear una entitat de seguretat de servei de l'Azure per al Customer Insights

Abans de crear un director de servei nou per al Customer Insights, comproveu si ja existeix a l'organització. En la majoria dels casos, ja existeix.

### <a name="look-for-an-existing-service-principal"></a>Cercar una entitat de servei existent

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com) i inicieu-hi la sessió a la vostra organització.

2. A **Serveis de l'Azure**, seleccioneu **Azure Active Directory**.

3. A **Administra**, seleccioneu **Aplicació de** Microsoft.

4. Afegiu un filtre per a **l'identificador de l'aplicació que**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` comença o cerqueu el nom `Dynamics 365 AI for Customer Insights`.

5. Si trobeu un registre coincident, significa que l'entitat de seguretat de servei ja existeix. [Concediu permisos](#grant-permissions-to-the-service-principal-to-access-the-storage-account) perquè el director del servei accedeixi al compte d'emmagatzematge.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que mostra un entitat de seguretat de servei existent.":::

6. Si no es retornen resultats, [creeu un nou director de servei](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Crear una nova entitat de servei

1. Instal·leu la versió més recent del PowerShell de l'Azure Active Directory per al Graph. Per obtenir més informació, aneu a [Instal·lació del PowerShell de l'Azure Active Directory per al Graph](/powershell/azure/active-directory/install-adv2).

   1. A l'ordinador, premeu la tecla Windows del teclat i cerqueu **el Windows PowerShell** i seleccioneu **Executa com a administrador**.

   1. A la finestra del PowerShell que s'obre, introduïu `Install-Module AzureAD`.

2. Creeu l'entitat de seguretat de servei per al Customer Insights amb el mòdul del PowerShell de l'Azure AD.

   1. A la finestra del PowerShell introduïu `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Substituïu *[l'identificador de directori]* per l'identificador de Directori real de la subscripció de l'Azure on vulgueu crear el principal del servei. El paràmetre del nom de l'entorn, `AzureEnvironmentName`, és opcional.
  
   1. Introduïu `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Aquesta ordre crea el principal de servei per al Customer Insights a la subscripció de l'Azure seleccionada.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Concedir permisos a l'entitat de servei per accedir al compte d'emmagatzematge

Per concedir permisos al director del servei per al compte d'emmagatzematge que voleu utilitzar al Customer Insights, s'ha d'assignar una de les funcions següents al compte d'emmagatzematge o al contenidor:

|Credencial|Requisits|
|----------|------------|
|Usuari que ha iniciat la sessió actualment|**Rol**: lector de dades blob d'emmagatzematge, col·laborador de blob d'emmagatzematge o propietari de blob d'emmagatzematge.<br>**Nivell**: permisos concedits al compte d'emmagatzematge o al contenidor.</br>|
|Director del servei Customer Insights -<br>Ús Azure Data Lake Storage com a font de dades</br>|Opció 1<ul><li>**Rol**: lector de dades blob d'emmagatzematge, col·laborador de dades blob d'emmagatzematge o propietari de dades blob d'emmagatzematge.</li><li>**Nivell**: permisos concedits al compte d'emmagatzematge.</li></ul>Opció 2 *(sense compartir l'accés del principal de servei al compte d'emmagatzematge)*<ul><li>**Funció 1**: lector de dades blob d'emmagatzematge, col·laborador de dades blob d'emmagatzematge o propietari de dades blob d'emmagatzematge.</li><li>**Nivell**: Permisos concedits al contenidor.</li><li>**Funció 2**: Delegat de dades blob d'emmagatzematge.</li><li>**Nivell**: permisos concedits al compte d'emmagatzematge.</li></ul>|
|Director del servei Customer Insights - <br>Ús Azure Data Lake Storage com a sortida o destinació</br>|Opció 1<ul><li>**Rol**: Col·laborador de dades blob d'emmagatzematge o propietari del blob d'emmagatzematge.</li><li>**Nivell**: permisos concedits al compte d'emmagatzematge.</li></ul>Opció 2 *(sense compartir l'accés del principal de servei al compte d'emmagatzematge)*<ul><li>**Rol**: Col·laborador de dades blob d'emmagatzematge o propietari del blob d'emmagatzematge.</li><li>**Nivell**: Permisos concedits al contenidor.</li><li>**Rol 2**: Delegat de blob d'emmagatzematge.</li><li>**Nivell**: permisos concedits al compte d'emmagatzematge.</li></ul>|

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com) i inicieu-hi la sessió a la vostra organització.

1. Obriu el compte d'emmagatzematge al qual voleu que tingui accés el director del servei del Customer Insights.

1. A la subfinestra esquerra, seleccioneu **Control d'accés (IAM)** i, a continuació, seleccioneu **Afegeix** > **Afegeix una assignació de funcions**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que mostra el portal de l'Azure mentre afegiu una assignació de funcions.":::

1. A la subfinestra **Afegeix una assignació de funcions**, definiu les propietats següents:
   - **Rol**: lector de dades blob d'emmagatzematge, col·laborador de blob d'emmagatzematge o propietari de blob d'emmagatzematge basat en les credencials esmentades anteriorment.
   - **Assignar accés a**: **Usuari, grup o director de servei**
   - **Seleccioneu** membres: **Dynamics 365 AI for Customer Insights** (el principal [de](#create-a-new-service-principal) servei que heu consultat anteriorment en aquest procediment)

1. Seleccioneu **Revisa + assigna**.

La propagació dels canvis pot trigar fins a 15 minuts.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Introduïu l'identificador de recurs de l'Azure o els detalls de la subscripció de l'Azure al fitxer adjunt del compte d'emmagatzematge al Customer Insights

Adjunteu un compte del Data Lake Storage al Customer Insights per [emmagatzemar les dades](manage-environments.md) de sortida o [utilitzar-les com a font de dades](connect-dataverse-managed-lake.md). Trieu entre un [enfocament basat en](#resource-based-storage-account-connection) recursos o un [enfocament basat en](#subscription-based-storage-account-connection) subscripcions i seguiu aquests passos.

### <a name="resource-based-storage-account-connection"></a>Connexió al compte d'emmagatzematge basat en recursos

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com), inicieu la sessió a la vostra subscripció i obriu el compte d'emmagatzematge.

1. A la subfinestra esquerra, aneu a **Configuració** > **punts** finals.

1. Copieu el valor de l'identificador de recurs del compte d'emmagatzematge.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copieu l'identificador de recurs del compte d'emmagatzematge.":::

1. Al Customer Insights, inseriu l'identificador de recurs al camp de recursos que es mostra a la pantalla de connexió del compte d'emmagatzematge.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduïu la informació de l'identificador de recurs del compte d'emmagatzematge.":::

1. Continueu amb els passos restants al Customer Insights per adjuntar el compte d'emmagatzematge.

### <a name="subscription-based-storage-account-connection"></a>Connexió al compte d'emmagatzematge basat en subscripcions

1. Aneu al [portal d'administració de l'Azure](https://portal.azure.com), inicieu la sessió a la vostra subscripció i obriu el compte d'emmagatzematge.

1. A la subfinestra esquerra, aneu a **Configuració** > **Propietats**.

1. Reviseu la subscripció, el **grup** de recursos i el **nom** del compte d'emmagatzematge per assegurar-vos que seleccioneu els valors adequats **al Customer Insights.**

1. Al Customer Insights, trieu els valors dels camps corresponents quan adjunteu el compte d'emmagatzematge.

1. Continueu amb els passos restants al Customer Insights per adjuntar el compte d'emmagatzematge.

[!INCLUDE [footer-include](includes/footer-banner.md)]
