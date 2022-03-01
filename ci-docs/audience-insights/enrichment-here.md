---
title: Enriquiment de amb l'enriquiment de tercers de HERE Technologies
description: Informació general sobre l'enriquiment de tercers de HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269502"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquiment de perfils de client amb HERE Technologies (versió preliminar)

HERE Technologies és una empresa de plataformes d'ubicació que proporciona dades i serveis centrats en la ubicació. Amb els serveis d'enriquiment de dades de HERE Technologies, podeu crear una localització més precisa dels clients amb la normalització d'adreces o l'extracció de la latitud i la longitud, entre d'altres.

## <a name="prerequisites"></a>Requisits previs

Per poder configurar els enriquiments de HERE Technologies, s'han de complir els requisits previs següents:

- Heu de tenir una subscripció activa amb HERE Technologies. Per obtenir una subscripció, podeu [registrar-vos aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [posar-vos en contacte directament amb HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Més informació sobre l'enriquiment d'ubicació de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Teniu la clau d'API de HERE Technologies.

- Teniu permisos d'[Administrador](permissions.md#administrator).

## <a name="configuration"></a>Configuració

1. Aneu a **Dades** > **Enriquiment**.

1. Seleccioneu **Enriqueix les meves dades** a la peça de HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Peça de HERE Technologies](media/HERE-tile.png "Peça de HERE Technologies")

1. Introduïu una **Clau de l'API de HERE Technologies** activa. Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**. 

1. Confirmeu totes dues entrades seleccionant **Connecta a HERE**.

1.  Seleccioneu **Afegeix dades** i trieu el **conjunt de dades del client** que voleu enriquir amb les dades d'ubicació de HERE Technologies. Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. Trieu si voleu assignar camps a l'adreça principal o secundària. Podeu especificar una assignació de camps per a totes dues adreces (per exemple, una adreça particular i de la feina) i enriquir els perfils per a ambdues adreces de manera separada. Seleccioneu **Següent**.

1. Definiu els camps dels perfils unificats que s'hauran d'utilitzar per cercar dades d'ubicació coincidents des de HERE Technologies. Els camps **Carrer 1** i **Codi postal** són obligatoris per a l'adreça principal o secundària seleccionada. Per augmentar la precisió de la coincidència, es poden afegir més camps.

   > [!div class="mx-imgBorder"]
   > ![Pàgina de configuració d'enriquiment de HERE Technologies](media/enrichment-HERE-configuration.png "Pàgina de configuració d'enriquiment de HERE Technologies")

1. Seleccioneu **Aplica** per completar l'assignació de camps.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres. També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab). El temps de processament dependrà de la mida de les dades del client i dels temps de resposta de l'API de HERE Technologies.

Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**. A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.

Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.

## <a name="next-steps"></a>Passos següents

Construïu a partir de les dades de clients enriquits. Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a HERE Technologies, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que HERE Technologies compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]