---
title: Connector del Power Apps (visualització prèvia)
description: Connecteu amb el Power Apps i el Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196888"
---
# <a name="power-apps-connector-preview"></a>Connector del Power Apps (visualització prèvia)

Incorporeu perfils de client unificats a les vostres aplicacions personalitzades amb el Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Connectar el Power Apps i el Dynamics 365 Customer Insights

El Customer Insights és una de les diverses [fonts de dades disponibles al Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulteu la documentació del Power Apps per obtenir més informació sobre com [afegir una connexió de dades a una aplicació](/powerapps/maker/canvas-apps/add-data-connection). També us recomanem que reviseu [com utilitza el Power Apps la delegació per gestionar grans conjunts de dades a les aplicacions de llenç](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entitats disponibles

Després d'afegir el Customer Insights com a connexió de dades, trieu les entitats següents a Power Apps:

- **Client**: per utilitzar les dades del [perfil del client unificat](customer-profiles.md).
- **UnifiedActivity** : per visualitzar la [cronologia d'activitat](activities.md) a l'aplicació.
- **ContactProfile**: per mostrar els contactes d'un client. Aquesta entitat només està disponible en entorns del Customer Insights per a comptes d'empresa.

## <a name="limitations"></a>Limitacions

### <a name="retrievable-entities"></a>Entitats recuperables

Només podeu recuperar les entitats **Client**, **UnifiedActivity**, **Segments** i **ContactProfile** a través del connector del Power Apps. ContactProfile només està disponible en entorns del Customer Insights per a comptes d'empresa. Es mostren altres entitats perquè el connector subjacent els admet mitjançant activacions al Power Automate.

Pots fer un màxim de 100 trucades cada 60 segons. Podeu trucar al punt final de l'API diverses vegades mitjançant el paràmetre $skip. [Obteniu més informació sobre el paràmetre $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegació

La delegació funciona per a l'entitat **Client** i **UnifiedActivity**.

- Delegació per a **l'entitat client** : Per utilitzar la delegació per a aquesta entitat, els camps s'han d'indexar a [l'índex de cerca i filtre](search-filter-index.md).  
- Delegació per a **UnifiedActivity**: la delegació per a aquesta entitat només funciona per als camps **ActivityId** i **CustomerId**.  
- Delegació per a **ContactProfile**: la delegació per a aquesta entitat només funciona per als camps **ContactId** i **CustomerId**. ContactProfile només està disponible en entorns del Customer Insights per a comptes d'empresa.

Per obtenir més informació sobre la delegació, aneu a [Funcions i operacions delegables del Power Apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Exemple de control de galeria

Opcionalment, afegiu perfils de client a un [control de galeria](/powerapps/maker/canvas-apps/add-gallery).

1. Afegiu un control de **galeria** a una aplicació que estigueu creant.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Afegir un element de galeria.":::

1. Seleccioneu **Client** com a font de dades dels elements.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Seleccioneu un origen de dades.":::

1. Canvieu el tauler de dades de la dreta per seleccionar quin camp de l'entitat Client es mostrarà a la galeria.

1. Si voleu mostrar qualsevol camp del client seleccionat a la galeria, empleneu la propietat **Text** d'una etiqueta utilitzant **{Name_of_the_gallery}.Selected{property_name}**  
    - Per exemple: _Gallery1.Selected.address1_city_

1. Per mostrar la cronologia unificada d'un client, afegiu-hi un element de galeria i afegiu la propietat **Elements** utilitzant **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Per exemple: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
