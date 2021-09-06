---
title: Connexió a taules al Microsoft Dataverse
description: Importeu dades d'un llac de dades administrat del Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033068"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Connectar-se a dades d'un llac de dades administrat del Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Aquest article proporciona informació sobre com els usuaris del Dataverse poden connectar-se ràpidament a les seves entitats analítiques en un llac gestionat pel Dataverse. Heu de ser administrador de l'organització del Dataverse per continuar i veure la llista d'entitats disponibles al llac administrat.

## <a name="important-considerations"></a>Consideracions importants

Les dades emmagatzemades en un servei en línia, com ara el Azure Data Lake Storage, es poden emmagatzemar en una ubicació diferent d'on es processen o s'emmagatzemen les dades al Dynamics 365 Customer Insights. En importar o connectar-vos a les dades emmagatzemades en un servei en línia, accepteu que les dades es poden transferir i emmagatzemar-se amb el Dynamics 365 Customer Insights.  [Més informació al Centre de confiança de Microsoft](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Connectar-se a un llac administrat del Dataverse

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2. Seleccioneu **Afegeix una font de dades**.

3. Seleccioneu **Connecta't al llac administrat pel Microsoft Dataverse** i seleccioneu **Següent**.

4. Introduïu un **Nom** per a la font de dades i seleccioneu **Següent**. Directrius del nom: 
   - Comenceu per una lletra.
   - Utilitzeu només lletres i xifres. Els caràcters especials i els espais no estan permesos.
   - Utilitzeu entre 3 i 64 caràcters.

5. Proporcioneu l'**Adreça del servidor** de l'organització del Dataverse i seleccioneu **Inicia la sessió**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Pantalla al pas d'ingesta de dades on un usuari pot introduir l'adreça URL de l'entorn del Dataverse.":::

6. Seleccioneu les taules que voleu ingerir com a entitats a les conclusions del públic de la llista disponible.    

   > [!NOTE]
   > Si algunes taules ja estan seleccionades, pot ser que altres aplicacions del Dynamics 365 les estiguin utilitzant (com ara el Dynamics 365 Sales Insights o el Customer Service Insights). Aquesta selecció no es pot canviar. Aquestes taules estaran disponibles com a entitats un cop creada la font de dades.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Quadre de diàleg que mostra una llista d'entitats de l'entorn del Dataverse.":::

7. Deseu la selecció per començar a sincronitzar les taules seleccionades des del Dataverse. Trobareu la connexió afegida recentment a la pàgina **Fonts de dades**. Es posarà a la cua per actualitzar-se i mostrarà el recompte d'entitats com a 0 fins que se sincronitzin totes les taules seleccionades.

Només una font de dades d'un entorn podrà utilitzar simultàniament el mateix llac administrat del Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editar una font de dades d'un llac gestionat del Dataverse

Només editeu la selecció d'entitats després de crear la font de dades. Per exemple, si s'han afegit entitats addicionals al Dataverse i també voleu importar-les.    
Per connectar-vos a un altre llac de dades del Dataverse, [creeu una font de dades nova](#connect-to-a-dataverse-managed-lake).

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2. Al costat de la font de dades que voleu actualitzar, seleccioneu els punts suspensius.

3. Seleccioneu l'opció **Edita** de la llista.

4. Seleccioneu les entitats addicionals a la llista disponible d'entitats i seleccioneu **Desa**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]