---
title: Creació d'un enllaç entre les conclusions del públic i les conclusions d'interacció
description: Creeu un enllaç actiu entre les conclusions del públic i les d'interacció per habilitar l'ús compartit bidireccional de dades.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229860"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Creació d'un enllaç entre les conclusions del públic i les conclusions d'interacció

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La integració entre les conclusions del públic i les conclusions d'interacció enllaça els entorns de les dues capacitats i permet compartir dades de manera bidireccional entre elles.

Utilitzeu perfils i segments unificats de les conclusions del públic per obtenir més opcions d'anàlisi a les conclusions d'interacció. Exporteu incidències que tenen un valor empresarial alt de les conclusions d'interacció. Utilitzeu aquestes incidències per afegir dades a perfils unificats de les conclusions del públic.

## <a name="prerequisites"></a>Requisits previs

- Els perfils de les conclusions del públic s'han d'emmagatzemar en un compte del Azure Data Lake Storage que tingueu o en un llac de dades administrat pel [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash;. 
- A més, l'entorn de les conclusions del públic ha de tenir un entorn del Dataverse associat. I si aquest entorn també utilitza el Dataverse per a l'emmagatzematge de dades, assegureu-vos de comprovar l'opció **Habilita l'ús compartit de dades** a la informació del públic. Per obtenir més informació, vegeu [Crear i configurar un entorn a les conclusions del públic](../audience-insights/create-environment.md).
- Necessiteu permisos d'administrador per als entorns de les conclusions del públic i les conclusions d'interacció.
- Els entorns enllaçats han d'estar a la mateixa regió geogràfica.

> [!NOTE]
> - Si la vostra subscripció a les conclusions del públic és una prova, que utilitza un llac de dades gestionat internament amb conclusions del públic, poseu-vos en contacte amb [pirequest@microsoft.com](mailto:pirequest@microsoft.com) per obtenir ajuda. 
> - Si el vostre entorn de conclusions del públic utilitza la vostra instància del Azure Data Lake Storage per emmagatzemar dades, heu d'afegir una entitat de seguretat de servei de l'Azure al compte d'emmagatzematge. Per obtenir més informació, aneu a [Connexió amb un compte de l'Azure Data Lake Storage amb l'entitat de seguretat de servei de l'Azure per a les conclusions del públic](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Crear un enllaç de l'entorn

Podeu crear un enllaç de l'entorn mitjançant l'actualització de la configuració **Administrador** > **Entorn** a les conclusions d'interacció.

**Per establir un enllaç actiu entre les conclusions del públic i les conclusions d'interacció**

1. A la pàgina **Administració de l'entorn**, seleccioneu la pestanya **Enllaça els entorns**.

    :::image type="content" source="media/integrate1.png" alt-text="Configurar un entorn.":::

1. Seleccioneu **Entorns de configuració** a la part superior esquerra o a la part inferior de la pantalla.

     :::image type="content" source="media/integrate2.png" alt-text="Seleccioneu un entorn de conclusions del públic.":::

1. Seleccioneu un entorn de conclusions del públic i, a continuació, seleccioneu ***Següent** per finalitzar. Ara podeu seleccionar característiques opcionals per als entorns enllaçats.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Habilitació dels segments i els atributs dels perfils unificats de les conclusions del públic

Després d'enllaçar els entorns, podeu seleccionar característiques opcionals per als entorns enllaçats. Aquestes característiques permeten atributs i segments del perfil unificats a partir de les conclusions del públic per a una anàlisi interactiva de les dades dels clients.

> [!IMPORTANT]
> Per tal que els segments de conclusions del públic es mostrin a les conclusions d'interacció, primer heu d'[executar la combinació i els processos descendents](../audience-insights/merge-entities.md). Els processos descendents són importants perquè generen una taula única que prepara els segments de conclusions del públic per compartir-se amb les conclusions sobre la interacció. (Si es planifica una actualització del sistema, inclourà automàticament processos descendents.)

**Per analitzar dades web a les conclusions sobre la interacció**

1. A la pàgina **Administració de l'entorn**, activeu la funció **Comparteix dades de conclusions del públic amb conclusions d'interacció**, i, a continuació, seleccioneu **Següent**.

    :::image type="content" source="media/integrate4.png" alt-text="Seleccioneu les característiques.":::

1. Seleccioneu els atributs dels perfils unificats que es convertiran en dimensions a les conclusions d'interacció. (No tots els atributs són dimensions útils. Per exemple, és probable que us calgui un **nom** o **cognom** com un atribut per analitzar les incidències del lloc web.)

    :::image type="content" source="media/integrate5.png" alt-text="Administra les dimensions.":::

   >[!NOTE]
   > Tots els atributs del perfil de conclusions del públic que representen identificadors (com ara l'**ID** i l'**ID alternatiu**) es filtren fora dels atributs disponibles i es converteixen en dimensions a les conclusions d'interacció.

1. Quan acabeu de seleccionar els atributs, seleccioneu **Següent**.
1. Afegiu usuaris que puguin veure les dimensions i els segments del perfil de conclusions del públic a les conclusions d'interacció.

    :::image type="content" source="media/integrate6.png" alt-text="Administreu l'accés a les dades del client.":::

   > [!IMPORTANT]
   > Si no afegiu explícitament usuaris en aquest pas, les dades s'amagaran per als usuaris a les conclusions d'interacció.
   > Per tal que els segments de conclusions del públic es mostrin a les conclusions d'interacció, primer heu d'[executar la combinació i els processos descendents](../audience-insights/merge-entities.md). Els processos descendents són importants perquè generen una taula única que prepara els segments de conclusions del públic per compartir-se amb les conclusions sobre la interacció. (Si es planifica una actualització del sistema, inclourà automàticament processos descendents.)

1. Reviseu la selecció i, a continuació, seleccioneu **Finalitza**.

    :::image type="content" source="media/integrate7.png" alt-text="Revisar la configuració de les dades dels clients.":::

## <a name="export-refined-events-to-audience-insights"></a>Exporteu incidències refinades a les conclusions del públic

Després de crear un enllaç entre entorns, podeu exportar les incidències refinades des de les conclusions d'interacció a les conclusions del públic i ingerir-les com una font de dades nova. 

Per obtenir més informació, aneu a [Integració de dades web des de les conclusions d'interacció amb les conclusions del públic](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
