---
title: Assignacions semàntiques (versió preliminar)
description: Informació general de les assignacions semàntiques i de com utilitzar-les.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: a60855f6d5616ca9b958752836d1071ae3433db0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642335"
---
# <a name="semantic-mappings-preview"></a>Assignacions semàntiques (versió preliminar)

Les assignacions semàntiques us permeten assignar les dades que no són d'activitat a esquemes predefinits. Aquests esquemes ajuden el Customer Insights a entendre millor els atributs de dades. L'assignació semàntica i les dades proporcionades permeten noves estadístiques i característiques a Customer Insights. Per assignar les dades de l'activitat a esquemes, reviseu la documentació d'[activitats](activities.md).

**Les assignacions semàntiques estan habilitades actualment per a entorns basats en comptes empresarials**. *ContactProfile* és l'únic tipus d'assignació semàntica disponible actualment al Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definir una assignació d'entitats semàntica de ContactProfile

1. Aneu a **Assignacions de DataSemantic** > **(previsualització)**.

1. Seleccioneu **Afegeix assignació semàntica** per iniciar l'experiència guiada.

1. Al pas de **Dades de l'entitat**, definiu els valors per als camps següents:

   - **Nom d'assignació d'entitat semàntica**: proporcioneu un nom per a l'assignació d'entitat semàntica.
   - **Entitat d'origen**: seleccioneu una entitat que inclogui dades de contacte.
   - **Clau principal**: seleccioneu el camp que identifica un registre de contacte. No hauria de contenir cap valor duplicat, valors buits o valors que faltin.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configurar l'assignació d'entitat semàntica amb el nom, l'entitat d'origen i la clau principal.":::

1. Per continuar, feu clic a **Següent**.

