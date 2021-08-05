---
title: Crear i configurar una versió de prova del Customer Insights
description: Passos per obtenir una subscripció de prova del Dynamics 365 Customer Insights i configurar-la.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f80654f03252142ce08241ff3ca3606be4595740
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650447"
---
# <a name="set-up-a-trial-environment"></a>Configuració un entorn de prova 

Una versió de prova del Dynamics 365 Customer Insights us permet revisar la capacitat clau i obtenir més informació sobre les diferents característiques. Una subscripció de prova se suprimeix després de caducar. Els entorns de prova són creats per usuaris individuals que es converteixen en administradors del seu entorn de prova. Poden convidar més usuaris a la seva prova i configurar les diferents característiques.

## <a name="create-a-trial-environment"></a>Crear un entorn de prova

Podeu registrar-vos en una prova a la [pàgina de registre en una prova](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Trieu l'opció **Registra'm en una prova gratuïta** i seleccioneu **Registra'm ara**.

1. Proporcioneu la vostra adreça de correu electrònic laboral o acadèmica, expliqueu-nos més sobre vosaltres mateixos i seleccioneu **Comença**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Diàleg per registrar-se a una instància de prova":::

1. Reviseu-ne les condicions i seleccioneu **Continua** per confirmar.

1. Proporcioneu un **Nom** per al vostre nou entorn. 

1. Definiu el **tipus** d'entorn com a **Prova**.

1. Al camp **Seleccioneu una demostració del sector**, opcionalment podeu triar un conjunt de dades específiques del sector. També podeu [canviar a una demostració del sector](#use-industry-specific-demo-data-sets-in-audience-insights) més endavant i començar amb el conjunt de dades per defecte.

1. Trieu la **Regió** per al vostre entorn.

1. Opcionalment, si sou l'administrador d'una organització del Dynamics 365: seleccioneu **Configuració avançada** i proporcioneu l'adreça URL de l'organització per utilitzar característiques de predicció, com ara la predicció de rotació del client. 

1. Seleccioneu **Crea**. 

Es triga uns instants a completar la configuració de l'entorn. Després de finalitzar, se us redirigeix a l'entorn de demostració o a la demostració del sector que trieu al pas anterior. Ara podeu explorar l'aplicació amb dades de demostració només de lectura. Per afegir les vostres pròpies dades a l'entorn, vegeu [Crear dades de demostració específiques de l'escenari al vostre propi entorn](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Captura de pantalla d'un entorn de prova creat recentment.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Utilitzar conjunts de dades de demostració específiques del sector a les conclusions del públic

La connexió de fonts de dades reals és un dels passos més importants per aprofitar el potencial del Customer Insights. Per provar funcions sense interferir amb les vostres pròpies dades, opcionalment podeu utilitzar dades de demostració específiques del sector. Hi ha un parell de conjunts de dades de demostració disponibles per als sectors següents: 

-   Automoció
-   Banca
-   Bens de consum
-   Govern
-   Assistència sanitària
-   Hospitalitat
-   Assegurances
-   Fabricació
-   Serveis professionals
-   Comerç

### <a name="see-industry-specific-demo-data-in-trials"></a>Veure dades de demostració específiques del sector en proves

Per obtenir una versió només de lectura del Customer Insights adaptada a un sector o escenari específic, comenceu a l'entorn de demostració. 
 
1.  A les conclusions del públic, trieu l'entorn **Demostració** al selector d'entorn.

2.  A **Inici**, trieu una opció al menú desplegable Selecciona una demostració del sector.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Trieu un sector per a l'entorn de prova.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Crear dades de demostració específiques de l'escenari en el vostre propi entorn

Com a administrador, seleccioneu el selector d'entorn a la capçalera de l'aplicació per crear un entorn nou. A l'entorn nou podeu configurar les vostres pròpies fonts de dades i configurar l'aplicació segons els vostres requisits. 

1.  A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2.  Per importar les vostres pròpies fonts de dades, aneu a la [guia sobre la ingesta de dades](data-sources.md).     
   Si preferiu treballar amb dades d'exemple que us permetin provar la ingesta de dades, podeu ingerir les dades de demostració del sector al vostre entorn. Trieu l'opció **Importa des de Datahub** i seguiu els passos que s'indiquen a continuació.

3.  Seleccioneu la targeta del sector que s'adapti al vostre escenari. 

4.  Reviseu i, opcionalment, actualitzeu el nom suggerit de la font de dades. 

5.  Seleccioneu **Següent** per ingerir les dades d'exemple. 

Ara podeu utilitzar les dades ingerides per adaptar el Customer Insights al vostre escenari. Per veure un entorn específic de les dades de demostració ingerides, trieu l'opció **Demostració de <Industry>** al selector d'entorn.

## <a name="limitations-in-trials"></a>Limitacions de les proves

- Les proves estan actives durant 30 dies de manera predeterminada. No obstant això, podeu ampliar-les després del dia 23 quan inicieu la sessió a la prova.
- No podeu utilitzar el vostre propi compte de l'Azure Data Lake Storage per emmagatzemar les dades de sortida durant una prova. No obstant això, podeu ingerir dades d'un compte del Data Lake Storage.
- Podeu emmagatzemar dades de fins a 3 GB a l'entorn del Dataverse que se subministra automàticament quan inicieu una prova del Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Copiar dades d'una versió de prova a una subscripció de pagament

En general, us recomanem que comenceu de nou amb les vostres pròpies dades quan actualitzeu a la versió de pagament del Customer Insights. 

Opcionalment, podeu copiar les vostres dades d'un entorn de prova si compreu el Customer Insights. Heu de ser l'administrador de la versió de prova del Customer Insights i l'administrador global del vostre inquilí del Microsoft 365 o l'administrador del Dynamics 365 a l'organització per migrar la configuració d'un entorn de prova a un entorn de pagament. 

Després d'iniciar la sessió a la instància de pagament del Customer Insights per primera vegada, se us demana que creeu un entorn nou. En aquest procés, podeu triar de copiar la configuració d'un entorn existent i migrar la majoria dels paràmetres. Si teniu els permisos esmentats anteriorment, l'entorn de prova es mostrarà en aquesta llista. Per obtenir més informació, vegeu [Copiar la configuració de l'entorn](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Passos següents

Reviseu els articles següents per ajudar-vos a començar a configurar el Customer Insights. 

- [Afegiu més usuaris i assigneu permisos](permissions.md).
- [Ingeriu les fonts de dades](data-sources.md) i executeu-les a través del [procés d'unificació de dades](data-unification.md) per obtenir [perfils de client unificats](customer-profiles.md).
- [Enriquir els perfils de client unificats](enrichment-hub.md) o [executar models predictius](predictions-overview.md).
- Creeu [segments](segments.md) per agrupar clients i [mesures](measures.md) per revisar els KPI.
- Configureu [connexions](connections.md) i [exportacions](export-destinations.md) per processar subconjunts de les vostres dades en altres aplicacions.