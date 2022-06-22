---
title: Connexió a taules al Microsoft Dataverse
description: Importeu dades d'un llac de dades administrat del Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: c470956b0453ac2558ed85acdeebba120a0ca55d
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011691"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Connectar-se a dades d'un llac de dades administrat del Microsoft Dataverse

Microsoft Dataverse els usuaris poden connectar-se ràpidament a entitats analítiques en un Microsoft Dataverse llac gestionat.

> [!NOTE]
> Heu de ser administrador de l'organització Dataverse per continuar i visualitzar la llista d'entitats disponibles al llac gestionat.

## <a name="important-considerations"></a>Consideracions importants

1. Les dades emmagatzemades en un servei en línia, com ara el Azure Data Lake Storage, es poden emmagatzemar en una ubicació diferent d'on es processen o s'emmagatzemen les dades al Dynamics 365 Customer Insights.En importar o connectar-vos a les dades emmagatzemades en serveis en línia, accepteu que les dades es puguin transferir i emmagatzemar amb Dynamics 365 Customer Insights. [Més informació al Microsoft Trust Center](https://www.microsoft.com/trust-center).
2. Només Dataverse són visibles les entitats amb [seguiment de](/power-platform/admin/enable-change-tracking-control-data-synchronization) canvis habilitat. Aquestes entitats es poden exportar al Dataverse llac de dades administrades i utilitzar-les al Customer Insights. Les taules fora de caixa Dataverse tenen el seguiment de canvis habilitat per defecte. Heu d'activar el seguiment de canvis per a taules personalitzades. Per comprovar si hi ha una Dataverse taula habilitada per al seguiment de canvis, aneu a [Power Apps](https://make.powerapps.com) > **Taules de dades** > **·**. Troba la taula del teu interès i selecciona-la. Aneu a **Opcions** > **avançades de** Configuració i reviseu la configuració De seguiment dels **canvis**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Connectar-se a un llac administrat del Dataverse

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Seleccioneu **Microsoft Dataverse**.

1. Introduïu un **nom** per a la font de dades i una descripció **opcional**.

1. Proporcioneu l'**Adreça del servidor** de l'organització del Dataverse i seleccioneu **Inicia la sessió**.

1. Seleccioneu les taules que voleu ingerir com a entitats al Customer Insights de la llista disponible.

   > [!NOTE]
   > Si algunes taules ja estan seleccionades, pot ser que altres aplicacions del Dynamics 365 les estiguin utilitzant (com ara el Dynamics 365 Sales Insights o el Customer Service Insights). Aquesta selecció no es pot canviar. Aquestes taules estaran disponibles com a entitats un cop creada la font de dades.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Quadre de diàleg que mostra una llista d'entitats de l'entorn del Dataverse.":::

1. Deseu la selecció per començar a sincronitzar les taules seleccionades des del Dataverse. Trobareu la connexió afegida recentment a la pàgina **Fonts de dades**. Es posarà a la cua per actualitzar-se i mostrarà el recompte d'entitats com a 0 fins que se sincronitzin totes les taules seleccionades.

Només una font de dades d'un entorn podrà utilitzar simultàniament el mateix llac administrat del Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editar una font de dades d'un llac gestionat del Dataverse

Només editeu la selecció d'entitats després de crear la font de dades. Per exemple, si s'han afegit entitats addicionals al Dataverse i també voleu importar-les.
Per connectar-vos a un altre llac de dades del Dataverse, [creeu una font de dades nova](#connect-to-a-dataverse-managed-lake).

1. Aneu a **Dades** > **Fonts de dades**.

1. Al costat de la font de dades que voleu actualitzar, seleccioneu **Edita**.

1. Seleccioneu les entitats addicionals a la llista disponible d'entitats i seleccioneu **Desa**.
