---
title: Administrar àrees de treball i entorns
description: Com crear, canviar el nom i suprimir àrees de treball i entorns.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 09cb3ddf0f8b4507b7eae6668ea3dad08cfcea29
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673777"
---
# <a name="manage-environments-and-workspaces"></a>Administrar entorns i àrees de treball

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Informació general

En aquest tema es tracta la manera d'administrar les àrees de treball i els entorns quan ja han estat creats. 

- Una *àrea de treball* és un espai on es poden emmagatzemar i administrar incidències i informes. És on podeu visualitzar l'activitat dels usuaris en temps real. Quan creeu una àrea de treball, seleccioneu el tipus de dades que voleu enviar a l'àrea de treball. Actualment, s'admeten les dades web i les aplicacions mòbils. Per obtenir més informació, vegeu [Crear una àrea de treball nova i afegir membres](create-workspace.md).

- Un *entorn* és una àrea on administreu les vostres àrees de treball i connexions. Per obtenir més informació, vegeu [Crear un entorn nou](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Administrar una àrea de treball existent

Podeu mantenir diverses àrees de treball simultàniament en un entorn. La vostra [funció](user-roles.md) determina com podeu treballar-hi. 

 - Heu de ser un administrador de l'entorn o un administrador de l'àrea de treball per administrar l'àrea de treball.
 - Com a administrador de l'àrea de treball, podeu canviar el nom de les àrees de treball existents o suprimir-les. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centre d'administració de l'àrea de treball.":::

### <a name="edit-a-workspace-name"></a>Edita un nom de l’àrea de treball

1. Aneu a **Administrador** > **Àrea de treball** i seleccioneu **Configuració**.

1. Introduïu un nom nou al quadre **Nom de l'àrea de treball**.

1. Seleccioneu **Desa** per aplicar els canvis.

### <a name="delete-a-workspace"></a>Suprimir una àrea de treball

Si suprimiu una àrea de treball, se suprimirà permanentment tot el contingut, les dades, la configuració i els permisos. Aquesta operació no es pot desfer.

1. Aneu a **Administrador** > **Àrea de treball** i seleccioneu **Configuració**.

1. Seleccioneu **Suprimeix l'àrea de treball**. 

1. Al quadre de diàleg **Suprimeix l'àrea de treball**, introduïu **CONFIRMA LA SUPRESSIÓ** tot en majúscules. 

1. Seleccioneu **Suprimeix** per suprimir de manera permanent l'àrea de treball.

### <a name="manage-workspace-members"></a>Administra els membres de l'àrea de treball

1. Aneu a **Administrador** > **Àrea de treball** i seleccioneu **Membres**.

1. Seleccioneu **Afegeix membres** per donar accés i [assignar funcions](user-roles.md). Actualment, només està disponible **Administrador de l'àrea de treball**.

1. Seleccioneu **Afegeix membres** per afegir-los a l'àrea de treball.

## <a name="manage-an-existing-environment"></a>Administrar un entorn existent

Com a administrador de l'entorn, podeu accedir a un entorn des de la subfinestra de navegació esquerra. Podeu configurar els paràmetres de l'entorn, altres administradors de l'entorn i àrees de treball. Seleccioneu pestanyes per desplaçar-vos entre diferents àrees del centre d'administració.

:::image type="content" source="media/environment-edit.png" alt-text="Centre d'administració de l'entorn.":::

### <a name="edit-an-environment-name"></a>Editar un nom d'entorn

1. Aneu a **Administrador** > **Entorn** i seleccioneu **Configuració**.

1. Actualitzeu el **Nom de l'entorn** i seleccioneu **Desa** per aplicar els canvis.

### <a name="delete-an-environment"></a>Suprimir un entorn

Els administradors d'entorn poden suprimir entorns. Per poder suprimir un entorn, heu de suprimir totes les àrees de treball que tingui.

1. Aneu a **Administrador** > **Entorn** i seleccioneu **Configuració**.

1. Seleccioneu **Suprimeix l'entorn**. 

1. Al quadre de diàleg **Suprimeix l'àrea de treball**, introduïu **CONFIRMA LA SUPRESSIÓ** tot en majúscules. 

1. Seleccioneu **Suprimeix** per suprimir l'entorn permanentment.

### <a name="manage-environment-members"></a>Administra els membres de l'entorn

1. Aneu a **Administrador** > **Entorn** i seleccioneu **Membres**.

1. Seleccioneu **Afegeix membres** per actualitzar els membres i [assignar funcions](user-roles.md). Actualment, només està disponible **Administrador de l'entorn**.

1. Seleccioneu **Afegeix membres** per afegir-los a l'entorn.

## <a name="manage-connections"></a>Administrar les connexions

Establir connexions amb les estadístiques del públic us permet veure informes dels coneixements d'interacció basada en perfils de client unificats. 

Per obtenir-ne més informació, consulteu [Creació d'un enllaç entre les conclusions del públic i les conclusions d'interacció](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Administrar dades personals

Per protegir les dades personals dels clients, podeu suprimir o exportar dades identificables de l'usuari final.

Per obtenir més informació, vegeu [Suprimir i exportar dades d'incidències que contenen informació personal](../dsr-rights-requests.md#deleting-and-exporting-event-data-containing-end-user-identifiable-information).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
