---
title: Com gestionar entorns
description: Obteniu informació sobre com podeu gestionar els entorns existents del Customer Insights com a administrador".
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833480"
---
# <a name="how-to-manage-environments"></a>Com: Gestionar entorns

Els administradors [creen](create-environment.md) i administren entorns. Poden canviar alguns paràmetres en entorns existents. L'empresa, el tipus, la regió, l'opció d'emmagatzematge i Dataverse la configuració es fixen després de crear l'entorn. Si voleu canviar aquesta configuració, reinicialitza l'entorn o crea un entorn nou.

## <a name="edit-an-existing-environment"></a>Editar un entorn existent

Podeu editar alguns dels detalls dels entorns existents.

1. Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

1. Seleccioneu la icona **Edita**.

   :::image type="content" source="media/edit-environment.png" alt-text="Icona per editar la configuració de l'entorn.":::

1. Al quadre **Edita l'entorn** podeu actualitzar la configuració de l'entorn.

Per començar amb un entorn nou, consulta [Crear un entorn nou](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Canviar el propietari d'un entorn

Diversos usuaris poden tenir permisos d'administració, però només un usuari és el propietari d'un entorn. Per defecte, és l'administrador qui crea un entorn inicialment. Com a administrador d'un entorn, podeu assignar la propietat a un altre usuari amb permisos d'administració.

1. Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

1. Seleccioneu la icona **Edita**.

1. Al quadre Edita l'entorn **·**, aneu al **pas Informació** bàsica.

1. Al camp Canvia el **propietari del camp d'entorn**, trieu el nou propietari de l'entorn.  

1. Seleccioneu **Revisa i finalitza** i, a continuació **, Actualitza** per aplicar els canvis.

## <a name="claim-ownership-of-an-environment"></a>Reclamar la propietat d'un entorn

Si el compte d'usuari del propietari se suprimeix o se suspèn, l'entorn no tindrà propietari. Cada usuari administrador pot reclamar la propietat i convertir-se en el nou propietari. Poden continuar sent propietaris de l'entorn o [canviar la propietat a un altre administrador](#change-the-owner-of-an-environment).

Per reclamar la propietat, seleccioneu el botó Pren la **propietat** que es mostra a la part superior de cada pàgina del Customer Insights quan el propietari original va sortir de l'organització.

## <a name="reset-an-existing-environment-preview"></a>Reinicialitza un entorn existent (visualització prèvia)

Com a propietari d'un entorn, podeu restablir un entorn a un estat buit si voleu suprimir totes les configuracions i suprimir les dades ingerides.

1. Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

1. Seleccioneu l'entorn que voleu restablir i seleccioneu l'el·lipsi vertical (&vellip;).

1. Trieu l'opció **Reinicialitza**.

   :::image type="content" source="media/reset-environment.png" alt-text="Control per restablir un entorn.":::

1. Trieu si voleu restablir tot l'entorn, tot excepte les fonts de dades o qualsevol cosa que estigui configurada a la part superior del perfil de client unificat.

1. Per confirmar-ho, introduïu el nom de l'entorn i seleccioneu **Reinicialitza**.

## <a name="delete-an-existing-environment"></a>Suprimir un entorn existent

Com a propietari d'un entorn, podeu suprimir un entorn que administreu.

1. Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

1. Seleccioneu l'entorn que voleu restablir i seleccioneu l'el·lipsi vertical (&vellip;). 

1. Trieu l'opció **Suprimeix**.

   :::image type="content" source="media/delete-environment.png" alt-text="Control per suprimir l'entorn.":::

1. Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Suprimeix**.

> [!IMPORTANT]
> Si suprimiu un entorn, no se suprimirà la connexió amb un Dataverse entorn. Si teniu previst connectar el mateix Dataverse entorn a un entorn nou del Customer Insights en el futur, heu de suprimir aquesta connexió Obteniu informació sobre com [suprimir una connexió existent a un Dataverse entorn](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
