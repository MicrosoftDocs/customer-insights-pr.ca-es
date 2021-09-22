---
title: Ús dels segments de conclusions del públic per filtrar informes de conclusions sobre la interacció
description: Utilitzeu els segments de conclusions del públic en l'anàlisi interactiva de dades de comportament capturades per les conclusions sobre la interacció al lloc web d'un client.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461046"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Ús dels segments de conclusions del públic per filtrar informes de conclusions sobre la interacció

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Amb les conclusions sobre la interacció, podeu utilitzar els segments de conclusions del públic en l'anàlisi interactiva de dades de comportament capturades per les conclusions sobre la interacció als llocs web.

## <a name="prerequisite"></a>Requisit previ

- Un entorn de conclusions d’interacció en què tingueu dades de segments de conclusions del públic enllaçades a l’entorn de conclusions del públic on es creen els segments i els perfils de clients. Més informació: [Creació d'un enllaç entre les conclusions del públic i les conclusions d'interacció](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Creació de segments de conclusions del públic 

> [!IMPORTANT]
> Per tal que els segments de conclusions del públic es mostrin a les conclusions d'interacció, primer heu d'[executar la combinació i els processos descendents](../audience-insights/merge-entities.md). Els processos descendents són importants perquè generen una taula única que prepara els segments de conclusions del públic per compartir-se amb les conclusions sobre la interacció. (Si es planifica una actualització del sistema, inclourà automàticament processos descendents.)

Podeu utilitzar els segments de conclusions del públic en informes personalitzats o predefinits de conclusions sobre les interaccions que heu creat. Per obtenir-ne més informació, aneu als [informes de perfil predefinits](profile-reports.md) i [creeu i editeu informes personalitzats](custom-reports.md).

**Per utilitzar segments de conclusions del públic en informes de conclusions sobre la interacció**

1. A la pàgina **Àrea de treball**, seleccioneu **Dades** i, a continuació, seleccioneu la pestanya **Segments**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Seleccioneu la pestanya Segments.":::

   >[!NOTE]
   > En seleccionar un segment de conclusions del públic, se us dirigirà a les conclusions del públic, on podeu saber com es va crear aquest segment pel que fa a les regles i la lògica. Per obtenir més informació sobre els segments de conclusions del públic, aneu a [Visualitzar i crear segments. ](../audience-insights/segments.md)

2. Seleccioneu un informe predefinit o [creeu un informe personalitzat](custom-reports.md) i, a continuació, seleccioneu **Afegeix una condició**. (En aquest exemple, hem triat l'informe **Visualitzacions de pàgina**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Afegiu una condició.":::

3. Seleccioneu **Filtra per segment**, expandiu la llista de **tipus de segments** i, a continuació, seleccioneu **Dades demogràfiques**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Seleccioneu el tipus de segment demogràfic.":::

4. Expandiu la llista **Nom del segment** i trieu un segment de conclusions del públic.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Trieu un segment.":::

5. Podeu aplicar un o diversos segments, inclòs el de comportament (conclusions sobre la interacció) i demogràfic (conclusions del públic). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Informe de visualitzacions de pàgina restringit als clients dels EUA i als segments de pàgina inicial.":::

A la imatge anterior, s'han seleccionat els segments **Clients dels EUA** i **Pàgina inicial**, la qual cosa restringeix l'informe **Visualitzacions de pàgina** per visualitzar aquests dos segments. 


>[!NOTE]
> Podeu utilitzar els segments de conclusions del públic per filtrar els informes personalitzats i predefinits i els embuts a les conclusions d'interacció. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]