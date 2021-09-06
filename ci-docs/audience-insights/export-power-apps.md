---
title: Connector del Power Apps
description: Connecteu amb el Power Apps i el Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031737"
---
# <a name="microsoft-power-apps-connector-preview"></a>Connector del Microsoft Power Apps (visualització prèvia)

Incorporeu perfils de client unificats a les vostres aplicacions personalitzades amb el Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Connectar el Power Apps i el Dynamics 365 Customer Insights

El Customer Insights és una de les diverses [fonts de dades disponibles al Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulteu la documentació del Power Apps per obtenir més informació sobre com [afegir una connexió de dades a una aplicació](/powerapps/maker/canvas-apps/add-data-connection). També us recomanem que reviseu [com utilitza el Power Apps la delegació per gestionar grans conjunts de dades a les aplicacions de llenç](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entitats disponibles

Després d'afegir el Customer Insights com a connexió de dades, podeu triar les entitats següents al Power Apps:

- Client: per utilitzar les dades del [perfil del client unificat](customer-profiles.md).
- UnifiedActivity: per mostrar la [cronologia d'activitat](activities.md) a l'aplicació.

## <a name="limitations"></a>Limitacions

### <a name="retrievable-entities"></a>Entitats recuperables

Només podeu recuperar les entitats **Client**, **UnifiedActivity** i **Segments** a través del connector del Power Apps. Es mostren altres entitats perquè el connector subjacent els admet mitjançant activacions al Power Automate.  

### <a name="delegation"></a>Delegació

La delegació funciona per a l'entitat Client i UnifiedActivity. 

- Delegació per a l'entitat **Client**: per utilitzar la delegació per a aquesta entitat, els camps s'han d'indexar a [Cerca i filtra l'índex](search-filter-index.md).  

- Delegació per a **UnifiedActivity**: la delegació per a aquesta entitat només funciona per als camps **ActivityId** i **CustomerId**.  

- Per obtenir més informació sobre la delegació, vegeu [Funcions i operacions delegables del Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Exemple de control de galeria

Per exemple, afegiu perfils de client a un [control de galeria](/powerapps/maker/canvas-apps/add-gallery).

1. Afegiu un control de **Galeria** a una aplicació que estigueu creant.

> [!div class="mx-imgBorder"]
> ![Afegir un element de galeria.](media/connector-powerapps9.png "Afegir un element de galeria")

1. Seleccioneu **Client** com a font de dades dels elements.

    > [!div class="mx-imgBorder"]
    > ![Seleccioneu un origen de dades.](media/choose-datasource-powerapps.png "Seleccioneu un origen de dades")

1. Podeu canviar la subfinestra de dades a la dreta per seleccionar quin camp de l'entitat Client es mostrarà a la galeria.

1. Si voleu mostrar qualsevol camp del client seleccionat a la galeria, empleneu la propietat Text d'una etiqueta: **{Name_of_the_gallery}.Selected.{property_name}**

    Exemple: Gallery1.Selected.address1_city

1. Per mostrar la cronologia unificada d'un client, afegiu-hi un element Galeria i afegiu la propietat Items: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Exemple: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]