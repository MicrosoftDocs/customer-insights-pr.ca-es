---
title: Assignacions semàntiques (versió preliminar)
description: Informació general de les assignacions semàntiques i de com utilitzar-les.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622923"
---
# <a name="semantic-mappings"></a>Assignacions semàntiques

Les assignacions semàntiques us permeten assignar les dades que no són d'activitat a esquemes predefinits. Aquests esquemes ajuden a entendre millor els atributs de dades a les conclusions del públic. Les assignacions semàntiques i les dades proporcionades permeten nous coneixements i característiques a les conclusions del públic. Per assignar les dades de l'activitat a esquemes, reviseu la documentació d'[activitats](activities.md).

**Les assignacions semàntiques estan habilitades actualment per a entorns basats en comptes empresarials**. *ContactProfile* és l'únic tipus d'assignació semàntica que actualment està disponible a les conclusions del públic.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definir una assignació d'entitats semàntica de ContactProfile

1. A les conclusions del públic, aneu a **Dades** > **Assignacions semàntiques (versió preliminar)**.

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

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.

## <a name="manage-existing-semantic-mappings"></a>Administrar assignacions semàntiques existents

A **Dades** > **Assignacions semàntiques (versió preliminar)**, podeu visualitzar totes les assignacions semàntiques desades i administrar-les. Cada assignació semàntica es representa amb una fila independent. Trobareu detalls sobre l'entitat d'origen, el tipus semàntic, el tipus d'assignació i el seu estat.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcions per administrar assignacions semàntiques.":::

- **Edita**: obre la configuració de l'assignació semàntica en el pas de revisió. Podeu canviar la configuració actual. Seleccioneu **Desa** i **Executa** per processar els canvis.

- **Actualitza**: actualitza l'assignació semàntica seleccionada amb les dades més actualitzades de les entitats que formen part de la seva configuració. Actualitzar qualsevol assignació semàntica determinada actualitzarà totes les assignacions semàntiques del mateix tipus.

- **Canvia el nom**: obre un diàleg on podeu introduir un nom diferent per a l'assignació semàntica seleccionada. Seleccioneu **Desa** per aplicar els canvis.

- **Suprimeix**: obre un diàleg per confirmar la supressió de l'assignació semàntica seleccionada. També podeu suprimir més d'una assignació semàntica alhora seleccionant les assignacions semàntiques i la icona de supressió. Seleccioneu **Suprimeix** per confirmar la supressió.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
