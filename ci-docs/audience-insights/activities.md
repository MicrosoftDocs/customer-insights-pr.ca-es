---
title: Activitats del client
description: Definiu activitats de client i visualitzeu-les a la cronologia del client.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267420"
---
# <a name="customer-activities"></a>Activitats del client

Combineu les activitats del client procedents de [diverses fonts](data-sources.md) al Dynamics 365 Customer Insights per crear una cronologia del client que enumeri les activitats en ordre cronològic. Podeu incloure la cronologia a les aplicacions d'interacció amb els clients del Dynamics 365 mitjançant el [complement Targeta del client](customer-card-add-in.md) o en un escriptori digital del Power BI.

## <a name="define-an-activity"></a>Definir una activitat

Les fonts de dades inclouen entitats amb dades transaccionals i d'activitats procedents de diverses fonts de dades. Identifiqueu aquestes entitats i seleccioneu les activitats que voleu visualitzar a la cronologia del client. Trieu l'entitat que inclogui l'activitat o les activitats de destinació.

1. A les conclusions del públic, aneu a **Dades** > **Activitats**.

1. Seleccioneu **Afegeix una activitat**.

   > [!NOTE]
   > Una entitat ha de tenir com a mínim un atribut del tipus **Data** per ser inclosa en una cronologia de client i no es poden afegir entitats sense camps **Data**. El control **Afegeix una activitat** està inhabilitat si no es troba cap entitat.

1. A la subfinestra **Afegeix una activitat**, definiu els valors per als camps següents:

   - **Entitat**: seleccioneu una entitat que inclogui dades transaccionals o d'activitat.
   - **Clau principal**: seleccioneu el camp que identifica de manera única un registre. No hauria de contenir cap valor duplicat, valors buits o valors que faltin.
   - **Marca de temps**: seleccioneu el camp que representa l'hora d'inici de l'activitat.
   - **Esdeveniment**: seleccioneu el camp que és l'esdeveniment de l'activitat.
   - **Adreça web**: seleccioneu el camp que representa una adreça URL en la qual es proporciona informació addicional sobre aquesta activitat. Per exemple, el sistema transaccional que és l'origen d'aquesta activitat. Aquesta adreça URL pot ser qualsevol camp de la font de dades; o bé, es pot crear com a camp nou mitjançant una transformació del Power Query. Aquestes dades d'URL s'emmagatzemaran a l'entitat Activitat unificada, que pot consumir-se de manera descendent amb API.
   - **Detalls**: opcionalment, seleccioneu el camp que s'afegeix per als detalls addicionals.
   - **Icona**: opcionalment, seleccioneu la icona que representa aquesta activitat.
   - **Tipus d'activitat**: definiu la referència del tipus d'activitat al Common Data Model que descriu millor la definició semàntica de l'activitat.

1. A la secció **Configura la relació**, configureu els detalls per connectar les dades d'activitat al client corresponent.

    - **Camp d'entitat d'activitat**: seleccioneu el camp a la vostra entitat d'activitat que s'utilitzarà per establir una relació amb una altra entitat.
    - **Entitat de client**: seleccioneu l'entitat de client d'origen corresponent amb la qual l'entitat activitat tindrà una relació. Només podeu relacionar-vos amb les entitats de client d'origen que s'utilitzen al procés d'unificació de dades.
    - **Camp d'entitat de client**: aquest camp mostra la clau principal de l'entitat de client d'origen com a seleccionada al procés d'assignació. Aquest camp de clau principal a l'entitat de client d'origen s'utilitza per establir una relació amb l'entitat d'activitat.
    - **Nom**: si ja hi ha una relació entre aquesta entitat d'activitat i l'entitat de client d'origen seleccionada, el nom de la relació serà només de lectura. Si no existeix aquesta relació, es crearà una relació nova amb el nom que es proporciona aquí.
   
   > [!div class="mx-imgBorder"]
   > ![Definir la relació d'entitat](media/activities-entities-define.png "Definir la relació d'entitat")

1. Seleccioneu **Desa** per aplicar els canvis.

1. A la pàgina **Activitats**, seleccioneu **Executa**.

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.

## <a name="edit-an-activity"></a>Editar una activitat

1. A les conclusions del públic, aneu a **Dades** > **Activitats**.

2. Seleccioneu l'entitat d'activitat que voleu editar i seleccioneu **Edita**. O bé, podeu passar el cursor per sobre de la fila d'entitat i seleccionar la icona **Edita**.

3. Feu clic a a la icona **Edita**.

4. A la subfinestra **Edita l'activitat**, actualitzeu els valors i seleccioneu **Desa**.

5. A la pàgina **Activitats**, seleccioneu **Executa**.

## <a name="delete-an-activity"></a>Suprimir una activitat

1. A les conclusions del públic, aneu a **Dades** > **Activitats**.

2. Seleccioneu l'entitat d'activitat que voleu suprimir i seleccioneu **Suprimeix**. O bé, podeu passar el cursor per sobre de la fila d'entitat i seleccionar la icona **Suprimeix**. A més, podeu seleccionar diverses entitats d'activitat per suprimir-les alhora.
   > [!div class="mx-imgBorder"]
   > ![Editar o suprimir la relació d'entitats](media/activities-entities-edit-delete.png "Editar o suprimir la relació d'entitats")

3. Seleccioneu a la icona **Suprimeix**.

4. Confirmeu la supressió.


[!INCLUDE[footer-include](../includes/footer-banner.md)]