---
title: Enriquiment amb l'enriquiment de tercers d'Experian
description: Informació general sobre l'enriquiment de tercers d'Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fabc3cc9faf4e11f46c396782b561ef61cd0f6d5
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618509"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquir els perfils de client amb dades demogràfiques d'Experian (versió preliminar)

Experian és un líder global en informes de crèdit d'empreses i consumidors i serveis de màrqueting. Amb els serveis d'enriquiment de dades dels clients d'Experian, podeu entendre millor els vostres clients enriquint els perfils dels clients amb dades demogràfiques com ara la mida de la llar, els ingressos i més.

## <a name="prerequisites"></a>Requisits previs

Per configurar Experian, cal complir els requisits previs següents:

- Heu de tenir una subscripció activa d'Experian. Per obtenir una subscripció, [poseu-vos en contacte directament amb Experian](https://www.experian.com/marketing-services/contact). [Obteniu més informació sobre l'enriquiment de dades d'Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Un administrador ja ha configurat una connexió d'Experian *o* teniu permisos d'[administrador](permissions.md#administrator). També necessiteu l'identificador d'usuari, l'identificador del grup i el número de model per al compte de Secure Transport (ST) habilitat per a SSH que Experian ha creat.

## <a name="supported-countriesregions"></a>Països o regions admesos

Actualment admetem l'enriquiment de perfils de clients només als Estats Units.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la peça d'Experian.

   > [!div class="mx-imgBorder"]
   > ![Peça de l'Experian.](media/experian-tile.png "Peça del Experian")
   > 

1. Seleccioneu una [connexió](connections.md) a la llista desplegable. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible. Si sou administrador, podeu crear una connexió seleccionant **Afegeix una connexió** i triant a la llista desplegable Experian. 

1. Seleccioneu **Connecta a Experian** per confirmar la selecció de la connexió.

1.  Seleccioneu **Següent** i trieu el **conjunt de dades de client** del qual voleu enriquir les dades demogràfiques d'Experian. Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client o seleccionar una entitat de segment per enriquir només els perfils de client del segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla quan trieu el conjunt de dades de clients.":::

1. Seleccioneu **Següent** i definiu els tipus de camps dels perfils unificats que s'han d'utilitzar per cercar dades demogràfiques coincidents a Experian. Cal com a mínim un dels camps **Nom i adreça**, **Telèfon** o **Correu electrònic**. Per tenir una precisió de coincidència superior, es poden afegir fins a dos camps més. Aquesta selecció afectarà els camps d'assignació als quals teniu accés al pas següent.

    > [!TIP]
    > Com més atributs d'identificador clau s'enviïn a Experian, més probable és que hi hagi un percentatge de coincidència superior.

1. Seleccioneu **Següent** per iniciar l'assignació de camp.

1. Definiu quins camps dels perfils unificats que s'han d'utilitzar per cercar dades demogràfiques coincidents a Experian. Els camps obligatoris estan marcats.

1. Proporcioneu un nom per a l'enriquiment i un nom per a l'entitat de sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

## <a name="configure-the-connection-for-experian"></a>Configurar la connexió per a Experian 

Heu de ser administrador per configurar les connexions. Seleccioneu **Afegeix una connexió** en configurar un enriquiment *o* aneu a **Administració** > **Connexions** i seleccioneu **Configura** a la peça d'Experian.

1. Seleccioneu **Introducció**.

1. Introduïu un nom per a la connexió al quadre **Nom de visualització**.

1. Introduïu l'identificador d'usuari, l'identificador del grup i el número de model vàlids per al compte de Secure Transport d'Experian.

1. Reviseu i proporcioneu el vostre consentiment per a la **Privadesa de les dades i conformitat** seleccionant **Accepta**.

1. Seleccioneu **Verifica** per validar la configuració.

1. Després de completar la verificació, seleccioneu **Desa**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Subfinestra de configuració de connexió a Experian":::

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres. També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab). El temps de processament depèn de la mida de les dades dels clients i dels processos d'enriquiment configurats per al vostre compte per Experian.

Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**. A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.

Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan permeteu que el Dynamics 365 Customer Insights transmeti dades a Experian, permeteu la transferència de dades fora del límit de conformitat per al Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals. Microsoft transferirà aquestes dades segons la vostra instrucció, però sou responsable d'assegurar que Experian compleixi les obligacions de privadesa o seguretat que tingueu. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
