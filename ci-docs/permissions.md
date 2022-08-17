---
title: Assignar permisos d'usuari
description: Informeu-vos sobre els permisos i les funcions d'usuari.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245407"
---
# <a name="assign-user-permissions"></a>Assignar permisos d'usuari

L'accés al Customer Insights està restringit als usuaris de l'organització que un administrador afegeix a l'aplicació. Un administrador pot afegir, editar o eliminar usuaris. Un usuari pot ser un sol usuari, grup o aplicació. Hi ha tres tipus de rols que pot tenir un usuari:

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
- Completa la **Unificació** de dades que dóna lloc a l'entitat unificada del perfil de client.
- Definiu **Relacions** i **Activitats**.
- Creeu segments mitjançant la pàgina **Segments**.
- Creeu mesures mitjançant la pàgina **Mesures**.
- Administrar la configuració i enriquir els perfils dels clients des de la pàgina **Enriquiment** (només per a enriquiment propi).
- Gestioneu i creeu exportacions basades [en connexions compartides amb els col·laboradors](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administrador

- Tots els permisos disponibles per al col·laborador.
- Canvieu la configuració de la **pàgina Sistema, inclosa la llengua de treball, actualitzeu les planificacions dels processos del** sistema i exporteu els registres de diagnòstic.
- Canvieu la configuració de la **pàgina Seguretat**, inclosos els usuaris, les claus API, els enllaços privats i el magatzem de claus.
- Definiu les definicions de filtre i cerca per a la pàgina Clients mitjançant la pàgina **Cerca i filtra l'índex** (accessible a través de la pàgina **Clients**).
- Administrar connexions i permetre-les per a altres funcions d'usuari a la pàgina **Connexions**.
- Administrar la configuració i enriquir els perfils dels clients des de la pàgina **Enriquiment** (per a tots els enriquiments).
- Administrar i crear exportacions a la pàgina **Exportacions**.
- Instal·leu i utilitzeu el **Complement de targeta del client**.
- Afegiu i utilitzeu el **connector del Power Apps**.
- Habiliteu l'ús de les [API del Customer Insights](apis.md).
- [Assigneu la propietat de l'entorn](manage-environments.md#change-the-owner-of-an-environment) a un altre administrador.

## <a name="admin-owner"></a>Administrador (propietari)

- Tots els permisos disponibles per a l'Administració.
- [Restableix i suprimeix](manage-environments.md#reset-an-existing-environment-preview) l'entorn.

## <a name="add-users"></a>Afegeix usuaris

1. Aneu a **Seguretat d'administració** > **i** seleccioneu la **pestanya Usuaris**.

1. Seleccioneu **Afegeix usuaris** per obrir la subfinestra **Afegeix o edita els permisos**.

1. Utilitzeu el **camp Cerca** per trobar l'usuari o el Azure Active Directory grup que voleu afegir. Seleccioneu una **Funció** per assignar-la a l'usuari o al grup.

1. Seleccioneu **Desa**. L'entorn actual es comparteix automàticament amb l'usuari o membres del grup. Els usuaris poden accedir a l'aplicació Customer Insights i treballar d'acord amb la funció especificada.

## <a name="view-current-permissions"></a>Veure els permisos actuals

Aneu a **Seguretat d'administració** > **i** seleccioneu la **pestanya Usuaris** per veure la llista d'usuaris actius i les seves assignacions de funcions. Podeu ordenar la llista d'usuaris per qualsevol columna o utilitzar el quadre de cerca per trobar un usuari concret.

## <a name="manage-current-users"></a>Gestionar els usuaris actuals

Aneu a **Seguretat d'administració** > **i** seleccioneu la **pestanya Usuaris**. Podeu ordenar la llista d'usuaris per qualsevol columna o utilitzar el quadre de cerca per trobar l'usuari que voleu gestionar.

Seleccioneu un usuari per veure les accions disponibles.

- **Editeu** per editar el rol de l'usuari al Customer Insights. Seleccioneu **Desa** per confirmar el canvi.
- **Suprimiu-lo** per suprimir l'usuari que no tingui accés al Customer Insights. Seleccioneu **Suprimeix** per confirmar la supressió.

[!INCLUDE [footer-include](includes/footer-banner.md)]
