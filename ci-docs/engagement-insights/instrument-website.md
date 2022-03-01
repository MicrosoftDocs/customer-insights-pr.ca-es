---
title: Afegir codi al vostre lloc web
description: Com s'afegeix una fragment de codi per capturar incidències al lloc web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035082"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instal·lar el fragment de codi en un lloc web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Aquest article descriu com ha d'instal·lar un administrador el fragment de codi en un lloc web. Veureu incidències a l'àrea de treball poc després d'afegir l'script al lloc web. Per obtenir més informació, vegeu [Administrar àrees de treball i entorn](manage-environments-workspaces.md). Per capturar esdeveniments a les aplicacions mòbils, vegeu [Informació general sobre els recursos per a desenvolupadors](developer-resources.md).


### <a name="prerequisites"></a>Requisits previs

* Per emmagatzemar les dades, heu de tenir permisos d'administrador per a l'àrea de treball.
* El vostre lloc web o projecte s'ha d'allotjar en línia per enviar dades d'activitat. El servidor no accepta les dades enviades des d'un fitxer local.


## <a name="add-code-to-your-website"></a>Afegir codi al vostre lloc web
1.  Aneu a **Administrador** > **Àrea de treball** i, a continuació, seleccioneu **Guia d'instal·lació**.
1. Seleccioneu **Copia el codi** per copiar el fragment de codi. Per defecte, la clau d'ingestió de l'àrea de treball està incrustada al fragment de codi.
:::image type="content" source="media/copy-code.png" alt-text="Captura de pantalla de la pàgina del fragment de codi.":::
3. Afegiu el fragment de codi copiat al lloc web, a prop del <head> l'etiqueta i abans de qualsevol altre script o etiquetes CSS.
4.  Publiqueu el lloc web actualitzat i espereu uns minuts per capturar el trànsit web entrant.
5.  Per veure les dades, seleccioneu l'àrea de treball al commutador de l'àrea de treball de la subfinestra de navegació. A continuació, seleccioneu un dels informes a la secció **Descobrir**.

## <a name="configuration-options"></a>Opcions de configuració

Podeu canviar les opcions de configuració següents al fragment de codi:

- **ingestionKey**: la clau d'ingestió que s'utilitza per enviar incidències a l'àrea de treball. Podeu canviar la clau d'ingestió per enviar incidències a una àrea de treball diferent. Una clau d'ingestió és única per a cada àrea de treball. 
- **autoCapture**: especifica si es capturen les visualitzacions de pàgina i les interaccions amb el lloc web. Té dues opcions:
    - **view** : definiu-lo com a *cert* per capturar visualitzacions de pàgina. Les visualitzacions de pàgina es capturen com a [incidències](glossary.md#event) *de visualització*, un tipus d'[incidència de base](glossary.md#base-event).
    - **click**: Definiu-lo com a *cert* per capturar interaccions de visitant al lloc web. Les interaccions es capturen com a [incidències](glossary.md#event) *d'acció*, un tipus d'[incidència de base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