1. En el pas **Relacions**, configureu els detalls per connectar les dades del compte a les seves dades de compte corresponents. Aquest pas visualitza la connexió entre entitats.  

   Hi ha dos tipus de camins de relació que es poden implementar: **Relacions directes** i **Relacions indirectes**. Per obtenir més informació, aneu a [camins de relació directes i indirectes](relationships.md#relationship-paths).

   1. Seleccioneu **Afegeix una relació** per configurar la relació.
   1. Trieu l'atribut de l'entitat d'origen que connecta l'entitat de contacte amb una altra entitat.
   1. Trieu l'entitat amb la qual voleu connectar l'entitat de contacte. Podeu triar una entitat de la secció **Entitats Compte** o **Entitat intermèdia**. Si seleccioneu una entitat intermèdia, heu de definir una segona relació per connectar-vos a l'entitat de compte de destinació.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Seleccioneu una entitat Compte o una entitat Intermèdia.":::

   1. Proporcioneu un **Nom de la relació**. Si ja hi ha una relació entre les vostres entitats, el nom de la relació és només de lectura. Si no hi ha cap relació, es crearà una relació nova amb el nom que proporcioneu.
   1. Seleccioneu **Aplica** per finalitzar la configuració de la relació.

   > [!NOTE]
   > Podeu configurar més relacions entre l'entitat de contacte i altres entitats de compte amb entitats intermèdies.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualització de diverses relacions que connecten entitats de contacte a entitats de compte.":::

1. Seleccioneu **Següent** quan hagueu acabat la configuració de la relació.

1. Al pas **Definiu el tipus semàntic**, trieu un **Tipus semàntic**. Actualment hi ha un **Tipus semàntic** anomenat *ContactProfile*.

1. Assigneu les dades al **Tipus semàntic** *ContactProfile* per als camps mostrats.
   - Camp necessari: identificador de contacte
   - Camps opcionals: nom, cognom, data de naixement, sexe, correu electrònic principal i telèfon principal

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Assigneu els atributs de dades de contacte als camps obligatoris i opcionals proporcionats.":::

1. Per continuar, feu clic a **Següent**.

1. Al pas **Revisió**, feu un cop d'ull a la configuració de l'assignació semàntica. Seleccioneu **Edita** per a la secció corresponent per fer-hi canvis.

1. Seleccioneu **Desa** per desar la nova **Assignació semàntica**.

1. Després de desar, podeu seleccionar **Executa** per al procés de l'assignació semàntica o podeu seleccionar **Tanca** per desar l'assignació semàntica sense processar-la.

1. Per executar una assignació semàntica en un moment posterior, seleccioneu l'assignació semàntica i seleccioneu **Actualitza**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Administrar assignacions semàntiques existents

A **Dades** > **Assignacions semàntiques (versió preliminar)**, podeu visualitzar totes les assignacions semàntiques desades i administrar-les. Cada assignació semàntica es representa amb una fila independent. Trobareu detalls sobre l'entitat d'origen, el tipus semàntic, el tipus d'assignació i el seu estat.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcions per administrar assignacions semàntiques.":::

- **Edita**: obre la configuració de l'assignació semàntica en el pas de revisió. Podeu canviar la configuració actual. Seleccioneu **Desa** i **Executa** per processar els canvis.

- **Actualitza**: actualitza l'assignació semàntica seleccionada amb les dades més actualitzades de les entitats que formen part de la seva configuració. Actualitzar qualsevol assignació semàntica determinada actualitzarà totes les assignacions semàntiques del mateix tipus.

- **Canvia el nom**: obre un diàleg on podeu introduir un nom diferent per a l'assignació semàntica seleccionada. Seleccioneu **Desa** per aplicar els canvis.

- **Suprimeix**: obre un diàleg per confirmar la supressió de l'assignació semàntica seleccionada. També podeu suprimir més d'una assignació semàntica alhora seleccionant les assignacions semàntiques i la icona de supressió. Seleccioneu **Suprimeix** per confirmar la supressió.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Utilitzeu una assignació d'entitats semàntiques ContactProfile per crear activitats de nivell de contacte

Després de crear una *assignació d'entitats semàntiques ContactProfile*, podeu capturar activitats de contactes. Us permet veure a la cronologia de l'activitat d'un compte quin contacte era el responsable de cada activitat. La majoria dels passos segueixen la configuració típica de l'assignació d'activitats.

   > [!NOTE]
   > Perquè les activitats de nivell de contacte funcionin, heu de tenir **atributs AccountID** i **ContactID** per a cada registre dins de les dades d'activitat.

1. [Definiu una assignació d'entitats *semàntiques ContactProfile* .](#define-a-contactprofile-semantic-entity-mapping) I executar l'assignació semàntica.

1. Aneu a **DataActivities** > **·**.

1. Seleccioneu **Afegeix activitat** per crear una activitat nova.

1. Anomeneu l'activitat, seleccioneu l'entitat d'activitat d'origen i seleccioneu la clau principal de l'entitat d'activitat.

1. **Al pas Relacions**, creeu una relació indirecta entre les dades d'origen de l'activitat als comptes, utilitzant les dades de contacte com a entitat intermediària. Per obtenir més informació, vegeu [camins](relationships.md#relationship-paths) de relació directa i indirecta.
   - Relació d'exemple per a una activitat anomenada *Compres*:
      - **Compres Dades de la data de l'activitat** > **d**'origen a l'atribut **ContactID**
      - **Dades** > **de data** de contacte a l'atribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Configuració de la relació d'exemple.":::

1. Després de configurar les relacions, seleccioneu Endavant **i completeu** la configuració de l'assignació d'activitats. Per obtenir passos detallats sobre la creació d'activitats, vegeu [definir una activitat](activities.md).

1. Executeu les assignacions d'activitats.

1. Les activitats del nivell de contacte ara seran visibles a la cronologia del client.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultat final després de configurar les activitats de contacte":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtratge de cronologia d'activitat a nivell de contacte

Després de configurar una assignació d'activitat de nivell de contacte i executar-la, s'actualitzarà la cronologia de l'activitat dels clients. Inclou els seus identificadors o noms, en funció de la configuració *de ContactProfile*, per a les activitats en què van actuar. Podeu filtrar les activitats per contactes a la cronologia per veure els contactes específics que us interessen. A més, podeu veure totes les activitats que no estan assignades a un contacte específic seleccionant **Activitats no assignades a un contacte**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opcions de filtratge disponibles per a les activitats de nivell de contacte.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
