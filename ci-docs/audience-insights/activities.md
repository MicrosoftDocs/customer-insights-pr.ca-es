---
title: Activitats del client
description: Definir activitats de client i visualitzar-les en una cronologia dels perfils del client.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c250efcd54ec126c0726b22a971cdedd89760d6b
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617957"
---
# <a name="customer-activities"></a>Activitats del client

Combinar les activitats de client de [diverses fonts de dades](data-sources.md) al Dynamics 365 Customer Insights per crear una cronologia on s'enumerin les activitats en ordre cronològic. Incloeu la cronologia a les aplicacions del Dynamics 365 amb la solució de [complement de targeta de client](customer-card-add-in.md) o en un escriptori digital del Power BI.

## <a name="define-an-activity"></a>Definir una activitat

Les fonts de dades poden incloure entitats amb dades transaccionals i d'activitats procedents de diverses fonts de dades. Identifiqueu aquestes entitats i seleccioneu les activitats que voleu visualitzar a la cronologia del client. Trieu l'entitat que inclogui l'activitat o les activitats de destinació.

Una entitat ha de tenir com a mínim un atribut del tipus **Data** per ser inclosa en una cronologia de client i no es poden afegir entitats sense camps **Data**. El control **Afegeix una activitat** està inhabilitat si no es troba cap entitat.

1. A les conclusions del públic, aneu a **Dades** > **Activitats**.

1. Seleccioneu **Afegeix una activitat** per iniciar l'experiència guiada per al procés de configuració de l'activitat.

1. Al pas **Dades de l'activitat**, definiu els valors per als camps següents:

   - **Nom de l'activitat**: seleccioneu un nom per a l'activitat.
   - **Entitat**: seleccioneu una entitat que inclogui dades transaccionals o d'activitat.
   - **Clau principal**: seleccioneu el camp que identifica de manera única un registre. No hauria de contenir cap valor duplicat, valors buits o valors que faltin.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configureu les dades de l'activitat amb el nom, l'entitat i la clau principal.":::

1. Seleccioneu **Següent** per anar al pas següent.

1. En el pas **Relació**, configureu els detalls per connectar les dades de l'activitat al seu registre de client corresponent. Aquest pas visualitza la connexió entre entitats.  

   - **Primer**: camp extern de la vostra entitat d'activitat que s'utilitzarà per establir una relació amb una altra entitat.
   - **Segon**: entitat de client d'origen corresponent amb la qual estarà relacionada l'entitat d'activitat. Només podeu relacionar amb entitats de client d'origen utilitzades en el procés d'unificació de dades.
   - **Tercer**: si ja hi ha una relació entre aquesta entitat d'activitat i l'entitat de client d'origen seleccionada, el nom de la relació tindrà lloc en mode només de lectura. Si no hi ha cap relació, es crearà una relació nova amb el nom que proporcioneu en aquest quadre.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiu la relació de l'entitat.":::

   > [!TIP]
   > En entorns B2B, podeu seleccionar entre les entitats de compte i altres entitats. Si seleccioneu una entitat de compte, el camí de la relació es defineix automàticament. Per a la resta d'entitats, heu de definir el camí de la relació per damunt d'una o diverses entitats intermèdies fins que arribeu a una entitat de compte.

1. Seleccioneu **Següent** per anar al pas següent. 

1. Al pas **Unificació d'activitats**, trieu la incidència d'activitat i l'hora d'inici de l'activitat. 
   - **Camps obligatoris**
      - **Activitat d'esdeveniment**: camp que és l'esdeveniment per a aquesta activitat.
      - **Marca horària**: camp que representa l'hora d'inici de la vostra activitat.

   - **Camps opcionals**
      - **Detall addicional**: camp amb informació rellevant per a aquesta activitat.
      - **Icona** : icona que representa millor aquest tipus d'activitat.
      - **Adreça web**: camp que conté una adreça URL amb informació sobre aquesta activitat. Per exemple, el sistema transaccional que és l'origen d'aquesta activitat. Aquesta adreça URL pot ser qualsevol camp de la font de dades; o bé, es pot crear com a camp nou mitjançant una transformació del Power Query. Les dades d'adreça URL s'emmagatzemaran a l'entitat *Activitat unificada*, que es pot consumir als registres avall mitjançant [API](apis.md).

   - **Mostra a la cronologia**
      - Trieu si voleu que es mostri aquesta activitat a la visualització de la cronologia dels vostres perfils de client. Seleccioneu **Sí** per mostrar l'activitat a la cronologia o **No** per amagar-la'n.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especifiqueu les dades de l'activitat de client en una entitat Activitat unificada.":::

1. Seleccioneu **Següent** per desplaçar-vos al pas següent. Podeu seleccionar **Acabament i revisió** per desar l'activitat ara amb el tipus d'activitat definit com a **Altres**. 

1. Al pas **Tipus d'activitat**, trieu el tipus d'activitat i, si voleu, seleccioneu si voleu assignar de manera semàntica alguns dels tipus d'activitats per utilitzar-lo en altres àrees del Customer Insights. Actualment, els tipus d'activitats de *Comentaris*, *Fidelitat*, *SalesOrder*, *SalesOrderLine* i *Subscripció* es poden assignar semànticament després d'acordar l'assignació dels camps. Si un tipus d'activitat no és rellevant per a la nova activitat, podeu triar *Altres* o *Crear-ne una de nova* per a un tipus d'activitat personalitzat.

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

## <a name="view-activity-timelines-on-customer-profiles"></a>Visualitzar cronologies d'activitats als perfils de client

Després de configurar activitats de client, seleccioneu **Mostra a la cronologia d'activitats** a la configuració de l'activitat per cercar totes les activitats del client al seu perfil de client.

Per obrir la cronologia d'un client, aneu a **Clients** i trieu el perfil de client que voleu visualitzar.

Si un client ha participat en una activitat que heu configurat, la trobareu a la secció **Cronologia d'activitats**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Visualitzar les activitats configurades als perfils de client.":::

Hi ha diverses maneres de filtrar les activitats a la cronologia d'activitats:

- Podeu seleccionar una o moltes de les icones d'activitat per refinar els resultats per incloure només els tipus seleccionats.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrar activitats per tipus utilitzant les icones.":::

- Podeu seleccionar **Filtra** per obrir una subfinestra de filtre per configurar els filtres de cronologia.

   1. Podeu filtrar per *ActivityType* i *Data*
   1. Seleccioneu **Aplica** per utilitzar els filtres a la cronologia d'activitats.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Utilitzeu la subfinestra de filtre per configurar les condicions de filtre.":::

Per suprimir filtres, seleccioneu la **x** al costat de cada filtre aplicat a la cronologia o seleccioneu **Esborra els filtres**.


> [!NOTE]
> Els filtres d'activitat se suprimeixen quan sortiu d'un perfil de client. Els heu d'aplicar cada vegada que obriu en un perfil de client.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
