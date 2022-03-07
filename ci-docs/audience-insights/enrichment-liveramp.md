---
title: Enriquiment de dades d'identitat LiveRamp
description: Enriqueix els perfils dels clients amb dades de LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373063"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enriquir perfils de clients amb dades d'identitat de LiveRamp (Previsualització) 

LiveRamp proporciona una resolució d'identitat fora de línia determinista i la consolidació de les dades dels clients. Podeu assignar identificadors personals a les vostres dades de client al gràfic d'identitat d'AbiliTec i rebre identificadors d'AbiliTec. A continuació, podeu utilitzar aquests identificadors per a una millor unificació de les dades dels clients. 

## <a name="prerequisites"></a>Requisits previs 

Per configurar l'enriquiment s'han de complir els requisits previs següents: 

- Teniu una subscripció activa a LiveRamp. Per obtenir una subscripció, poseu-vos en contacte amb l'equip del compte liveramp o per [dynamics@liveramp.com](mailto:dynamics@liveramp.com) obtenir més informació.   

- Una subscripció activa d'AbiliTec amb un identificador de client i secret per accedir a l'API. Per obtenir més informació, vegeu [El centre de desenvolupadors de l'API d'AbiliTec](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Països o regions admesos 

Actualment admetem perfils de clients enriquidors només amb dades de LiveRamp als Estats Units. 

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment 

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**. 

1. Seleccioneu **Enriqueix les meves dades** a la **peça Identitat**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Mosaic d'identitat a la pàgina visió general d'enriquiment.":::

1. Seleccioneu una [connexió](connections.md) a la llista desplegable. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible. Si sou administrador, podeu crear una connexió seleccionant **Afegeix una connexió**. Trieu **LiveRamp** de la llista desplegable. 

1. Seleccioneu **Endavant** i trieu el **conjunt** de dades del client que voleu enriquir amb les dades d'identitat de LiveRamp. Podeu seleccionar l'entitat *Client* per enriquir tots els vostres perfils de client o seleccionar una *entitat de segment* per enriquir només els perfils de clients continguts en aquest segment. 

1. Seleccioneu **Següent** i definiu quin tipus de camps dels perfils unificats s'han d'utilitzar per cercar dades d'identitat coincidents de LiveRamp. Cal com a mínim un dels camps **Nom i adreça** **, Telèfon** o **correu** electrònic. 

   > [!TIP]
   > Com més identificadors i camps de clau assigneu, més probabilitats hi ha d'una taxa de coincidència més alta 

1. Assigneu els camps de l'entitat Client *unificada* que s'utilitzaran per fer coincidir amb el gràfic de l'ID de l'AbiliTec de LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opcions d'assignació de dades per a l'enriquiment liveRamp.":::

1. Seleccioneu **Següent** per completar l'assignació de camp. 

1. Proporcioneu un **nom** per a l'enriquiment i l'entitat **Sortida**. 

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions. 

## <a name="configure-the-connection-for-liveramp"></a>Configura la connexió per a LiveRamp 

Heu de ser administrador per configurar les [connexions](connections.md). Seleccioneu **Afegeix una connexió** en configurar l'enriquiment o aneu a **AdminConnections** > **i** seleccioneu **Configura** a la **peça LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Subfinestra de configuració per configurar la connexió al servei LiveRamp AbiliTec.":::

1. Per al **nom** de visualització, introduïu el nom de la connexió. 

1. Proporcioneu un identificador de client liveRamp vàlid i un secret. 

1. Reviseu-ho i proporcioneu el vostre consentiment per a la **Privadesa i el compliment de les dades** seleccionant la casella de selecció **Ho accepto**. 

1. Seleccioneu **Verifica** per validar la configuració. 

1. Per completar la connexió, seleccioneu **Desa**. 

## <a name="enrichment-results"></a>Resultats de l'enriquiment 

Per iniciar el procés d'enriquiment, seleccioneu Executa des de la barra d'ordres. També podeu permetre que el sistema executi l'enriquiment automàticament com a [part de l'actualització](system.md#schedule-tab) programada. El temps de processament depèn de la mida de les dades dels clients. 

Un cop finalitzat el procés d'enriquiment, podeu revisar les dades de perfils de clients recentment enriquits **.** A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits. 

Podeu accedir a una visualització detallada de cada perfil enriquit seleccionant **Dades enriquides** deView. 

## <a name="next-steps"></a>Passos següents

Construïu a partir de les dades de clients enriquits. Utilitzeu els identificadors d'AbiliTec per consolidar perfils de clients en una visualització basada en persones. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades 

Quan habiliteu Dynamics 365 Customer Insights transmetre dades a LiveRamp, permeteu la transferència de dades fora del límit de compliment de Dynamics 365 Customer Insights, incloses dades potencialment sensibles, com ara dades personals. Microsoft transferirà aquestes dades a les instruccions, però sou responsable d'assegurar-vos que LiveRamp compleixi amb qualsevol obligació de privadesa o de seguretat que pugueu tenir. Per obtenir més informació, consulteu la [Declaració](https://go.microsoft.com/fwlink/?linkid=396732) de privadesa de Microsoft. L'administrador del Dynamics 365 Customer Insights pot suprimir aquest enriquiment en qualsevol moment per deixar de continuar utilitzant aquesta funcionalitat. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
