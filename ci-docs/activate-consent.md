---
title: Activa les regles de consentiment per als segments
description: Seguiu aquests passos per enllaçar les dades del consentiment i activar els controls de consentiment al Dynamics 365 Customer Insights. Un administrador també pot desactivar les comprovacions de consentiment.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755158"
---
# <a name="activate-consent-rules"></a>Activa les regles de consentiment

El [Centre de consentiment (previsualització)](consent-management/overview.md) us ajuda a harmonitzar les dades de consentiment de diverses fonts. Utilitzeu l'entitat Consentiment *unificat* per aplicar comprovacions de consentiment per defecte. Després d'importar dades de consentiment i configurar les regles del mapa, l'entitat *Consentiment* se sincronitza automàticament amb Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Habilita comprovacions de consentiment

Amb les dades de consentiment importades al Centre de consentiment (previsualització) i les regles configurades, podeu habilitar les comprovacions de consentiment. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Pestanya Consentiment a la configuració del Customer Insights amb dades de consentiment activades.":::

1. Al Customer Insights, aneu a **Administració** > **Sistema**.

1. Seleccioneu la **pestanya Consentiment (previsualització**).

1. A la **secció Habilita les comprovacions** de consentiment, definiu el commutador a **Activat** per a totes les àrees que vulgueu habilitar.

1. Activeu la casella de selecció Permet la **substitució de les regles** de consentiment per defecte per eliminar les comprovacions de consentiment per defecte imposades en un segment concret. 

1. Al menú desplegable, seleccioneu on voleu permetre les substitucions.     

1. A la **secció Enllaç consentiment per a perfils** de clients, trieu l'atribut que s'utilitza com a identificador per enllaçar les dades de consentiment a les dades del client. Probablement serà un número de telèfon o una adreça de correu electrònic. 

1. Seleccioneu **Desa** per aplicar la configuració.

## <a name="disable-consent-checks"></a>Inhabilita les comprovacions de consentiment

Per deixar d'utilitzar les dades de consentiment a Customer Insights, un administrador ha d'actualitzar la configuració del sistema en conseqüència.

1. Al Customer Insights, aneu a **Administració** > **Sistema**.

1. Seleccioneu la **pestanya Consentiment (previsualització**).

1. A la **secció Habilita les comprovacions** de consentiment, definiu el commutador a **Desactivat**.

> [!TIP]
> Per deixar d'utilitzar la capacitat de gestió de consentiments, vegeu [Configuració del sistema al Centre de consentiment (visualització prèvia)](consent-management/system-settings.md).
