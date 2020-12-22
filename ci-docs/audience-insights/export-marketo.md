---
title: Exportar dades del Customer Insights a Marketo
description: Apreneu a configurar la connexió a Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570391"
---
# <a name="connector-for-marketo-preview"></a>Connector per a Marketo (versió preliminar)

Exporteu segments de perfils de client unificats per generar campanyes, proporcionar màrqueting per correu electrònic i utilitzar grups específics de clients amb Marketo.

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte de Marketo](https://login.marketo.com/) i les credencials d'administrador corresponents.
-   Hi ha llistes a Marketo amb els identificadors corresponents. Per obtenir més informació, vegeu [Llistes de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Teniu [segments configurats](segments.md).
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="connect-to-marketo"></a>Connectar-se a Marketo

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A **Marketo**, seleccioneu **Configura**.

1. Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.

1. Introduïu l'**[ID del client, el Secret del client i el Nom de l'amfitrió de l'extrem REST de Marketo](https://developers.marketo.com/rest-api/authentication/)**.

1. Introduïu l'**[ID de la llista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Seleccioneu **Accepto** per confirmar el **Compliment i privadesa de les dades** i seleccioneu **Connecta't** per inicialitzar la connexió a Marketo.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Captura de pantalla d'exportació per a la connexió a Marketo":::

1. Seleccioneu **Següent** per configurar l'exportació.

## <a name="configure-the-connector"></a>Configurar el connector

1. A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client. 

1. També podeu exportar el **Nom**, el **Cognom**, la **Ciutat**, l'**Estat** i el **País/regió** com a camps addicionals per crear missatges de correu electrònic més personalitzats. Seleccioneu **Afegeix un atribut** per assignar aquests camps.

1. Seleccioneu els segments que voleu exportar. Podeu exportar fins a un total d'un milió de perfils de client a Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Seleccioneu els camps i els segments que voleu exportar a Marketo":::

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab). A Marketo, ara podeu cercar els segments a les [llistes de Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a un milió de perfils per exportació a Marketo.
- L'exportació a Marketo es limita als segments.
- L'exportació de segments amb un total d'un milió de perfils pot durar fins a 3 hores. 
- El nombre de perfils que podeu exportar a Marketo és limitat i dependrà del contracte que tingueu amb Marketo.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Marketo, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Marketo compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
