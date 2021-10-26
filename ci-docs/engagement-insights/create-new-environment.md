---
title: Creació d'un entorn nou
description: Finalitat d'un entorn i com crear-ne un de nou.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648105"
---
# <a name="create-a-new-environment"></a>Creació d'un entorn nou 

## <a name="overview"></a>Informació general

Un entorn és una àrea on administreu les vostres àrees de treball i connexions. La manera d'utilitzar els entorns depèn de la vostra organització i del cas d'ús. Per exemple, podeu crear:

- Un entorn únic.
- Entorns diferents per a provar i produir.
- Entorns separats per a equips o departaments específics de la vostra organització que contenen incidències rellevants per a cada públic.
- Entorns separats per a diferents branques globals de la vostra empresa.
- Connexions a la capacitat d'estadístiques del públic del Customer Insights.

## <a name="create-a-new-environment"></a>Creació d'un entorn nou

1. A la dreta del bàner principal, seleccioneu el selector d'entorn i després feu clic a  **+Crea**.

   :::image type="content" source="media/environment-picker.png" alt-text="Seleccioneu el selector d'entorn.":::

1. A la subfinestra **Instal·lació**, escriviu un **Nom d'entorn**.

1. Trieu el **Tipus** de compte, en funció del tipus de pla.

1. Trieu la **Regió** i seleccioneu **Següent**. 

1. Escriviu un **Nom de l'àrea de treball**, que us permet recopilar dades per a llocs web o aplicacions específics. Per obtenir més informació, vegeu [Crear una àrea de treball](create-workspace.md).

1. Trieu el **Tipus d'àrea de treball** (web o mòbil) que voleu crear. 

1. Seleccioneu **Mostra la configuració avançada** per habilitar o inhabilitar aquesta configuració opcional:

   - Activeu o desactiveu **De desconegut a conegut** en "habilitat" per associar incidències web amb usuaris que s'han autenticat anteriorment. Per obtenir més informació, vegeu [Reconèixer incidències web de visitants autenticats prèviament](unknown-to-known.md)
   - Commuteu **Filtra el trànsit del bot** "habilitat" per eliminar el trànsit web dels bots per a aquesta àrea de treball. 

1. Quan hagueu acabat, seleccioneu **Completat**. 

1. Instal·leu el fragment de codi per iniciar la recepció de dades i, a continuació, seleccioneu **Acabament** per crear l'àrea de treball. Per obtenir més informació, consulteu [Informació general dels recursos per a desenvolupadors](developer-resources.md).

> [!NOTE]
> Ara podeu afegir membres i assignar el seu nivell de permís des de la llista **Funcions**. Per obtenir més informació, vegeu [Funcions i permisos](user-roles.md). 

Per obtenir més informació, vegeu [Administrar entorns i àrees de treball](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Treballar amb el nou entorn

- [Creeu una àrea de treball](../engagement-insights/create-workspace.md) i afegiu-hi membres.
- [Afegiu codi al lloc web](../engagement-insights/instrument-website.md) o a l'[aplicació mòbil](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Visualitzeu un [informe en temps real](../engagement-insights/view-reports.md) o creeu [informes personalitzats](../engagement-insights/custom-reports.md).
- [Creeu incidències refinades](../engagement-insights/refined-events.md) per a l'exportació.
- [Exporteu les dades](../engagement-insights/export-events.md) al Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
