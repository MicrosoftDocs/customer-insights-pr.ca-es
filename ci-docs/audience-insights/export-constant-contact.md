---
title: Exportar dades del Customer Insights a Constant Contact
description: Apreneu a configurar la connexió i exportar a Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760476"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a>Exportar llistes de segments a Constant Contact (versió preliminar)

Exporteu segments de perfils de client unificats a Constant Contact i utilitzeu-los per a activitats de màrqueting. 

## <a name="prerequisites-for-a-connection"></a>Requisits previs per a una connexió

-   Teniu un [compte de Constant Contact](https://www.constantcontact.com/account-home) i les credencials d'administrador corresponents.
-   Teniu [segments configurats](segments.md) a les conclusions del públic.
-   Els perfils de client unificats dels segments exportats contenen un camp que representa una adreça electrònica.

## <a name="known-limitations"></a>Limitacions conegudes

- Podeu exportar fins a 1 milió de perfils per exportació a Constant Contact.
- L'exportació a Constant Contact es limita als segments.
- L'exportació de fins a 1 milió de perfils a Constant Contact pot trigar fins a 1 hora com a màxim. 
- El nombre de perfils que podeu exportar a Constant Contact depèn i està limitat pel contracte amb Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Configuració de la connexió a Constant Contact

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Constant Contact** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccioneu **Accepto** per confirmar la **privadesa de les dades i el compliment**.

1. Seleccioneu **Connecta't** per inicialitzar la connexió a Constant Contact.

1. Seleccioneu **Autentica amb AdRoll** i proporcioneu les vostres credencials d'administració per a Constant Contact. 

1. Seleccioneu **Afegeix-me com a usuari d'exportació** i proporcioneu les vostres credencials del Customer Insights.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una destinació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Constant Contact. Si no veieu aquest nom de secció, no hi ha cap connexió d'aquest tipus disponible.

1. Introduïu l'[**ID de llista de Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Obriu una llista a Constant Contact per trobar l'identificador de llista a l'adreça URL.

1. A la secció **Coincidència de les dades**, al camp **Correu electrònic**, seleccioneu el camp del perfil de client unificat que representa l'adreça electrònica d'un client. Cal que exporteu segments a Constant Contact.

1. També podeu exportar el Nom i el Cognom com a camps addicionals per crear missatges de correu electrònic més personalitzats. Seleccioneu **Afegeix un atribut** per assignar aquests camps.

1. Seleccioneu els segments que voleu exportar.

1. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan permeteu al Dynamics 365 Customer Insights transmetre dades a Constant Contact, permeteu la transferència de dades fora del límit del Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals. Microsoft transferirà aquestes dades quan ho indiqueu, però sou responsable d'assegurar-vos que Constant Contact compleixi les obligacions de privadesa o de seguretat que pugueu teniu. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador del Dynamics 365 Customer Insights pot suprimir aquesta destinació d'exportació en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.
