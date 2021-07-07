---
title: Activitats del client
description: Definiu activitats de client i visualitzeu-les a la cronologia del client.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304914"
---
# <a name="customer-activities"></a>Activitats del client

Combinar les activitats de client de [diverses fonts de dades](data-sources.md) al Dynamics 365 Customer Insights per crear una cronologia on s'enumerin les activitats en ordre cronològic. Incloeu la cronologia a les aplicacions del Dynamics 365 amb la solució de [complement de targeta de client](customer-card-add-in.md) o en un escriptori digital del Power BI.

## <a name="define-an-activity"></a>Definir una activitat

Les fonts de dades poden incloure entitats amb dades transaccionals i d'activitats procedents de diverses fonts de dades. Identifiqueu aquestes entitats i seleccioneu les activitats que voleu visualitzar a la cronologia del client. Trieu l'entitat que inclogui l'activitat o les activitats de destinació.

> [!NOTE]
> Una entitat ha de tenir com a mínim un atribut del tipus **Data** per ser inclosa en una cronologia de client i no es poden afegir entitats sense camps **Data**. El control **Afegeix una activitat** està inhabilitat si no es troba cap entitat.

1. A les conclusions del públic, aneu a **Dades** > **Activitats**.

1. Seleccioneu **Afegeix una activitat** per iniciar l'experiència guiada per al procés de configuració de l'activitat.

1. Al pas **Dades de l'activitat**, definiu els valors per als camps següents:

   - **Nom de l'activitat**: seleccioneu un nom per a l'activitat.
   - **Entitat**: seleccioneu una entitat que inclogui dades transaccionals o d'activitat.
   - **Clau principal**: seleccioneu el camp que identifica de manera única un registre. No hauria de contenir cap valor duplicat, valors buits o valors que faltin.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configureu les dades de l'activitat amb el nom, l'entitat i la clau principal.":::

1. Seleccioneu **Següent** per anar al pas següent.

1. En el pas **Relació**, configureu els detalls per connectar les dades de l'activitat al client corresponent. Aquest pas visualitza la connexió entre entitats.  

   - **Primer**: camp extern de la vostra entitat d'activitat que s'utilitzarà per establir una relació amb una altra entitat.
   - **Segon**: entitat de client d'origen corresponent amb la qual estarà relacionada l'entitat d'activitat. Només podeu relacionar amb entitats de client d'origen utilitzades en el procés d'unificació de dades.
   - **Tercer**: si ja hi ha una relació entre aquesta entitat d'activitat i l'entitat de client d'origen seleccionada, el nom de la relació tindrà lloc en mode només de lectura. Si no hi ha cap relació, es crearà una relació nova amb el nom que proporcioneu en aquest quadre.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiu la relació de l'entitat.":::

1. Seleccioneu **Següent** per anar al pas següent. 

1. Al pas **Unificació d'activitats**, trieu la incidència d'activitat i l'hora d'inici de l'activitat. 
   - **Camps obligatoris**
      - **Activitat d'esdeveniment**: camp que és l'esdeveniment per a aquesta activitat.
      - **Marca horària**: camp que representa l'hora d'inici de la vostra activitat.

   - **Camps opcionals**
      - **Detall addicional**: camp amb informació rellevant per a aquesta activitat.
      - **Icona** : icona que representa millor aquest tipus d'activitat.
      - **Adreça web**: camp que conté una adreça URL amb informació sobre aquesta activitat. Per exemple, el sistema transaccional que és l'origen d'aquesta activitat. Aquesta adreça URL pot ser qualsevol camp de la font de dades; o bé, es pot crear com a camp nou mitjançant una transformació del Power Query. Les dades d'adreça URL s'emmagatzemaran a l'entitat *Activitat unificada*, que es pot consumir als registres avall mitjançant [API](apis.md).
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especifiqueu les dades de l'activitat de client en una entitat Activitat unificada.":::

1. Seleccioneu **Següent** per desplaçar-vos al pas següent. Podeu seleccionar **Acabament i revisió** per desar l'activitat ara amb el tipus d'activitat definit com a **Altres**. 

1. Al pas **Tipus d'activitat**, trieu el tipus d'activitat i, si voleu, seleccioneu si voleu assignar de manera semàntica alguns dels tipus d'activitats per utilitzar-lo en altres àrees del Customer Insights. Actualment, els tipus d'activitats de *Subscripció* i *SalesOrderLine* es poden assignar de manera semàntica després d'acordar l'assignació dels camps. Si un tipus d'activitat no és rellevant per a la nova activitat, podeu triar *Altres* o *Crear-ne una de nova* per a un tipus d'activitat personalitzat.

1. Seleccioneu **Següent** per desplaçar-vos al pas següent. 

1. Al pas **Revisió**, verifiqueu les seleccions. Torneu a qualsevol dels passos anteriors i actualitzeu la informació si cal.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Reviseu els camps especificats d'una activitat.":::
   
1. Seleccioneu **Desa l'activitat** per aplicar els canvis i seleccioneu **Fet** per tornar a **Dades** > **Activitats**. Aquí podeu veure quines activitats hi ha definides per mostrar-les a la cronologia. 

1. A la pàgina **Activitats**, seleccioneu **Executa** per processar l'activitat. 

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.


## <a name="manage-existing-activities"></a>Administrar activitats existents

A **Dades** > **Activitats**, podeu visualitzar totes les activitats desades i administrar-les. Cada activitat està representada per una fila que també inclou detalls sobre l'origen, l'entitat i el tipus d'activitat.

Les accions següents estan disponibles en seleccionar una activitat. 

- **Editar**: s'obre la configuració de l'activitat al pas de revisió. Podeu canviar qualsevol o tota la configuració actual des d'aquest pas. Després de canviar la configuració, seleccioneu **Desa l'activitat** i, a continuació, seleccioneu **Executa** per processar els canvis.

- **Canvia el nom**: obre un diàleg on podeu introduir un nom diferent per a l'activitat seleccionada. Seleccioneu **Desa** per aplicar els canvis.

- **Suprimeix**: s'obre un diàleg per confirmar la supressió de l'activitat seleccionada. També podeu suprimir més d'una activitat alhora seleccionant les activitats i, a continuació, seleccionant la icona de supressió. Seleccioneu **Suprimeix** per confirmar la supressió.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
