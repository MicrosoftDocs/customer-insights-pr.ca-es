---
title: Utilitzar dimensions demogràfiques per dividir dades de comportament (dimensions curades)
description: Utilitzeu dimensions curades del perfil unificat per habilitar les propietats del perfil del client de les conclusions del públic.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232955"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Utilitzar dimensions demogràfiques per dividir dades de comportament

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mitjançant dimensions demogràfiques del perfil unificat, els usuaris de conclusions d'interacció poden accedir a propietats del perfil de conclusions del públic. A continuació, podeu compartir aquestes propietats en l'anàlisi interactiva de dades de comportament, incloses les dades capturades per les conclusions sobre la interacció al vostre lloc web o la vostra aplicació mòbil.

>[!NOTE]
> Els coneixements d'interacció inclouen dimensions estàndard per a les propietats de la incidència. Més informació: [Visualitzar i crear dimensions](dimensions.md)

## <a name="prerequisite"></a>Requisit previ

- Un entorn de conclusions d’interacció en què tingueu dades de perfil del client enllaçades a l’entorn de conclusions del públic on es creen els perfils de clients. Més informació: [Creació d'un enllaç entre les conclusions del públic i les conclusions d'interacció](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Després de crear un enllaç entre els entorns de conclusions del públic i d'interacció, pot ser que només vulgueu dades específiques de les propietats del perfil del client, que poden ser útils com a dimensions de les conclusions d'interacció. Per obtenir-ne més informació, aneu a [Habilitació dels segments i els atributs dels perfils unificats de les conclusions del públic](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Crear un informe nou personalitzat

1. A la subfinestra esquerra, seleccioneu **Personalitzat** > **Informe nou** i, a continuació, seleccioneu la mètrica que voleu. (En aquest exemple, hem triat **Visualitzacions de pàgina per hora**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Seleccioneu una mètrica.":::

2. A l'editor de visualitzacions, seleccioneu **Dimensions** i, a continuació, seleccioneu **Dades demogràfiques** al menú desplegable **Tipus de dimensió**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Seleccioneu dades demogràfiques.":::

3. Seleccioneu una dimensió **Signal.Customer.*xxx***. (En aquest exemple es mostra Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Seleccioneu una dimensió.":::
  
## <a name="limitations"></a>Limitacions

Actualment, només podeu utilitzar dimensions demogràfiques per dividir dades de comportament.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
