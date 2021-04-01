---
title: Enriquiment de perfils d'empresa amb l'enriquiment de tercers de Leadspace
description: Informació general sobre l'enriquiment de tercers de Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597637"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquiment de perfils d'empresa amb el Leadspace (versió preliminar)

Leadspace és una empresa de ciència de dades que proporciona una plataforma de dades de clients B2B. Permet enriquir les dades als clients amb perfils de clients unificats per a les empreses. Els enriquiments inclouen atributs addicionals com ara la mida de l'empresa, la ubicació, el sector, etc.

## <a name="prerequisites"></a>Requisits previs

Per configurar el Leadspace, cal complir els requisits previs següents:

- Teniu una llicència activa de Leadspace i la "clau perpètua" (anomenada **Testimoni del Leadspace**). Poseu-vos en contacte directament amb [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) per obtenir informació detallada sobre el seu producte.
- Teniu permisos d'[Administrador](permissions.md#administrator).
- Tenir [perfils de clients unificats](customer-profiles.md) per a empreses.

## <a name="configuration"></a>Configuració

1. A les conclusions del públic, aneu a **Dades** > **Enriquiment**.

1. Seleccioneu **Enriqueix les meves dades** a la peça de Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla de la peça de Leadspace.":::

1. Seleccioneu **Comença** i, a continuació, introduïu un **Testimoni del Leadspace** actiu (clau perpètua). Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**. Seleccioneu **Connexió al Leadspace** per confirmar totes dues entrades.

1. Seleccioneu **Assigna dades** i trieu el conjunt de dades que voleu enriquir amb les dades de l'empresa de Leadspace. Podeu seleccionar l'entitat *Client* per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Trieu entre el perfil de client i l'enriquiment del segment.":::

1. Feu clic a **Següent** i definiu els camps dels perfils unificats que s'hauran d'utilitzar per cercar les dades coincidents de l'empresa de Leadspace. El camp **Nom de l'empresa** és obligatori. Per augmentar la precisió de la coincidència, es poden afegir fins a dos camps més, **Lloc web de l'empresa** i **Ubicació de l'empresa**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Subfinestra d'assignació de camps de Leadspace.":::
   
1. Seleccioneu **Aplica** per completar l'assignació de camps.

1. Seleccioneu **Executa** per enriquir els perfils d'empresa. La durada de l'enriquiment dependrà del nombre de perfils de client unificats.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Després d'actualitzar l'enriquiment, podeu revisar les dades d'empresa enriquides recentment a [Els meus enriquiments](enrichment-hub.md). Podeu trobar-hi l'hora de l'última actualització i el nombre de perfils enriquits.

Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.

Per obtenir més informació, vegeu [API del Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Passos següents

Construïu a partir de les dades de clients enriquits. Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Leadspace, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Leadspace compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]