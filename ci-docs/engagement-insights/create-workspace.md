---
title: Crea una àrea de treball nova
description: Finalitat d'una àrea de treball i com crear-ne una de nova.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 816f948331a06794c15000eb779f93cc7fdda202
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645298"
---
# <a name="create-a-new-workspace-and-add-members"></a>Crear una àrea de treball nova i afegir-hi membres

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Una àrea de treball és com podeu visualitzar l'activitat dels usuaris en temps real per comprendre millor el públic. És on emmagatzemeu i administreu les incidències i els informes.

Quan creeu una àrea de treball, seleccioneu el tipus de dades en què us voleu centrar. Podeu afegir altres usuaris o membres a una àrea de treball existent en qualsevol moment. 

## <a name="create-a-new-workspace"></a>Crea una àrea de treball nova

El procés de creació d'una àrea de treball inclou la configuració de l'*entorn* per organitzar l'àrea de treball. Un entorn és un espai que pot contenir una o diverses àrees de treball. Podeu utilitzar un entorn per administrar les àrees de treball i les connexions amb la capacitat dels coneixements d'interacció del Customer Insights.

1. Seleccioneu **Crea** al commutador de l'àrea de treball.

   :::image type="content" source="media/new-workspace.png" alt-text="Pàgina del Customer Insights amb una crida a la subfinestra de navegació i a la descripció.":::

1. A la subfinestra **Àrea de treball**, introduïu un **Nom d'àrea de treball**.

   :::image type="content" source="media/workspace-name.png" alt-text="Escriviu el nom de l'àrea de treball.":::

1. Trieu el tipus de plataforma (web o mòbil) que voleu mesurar.

1. Seleccioneu **Mostra la configuració avançada** per habilitar o inhabilitar aquesta configuració opcional:

   - Activeu o desactiveu **De desconegut a conegut** en "habilitat" per associar incidències web amb usuaris que s'han autenticat anteriorment. Per obtenir més informació, vegeu [Reconèixer incidències web de visitants autenticats prèviament](unknown-to-known.md)
   - Commuteu **Filtra el trànsit del bot** "habilitat" per eliminar el trànsit web dels bots per a aquesta àrea de treball. 

1. Quan hagueu acabat, seleccioneu **Completat**. 

1. Instal·leu el fragment de codi per iniciar la recepció de dades i, a continuació, seleccioneu **Acabament** per crear l'àrea de treball. Per obtenir més informació, consulteu [Informació general dels recursos per a desenvolupadors](developer-resources.md).

> [!NOTE]
> Ara podeu afegir membres i assignar el seu nivell de permís des de la llista **Funcions**. Per obtenir més informació, vegeu [Funcions i permisos](user-roles.md). 

Per obtenir més informació, vegeu [Administrar entorns i àrees de treball](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
