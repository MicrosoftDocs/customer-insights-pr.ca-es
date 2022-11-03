---
title: Activitats de contacte amb clients o empreses
description: Definiu les activitats de contacte amb clients o empreses i visualitzeu-les en una cronologia als perfils de clients.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723769"
---
# <a name="customer-or-business-contact-activities"></a>Activitats de contacte amb clients o empreses

Les activitats del client són accions o esdeveniments realitzats per clients o contactes comercials. Per exemple, transaccions, durada de les trucades d'assistència, ressenyes de llocs web, compres o devolucions. Aquestes activitats es troben en una o més fonts de dades. Amb el Coneixement de clients, consolideu les activitats dels clients a partir d'aquestes [fonts](data-sources.md) de dades i associeu-les als perfils de clients. Aquestes activitats apareixen cronològicament en una cronologia al perfil del client. Incloeu la cronologia a les aplicacions del Dynamics 365 amb la [solució de complement](customer-card-add-in.md) de targeta de client.

## <a name="define-a-customer-activity"></a>Definir una activitat de client

Una entitat ha de tenir almenys un atribut del tipus **Date** per incloure'l en una cronologia del client. El control **Afegeix una activitat** està inhabilitat si no es troba cap entitat.

1. Aneu a **Activitats de dades** > **·**.

1. Seleccioneu **Afegeix activitat** per iniciar l'experiència guiada.

1. Al pas Dades de l'activitat **·**, introduïu la informació següent:

   - **Nom de l'activitat**: seleccioneu un nom per a l'activitat.
   - **Entitat** d'activitat: seleccioneu una entitat que inclogui dades transaccionals o d'activitat.
   - **Clau principal**: seleccioneu el camp que identifica de manera única un registre. No hauria de contenir cap valor duplicat, valors buits o valors que faltin.

     > [!NOTE]
     > La clau principal de cada fila ha de mantenir-se coherent en font de dades actualitzacions. Si la clau principal d'una fila s'actualitza en una font de dades actualització, crea duplicats a l'entitat Activitat de sortida. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configureu les dades de l'activitat amb el nom, l'entitat i la clau principal.":::

1. Seleccioneu **Següent**.

1. **Al pas Relació**, seleccioneu **Afegeix una relació** per connectar les dades de l'activitat al registre de client corresponent. Aquest pas visualitza la connexió entre entitats.  

   - **Clau** externa: Camp exterior en la seva entitat d'activitat que s'utilitzarà per establir una relació amb una altra entitat.
   - **A nom de l'entitat**: Entitat client d'origen corresponent amb la qual estarà en relació l'entitat de la seva activitat. Només podeu relacionar amb entitats de client d'origen utilitzades en el procés d'unificació de dades.
   - **Nom** de la relació: si ja existeix una relació entre aquesta entitat d'activitat i l'entitat de client d'origen seleccionada, el nom de la relació estarà en mode de només lectura. Si no hi ha cap relació, es crearà una relació nova amb el nom que proporcioneu en aquest quadre.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definiu la relació de l'entitat.":::

   > [!TIP]
   > En entorns d'empresa a empresa, podeu seleccionar entre les entitats de compte i altres entitats. Si seleccioneu una entitat de compte, el camí de la relació es defineix automàticament. Per a la resta d'entitats, heu de definir el camí de la relació per damunt d'una o diverses entitats intermèdies fins que arribeu a una entitat de compte.

1. Seleccioneu **Aplica** per crear la relació.

1. Seleccioneu **Següent**.

1. Al pas **Unificació d'activitats**, trieu la incidència d'activitat i l'hora d'inici de l'activitat.
   - **Camps obligatoris**
      - **Activitat d'esdeveniment**: camp que és l'esdeveniment per a aquesta activitat.
      - **Marca horària**: camp que representa l'hora d'inici de la vostra activitat.

   - **Camps opcionals**
      - **Detall addicional**: camp amb informació rellevant per a aquesta activitat.
      - **Icona** : icona que representa millor aquest tipus d'activitat.
      - **Adreça web**: camp que conté una adreça URL amb informació sobre aquesta activitat. Per exemple, el sistema transaccional que és l'origen d'aquesta activitat. Aquest URL pot ser qualsevol camp del font de dades o es pot construir com un camp nou mitjançant una Power Query transformació. Les dades d'adreça URL s'emmagatzemaran a l'entitat *Activitat unificada*, que es pot consumir als registres avall mitjançant [API](apis.md).

   - **Mostra a la cronologia**
      - Trieu si voleu que es mostri aquesta activitat a la visualització de la cronologia dels vostres perfils de client. Seleccioneu **Sí** per mostrar l'activitat a la cronologia o **No** per amagar-la'n.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especifiqueu les dades de l'activitat de client en una entitat Activitat unificada.":::

1. Seleccioneu **Següent** per triar el tipus d'activitat o seleccioneu **Finalitza i revisa** per desar l'activitat amb el tipus d'activitat definit com a **Altres**.

1. Al pas **Tipus d'activitat**, trieu el tipus d'activitat i, si voleu, seleccioneu si voleu assignar de manera semàntica alguns dels tipus d'activitats per utilitzar-lo en altres àrees del Customer Insights. Actualment, *els tipus d'activitat Feedback*, *Loyalty*, *SalesOrder* *, SalesOrderLine* i *Subscription* admeten semàntica després d'acceptar mapejar els camps. Si un tipus d'activitat no és rellevant per a la nova activitat, podeu triar *Altres* o *Crear-ne una de nova* per a un tipus d'activitat personalitzat.

1. Seleccioneu **Següent**.

