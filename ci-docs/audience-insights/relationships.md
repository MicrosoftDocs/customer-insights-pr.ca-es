---
title: Relacions entre entitats i camins d'entitats
description: Creeu i administreu relacions entre entitats procedents de diverses fonts de dades.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269856"
---
# <a name="relationships-between-entities"></a>Relacions entre entitats

Les relacions us ajuden a connectar entitats i generen un gràfic de dades quan les entitats comparteixen un identificador comú (clau externa) al qual es pot fer referència d'una entitat a una altra. Les entitats connectades us permeten definir segments i mesures segons diverses fonts de dades.

Hi ha dos tipus de relacions. Relacions del sistema no editables, que es creen automàticament, i relacions personalitzades, creades i configurades pels usuaris.

Durant els processos de coincidència i combinació, les relacions del sistema es creen en segon terme segons coincidències intel·ligents. Aquestes relacions ajuden a relacionar els registres de perfil del client amb registres d'altres entitats corresponents. El diagrama següent il·lustra la creació de tres relacions del sistema quan l'entitat de client coincideix amb entitats addicionals per produir l'entitat de perfil del client final.

> [!div class="mx-imgBorder"]
> ![Creació de relació](media/relationships-entities-merge.png "Creació de relació")

- Es crea una **relació *CustomerToContact*** entre l'entitat Client i l'entitat Contacte. L'entitat Client obté el camp clau **Contact_contactId** relacionar-se amb el camp clau **contactId** de l'entitat Contacte.
- Es crea una **relació *CustomerToAccount*** entre l'entitat Client i l'entitat Compte. L'entitat Client obté el camp clau **Account_contactId** relacionar-se amb el camp clau **accountId** de l'entitat Compte.
- Es crea una **relació *CustomerToWebAccount*** entre l'entitat Client i l'entitat WebAccount. L'entitat Client obté el camp clau **WebAccount_webaccountId** relacionar-se amb el camp clau **webaccountId** de l'entitat WebAccount.

## <a name="create-a-relationship"></a>Crear una relació

Definiu les relacions personalitzades a la pàgina **Relacions**. Cada relació es compon d'una entitat d'origen (l'entitat que conté la clau externa) i una entitat de destinació (l'entitat a la qual apunta la clau externa de l'entitat d'origen).

1. A les conclusions del públic, aneu a **Dades** > **Relacions**.

2. Seleccioneu **Nova relació**.

3. A la subfinestra **Afegeix una relació**, proporcioneu la informació següent:

   > [!div class="mx-imgBorder"]
   > ![Introduïu els detalls de la relació](media/relationships-add.png "Introduïu els detalls de la relació")

   - **Nom de la relació**: nom que reflecteix la finalitat de la relació (per exemple, **AccountWebLogs**).
   - **Descripció**: descripció de la relació.
   - **Entitat d'origen**: seleccioneu l'entitat que s'utilitza com a origen a la relació (per exemple, WebLog).
   - **Cardinalitat**: seleccioneu la cardinalitat dels registres de l'entitat d'origen. Per exemple, "molts" significa que hi ha diversos registres Weblog relacionats amb un WebAccount.
   - **Camp de clau d'origen**: representa el camp de clau externa a l'entitat d'origen. Per exemple, WebLog té el camp de clau externa **accountId**.
   - **Entitat de destinació**: seleccioneu l'entitat que s'utilitza com a destinació a la relació (per exemple, WebAccount).
   - **Cardinalitat de destinació**: seleccioneu la cardinalitat dels registres de l'entitat de destinació. Per exemple, "un" significa que hi ha diversos registres Weblog relacionats amb un WebAccount.
   - **Camp de clau de destinació**: aquest camp representa el camp de clau de l'entitat de destinació. Per exemple, WebAccount té el camp de clau **accountId**.

> [!NOTE]
> Només s'admeten les relacions de diversos a un i d'un a un. Es poden crear relacions de diversos a diversos amb dues relacions de diversos a un i una entitat d'enllaç (una entitat que s'utilitza per connectar l'entitat d'origen i l'entitat de destinació).

## <a name="delete-a-relationship"></a>Suprimir una relació

1. A les conclusions del públic, aneu a **Dades** > **Relacions**.

2. Activeu les caselles de selecció de les relacions que voleu suprimir.

3. Seleccioneu **Suprimeix** a la part superior de la taula **Relacions**.

4. Confirmeu la supressió.

## <a name="next-step"></a>Pas següent

Les relacions de sistema i personalitzades s'utilitzen per crear segments basats en diverses fonts de dades que ja no estan aïllades. Per obtenir més informació, vegeu [Segments](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]