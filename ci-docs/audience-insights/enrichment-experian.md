---
title: Enriquiment de amb l'enriquiment de tercers d'Experian
description: Informació general sobre l'enriquiment de tercers d'Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896361"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquir perfils de clients amb dades demogràfiques d'Experian (versió preliminar)

Experian és un líder mundial en informes de consum i cedit empresarial i serveis de màrqueting. Amb els serveis d'enriquiment de dades d'Experian, podeu obtenir una comprensió més profunda dels clients enriquint els perfils dels clients amb dades demogràfiques com la mida de la llar, els ingressos i més.

## <a name="prerequisites"></a>Requisits previs

Per configurar Experian, cal complir els següents requisits previs:

- Tenir una subscripció d'Experian activa. Per obtenir una subscripció, [poseu-vos en contacte amb Experian](https://www.experian.com/marketing-services/contact) directament. [Més informació sobre l'enriquiment de dades d'Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Un administrador ja ha configurat una connexió de l'Experian *o* teniu permisos d'[administrador](permissions.md#administrator). També necessiteu l'identificador d'usuari, l'identificador del grup i el número de model per al compte de Transport segur (ST) habilitat per a SSH que l'Experian ha creat.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la peça d'Experian.

   > [!div class="mx-imgBorder"]
   > ![Peça d'Experian](media/experian-tile.png "Peça d'Experian")
   > 

1. Seleccioneu una [connexió](connections.md) a la llista desplegable. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible. Si sou un administrador, podeu crear una connexió seleccionant **Afegeix una connexió** i triant Experian al menú desplegable. 

1. Seleccioneu **Connecta't a Experian** per confirmar la selecció de la connexió.

1.  Seleccioneu **Següent** i trieu el **Conjunt de dades de client** que voleu enriquir amb les dades demogràfiques de l'Experian. Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. Seleccioneu **Següent** i definiu els tipus de camps dels perfils unificats que s'han d'utilitzar per cercar dades demogràfiques coincidents de l'Experian. Cal com a mínim un dels camps **Nom i adreça**, **Telèfon** o **Correu electrònic**. Per tenir una precisió de coincidència superior, es poden afegir fins a dos camps més. Aquesta selecció afectarà els camps d'assignació als quals teniu accés al pas següent.

    > [!TIP]
    > Si envieu més atributs d'identificador clau a Experian, probablement es produirà un percentatge de coincidència més alt.

1. Seleccioneu **Següent** per iniciar l'assignació de camp.

1. Definiu quins camps dels perfils unificats que s'han d'utilitzar per cercar dades demogràfiques coincidents de l'Experian. Els camps obligatoris estan marcats.

1. Proporcioneu un nom per a l'enriquiment i un nom per a l'entitat de sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

## <a name="configure-the-connection-for-experian"></a>Configurar la connexió per a l'Experian 

Heu de ser administrador per configurar les connexions. Seleccioneu **Afegeix una connexió** en configurar un enriquiment *o* aneu a **Administració** > **Connexions** i seleccioneu **Configuració** a la peça Experian.

1. Seleccioneu **Introducció**.

1. Introduïu un nom per a la connexió al quadre **Nom de visualització**.

1. Introduïu l'identificador d'usuari, l'identificador del grup i el número de model vàlids per al compte de transport segur d'Experian.

1. Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**

1. Seleccioneu **Verifica** per validar la configuració.

1. Després de completar la verificació, seleccioneu **Desa**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Subfinestra de configuració de la connexió d'Experian.":::

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
