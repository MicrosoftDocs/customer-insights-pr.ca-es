---
title: Configuració de seguretat a Dynamics 365 Customer Insights
description: Més informació sobre la configuració de seguretat al Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653776"
---
# <a name="security-overview-page"></a>Pàgina de visió general de seguretat

La **pàgina Seguretat** llista les opcions per configurar els permisos i les funcions de l'usuari que ajuden a fer-les Dynamics 365 Customer Insights més segures. Només els administradors poden accedir a aquesta pàgina. 

Aneu a **AdminSecurity** > **per** configurar la configuració.

La **pàgina Seguretat** inclou les pestanyes següents:
- [Usuaris](#users-tab)
- [API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Pestanya Usuaris

L'accés a l'Insights del client està restringit als usuaris de la vostra organització que un administrador ha afegit a l'aplicació. La **pestanya Usuaris** us permet gestionar l'accés de l'usuari i els seus permisos. Per obtenir més informació, vegeu [Permisos](permissions.md) d'usuari.

## <a name="apis-tab"></a>Pestanya APIs

Visualitza i gestiona les claus per utilitzar les API [del](apis.md) Customer Insights amb les dades del teu entorn.

Podeu crear claus primàries i secundàries noves seleccionant **Regenera la primària** o **Regenera la secundària**. 

Per bloquejar l'accés de l'API a l'entorn, seleccioneu **Inhabilita**. Si les API estan inhabilitades, pots seleccionar **Habilita** per tornar a concedir accés.

## <a name="key-vault-tab"></a>Pestanya Dipòsit de claus

La **pestanya Key Vault** us permet enllaçar i administrar el vostre propi [dipòsit](/azure/key-vault/general/basic-concepts) de claus de l'Azure a l'entorn.
El magatzem de claus dedicat es pot utilitzar per escenificar i utilitzar els secrets en el límit de compliment de l'organització. El Customer Insights pot utilitzar els secrets de l'Azure Key Vault per [configurar connexions](connections.md) a sistemes de tercers.

Per obtenir més informació, vegeu [Portar el vostre propi magatzem de claus de l'Azure](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
