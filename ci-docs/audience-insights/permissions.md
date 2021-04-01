---
title: Administrar permisos d'usuaris
description: Informeu-vos sobre els permisos i les funcions d'usuari.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595690"
---
# <a name="user-permissions"></a>Permisos d'usuari

La pàgina **Permisos** és on configurareu funcions i permisos per utilitzar les conclusions del públic.

Heu de tenir permisos d'administrador per veure la pàgina. Per accedir a la pàgina de permisos de les conclusions del públic, aneu a **Administració** > **Permisos**.

Hi ha tres tipus de funcions:

## <a name="viewer"></a>Visualitzador

- Exploreu conclusions i segments a les pàgines **Inici** i **Segments**.
- Cerqueu i filtre perfils de client mitjançant la pàgina **Clients**. S'ha de poder cercar a tots els camps.
- Visualitzeu i exploreu la pàgina **Enriquiment**.
- Exploreu i exporteu entitats mitjançant la pàgina **Entitats**.
- Visualitzeu l'estat dels processos del sistema mitjançant la pàgina **Sistema**.
- Exporteu segments de la pàgina **Segments**.
- Instal·leu i utilitzeu l'escriptori digital del **Power BI Customer Insights**.

## <a name="contributor"></a>Col·laborador

- Tots els permisos disponibles per al visualitzador.
- Carregueu i transformeu dades mitjançant la pàgina **Fonts de dades**.
- Completeu les seccions d'*Unificació de dades* (**Assignació**, **Coincidència** i **Combinació**) resultants a l'entitat de perfil de client unificat.
- Definiu **Relacions** i **Activitats**.
- Creeu segments mitjançant la pàgina **Segments**.
- Creeu mesures mitjançant la pàgina **Mesures**.
- Administrar la configuració i enriquir els perfils dels clients des de la pàgina **Enriquiment** (només per a enriquiment propi).

## <a name="administrator"></a>Administrador

- Tots els permisos disponibles per al col·laborador.
- Canvieu la configuració de la pàgina **Sistema**, incloent-hi l'idioma de treball i les planificacions d'actualitzacions per als processos del sistema.
- Visualitzeu i afegiu permisos mitjançant la pàgina **Permisos**.
- Definiu les definicions de filtre i cerca per a la pàgina Clients mitjançant la pàgina **Cerca i filtra l'índex** (accessible a través de la pàgina **Clients**).
- Definiu destinacions de segment del Dynamics 365 Sales mitjançant la pàgina **Destinacions d'exportació**.
- Administrar la configuració i enriquir els perfils dels clients des de la pàgina **Enriquiment** (per a tots els enriquiments).
- Instal·leu i utilitzeu el **Complement de targeta del client**.
- Afegiu i utilitzeu el **connector del Power Apps**.
- Habiliteu l'ús de les [API del Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Assignar funcions i permisos

1. A les conclusions del públic, aneu a **Administració** > **Permisos**.

1. Seleccioneu **Afegeix usuaris** per obrir la subfinestra **Afegeix o edita els permisos**.

1. Utilitzeu el camp **Cerca** per cercar el grup o l'usuari de l'Azure Active Directory al que voleu ajustar els permisos. Seleccioneu una **Funció** per assignar-la a l'usuari o al grup.

1. Seleccioneu **Desa**. L'entorn actual es compartirà automàticament amb l'usuari o els membres del grup pels quals hagueu canviat els permisos. Els usuaris poden accedir a l'aplicació Customer Insights i treballar d'acord amb la funció especificada.

## <a name="view-current-permissions"></a>Veure els permisos actuals

A les conclusions del públic, aneu a **Administració** > **Permisos** per veure les assignacions de funcions que hi ha actives actualment.

- La columna **Tipus** especifica un únic usuari, grup o aplicació. El sistema admet usuaris i grups individuals.
- Les funcions s'especifiquen a la columna **Funció**.
- Seleccioneu qualsevol títol de columna per ordenar els resultats pel valor de la columna.
- Utilitzeu el camp **Cerca** de la part superior de la pàgina per localitzar usuaris concrets.


[!INCLUDE[footer-include](../includes/footer-banner.md)]