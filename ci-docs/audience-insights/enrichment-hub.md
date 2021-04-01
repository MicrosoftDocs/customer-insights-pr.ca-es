---
title: Enriquir perfils de client unificats
description: Utilitzeu les capacitats disponibles per enriquir les dades dels clients.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597683"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquiment per a perfils de clients (versió preliminar)

Utilitzeu dades de diverses fonts, com ara Microsoft i altres associats, per enriquir les dades dels clients.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pàgina del centre d'enriquiment":::

A les conclusions del públic, aneu a **Dades** > **Enriquiment** per treballar amb les opcions d'enriquiment.    
Heu de tenir permisos de col·laborador o administrador per crear o editar els enriquiments. Per obtenir més informació, vegeu [Permisos](permissions.md).

A la pestanya **Detecta**, trobareu els següents enriquiments:

- [Marques](enrichment-microsoft-graph.md), proporcionades pel Microsoft Graph
- [Interessos](enrichment-microsoft-graph.md), proporcionats pel Microsoft Graph
- [Dades de l'empresa](enrichment-leadspace.md) proporcionades per Leadspace
- [Dades demogràfiques](enrichment-experian.md) proporcionades per Experian
- [Dades d'ubicació](enrichment-here.md) proporcionades per HERE Technologies
- [Dades personalitzades](enrichment-SFTP-custom-import.md) a través del protocol de transferència segura de fitxers (SFTP)

A la pestanya **Els meus enriquiments** podeu veure els enriquiments que heu configurat i editar-ne les propietats.

## <a name="manage-existing-enrichments"></a>Administrar els enriquiments existents

Aneu a **Els meus enriquiments** per veure tots els enriquiments que heu configurat. Cada enriquiment es representa com una fila que inclou informació addicional sobre l'enriquiment.

Seleccioneu un enriquiment per veure les opcions disponibles. Alternativament, podeu seleccionar els punts suspensius (...) en un element de la llista per veure les opcions.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcions per administrar els enriquiments a la llista d'enriquiments":::

- **Visualitzeu** els detalls de l'enriquiment amb el nombre de perfils de client enriquits.
- **Editeu** la configuració d'enriquiment.
- **Executeu** l'enriquiment per actualitzar els perfils dels clients amb les últimes dades.
- **Desactiveu** un enriquiment existent per impedir que s'actualitzi de manera automàtica amb cada actualització planificada. Les dades de l'última actualització correcta continuaran estaran disponibles. **Activeu** un enriquiment inactiu per reiniciar l'actualització automàtica amb cada actualització planificada.
- **Suprimiu** un enriquiment.

Podeu executar o desactivar múltiples enriquiments alhora seleccionant-los a la llista. Les opcions de visualització i edició no estan disponibles com a accions massives i només funcionen per a un enriquiment a la vegada.


[!INCLUDE[footer-include](../includes/footer-banner.md)]