---
title: Configuració de seguretat a Customer Insights
description: Més informació sobre la configuració de seguretat al Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947403"
---
# <a name="security-settings-in-customer-insights"></a>Configuració de seguretat a Customer Insights

La **pàgina Seguretat** llista les opcions per configurar els permisos i les funcions de l'usuari que ajuden a fer-les Dynamics 365 Customer Insights més segures. Només els administradors poden accedir a aquesta pàgina.

Aneu a **Seguretat** > **de l'administrador** per configurar la configuració.

La **pàgina Seguretat** inclou les pestanyes següents:

- [Usuaris](#users-tab)
- [API](#apis-tab)
- [Enllaços privats](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Accedir de manera segura a les dades dels clients amb el Customer Lockbox (Visualització prèvia)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Pestanya Usuaris

L'accés a l'Insights del client està restringit als usuaris de la vostra organització que un administrador ha afegit a l'aplicació. La **pestanya Usuaris** us permet gestionar l'accés de l'usuari i els seus permisos. Per obtenir més informació, vegeu [Permisos](permissions.md) d'usuari.

## <a name="apis-tab"></a>Pestanya APIs

Visualitza i gestiona les claus per utilitzar les API [del](apis.md) Customer Insights amb les dades del teu entorn.

Podeu crear claus primàries i secundàries noves seleccionant **Regenera la primària** o **Regenera la secundària**. 

Per bloquejar l'accés de l'API a l'entorn, seleccioneu **Inhabilita**. Si les API estan inhabilitades, pots seleccionar **Habilita** per tornar a concedir accés.

## <a name="private-links-tab"></a>Pestanya Enllaços privats

[L'Azure Private Link](/azure/private-link/private-link-overview) permet que les Estadístiques del client es connectin al vostre Azure Data Lake Storage compte a un punt final privat de la xarxa virtual. Per a les dades d'un compte d'emmagatzematge, que no estan exposades a Internet pública, Private Link permet la connexió a aquesta xarxa restringida.

> [!IMPORTANT]
> Requisit mínim de funció per configurar una connexió d'enllaç privat:
>
> - Estadístiques del client: administrador
> - Funció integrada de l'Azure: [Contributor del compte d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permisos per a la funció personalitzada de l'Azure: [Microsoft.Storage/storageAccounts/read i Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Configurar l'enllaç privat a Customer Insights és un procés de dos passos. En primer lloc, inicieu la creació d'un enllaç privat des d'enllaços privats de **seguretat** > **d'administrador** > **a** Les estadístiques del client. La **subfinestra Afegeix enllaços** privats llista els comptes d'emmagatzematge de l'inquilí que teniu permisos per veure. Seleccioneu el compte d'emmagatzematge i proporcioneu el consentiment per crear l'enllaç privat.

A continuació, heu d'aprovar l'enllaç privat al costat del compte d'emmagatzematge del llac de dades. Obriu l'enllaç presentat en pantalla per aprovar el nou enllaç privat.

## <a name="key-vault-tab"></a>Pestanya Dipòsit de claus

La **pestanya Key Vault** us permet enllaçar i administrar el vostre propi [dipòsit](/azure/key-vault/general/basic-concepts) de claus de l'Azure a l'entorn.
El magatzem de claus dedicat es pot utilitzar per escenificar i utilitzar els secrets en el límit de compliment de l'organització. El Customer Insights pot utilitzar els secrets de l'Azure Key Vault per [configurar connexions](connections.md) a sistemes de tercers.

Per obtenir més informació, vegeu [Portar el vostre propi magatzem de claus de l'Azure](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Accedir de manera segura a les dades dels clients amb el Customer Lockbox (Visualització prèvia)

Customer Insights utilitza la capacitat de Bloqueig del Power Platform client. El Customer Lockbox proporciona una interfície per revisar i aprovar (o rebutjar) sol·licituds d'accés a dades. Aquestes sol·licituds es produeixen quan es necessita accés a les dades dels clients per resoldre un cas de suport tècnic. Per utilitzar aquesta característica, el Customer Insights ha de tenir una connexió existent amb un entorn de Microsoft Dataverse l'inquilí.

Per obtenir més informació sobre el quadre de bloqueig del client, vegeu el [resum](/power-platform/admin/about-lockbox#summary) de La caixa de bloqueig del Power Platform client. L'article també descriu el [flux de treball](/power-platform/admin/about-lockbox#workflow) i la configuració [necessària](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) per habilitar el quadre de bloqueig del client.

> [!IMPORTANT]
> Els administradors globals Power Platform o Power Platform els administradors poden aprovar les sol·licituds de Bloqueig del Client emeses per a l'Insights del Client.

[!INCLUDE [footer-include](includes/footer-banner.md)]
