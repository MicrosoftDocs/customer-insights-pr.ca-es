---
title: Configurar els paràmetres de seguretat
description: Obteniu més informació sobre la configuració de seguretat a Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246050"
---
# <a name="configure-security-settings"></a>Configurar els paràmetres de seguretat

Administra les claus API, accedeix a les dades del client i configura un Azure Private Link.

## <a name="manage-api-keys"></a>Administrar les claus API

Visualitzeu i administreu les claus per utilitzar les API [del](apis.md) Customer Insights amb les dades del vostre entorn.

1. Aneu a **Seguretat del sistema** > **i seleccioneu la** pestanya **API**.

1. Si l'accés de l'API a l'entorn no s'ha configurat, seleccioneu **Habilita**. O bé, per bloquejar l'accés de l'API a l'entorn, seleccioneu **Inhabilita** i confirma.

1. Gestioneu les claus API primàries i secundàries:

   1. Per mostrar la clau API principal o secundària, seleccioneu mostra el **símbol**.

   1. Per copiar la clau API principal o secundària, seleccioneu el **símbol Copia**.

   1. Per crear claus API primàries o secundàries noves, seleccioneu **Regenera les primàries** o **Regenera secundàries**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Accediu de manera segura a les dades dels clients amb Customer Lockbox (Visualització prèvia)

El Customer Insights utilitza la Power Platform capacitat Customer Lockbox. Customer Lockbox proporciona una interfície per revisar i aprovar (o rebutjar) les sol·licituds d'accés a dades. Aquestes sol·licituds es produeixen quan es necessita l'accés a les dades dels clients per resoldre un cas de suport tècnic. Per utilitzar aquesta característica, el Customer Insights ha de tenir una connexió existent amb un Microsoft Dataverse entorn de l'inquilí.

Per obtenir més informació sobre Customer Lockbox, vegeu el [resum](/power-platform/admin/about-lockbox#summary) de Power Platform Customer Lockbox. L'article també descriu el [flux de treball](/power-platform/admin/about-lockbox#workflow) i la configuració [necessària](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) per habilitar Customer Lockbox.

> [!IMPORTANT]
> Els administradors globals Power Platform o Power Platform administradors poden aprovar les sol·licituds de Customer Lockbox emeses per al Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Configuració d'un enllaç privat de l'Azure

[Azure Private Link](/azure/private-link/private-link-overview) permetem que el Customer Insights es connecti al vostre Azure Data Lake Storage compte a través d'un punt final privat de la vostra xarxa virtual. Per a les dades d'un compte d'emmagatzematge, que no estan exposades a Internet pública, Private Link permet la connexió a aquesta xarxa restringida.

> [!IMPORTANT]
> Requisit mínim de funció per configurar una connexió d'enllaç privat:
>
> - Estadístiques del client: administrador
> - Rol integrat de l'Azure: [Col·laborador del compte d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permisos per a la funció personalitzada de l'Azure: [Microsoft.Storage/storageAccounts/read i Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. A Customer Insights, aneu a **Seguretat d'administració** > **i** seleccioneu la **pestanya Enllaços privats**.

1. Seleccioneu **Afegeix un enllaç** privat.

   La **subfinestra Afegeix un enllaç** privat mostra els comptes d'emmagatzematge de l'inquilí que tens permisos per veure.

1. Seleccioneu la subscripció, el grup de recursos i el compte d'emmagatzematge.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa**.

1. Aneu al vostre compte del Data Lake Storage i obriu l'enllaç que es presenta a la pantalla.

1. Aprova l'enllaç privat.


[!INCLUDE [footer-include](includes/footer-banner.md)]
