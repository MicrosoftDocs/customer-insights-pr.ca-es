---
title: Administrar permisos d'usuaris
description: Informeu-vos sobre els permisos i les funcions d'usuari.
ms.date: 02/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: 8022563f8994400b88389c20d7d661d9ea82bab1
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833710"
---
# <a name="user-permissions"></a>Permisos d'usuari

La **pàgina Permisos** és on configurareu funcions i permisos per utilitzar el Customer Insights.

Heu de tenir permisos d'administrador per veure la pàgina. Per accedir a la pàgina de permisos, aneu a **Usuaris de seguretat** > **d'administració** > **·**.

Hi ha tres tipus de funcions:

## <a name="viewer"></a>Visualitzador

- Exploreu conclusions i segments a les pàgines **Inici** i **Segments**.
- Cerqueu i filtre perfils de client mitjançant la pàgina **Clients**. S'ha de poder cercar a tots els camps.
- Visualitzeu i exploreu la pàgina **Enriquiment**.
- Exploreu i exporteu entitats mitjançant la pàgina **Entitats**.
- Visualitzeu l'estat dels processos del sistema mitjançant la pàgina **Sistema**.
- Visualitzeu les exportacions a la pàgina **Exportacions**.
- Instal·leu i utilitzeu l'escriptori digital del **Power BI Customer Insights**.

## <a name="contributor"></a>Col·laborador

- Tots els permisos disponibles per al visualitzador.
- Carregueu i transformeu dades mitjançant la pàgina **Fonts de dades**.
- Completat ***Unificació** de dades que donen lloc a l'entitat unificada del perfil de client.
- Definiu **Relacions** i **Activitats**.
- Creeu segments mitjançant la pàgina **Segments**.
- Creeu mesures mitjançant la pàgina **Mesures**.
- Administrar la configuració i enriquir els perfils dels clients des de la pàgina **Enriquiment** (només per a enriquiment propi).
- Administrar i crear exportacions a partir de connexions compartides amb col·laboradors. [Més informació sobre com els administradors permeten als col·laboradors utilitzar una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administrador

- Tots els permisos disponibles per al col·laborador.
- Canvieu la configuració de la pàgina **Sistema**, incloent-hi l'idioma de treball i les planificacions d'actualitzacions per als processos del sistema.
- Visualitzeu i afegiu permisos mitjançant la pàgina **Permisos**.
- Definiu les definicions de filtre i cerca per a la pàgina Clients mitjançant la pàgina **Cerca i filtra l'índex** (accessible a través de la pàgina **Clients**).
- Administrar connexions i permetre-les per a altres funcions d'usuari a la pàgina **Connexions**.
- Administrar la configuració i enriquir els perfils dels clients des de la pàgina **Enriquiment** (per a tots els enriquiments).
- Administrar i crear exportacions a la pàgina **Exportacions**.
- Instal·leu i utilitzeu el **Complement de targeta del client**.
- Afegiu i utilitzeu el **connector del Power Apps**.
- Habiliteu l'ús de les [API del Customer Insights](apis.md).
- [Assigna la propietat de l'entorn](manage-environments.md#change-the-owner-of-an-environment) a un altre administrador.

## <a name="admin-owner"></a>Administrador (propietari)

- Tots els permisos disponibles per a l'administrador.
- [Reinicialitza i suprimeix](manage-environments.md#reset-an-existing-environment-preview) l'entorn.

## <a name="assign-roles-and-permissions"></a>Assignar funcions i permisos

1. Aneu a **seguretat** > **de l'administrador**> **Usuaris***.

1. Seleccioneu **Afegeix usuaris** per obrir la subfinestra **Afegeix o edita els permisos**.

1. Utilitzeu el camp **Cerca** per cercar el grup o l'usuari de l'Azure Active Directory al que voleu ajustar els permisos. Seleccioneu una **Funció** per assignar-la a l'usuari o al grup.

1. Seleccioneu **Desa**. L'entorn actual es compartirà automàticament amb l'usuari o els membres del grup pels quals hagueu canviat els permisos. Els usuaris poden accedir a l'aplicació Customer Insights i treballar d'acord amb la funció especificada.

## <a name="view-current-permissions"></a>Veure els permisos actuals

Aneu a **Usuaris** > **de seguretat** > **d'administració** per veure quines tasques de rol estan actives actualment.

- La columna **Tipus** especifica un únic usuari, grup o aplicació. El sistema admet usuaris i grups individuals.
- Les funcions s'especifiquen a la columna **Funció**.
- Seleccioneu qualsevol títol de columna per ordenar els resultats pel valor de la columna.
- Utilitzeu el camp **Cerca** de la part superior de la pàgina per localitzar usuaris concrets.


[!INCLUDE [footer-include](includes/footer-banner.md)]
