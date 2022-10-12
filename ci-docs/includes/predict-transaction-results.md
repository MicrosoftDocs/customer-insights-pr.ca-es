---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611122"
---
- **Rendiment del model de** formació: Els graus A, B o C indiquen el rendiment de la predicció i us poden ajudar a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida.

  Les qualificacions es determinen segons les regles següents:
  - **A** quan el model ha predit correctament com a mínim el 50 % del total de les prediccions, i el percentatge de prediccions precises per als clients que han rotat és superior a la ràtio de referència com a mínim en un 10 %.
  - **B** quan el model ha predit correctament com a mínim el 50 % del total de les prediccions, i el percentatge de prediccions precises per als clients que han rotat és fins a un 10 % superior al valor de referència.
  - **C** quan el model va predir amb precisió menys del 50% de les prediccions totals, o quan el percentatge de prediccions precises per als clients que van batre és inferior a la línia de base.
  - **La línia** de base pren el predicció entrada de finestra de temps per al model (per exemple, un any) i crea diferents fraccions de temps dividint-lo per 2 fins que arribi a un mes o menys. Utilitza aquestes fraccions per crear una regla de negocis per als clients que no han comprat durant aquest període. Aquests clients es consideren rotació. La regla de negoci basada en el temps amb la capacitat més alta de predir qui és probable que xuclar es tria com a model de referència.

- **Probabilitat de rotació (nombre de clients)**: grups de clients segons el risc predit de rotació. Opcionalment, [creeu segments de clients](../prediction-based-segment.md) amb alt risc de rebrot. Aquests segments ajuden a entendre on heu de definit la data límit de la subscripció del segment.

- **Factors més influents**: hi ha molts factors que s'han de tenir en compte a l'hora de crear la predicció. Cadascun dels factors té la seva importància calculada per a les prediccions agregades que crea un model. Utilitzeu aquests factors per ajudar-vos a validar els resultats predicció. O utilitzeu aquesta informació més endavant per [crear segments](../prediction-based-segment.md) que puguin ajudar a influir en el risc de rebrot per als clients.