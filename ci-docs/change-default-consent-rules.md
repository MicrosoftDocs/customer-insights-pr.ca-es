---
title: Administra les regles de consentiment per defecte als segments
description: Amb la capacitat de gestió del consentiment, podeu desactivar o canviar les regles de consentiment per defecte si les substitucions estan habilitades.
ms.date: 12/01/2021
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 43f03ea97765e112a8ea2a7da97cc548c8c84dfc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642241"
---
# <a name="disable-or-change-default-consent-rules"></a>Inhabilita o canvia les regles de consentiment per defecte

Si les vostres organitzacions utilitzen la [capacitat](consent-management/overview.md) de gestió de consentiments amb Dynamics 365 Customer Insights, [els administradors poden fer complir les regles](activate-consent.md) de consentiment per als segments. 

Amb les normes de consentiment aplicades a l'àrea del segment, cada segment informa sobre l'estat de la comprovació de consentiment i les regles. Si es permeten les substitucions, les regles de consentiment per defecte estan desactivades per a segments específics. Cada creador d'un segment pot afegir més regles de consentiment a la part superior de les regles predeterminades a un segment. 

## <a name="for-administrators"></a>Per als administradors

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Creador de segments amb opcions de regla de consentiment.":::

**Per desactivar les regles de consentiment per defecte:**

1. A la **notificació de les regles** de consentiment, seleccioneu **Mostra els detalls**. 

1. Definiu les **regles** de consentiment per defecte per desactivar-les **·**.

**Per afegir més regles de consentiment:**

1. A la **notificació de les regles** de consentiment, seleccioneu **Mostra els detalls**. 

1. Seleccioneu **Afegeix regles** de consentiment i trieu una regla de consentiment al menú desplegable Selecciona el **tipus** de dades de consentiment.

1. Seleccioneu **Desa** per aplicar la regla nova al segment.

## <a name="for-contributors"></a>Per a col·laboradors

Per crear un segment sense regles de consentiment aplicades, heu de treballar amb l'administrador per desactivar-los al segment. Tanmateix, podeu afegir les vostres pròpies regles de consentiment als segments que posseïu i gestioneu.

És un procés de tres passos: 
1. [Creeu el segment](segments.md) a Customer Insights i deseu-lo. 

1. Compartiu el nom del segment amb l'administrador i demaneu-li que [habiliti les substitucions per al segment](activate-consent.md). 

1. Torneu a obrir els segments. A la **notificació de les regles** de consentiment, seleccioneu **Consulta els detalls** i afegiu les regles de consentiment que voleu aplicar. A continuació, **deseu** i **executeu** el segment.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
