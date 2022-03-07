---
title: Activar les regles de consentiment per als segments
description: Seguiu aquests passos per enllaçar dades de consentiment i activar les comprovacions de consentiment a les estadístiques de l'audiència. Un administrador també pot inhabilitar les comprovacions de consentiment.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790765"
---
# <a name="activate-consent-rules"></a>Activar les regles de consentiment

El [Centre de consentiment (previsualització) us ajuda a](../consent-management/overview.md) harmonitzar les dades de consentiment de diverses fonts. Utilitzeu l'entitat consentiment unificat *·* per aplicar comprovacions de consentiment per defecte. Després d'importar dades de consentiment al Centre de consentiment i configurar les regles de les dades, *l'entitat Consent* se sincronitza automàticament amb les estadístiques de l'audiència.

## <a name="enable-consent-checks"></a>Habilita comprovacions de consentiment

Amb les dades de consentiment importades al Centre de consentiment (previsualització) i les regles establertes, podeu habilitar les comprovacions de consentiment. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Pestanya Consentiment a la configuració d'informació de l'auditori amb dades de consentiment activades.":::

1. A les conclusions del públic, aneu a **Administració** > **Sistema**.

1. Seleccioneu la **pestanya Consentiment (previsualització).**

1. A la secció Habilita les **comprovacions de** consentiment, definiu el commutador **Activa per a totes les** àrees que voleu habilitar.

1. Activeu la **casella de selecció Permet substituir les regles de consentiment per defecte per suprimir les** comprovacions de consentiment per defecte aplicades en un segment determinat. 

1. Al menú desplegable, seleccioneu on voleu permetre les sobrecàrrega.     

1. A la **secció Enllaç consenteix als perfils** de client, trieu l'atribut que s'utilitza com a identificador per enllaçar les dades de consentiment a les dades del client. Probablement serà un número de telèfon o una adreça de correu electrònic. 

1. Seleccioneu **Desa** per aplicar la configuració.

## <a name="disable-consent-checks"></a>Inhabilita les comprovacions de consentiment

Per deixar d'utilitzar dades de consentiment en les estadístiques de l'audiència, un administrador ha d'actualitzar la configuració del sistema en conseqüència.

1. A les conclusions del públic, aneu a **Administració** > **Sistema**.

1. Seleccioneu la **pestanya Consentiment (previsualització).**

1. A la **secció Habilita les comprovacions de** consentiment, definiu el commutador a **Desactiva**.
