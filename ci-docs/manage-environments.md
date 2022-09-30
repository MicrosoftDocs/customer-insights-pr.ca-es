---
title: Gestionar entorns
description: Obteniu informació sobre com podeu administrar els entorns existents del Customer Insights com a administrador.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588800"
---
# <a name="manage-environments"></a>Gestionar entorns

Els administradors [creen](create-environment.md) i administren entorns. Poden canviar alguns paràmetres en entorns existents. L'empresa, el tipus, la regió, l'opció d'emmagatzematge i Dataverse la configuració es fixen després de crear l'entorn. Si voleu canviar aquesta configuració, [restableix l'entorn](#reset-an-existing-environment-preview) o [crea un entorn nou](create-environment.md).

## <a name="edit-an-existing-environment"></a>Editar un entorn existent

Editeu els detalls d'un entorn existent, com ara el nom o la configuració de l'entorn per defecte.

1. Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

1. Seleccioneu la icona **Edita**.

   :::image type="content" source="media/edit-environment.png" alt-text="Icona per editar la configuració de l'entorn.":::

1. A la subfinestra Entorn d'edició **·**, actualitzeu la configuració de l'entorn.

1. Selecciona **Revisar i finalitzar** i, a continuació **, Actualitzar** per aplicar els canvis.

## <a name="change-the-owner-of-an-environment"></a>Canviar el propietari d'un entorn

Diversos usuaris poden tenir permisos d'administrador, però només un usuari és el propietari d'un entorn. Per defecte, és l'administrador qui crea un entorn inicialment. Com a administrador d'un entorn, podeu assignar la propietat a un altre usuari amb permisos d'administrador.

1. Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

1. Seleccioneu la icona **Edita**.

1. A la **subfinestra Entorn d'edició**, aneu al **pas Informació** bàsica.

1. Al camp Canvia el **propietari de l'entorn**, trieu el nou propietari de l'entorn.  

1. Selecciona **Revisar i finalitzar** i, a continuació **, Actualitzar** per aplicar els canvis.

## <a name="claim-ownership-of-an-environment"></a>Reclamar la propietat d'un entorn

Si se suprimeix o se suspèn el compte d'usuari del propietari, l'entorn no en tindrà cap propietari. Qualsevol usuari administrador pot reclamar la propietat i convertir-se en el nou propietari. L'administrador propietari pot continuar sent el propietari de l'entorn o [canviar la propietat a un altre administrador](#change-the-owner-of-an-environment).

Per reclamar la propietat, seleccioneu el botó Pren la **propietat** que es mostra a la part superior de totes les pàgines del Customer Insights quan el propietari original va abandonar l'organització.

## <a name="reset-an-existing-environment-preview"></a>Restablir un entorn existent (vista prèvia)

Com a propietari d'un entorn, restableix un entorn a un estat buit si voleu suprimir totes les configuracions i eliminar les dades ingerides.

1. Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

1. Seleccioneu l'entorn que voleu restablir i seleccioneu els punts suspensius verticals (&vellip;).

1. Trieu **Restableix (previsualització)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Control per restablir un entorn.":::

1. Trieu si voleu restablir tot l'entorn, tot excepte les fonts de dades o qualsevol cosa que estigui configurada a la part superior del perfil de client unificat.

1. Per confirmar-ho, introduïu el nom de l'entorn i seleccioneu **Restableix**.

## <a name="delete-an-existing-environment"></a>Suprimir un entorn existent

Com a propietari d'un entorn, podeu suprimir-lo.

> [!IMPORTANT]
> La supressió d'un entorn no elimina la connexió a un Dataverse entorn. Si teniu previst connectar el mateix Dataverse entorn a un entorn nou del Customer Insights en el futur, heu de [suprimir aquesta connexió amb l'entorn Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

1. Seleccioneu l'entorn que voleu suprimir i seleccioneu els punts suspensius verticals (&vellip;). 

1. Trieu **Suprimeix**.

   :::image type="content" source="media/delete-environment.png" alt-text="Control per eliminar l'entorn.":::

1. Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Suprimeix**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
