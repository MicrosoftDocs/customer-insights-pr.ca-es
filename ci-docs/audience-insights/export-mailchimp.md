---
title: Exportar dades del Customer Insights a Mailchimp
description: Apreneu a configurar la connexió a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598189"
---
# <a name="connector-for-mailchimp-preview"></a>Connector per a Mailchimp (versió preliminar)

Exporteu segments de perfils de client unificats a Mailchimp per crear butlletins i campanyes de correu electrònic.

## <a name="prerequisites"></a>Requisits previs

-   Teniu un [compte de Mailchimp](https://mailchimp.com/) i les credencials d'administrador corresponents.
-   Hi ha públics a Mailchimp amb els identificadors corresponents. Per obtenir més informació, vegeu [Públics de Mailchimp](https://mailchimp.com/help/create-audience/).
-   Teniu [segments configurats](segments.md).
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="connect-to-mailchimp"></a>Connecta al Mailchimp

1. Aneu a **Administració** > **Destinacions d'exportació**.

1. A **Mailchimp**, seleccioneu **Configura**.

1. Doneu a la destinació d'exportació un nom reconeixible al camp **Nom de visualització**.

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Introduïu el vostre **[Identificador de públic del Mailchimp](https://mailchimp.com/help/find-audience-id/)** i seleccioneu **Connecta't** per inicialitzar la connexió a Mailchimp.

1. Seleccioneu **Autentica amb el Mailchimp** i indiqueu les vostres credencials de Mailchimp.

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Captura de pantalla d'exportació per a la connexió a Mailchimp":::

1. Seleccioneu **Següent** per configurar l'exportació.

## <a name="configure-the-connector"></a>Configurar el connector

1. A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client. 

1. També podeu exportar el **Nom** i el **Cognom** com a camps addicionals per crear missatges de correu electrònic més personalitzats. Seleccioneu **Afegeix un atribut** per assignar aquests camps.

1. Seleccioneu els segments que voleu exportar. Podeu exportar fins a un total d'un milió de perfils de client a Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Seleccioneu els camps i els segments que voleu exportar a Mailchimp":::

1. Seleccioneu **Desa**.

## <a name="export-the-data"></a>Exportar les dades

Podeu [exportar les dades segons demanda](export-destinations.md). L'exportació també s'executarà amb cada [actualització planificada](system.md#schedule-tab). A Mailchimp, ara podeu cercar els segments als [públics de Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Limitacions conegudes

- Fins a un milió de perfils per exportació a Mailchimp.
- L'exportació a Mailchimp es limita als segments.
- L'exportació de segments amb un total d'un milió de perfils pot durar fins a tres hores a causa de les possibles limitacions del proveïdor. 
- El nombre de perfils que podeu exportar a Mailchimp és limitat i dependrà del contracte que tingueu amb Mailchimp.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights perquè transmeti dades a Mailchimp, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Mailchimp compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]