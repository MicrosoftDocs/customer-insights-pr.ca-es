---
title: Connectar-se a dades d'un llac de dades administrat del Microsoft Dataverse
description: Importeu dades d'un llac de dades administrat del Microsoft Dataverse.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206941"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Connectar-se a dades d'un llac de dades administrat del Microsoft Dataverse

Microsoft Dataverse els usuaris es poden connectar ràpidament a entitats analítiques en un Microsoft Dataverse llac gestionat. Només una font de dades d'un entorn podrà utilitzar simultàniament el mateix llac administrat del Dataverse.

> [!NOTE]
> Heu de ser administrador de l'organització Dataverse per continuar i veure la llista d'entitats disponibles al llac gestionat.

## <a name="prerequisites"></a>Requisits previs

- Les dades emmagatzemades en un servei en línia, com ara el Azure Data Lake Storage, es poden emmagatzemar en una ubicació diferent d'on es processen o s'emmagatzemen les dades al Dynamics 365 Customer Insights.En importar o connectar-vos a les dades emmagatzemades als serveis en línia, accepteu que les dades es puguin transferir i emmagatzemar amb Dynamics 365 Customer Insights. [Obteniu més informació al Centre](https://www.microsoft.com/trust-center) de confiança de Microsoft.

- Només Dataverse són visibles les entitats amb [el seguiment de](/power-platform/admin/enable-change-tracking-control-data-synchronization) canvis activat. Aquestes entitats es poden exportar al llac de Dataverse dades gestionat i utilitzar-les al Customer Insights. Les taules estàndard tenen el seguiment de Dataverse canvis activat de manera predeterminada. Heu d'activar el seguiment de canvis per a les taules personalitzades. Per comprovar si una Dataverse taula està habilitada per al seguiment de canvis, aneu a [Power Apps](https://make.powerapps.com) > **Taules** > **de dades**. Troba la taula del teu interès i selecciona-la. Aneu a **Opcions avançades** > **de configuració** i reviseu la configuració Seguiment dels **canvis**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Connectar-se a un llac administrat del Dataverse

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Seleccioneu **Microsoft Dataverse**.

1. Introduïu un **nom** per al font de dades i una descripció opcional.**·**

1. Proporcioneu l'**Adreça del servidor** de l'organització del Dataverse i seleccioneu **Inicia la sessió**.

1. Seleccioneu les taules que voleu ingerir com a entitats al Customer Insights de la llista disponible.

   > [!NOTE]
   > Si algunes taules ja estan seleccionades, pot ser que altres aplicacions del Dynamics 365 les estiguin utilitzant (com ara el Dynamics 365 Sales Insights o el Customer Service Insights). Aquesta selecció no es pot canviar. Aquestes taules estaran disponibles com a entitats un cop creada la font de dades.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Quadre de diàleg que mostra una llista d'entitats de l'entorn del Dataverse.":::

1. Deseu la selecció per començar a sincronitzar les taules seleccionades des del Dataverse. Trobareu la connexió afegida recentment a la pàgina **Fonts de dades**. Es posarà a la cua per actualitzar-se i mostrarà el recompte d'entitats com a 0 fins que se sincronitzin totes les taules seleccionades.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

La càrrega de les dades pot tardar temps. Després d'una actualització correcta, les dades ingerides es poden revisar des de la [**pàgina Entitats**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editar una font de dades d'un llac gestionat del Dataverse

Només editeu la selecció d'entitats després de crear la font de dades. Per exemple, si s'han afegit entitats addicionals al Dataverse i també voleu importar-les.
Per connectar-vos a un altre llac de dades del Dataverse, [creeu una font de dades nova](#connect-to-a-dataverse-managed-lake).

1. Aneu a **Dades** > **Fonts de dades**.

1. Al costat de la font de dades voleu actualitzar, seleccioneu **Edita**.

1. Seleccioneu entitats addicionals de la llista d'entitats disponibles.

1. Feu clic **a Desa** per aplicar els canvis i tornar a la **pàgina Fonts** de dades.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
