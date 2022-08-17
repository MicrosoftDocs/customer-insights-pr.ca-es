---
title: Enriquir els perfils d'empresa amb Leadspace (preview)
description: Informació general sobre l'enriquiment de tercers de Leadspace.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237938"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Enriquir els perfils d'empresa amb Leadspace (preview)

Leadspace és una empresa de ciència de dades que proporciona una plataforma de dades de clients d'empresa a empresa. Permet als entorns amb perfils de client unificats basats en comptes enriquir les seves dades. Enriquiu els *perfils de client* amb atributs com ara la mida de l'empresa, la ubicació o el sector. Enriquiu els *Perfils de contacte* amb atributs com ara el títol, la persona o la verificació de correu electrònic.

## <a name="prerequisites"></a>Requisits previs

- Una llicència de Leadspace activa.
- [Perfils de clients unificats](customer-profiles.md) basats en comptes.
- Un administrador configura [una connexió](connections.md)[d'espai](#configure-the-connection-for-leadspace) de clients potencials. Poseu-vos en contacte directament amb [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) per obtenir informació sobre el producte.

## <a name="configure-the-connection-for-leadspace"></a>Configurar la connexió per al Leadspace

Heu de ser [administrador al Customer Insights i tenir la "clau perpètua" (anomenada](permissions.md#admin) testimoni de **Leadspace**).

1. Seleccioneu **Afegeix connexió** en configurar un enriquiment o aneu a **Connexions** > **d'administració** i seleccioneu **Configura** a la peça Espai de contactes.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Pàgina de configuració de la connexió del Leadspace.":::

1. Introduïu un nom per a la connexió i un testimoni de Leadspace vàlid.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Verifica** per validar la configuració i, a continuació, seleccioneu **Desa**.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a les dades **de l'empresa** de la peça Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla de la peça de Leadspace.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu la connexió. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Seleccioneu **Següent**.

1. Seleccioneu el **conjunt** de dades de clients i trieu el perfil o segment que voleu enriquir amb les dades de l'empresa de Leadspace. L'entitat *Client* enriqueix tots els teus perfils de client, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. Definiu quin tipus de camps dels perfils unificats voleu utilitzar per a la coincidència: l'adreça principal i/o secundària. Podeu especificar una assignació de camps per a ambdues adreces i enriquir els perfils de les dues adreces per separat. Per exemple, per a una adreça de casa i una adreça comercial. Seleccioneu **Següent**.

1. Assigneu els vostres camps a les dades de l'empresa de Leadspace. El camp **Nom de l'empresa** és obligatori. Per augmentar la precisió de la coincidència, es poden afegir fins a dos camps més, **Lloc web de l'empresa** i **Ubicació de l'empresa**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Subfinestra d'assignació de camps de Leadspace.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Activeu la casella si teniu *Perfils de contacte* que voleu enriquir. El Customer Insights assignarà automàticament els camps obligatoris.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Enriquiment dels registres de contacte del Leadspace.":::

1. Seleccioneu **Següent**.

1. Proporcioneu un **nom** per a l'enriquiment i el nom de l'entitat **de sortida**.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o tancar per tornar a la **pàgina Enriquiments**.

## <a name="view-enrichment-results"></a>Veure resultats d'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Per obtenir més informació, vegeu [API del Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
