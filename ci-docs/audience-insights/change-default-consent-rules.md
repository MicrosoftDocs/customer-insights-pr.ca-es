---
title: Administra les regles de consentiment per defecte als segments
description: Amb la capacitat de gestió del consentiment, podeu desactivar o canviar les regles de consentiment per defecte si les substitucions estan habilitades.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884158"
---
# <a name="disable-or-change-default-consent-rules"></a>Inhabilita o canvia les regles de consentiment per defecte

Si les organitzacions utilitzen la [capacitat de gestió de consentiment combinada amb les](../consent-management/overview.md) estadístiques del públic, [els administradors poden fer complir les regles de consentiment](activate-consent.md) per als segments. 

Amb les normes de consentiment aplicades a l'àrea del segment, cada segment informa sobre l'estat de la comprovació de consentiment i les regles. Si es permeten les substitucions, les regles de consentiment per defecte estan desactivades per a segments específics. Cada creador d'un segment pot afegir més regles de consentiment a la part superior de les regles predeterminades a un segment. 

## <a name="for-administrators"></a>Per als administradors

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Creador de segments amb opcions de regla de consentiment.":::

**Per desactivar les regles de consentiment per defecte:**

1. A la **notificació de les regles de** consentiment, seleccioneu **Mostra els detalls**. 

1. Definiu les **regles de consentiment per defecte** per **desactivar**.

**Per afegir més regles de consentiment:**

1. A la **notificació de les regles de** consentiment, seleccioneu **Mostra els detalls**. 

1. Seleccioneu **Afegeix regles de consentiment** i trieu una regla de consentiment al menú desplegable Selecciona el tipus de **dades de** consentiment.

1. Seleccioneu **Desa** per aplicar la regla nova al segment.

## <a name="for-contributors"></a>Per a col·laboradors

Per crear un segment sense regles de consentiment aplicades, heu de treballar amb l'administrador per desactivar-los al segment. Tanmateix, podeu afegir les vostres pròpies regles de consentiment als segments que posseïu i gestioneu.

És un procés de tres passos: 
1. [Creeu el segment](segments.md) a les estadístiques del públic i deseu-lo. 

1. Compartiu el nom del segment amb l'administrador i demaneu-li que [habiliti les substitucions per al segment](activate-consent.md). 

1. Torneu a obrir els segments. A la **notificació de les regles de** consentiment, seleccioneu **Consulta els detalls i** afegiu les regles de consentiment que voleu aplicar. A continuació, **deseu** i **executeu** el segment.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
