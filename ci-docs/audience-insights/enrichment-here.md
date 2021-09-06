---
title: Enriquiment amb l'enriquiment de tercers de HERE Technologies
description: Informació general sobre l'enriquiment de tercers de HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: be0ac9fa29ce1569d06e4e539e95824c0a3ada4dcf49802c2b574e9d91730630
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032562"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquiment de perfils de client amb HERE Technologies (versió preliminar)

HERE Technologies és una empresa de plataformes d'ubicació que proporciona dades i serveis centrats en la ubicació. Amb els serveis d'enriquiment de dades de HERE Technologies, podeu crear una localització més precisa dels clients amb la normalització d'adreces o l'extracció de la latitud i la longitud, entre d'altres.

## <a name="prerequisites"></a>Requisits previs

Per poder configurar els enriquiments de HERE Technologies, s'han de complir els requisits previs següents:

- Heu de tenir una subscripció activa amb HERE Technologies. Per obtenir una subscripció, podeu [registrar-vos aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [posar-vos en contacte directament amb HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Més informació sobre l'enriquiment d'ubicació de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Hi ha una [connexió](connections.md) a HERE disponible *o* teniu permisos d'[administrador](permissions.md#administrator) i la clau API de HERE Technologies.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment**. 

1. Seleccioneu **Enriqueix les meves dades** a la peça HERE Technologies i seleccioneu **Comença**.

   > [!div class="mx-imgBorder"]
   > ![Peça de HERE Technologies.](media/HERE-tile.png "Peça de HERE Technologies")

1. Seleccioneu una [connexió](connections.md) a la llista desplegable. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible. Si sou administrador, podeu crear una connexió seleccionant **Afegeix una connexió**. A la llista desplegable, trieu **HERE Technologies**. 

1. Seleccioneu **Connecta't a HERE Technologies** per confirmar la selecció.

1.  Seleccioneu **Següent** i trieu el **Conjunt de dades de client** que voleu enriquir amb les dades d'ubicació de HERE Technologies. Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. Trieu si voleu assignar camps a l'adreça principal o secundària. Podeu especificar una assignació de camps per a ambdues adreces i enriquir els perfils de les dues adreces per separat. Per exemple, si hi ha una casa i una adreça de negoci. Seleccioneu **Següent**.

1. Definiu els camps dels perfils unificats que s'hauran d'utilitzar per cercar dades d'ubicació coincidents des de HERE Technologies. Els camps **Carrer 1** i **Codi postal** són obligatoris per a l'adreça principal o secundària seleccionada. Per augmentar la precisió de la coincidència, es poden afegir més camps.

   > [!div class="mx-imgBorder"]
   > ![Pàgina de configuració d'enriquiment de HERE Technologies.](media/enrichment-HERE-configuration.png "Pàgina de configuració d'enriquiment de HERE Technologies")

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un nom per a l'enriquiment. 

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

## <a name="configure-the-connection-for-here-technologies"></a>Configurar la connexió per a HERE Technologies 

Heu de ser administrador per configurar les connexions. Seleccioneu **Afegeix una connexió** en configurar un enriquiment *o* aneu a **Administració** > **Connexions** i seleccioneu **Configuració** a la peça HERE Technologies.

1. Introduïu un nom per a la connexió al quadre **Nom de visualització**.

1. Proporcioneu una clau d'API vàlida de HERE Technologies.

1. Reviseu i proporcioneu el vostre consentiment per a la **Privadesa de les dades i conformitat** seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració.

1. Després de completar la verificació, seleccioneu **Desa**.

   > [!div class="mx-imgBorder"]
   > ![Pàgina de configuració de la connexió de HERE Technologies.](media/enrichment-HERE-connection.png "Pàgina de configuració de la connexió de HERE Technologies")

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres. També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab). El temps de processament dependrà de la mida de les dades del client i dels temps de resposta de l'API de HERE Technologies.

Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**. A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.

Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.

## <a name="next-steps"></a>Passos següents

Construïu a partir de les dades de clients enriquits. Creeu [segments](segments.md) i [mesures](measures.md) i, fins i tot, [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a HERE Technologies, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que HERE Technologies compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
