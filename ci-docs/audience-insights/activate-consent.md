---
title: Activa les regles de consentiment per als segments
description: Seguiu aquests passos per enllaçar les dades de consentiment i activar les comprovacions de consentiment a les estadístiques del públic. Un administrador també pot desactivar les comprovacions de consentiment.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 552cb0739c4d17266dd028638df067f3384b738a
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884062"
---
# <a name="activate-consent-rules"></a>Activa les regles de consentiment

El [Centre de consentiment (previsualització) us ajuda a](../consent-management/overview.md) harmonitzar les dades de consentiment de diverses fonts. Utilitzeu l'entitat Consentiment unificat *per* aplicar comprovacions de consentiment per defecte. Després d'importar dades de consentiment al Centre de consentiment i configurar les regles de les dades, *l'entitat Consentiment se sincronitza automàticament amb les* estadístiques del públic.

## <a name="enable-consent-checks"></a>Habilita comprovacions de consentiment

Amb les dades de consentiment importades al Centre de consentiment (previsualització) i les regles configurades, podeu habilitar les comprovacions de consentiment. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Pestanya Consentiment a la configuració de les estadístiques del públic amb dades de consentiment activades.":::

1. A les conclusions del públic, aneu a **Administració** > **Sistema**.

1. Seleccioneu la **pestanya Consentiment (previsualització).**

1. A la **secció Habilita les comprovacions de** consentiment, definiu el commutador a **Activat per a totes les** àrees que vulgueu habilitar.

1. Activeu la casella de selecció Permet la **substitució de les regles de consentiment per defecte** per eliminar les comprovacions de consentiment per defecte imposades en un segment concret. 

1. Al menú desplegable, seleccioneu on voleu permetre les substitucions.     

1. A la **secció Enllaç consentiment per a perfils de** clients, trieu l'atribut que s'utilitza com a identificador per enllaçar les dades de consentiment a les dades del client. Probablement serà un número de telèfon o una adreça de correu electrònic. 

1. Seleccioneu **Desa** per aplicar la configuració.

## <a name="disable-consent-checks"></a>Inhabilita les comprovacions de consentiment

Per deixar d'utilitzar les dades de consentiment a les estadístiques de públic, un administrador ha d'actualitzar la configuració del sistema en conseqüència.

1. A les conclusions del públic, aneu a **Administració** > **Sistema**.

1. Seleccioneu la **pestanya Consentiment (previsualització).**

1. A la **secció Habilita les comprovacions de** consentiment, definiu el commutador a **Desactivat**.

> [!TIP]
> Per deixar d'utilitzar la capacitat d'administració de consentiment, vegeu [Configuració del sistema al Centre de consentiment (visualització prèvia).](../consent-management/system-settings.md)
