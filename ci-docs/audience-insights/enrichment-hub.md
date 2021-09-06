---
title: Enriquir perfils de client unificats
description: Utilitzeu les capacitats disponibles per enriquir les dades dels clients.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: a64bbd754d4013d0a6243074ac9f55991547be82b269047a9937b583baf98697
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032516"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquiment per a perfils de clients (versió preliminar)

Utilitzeu dades de diverses fonts, com ara Microsoft i altres associats, per enriquir les dades dels clients.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Pàgina del centre d'enriquiment.":::

A les conclusions del públic, aneu a **Dades** > **Enriquiment** per treballar amb les opcions d'enriquiment.  

Heu de tenir permisos de col·laborador o administrador per crear o editar els enriquiments. Per obtenir més informació, vegeu [Permisos](permissions.md).

A la pestanya **Detecta**, trobareu els següents enriquiments:

- [Marques](enrichment-microsoft.md) proporcionades per Microsoft
- [Interessos](enrichment-microsoft.md) proporcionats per Microsoft
- [Adreces millorades](enrichment-enhanced-addresses.md) proporcionades per Microsoft
- [Dades de l'empresa](enrichment-leadspace.md) proporcionades per Leadspace
- [Dades demogràfiques](enrichment-experian.md) proporcionades per Experian
- [Dades d'ubicació](enrichment-here.md) proporcionades per HERE Technologies
- [Dades personalitzades](enrichment-SFTP-custom-import.md) a través del protocol de transferència segura de fitxers (SFTP)

A la pestanya **Els meus enriquiments** podeu veure els enriquiments que heu configurat i editar-ne les propietats.

## <a name="manage-existing-enrichments"></a>Administrar els enriquiments existents

Aneu a la pestanya **Els meus enriquiments** per veure tots els enriquiments configurats. Cada enriquiment es representa com una fila que inclou informació addicional sobre l'enriquiment.

Seleccioneu l'enriquiment per veure les opcions disponibles. També podeu seleccionar els punts suspensius (...) en un element de llista per veure les opcions. Si heu configurat diversos enriquiments, podeu utilitzar el quadre de cerca per trobar-lo ràpidament.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcions per administrar els enriquiments a la llista d'enriquiments.":::

- **Visualitzeu** els detalls de l'enriquiment amb el nombre de perfils de client enriquits.
- **Editeu** la configuració d'enriquiment.
- **Executeu** l'enriquiment per actualitzar els perfils dels clients amb les últimes dades.
- **Desactiveu** un enriquiment existent per impedir que s'actualitzi de manera automàtica amb cada actualització planificada. Les dades de l'última actualització correcta continuaran estaran disponibles. **Activeu** un enriquiment inactiu per reiniciar l'actualització automàtica amb cada actualització planificada.
- **Suprimeix** l'enriquiment.

Executeu o desactiveu diversos enriquiments alhora seleccionant-los a la llista. Les opcions de visualització i edició no estan disponibles com a acció massiva. Només funcionen per a un enriquiment alhora.

## <a name="enrichments-and-connections"></a>Enriquiments i connexions

Les millores de tercers es configuren mitjançant [connexions](connections.md), que un administrador configura amb credencials i proporciona el consentiment per a les transferències de dades. Els administradors i els col·laboradors poden utilitzar la connexió per configurar enriquiments.  

## <a name="multiple-enrichments-of-the-same-type"></a>Múltiples enriquiments del mateix tipus

L'entitat que s'ha d'enriquir s'especifica durant la configuració de l'enriquiment, la qual cosa us permet enriquir només un subconjunt dels vostres perfils. Per exemple, podeu enriquir només les dades d'un segment concret. Podeu configurar diversos enriquiments del mateix tipus i reutilitzar la mateixa connexió. Alguns enriquiments tindran límits pel que fa al nombre d'enriquiments del mateix tipus que es poden crear. Els límits i l'ús actual es poden veure a la pàgina **Enriquiment**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
