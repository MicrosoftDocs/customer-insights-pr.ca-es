---
title: Enriquiment de amb l'enriquiment de tercers d'Experian
description: Informació general sobre l'enriquiment de tercers d'Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269548"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquir perfils de clients amb dades demogràfiques d'Experian (versió preliminar)

Experian és un líder mundial en informes de consum i cedit empresarial i serveis de màrqueting. Amb els serveis d'enriquiment de dades d'Experian, podeu obtenir una comprensió més profunda dels clients enriquint els perfils dels clients amb dades demogràfiques com la mida de la llar, els ingressos i més.

## <a name="prerequisites"></a>Requisits previs

Per configurar Experian, cal complir els següents requisits previs:

- Tenir una subscripció d'Experian activa. Per obtenir una subscripció, [poseu-vos en contacte amb Experian](https://www.experian.com/marketing-services/contact) directament. [Més informació sobre l'enriquiment de dades d'Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Tenir l'ID d'usuari, l'ID de grup i el número de model per al vostre compte de transport segur (ST) amb SSH que Experian us ha creat.
- Teniu permisos d'[Administrador](permissions.md#administrator) a les conclusions del públic.

## <a name="configuration"></a>Configuració

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la peça d'Experian.

   > [!div class="mx-imgBorder"]
   > ![Peça d'Experian](media/experian-tile.png "Peça d'Experian")

1. Seleccioneu **Comença** i introduïu l'ID d'usuari, l'ID de grup i el número de model per al vostre compte de transport segur d'Experian. Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**. Confirmeu totes les entrades seleccionant **Aplica**.

## <a name="map-your-fields"></a>Assignació dels camps

1.  Seleccioneu **Afegeix dades** i trieu el **conjunt de dades del client** que voleu enriquir amb les dades demogràfiques d'Experian. Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.

1. Seleccioneu els identificadors clau de **Nom i adreça**, **Correu electrònic** o **Telèfon** per enviar a Experian per a la resolució d'identitats.

   > [!TIP]
   > Si envieu més atributs d'identificador clau a Experian, probablement es produirà un percentatge de coincidència més alt.

1. Seleccioneu **Següent** i assigneu els atributs corresponents de la vostra entitat de client unificat per als camps d'identificador clau seleccionats.

1. Seleccioneu **Afegeix un atribut** per assignar qualsevol atribut addicional que vulgueu enviar a Experian.

1.  Seleccioneu **Desa** per completar l'assignació de camps.

    > [!div class="mx-imgBorder"]
    > ![Assignació de camps d'Experian](media/experian-field-mapping.png "Assignació de camps d'Experian")

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres. També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab). El temps de processament dependrà de la mida de les dades del client i dels processos d'enriquiment creats per al vostre compte per Experian.

Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**. A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.

Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.

## <a name="next-steps"></a>Passos següents

Construïu a partir de les dades de clients enriquits. Creeu [segments](segments.md), [mesures](measures.md) i fins i tot [exporteu les dades](export-destinations.md) per oferir experiències personalitzades als vostres clients.

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu el Dynamics 365 Customer Insights perquè transmeti dades a Experian, permeteu la transferència de dades fora dels límits de compliment del Dynamics 365 Customer Insights, incloent-hi dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons el que indiqueu; tanmateix, teniu la responsabilitat d'assegurar-vos que Experian compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]