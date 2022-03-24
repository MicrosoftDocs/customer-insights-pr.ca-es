---
title: Enriquir els perfils de client amb les dades d'ubicació de l'Azure Maps
description: Informació general sobre l'enriquiment principal de l'Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 2cc44f7b453d2aca328c397b14787c8a02c5e490
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376634"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Enriquiment dels perfils de client amb l'Azure Maps (versió preliminar)

L'Azure Maps proporciona dades i serveis centrats en la ubicació per proporcionar experiències basades en dades geoespacials amb la intel·ligència d'ubicació integrada. Els serveis d'enriquiment de dades de l'Azure Maps milloren la precisió de la informació d'ubicació dels vostres clients. Proporciona capacitats com ara la normalització d'adreces i l'extracció de latitud i longitud al Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisits previs

Per configurar l'enriquiment de dades de l'Azure Maps, cal complir els requisits previs següents:

- Heu de tenir una subscripció activa de l'Azure Maps. Per obtenir una subscripció, podeu [registrar-vos o obtenir una versió de prova gratuïta](https://azure.microsoft.com/services/azure-maps/).

- Hi ha disponible una [connexió](connections.md) de l'Azure Maps *o* teniu permisos d'[administrador](permissions.md#admin) i una clau de l'API de l'Azure Maps activa.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment**. 

1. A la peça **Ubicació**, seleccioneu **Enriqueix les meves dades**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Peça Azure Maps.":::

1. Seleccioneu una [connexió](connections.md) a la llista desplegable. Si no hi ha disponible cap connexió de l'Azure Maps, poseu-vos en contacte amb un administrador. Si sou un administrador, podeu [configurar la connexió per a l'Azure Maps](#configure-the-connection-for-azure-maps). 

1. Seleccioneu **Següent** per confirmar la selecció.

1. Trieu el **Conjunt de dades de clients** que voleu enriquir amb les dades d'ubicació de l'Azure Maps. Podeu seleccionar l'entitat **Client** per enriquir tots els perfils de client unificats o seleccionar una entitat de segment per enriquir només els perfils de client que s'hi contenen.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Captura de pantalla de la tria del conjunt de dades del client.":::

1. Trieu si voleu assignar els camps a l'adreça principal o secundària. Podeu especificar una assignació de camp per a ambdues adreces i enriquir els perfils de les dues adreces per separat; per exemple, per a una adreça particular i una adreça comercial. Seleccioneu **Següent**.

1. Definiu quins camps dels perfils unificats s'han d'utilitzar per cercar dades d'ubicació coincidents de l'Azure Maps. Els camps **Carrer 1** i **Codi postal** són obligatoris per a l'adreça principal o secundària seleccionada. Per obtenir una precisió de coincidència més elevada, podeu afegir més camps.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Pàgina de configuració d'enriquiment de l'Azure Maps.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Avalueu si voleu modificar la **Configuració avançada**. Es proporcionen per donar la màxima flexibilitat a l'hora de gestionar casos d'ús avançat, però en la majoria dels casos els valors per defecte seran adequats:
   - **Tipus d'adreces**: el comportament per defecte és que l'enriquiment retorni la coincidència de la millor adreça encara que sigui incompleta. Per obtenir només les adreces completes (per exemple, les adreces que inclouen el número de domicili), desactiveu totes les caselles de selecció excepte **Adreces de punts**. 
   - **Llengua**: per defecte, les adreces es retornen en la llengua de la regió a la qual l'adreça ha de pertànyer. Per aplicar una llengua d'adreça estandarditzada, seleccioneu la llengua al menú desplegable. Per exemple, si seleccioneu **Català**, retornarà **Copenhaguen, Dinamarca** en comptes de **København, Danmark**.

1. Proporcioneu un nom per a l'enriquiment.

1. Reviseu les vostres opcions i, a continuació, seleccioneu **Desa l'enriquiment**.

## <a name="configure-the-connection-for-azure-maps"></a>Configurar la connexió per a l'Azure Maps

Heu de ser un administrador dels coneixements del públic per configurar les connexions. Seleccioneu **Afegeix una connexió** en configurar un enriquiment o aneu a **Administració** > **Connexions** i seleccioneu **Configura** a la peça de l'Azure Maps.

1. Al quadre de diàleg **Nom de visualització**, introduïu un nom per a la connexió.

1. Proporcioneu una clau API de l'Azure Maps vàlida.

1. Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**

1. Seleccioneu **Verifica** per validar la configuració.

1. Després de completar la verificació, seleccioneu **Desa**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Pàgina de configuració de la connexió de l'Azure Maps.":::

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres. També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab). El temps de processament dependrà de la mida de les dades dels vostres clients i dels temps de resposta de l'API.

Un cop completat el procés d'enriquiment, podeu revisar les dades dels perfils de client acabats d'enriquir a **Els meus enriquiments**. A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.

Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan permeteu que el Dynamics 365 Customer Insights transmeti dades a l'Azure Maps, permeteu la transferència de dades fora del límit de conformitat per al Dynamics 365 Customer Insights, incloent-hi dades potencialment confidencials, com ara dades personals. Microsoft transferirà aquestes dades segons la vostra instrucció, però sou responsable d'assegurar que l'Azure Maps compleixi les obligacions de privadesa o seguretat que tingueu. Per obtenir més informació, aneu a la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
