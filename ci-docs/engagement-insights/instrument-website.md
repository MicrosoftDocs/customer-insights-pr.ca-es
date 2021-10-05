---
title: Afegir codi al vostre lloc web
description: Com s'afegeix un fragment de codi per capturar incidències del Dynamics 365 Customer Insights al lloc web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558781"
---
# <a name="install-the-web-sdk-on-a-website"></a>Instal·lar l'SDK web en un lloc web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En aquest article es descriu com un administrador instal·la el conjunt d'eines de desenvolupament de programari web (SDK) en un lloc web. Començareu a veure incidències a l'espai de treball poc després d'instrumentar el lloc web. Per obtenir més informació, vegeu [Administrar àrees de treball i entorn](manage-environments-workspaces.md). Per capturar esdeveniments a les aplicacions mòbils, vegeu [Informació general sobre els recursos per a desenvolupadors](developer-resources.md).


### <a name="prerequisites"></a>Requisits previs

* Per emmagatzemar les dades, heu de tenir permisos d'administrador per a l'àrea de treball.
* El vostre lloc web o projecte s'ha d'allotjar en línia per enviar dades d'activitat. El servidor no accepta les dades enviades des d'un fitxer local.


## <a name="add-web-sdk-to-your-website"></a>Afegir SDK web al vostre lloc web

Aneu a **Administrador** > **Àrea de treball** i, a continuació, seleccioneu **Guia d'instal·lació**. Hi ha dues opcions per instal·lar una SDK web. La primera és utilitzar un enllaç de baixada, i la segona és instal·lar un paquet d'administrador de paquets de node (NPM).

### <a name="option-1-using-the-download-link"></a>Opció 1: amb l'enllaç de baixada

1. Seleccioneu **Copia el codi** per copiar el fragment de codi. Per defecte, la clau d'ingestió de l'àrea de treball està incrustada al fragment de codi.
  :::image type="content" source="media/copy-code.png" alt-text="Captura de pantalla de la pàgina del fragment de codi.":::

1. Afegiu el codi copiat al lloc web, a prop de <head> l'etiqueta i abans de qualsevol altre script o etiquetes CSS.
1. Publiqueu el lloc web actualitzat i espereu uns minuts per capturar el trànsit web entrant.
1. Per veure les dades, seleccioneu l'àrea de treball al commutador de l'àrea de treball de la subfinestra de navegació. A continuació, seleccioneu un dels informes a la secció **Descobrir**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Opció 2: utilitzar el paquet NPM (recomanat per a les aplicacions web basades en JavaScript)

1. Aneu a la nostra [pàgina web d'NPM](https://www.npmjs.com/package/engagementinsights-web) i seguiu les instruccions per instal·lar i configurar el paquet NPM de l'SDK web.
1. Publiqueu el lloc web actualitzat i espereu uns minuts per capturar el trànsit web entrant.
1. Per veure les dades, seleccioneu l'àrea de treball al commutador de l'àrea de treball de la subfinestra de navegació. A continuació, seleccioneu un dels informes a la secció **Descobrir**.

## <a name="configuration-options"></a>Opcions de configuració

Podeu canviar les opcions de configuració següents al fragment de codi:

- **ingestionKey**: la clau d'ingestió que s'utilitza per enviar incidències a l'àrea de treball. Podeu canviar la clau d'ingestió per enviar incidències a una àrea de treball diferent. Una clau d'ingestió és única per a cada àrea de treball.
- **autoCapture**: especifica si es capturen les visualitzacions de pàgina i les interaccions amb el lloc web. Té dues opcions:
    - **view** : definiu-lo com a *cert* per capturar visualitzacions de pàgina. Les visualitzacions de pàgina es capturen com a [incidències](glossary.md#event) *de visualització*, un tipus d'[incidència de base](glossary.md#base-event).
    - **click**: Definiu-lo com a *cert* per capturar interaccions de visitant al lloc web. Les interaccions es capturen com a [incidències](glossary.md#event) *d'acció*, un tipus d'[incidència de base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
