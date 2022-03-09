---
title: Enriquiment de perfils d'empresa amb l'enriquiment de tercers de Leadspace
description: Informació general sobre l'enriquiment de tercers de Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f89ef6842c21cf6b78154586f818beffbcdcffb9
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230622"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquiment de perfils d'empresa amb el Leadspace (versió preliminar)

Leadspace és una empresa de ciència de dades que proporciona una plataforma de dades de clients d'empresa a empresa. Permet als entorns amb perfils de client unificats basats en comptes enriquir les seves dades. Enriquiu els *perfils de client* amb atributs com ara la mida de l'empresa, la ubicació o el sector. Enriquiu els *Perfils de contacte* amb atributs com ara el títol, la persona o la verificació de correu electrònic.

## <a name="prerequisites"></a>Requisits previs

Per configurar el Leadspace, cal complir els requisits previs següents:

- Teniu una llicència activa del Leadspace.
- Teniu [perfils de client unificats](customer-profiles.md) basats en comptes.
- Un administrador ja ha configurat una connexió del Leadspace o teniu permisos d'[administrador](permissions.md#administrator) i la "clau perpètua" (anomenada **testimoni del Leadspace**). Poseu-vos en contacte directament amb [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) per obtenir informació sobre el producte.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. A les conclusions del públic, aneu a **Dades** > **Enriquiment**.

1. Seleccioneu **Enriqueix les meves dades** a la peça Leadspace i seleccioneu **Comença**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla de la peça de Leadspace.":::

1. Seleccioneu una [connexió](connections.md) a la llista desplegable. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible. Si sou administrador, podeu crear una connexió seleccionant **Afegeix una connexió** i triant **Leadspace**. 

1. Seleccioneu **Connecta't a Leadspace** per confirmar la selecció de la connexió.

1. Seleccioneu **Següent** i trieu el **Conjunt de dades de client** que voleu enriquir amb les dades de l'empresa des de Leadspace. Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. Seleccioneu **Següent** i definiu els tipus de camps dels perfils unificats que s'utilitzen per cercar dades empresarials coincidents de Leadspace. El camp **Nom de l'empresa** és obligatori. Per augmentar la precisió de la coincidència, es poden afegir fins a dos camps més, **Lloc web de l'empresa** i **Ubicació de l'empresa**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Subfinestra d'assignació de camps de Leadspace.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Activeu la casella si teniu *Perfils de contacte* que voleu enriquir. Les conclusions del públic s'assignaran automàticament als camps necessaris.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Enriquiment dels registres de contacte del Leadspace.":::
 
1. Proporcioneu un nom per a l'enriquiment i seleccioneu **Desa l'enriquiment** després de revisar les vostres opcions.


## <a name="configure-the-connection-for-leadspace"></a>Configurar la connexió per al Leadspace 

Heu de ser administrador per configurar les connexions. Seleccioneu **Afegeix una connexió** en configurar un enriquiment *o* aneu a **Administració** > **Connexions** i seleccioneu **Configuració** a la peça Leadspace.

1. Seleccioneu **Introducció**. 

1. Introduïu un nom per a la connexió al quadre **Nom de visualització**.

1. Proporcioneu un testimoni vàlid del Leadspace.

1. Reviseu i proporcioneu el vostre consentiment per a la **Privadesa de les dades i conformitat** seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració.

1. Després de completar la verificació, seleccioneu **Desa**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Pàgina de configuració de la connexió del Leadspace.":::

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Després d'actualitzar l'enriquiment, podeu revisar les dades d'empresa enriquides recentment a [Els meus enriquiments](enrichment-hub.md). Podeu trobar-hi l'hora de l'última actualització i el nombre de perfils enriquits.

Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.

Per obtenir més informació, vegeu [API del Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Passos següents


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Leadspace, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Leadspace compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