1. Al pas **Revisió**, verifiqueu les seleccions. Torneu a qualsevol dels passos anteriors i actualitzeu la informació si cal.

1. Seleccioneu **Desa l'activitat** per aplicar els canvis i seleccioneu **Fet** per tornar a **Dades** > **Activitats**. Es mostra l'activitat creada.

1. Després de crear totes les vostres activitats, seleccioneu **Executa** per processar-les.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Gestionar les activitats existents dels clients

Aneu a **Activitats** > **de dades** per veure les activitats desades, la seva entitat d'origen, el tipus d'activitat i si s'inclouen a la cronologia del client. Podeu ordenar la llista d'activitats per qualsevol columna o utilitzar el quadre de cerca per trobar l'activitat que voleu gestionar.

Seleccioneu una activitat per veure les accions disponibles.

- **Editeu** l'activitat per canviar-ne la configuració. La configuració s'obre al pas de revisió. Després de canviar la configuració, seleccioneu **Desa l'activitat** i, a continuació, seleccioneu **Executa** per processar els canvis.
- **Canvieu** el nom de l'activitat. Seleccioneu **Desa** per aplicar els canvis.
- **Suprimiu** l'activitat. Per suprimir més d'una activitat alhora, seleccioneu les activitats i, a continuació, **Suprimeix**. Confirmar la supressió.

## <a name="view-activity-timelines-on-customer-profiles"></a>Visualitzar cronologies d'activitats als perfils de client

1. Si heu seleccionat **Mostra a la cronologia de** l'activitat a la configuració de l'activitat, aneu a **Clients** i seleccioneu un perfil de client per veure les activitats del client a la **secció Cronologia** d'activitats.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Visualitzar les activitats configurades als perfils de client.":::

1. Per filtrar les activitats a la cronologia de l'activitat:

   - Seleccioneu una o més de les icones d'activitat per definir millor els resultats per incloure només els tipus seleccionats.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrar activitats per tipus utilitzant les icones.":::

   - Seleccioneu **Filtre** per obrir un tauler de filtre per configurar els filtres de cronologia. Filtreu per *ActivityType* i/o *Date*. Seleccioneu **Aplica**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Utilitzeu la subfinestra de filtre per configurar les condicions de filtre.":::

> [!NOTE]
> Els filtres d'activitat se suprimeixen quan sortiu d'un perfil de client. Els heu d'aplicar cada vegada que obriu un perfil de client.

## <a name="define-a-contact-activity"></a>Definir una activitat de contacte

Per als comptes d'empresa (B a B), utilitzeu una *entitat ContactProfile* per capturar activitats de contactes. Podeu veure a la cronologia d'activitats d'un compte quin contacte era el responsable de cada activitat. La majoria de passos segueixen la configuració de l'assignació d'activitat del client.

   > [!NOTE]
   > Per definir una activitat a nivell de contacte, s'ha de crear una *entitat ContactProfile*, ja sigui com a perfil [de contacte unificat](data-unification-contacts.md) o mitjançant [mapatge](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) semàntic.
   >
   > Heu de tenir **atributs AccountID** i **ContactID** per a cada registre a les dades de l'activitat.
  
1. Aneu a **Activitats de dades** > **·**.

1. Seleccioneu **Afegeix activitat**.

1. Al pas Dades de l'activitat **·**, introduïu la informació següent:

   - **Nom de l'activitat**: seleccioneu un nom per a l'activitat.
   - **Entitat** d'activitat: seleccioneu una entitat que inclogui dades transaccionals o d'activitat.
   - **Clau principal**: seleccioneu el camp que identifica de manera única un registre. No hauria de contenir cap valor duplicat, valors buits o valors que faltin.

     > [!NOTE]
     > La clau principal de cada fila ha de mantenir-se coherent en font de dades actualitzacions. Si la clau principal d'una fila s'actualitza en una font de dades actualització, crea duplicats a l'entitat Activitat de sortida. 


1. **Al pas Relacions**, creeu una relació indirecta entre les dades de la font de l'activitat i els comptes, utilitzant les vostres dades de contacte com a entitat intermediària. Per obtenir més informació, vegeu [camins de relació directa i indirecta](relationships.md#relationship-paths).
   - Exemple de relació per a una activitat anomenada *Compres*:
      - **Compres Font Dades d'activitat Dades** > **de contacte a** l'atribut **ContactID**
      - **Dades de contacte** > **Dades del compte a** l'atribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Exemple de configuració de relacions.":::

1. Després de configurar les relacions, seleccioneu **Següent** i completeu la configuració de l'assignació d'activitats. Per obtenir passos detallats sobre la creació d'activitats, vegeu [definir una activitat](#define-a-customer-activity) de client.

1. Executeu els vostres mapes d'activitats.

1. Les vostres activitats al nivell de contacte ara seran visibles a la cronologia del client.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultat final després de configurar les activitats de contacte":::

## <a name="contact-level-activity-timeline-filtering"></a>Filtratge de la cronologia de l'activitat a nivell de contacte

Després de configurar un mapatge d'activitats de nivell de contacte i executar-lo, s'actualitzarà la cronologia d'activitats dels vostres clients. Inclou els seus identificadors o noms, en funció de la configuració *de ContactProfile*, per a les activitats en què van actuar. Podeu filtrar les activitats per contactes a la cronologia per veure els contactes específics que us interessen. A més, podeu veure totes les activitats que no estan assignades a un contacte específic seleccionant **Activitats no assignades a un Contacte**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opcions de filtratge disponibles per a les activitats de nivell de contacte.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
