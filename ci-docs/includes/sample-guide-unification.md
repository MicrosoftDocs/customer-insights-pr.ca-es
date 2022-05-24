---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755532"
---
Després d'ingerir les dades, inicieu el procés d'unificació de dades per crear un perfil de client unificat. Per obtenir més informació, vegeu [Unificació de les dades](../data-unification.md).

### <a name="select-source-fields"></a>Seleccioneu els camps d'origen

1. Un cop ingerides les dades, assigneu contactes de les dades de comerç electrònic i fidelització a tipus de dades comuns. Aneu a Unificació de **dades** > **·**.

1. Seleccioneu les entitats que representen el perfil del client (**eCommerceContacts** i **loyCustomers**).

   ![unificar les fonts de dades de comerç electrònic i de fidelització.](../media/unify-ecommerce-loyalty.png)

1. Seleccioneu **ContactId** com a clau principal per a **eCommerceContacts** i **LoyaltyID** com a clau principal per a **loyCustomers**.

1. Seleccioneu **Següent**. Omet els registres duplicats i selecciona **Següent**.

### <a name="match-conditions"></a>Condicions de coincidència

1. Trieu **Els contactes electrònics: el comerç electrònic** com a entitat principal i inclou tots els registres.

1. Trieu **loyCustomers: LoyaltyScheme** i incloeu tots els registres.

1. Afegeix una regla:
   - Seleccioneu **FullName** tant per a eCommerceContactes com per a loyCustomers.
   - Seleccioneu **Tipus (Telèfon, Nom, Adreça, ...)** per **Normalitzar**.
   - Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.
   - Introduïu **FullName, correu electrònic** per al nom.

1. Afegeix una segona condició per a l'adreça electrònica:
   - Seleccioneu **Correu electrònic** tant per a eCommerceContactes com per a loyCustomers.
   - Deixeu Normalitza en blanc.
   - Definiu el **Nivell de precisió**: **Bàsic** i el **Valor**: **Alt**.

   ![Unifiqueu la regla de coincidència per al nom i el correu electrònic.](../media/unify-match-rule.png)

1. Seleccioneu **Fet**.

1. Seleccioneu **Següent**.

### <a name="unify-fields"></a>Unificar camps

1. Canvieu el nom de l'entitat **ContactId** per **a loyCustomers** a **ContactIdLOYALTY** per diferenciar-la dels altres identificadors ingerits.

1. Seleccioneu **Endavant** per revisar i, a continuació, seleccioneu **Crea perfils** de client.
