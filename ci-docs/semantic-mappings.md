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
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183619"
---
# <a name="semantic-mappings-preview"></a>Assignacions semàntiques (versió preliminar)

Les assignacions semàntiques us permeten assignar les dades que no són d'activitat a esquemes predefinits. Aquests esquemes ajuden el Customer Insights a entendre millor els atributs de dades. L'assignació semàntica i les dades proporcionades permeten noves estadístiques i característiques al Customer Insights. Per assignar les dades de l'activitat a esquemes, reviseu la documentació d'[activitats](activities.md).

**Les assignacions semàntiques estan habilitades actualment per a entorns basats en comptes empresarials**. *ContactProfile* és l'únic tipus d'assignació semàntica disponible actualment al Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definir una assignació d'entitats semàntica de ContactProfile

1. Aneu a **Mapes semàntics de dades** > **(vista prèvia)**.

1. Seleccioneu **Afegeix assignació semàntica** per iniciar l'experiència guiada.

1. Al pas de **Dades de l'entitat**, definiu els valors per als camps següents:

   - **Nom** de l'assignació d'entitats semàntiques: Nom per a l'assignació d'entitats semàntiques.
   - **Entitat d'origen**: entitat que inclou dades de contacte.
   - **Clau primària**: camp que identifica de manera única un registre de contacte. No hauria de contenir cap valor duplicat, valors buits o valors que faltin.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configurar l'assignació d'entitat semàntica amb el nom, l'entitat d'origen i la clau principal.":::

1. Seleccioneu **Següent**.

1. En el pas **Relacions**, configureu els detalls per connectar les dades del compte a les seves dades de compte corresponents. Aquest pas visualitza la connexió entre entitats.  

   Hi ha dos tipus de camins de relació que es poden implementar: **Relacions directes** i **Relacions indirectes**. Per obtenir més informació, aneu a [camins de relació directes i indirectes](relationships.md#relationship-paths).

   1. Seleccioneu **Afegeix relació** per configurar la relació.
   1. Trieu l'atribut de l'entitat d'origen que connecta l'entitat de contacte amb una altra entitat.
   1. Trieu l'entitat amb la qual voleu connectar l'entitat de contacte. Trieu una entitat de la **secció Entitats** del compte o Entitat **intermèdia**. Si seleccioneu una entitat intermèdia, definiu una segona relació per connectar-vos a l'entitat del compte de destinació.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Seleccioneu una entitat Compte o una entitat Intermèdia.":::

   1. Proporcioneu un **Nom de la relació**. Si ja hi ha una relació entre les vostres entitats, el nom de la relació és només de lectura. Si no hi ha cap relació, es crearà una relació nova amb el nom que proporcioneu.
   1. Seleccioneu **Aplica** per finalitzar la configuració de la relació.

   > [!NOTE]
   > Podeu configurar més relacions entre l'entitat de contacte i altres entitats de compte amb entitats intermèdies.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualització de diverses relacions que connecten entitats de contacte a entitats de compte.":::

1. Seleccioneu **Següent**.

1. Al pas **Definiu el tipus semàntic**, trieu un **Tipus semàntic**. Actualment hi ha un **Tipus semàntic** anomenat *ContactProfile*.

1. Assigneu el vostre identificador de contacte al *tipus semàntic ContactProfile* Tipus **de** contacte. Opcionalment, assigneu altres camps, com ara nom, cognom, sexe o correu electrònic.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Assigneu els atributs de dades de contacte als camps obligatoris i opcionals proporcionats.":::

1. Seleccioneu **Següent**.

1. En el pas **De revisió**, reviseu la configuració de l'assignació semàntica. Per fer canvis, seleccioneu **Edita** per a la secció corresponent.

1. Seleccioneu **Desa**.

1. Per processar l'assignació semàntica, seleccioneu **Executa**. O seleccioneu **Tanca** per desar l'assignació semàntica sense processar-la. Per executar-lo més tard, seleccioneu l'assignació semàntica i seleccioneu **Actualitza**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Administrar assignacions semàntiques existents

Aneu a **Mapes semàntics de dades** > **(vista prèvia)** per veure les assignacions semàntiques desades, la seva entitat d'origen, el tipus semàntic, el tipus d'assignació i l'estat.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcions per administrar assignacions semàntiques.":::

Seleccioneu l'assignació semàntica per veure les accions disponibles.
- **Editeu** la configuració actual. Seleccioneu **Desa** i **Executa** per processar els canvis.
- **Actualitzeu** l'assignació semàntica per incloure les dades més recents. Actualitzar qualsevol assignació semàntica determinada actualitzarà totes les assignacions semàntiques del mateix tipus.
- **Canvieu** el nom de l'assignació semàntica. Seleccioneu **Desa**.
- **Suprimir** l'assignació semàntica. Per eliminar més d'un mapatge semàntic alhora, seleccioneu els mapes semàntics i la icona d'esborrar. Seleccioneu **Suprimeix** per confirmar la supressió.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Utilitzeu una assignació d'entitats semàntiques ContactProfile per crear activitats a nivell de contacte

Després de crear un mapatge d'entitats *semàntiques ContactProfile*, podeu capturar activitats de contactes. Us permet veure a la cronologia d'activitats d'un compte quin contacte era responsable de cada activitat. La majoria de passos segueixen la configuració típica de l'assignació d'activitats.

   > [!NOTE]
   > Perquè les activitats del nivell de contacte funcionin, heu de tenir **atributs AccountID** i **ContactID** per a cada registre a les dades de l'activitat.

1. [Definiu un mapatge *d'entitats* semàntiques ContactProfile](#define-a-contactprofile-semantic-entity-mapping) i executeu l'assignació semàntica.

1. Aneu a **Activitats** > **de dades**.

1. Seleccioneu **Afegeix activitat** per crear una activitat nova.

1. Anomeneu l'activitat, seleccioneu l'entitat d'activitat d'origen i seleccioneu la clau principal de l'entitat de l'activitat.

1. **Al pas Relacions**, creeu una relació indirecta entre les dades de la font de l'activitat i els comptes, utilitzant les vostres dades de contacte com a entitat intermediària. Per obtenir més informació, vegeu [camins](relationships.md#relationship-paths) de relació directa i indirecta.
   - Exemple de relació per a una activitat anomenada *Compres*:
      - **Compres Font Dades d'activitat Dades** > **de contacte a** l'atribut **ContactID**
      - **Dades de contacte** > **Dades del compte a** l'atribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Exemple de configuració de relacions.":::

1. Després de configurar les relacions, seleccioneu **Següent** i completeu la configuració de l'assignació d'activitats. Per obtenir passos detallats sobre la creació d'activitats, vegeu [definir una activitat](activities.md).

1. Executeu els vostres mapes d'activitats.

1. Després que s'executi una assignació d'activitat al nivell de contacte, seleccioneu **Clients**. Les activitats del nivell de contacte es mostren a la cronologia del client.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultat final després de configurar les activitats de contacte":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtratge de la cronologia de l'activitat a nivell de contacte

La cronologia d'activitats dels vostres clients inclou els seus identificadors o noms, en funció de la *configuració de ContactProfile*, per a les activitats en què han actuat. Filtreu les activitats per contactes a la cronologia per veure els contactes específics que us interessin. Per visualitzar totes les activitats que no estan assignades a un contacte específic, seleccioneu **Activitats no assignades a un Contacte**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Opcions de filtratge disponibles per a les activitats de nivell de contacte.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
