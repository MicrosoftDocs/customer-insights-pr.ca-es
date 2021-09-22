---
title: Administrar àrees de treball i entorns
description: Com crear, canviar el nom i suprimir àrees de treball i entorns.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034030"
---
# <a name="manage-environments-and-workspaces"></a>Administrar entorns i àrees de treball

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Informació general

Una àrea de treball és un espai on es poden emmagatzemar i administrar incidències i informes. És on podeu visualitzar l'activitat dels usuaris en temps real. Quan creeu una àrea de treball, seleccioneu el tipus de dades que voleu enviar a l'àrea de treball. Actualment, s'admeten les dades web i les aplicacions mòbils.

Un entorn és una àrea on administreu les vostres àrees de treball i connexions. La manera d'utilitzar els entorns depèn de la vostra organització i del cas d'ús. Per exemple, podeu crear:

-   Un entorn únic.
-   Entorns diferents per a provar i produir.
-   Entorns separats per a equips o departaments específics de la vostra organització que contenen incidències rellevants per a cada públic.
-   Entorns separats per a diferents branques globals de la vostra empresa.
-   Connexions a la capacitat d'estadístiques del públic del Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Triar un entorn i crear una àrea de treball 

Cada àrea de treball ha de ser en un entorn. Podeu seleccionar un entorn existent o crear-ne un de nou quan creeu una àrea de treball. A continuació, podeu afegir membres de l'àrea de treball i començar a recopilar dades.

**Per a crear la vostra primera àrea de treball**

1. Als coneixements d'interacció, seleccioneu **Crea** al commutador de l'àrea de treball. 

   :::image type="content" source="media/New-workspace.png" alt-text="Selector d'àrea de treball de la pàgina del Customer Insights.":::

1. Trieu un entorn de la llista o seleccioneu **Crea un entorn nou**.

1. Introduïu un nom a **Nom de l'àrea de treball**. 

1. Seleccioneu el tipus d'entorn que voleu crear, en funció de si voleu mesurar què succeeix en un lloc web o en una aplicació mòbil. 

1. Podeu afegir membres i assignar el seu nivell de permís des de la llista de **Funcions**. A continuació, seleccioneu **Finalitza** per crear l'àrea de treball o **Següent** per instal·lar el codi. 

1. Instal·leu el fragment de codi per començar a rebre dades i, a continuació, seleccioneu **Fet**. 

## <a name="manage-a-workspace"></a>Administrar una àrea de treball

Podeu mantenir diverses àrees de treball simultàniament en un entorn. La vostra [funció](user-roles.md) determina com podeu treballar-hi. 

 - Heu de ser un administrador de l'entorn o un administrador de l'àrea de treball per administrar l'àrea de treball.
 - Com a administrador de l'àrea de treball, podeu canviar el nom de les àrees de treball existents o suprimir-les. 

### <a name="edit-a-workspace-name"></a>Edita un nom de l’àrea de treball

1. Aneu a **Administrador** > **Àrea de treball** i seleccioneu **Configuració**.

1. Introduïu un nom nou al quadre **Nom de l'àrea de treball**.

1. Seleccioneu **Desa** per aplicar els canvis.

### <a name="delete-a-workspace"></a>Suprimir una àrea de treball

Si suprimiu una àrea de treball, se'n suprimirà de manera permanent tot el contingut, les dades, la configuració i els permisos. Aquesta operació no es pot desfer.

1. Aneu a **Administrador** > **Àrea de treball** i seleccioneu **Configuració**.

1. Seleccioneu **Suprimeix l'àrea de treball**. 

1. Al diàleg **Supressió de l'àrea de treball**, introduïu **CONFIRMA LA SUPRESSIÓ**. 

1. Seleccioneu **Suprimeix** per suprimir de manera permanent l'àrea de treball.

### <a name="manage-workspace-members"></a>Administra els membres de l'àrea de treball

1. Aneu a **Administrador** > **Àrea de treball** i seleccioneu **Membres**.

1. Seleccioneu **Afegeix membres** per donar accés i [assignar funcions](user-roles.md). Actualment, només està disponible **Administrador de l'àrea de treball**.

1. Si configureu una [connexió amb les estadístiques del públic](configure-connections.md), podeu seleccionar **Permet l'accés a les dades de perfil** per permetre que el membre vegi informes basats en [perfils d'usuari](profile-reports.md).

1. Seleccioneu **Afegeix membres** per afegir-los a l'àrea de treball.

## <a name="manage-an-environment"></a>Gestionar un entorn

Com a administrador de l'entorn, podeu accedir a un entorn des de la subfinestra de navegació esquerra. Podeu modificar la configuració de l'entorn, altres administradors de l'entorn, àrees de treball i [connexions amb les estadístiques del públic](configure-connections.md). Seleccioneu pestanyes per desplaçar-vos entre diferents àrees del centre d'administració.

:::image type="content" source="media/New-environment.png" alt-text="Centre d'administració de l'entorn.":::

### <a name="create-an-environment"></a>Creació d'un entorn

1. Al selector d'àrees de treball, seleccioneu **+Crea**.

1. A l'experiència guiada, obriu el menú desplegable **Entorn** i seleccioneu **Crea un entorn nou**. 

1. Proporcioneu un **Nom d'entorn**.

   :::image type="content" source="media/create-environment.png" alt-text="Pas de l'experiència guiada per especificar els detalls de l'entorn.":::

1. Trieu la **Regió** i seleccioneu **Següent**. 

1. Proporcioneu un Nom d'àrea de treball i trieu quin tipus d'àrea de treball voleu crear. 

1.  Opcionalment, afegiu membres i copieu els fragment de codi per completar el procés de creació.

### <a name="rename-an-environment"></a>Canviar el nom d'un entorn

1. Aneu a **Administrador** > **Entorn** i seleccioneu **Configuració**.

1. Actualitzeu el **Nom de l'entorn** i seleccioneu **Desa** per aplicar els canvis.

### <a name="manage-environment-members"></a>Administra els membres de l'entorn

1. Aneu a **Administrador** > **Entorn** i seleccioneu **Membres**.

1. Seleccioneu **Afegeix membres** per actualitzar els membres i [assignar funcions](user-roles.md). Actualment, només està disponible **Administrador de l'entorn**.

1. Si configureu una [connexió amb les estadístiques del públic](configure-connections.md), podeu seleccionar **Permet l'accés a les dades de perfil** per permetre que el membre vegi informes basats en [perfils d'usuari](profile-reports.md).

1. Seleccioneu **Afegeix membres** per afegir-los a l'entorn.

### <a name="delete-an-environment"></a>Suprimir un entorn

Els administradors d'entorn poden suprimir entorns. Per poder suprimir un entorn, heu de suprimir totes les àrees de treball que tingui.

1. Aneu a **Administrador** > **Entorn** i seleccioneu **Configuració**.

1. Seleccioneu **Suprimeix l'entorn**. 

1. Al diàleg **Supressió de l'àrea de treball**, introduïu **CONFIRMA LA SUPRESSIÓ**. 

1. Seleccioneu **Suprimeix** per suprimir l'entorn permanentment.

## <a name="manage-connections"></a>Administrar les connexions

Establir connexions amb les estadístiques del públic us permet veure informes dels coneixements d'interacció basada en perfils de client unificats. 

Per obtenir-ne més informació, consulteu [Configurar connexions](configure-connections.md).

## <a name="manage-personal-data"></a>Administrar dades personals

Per protegir les dades personals dels clients, podeu suprimir o exportar dades identificables de l'usuari final.

Per obtenir més informació, vegeu [Suprimir i exportar dades d'incidències que contenen informació personal](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
