---
title: Connectar amb entitats del llac administrat del Common Data Service
description: Importeu dades d'un llac de dades administrat del Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643386"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Connectar-se a dades d'un llac de dades administrat del Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Aquest article proporciona informació sobre com els clients del Dynamics 365 existents es poden connectar ràpidament a les seves entitats analítiques en el llac administrat del Common Data Service. Heu de ser administrador de l'organització del Common Data Service per continuar i veure la llista d'entitats disponibles al llac administrat.

## <a name="important-considerations"></a>Consideracions importants

Les dades emmagatzemades en un servei en línia, com ara el Azure Data Lake Storage, es poden emmagatzemar en una ubicació diferent d'on es processen o s'emmagatzemen les dades al Dynamics 365 Customer Insights. En importar o connectar-vos a les dades emmagatzemades en un servei en línia, accepteu que les dades es poden transferir i emmagatzemar-se amb el Dynamics 365 Customer Insights.  [Més informació al Centre de confiança de Microsoft](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Connectar-se a un llac administrat del Common Data Service

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2. Seleccioneu **Afegeix una font de dades**.

3. Seleccioneu **Connecta't al Common Data Service** i seleccioneu **Següent**.

4. Introduïu un **Nom** per a la font de dades i seleccioneu **Següent**.

5. Proporcioneu l'**adreça del servidor** de l'organització del Common Data Service i, a continuació, seleccioneu **inicia la sessió**.

   > [!div class="mx-imgBorder"]
   > ![Quadre de diàleg per introduir l'adreça del servidor del Common Data Service](media/enter-CDS-org-details.png)

6. Seleccioneu les entitats que voleu ingerir a la llista disponible.    

   > [!NOTE]
   > Si algunes entitats ja estan seleccionades, pot ser que s'utilitzin en altres aplicacions del Dynamics 365 (com ara el Dynamics 365 Sales Insights o el Customer Service Insights). Aquesta selecció no es pot canviar. Aquestes entitats estaran disponibles quan es creï la font de dades.

   > [!div class="mx-imgBorder"]
   > ![Quadre de diàleg que mostra una llista d'entitats de l'organització del Common Data Service](media/select-analytical-entities.png)

7. Deseu la selecció per iniciar la sincronització de les entitats seleccionades al llac gestionat del Common Data Service. Trobareu la connexió afegida recentment a la pàgina **Fonts de dades**. Es posarà en cua per actualitzar-se i mostrarà el recompte d'entitats com a 0 fins que totes les entitats se sincronitzin.

Només una font de dades d'un entorn podrà utilitzar simultàniament el mateix llac administrat del Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Editar una font de dades d'un llac gestionat del Common Data Service

Només editeu la selecció d'entitats després de crear la font de dades. Per exemple, si s'han afegit entitats addicionals al Common Data Service i també voleu importar-les.    
Per connectar-vos a un Common Data Service diferent, [creeu una nova font de dades](#connect-to-a-common-data-service-managed-lake).

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2. Al costat de la font de dades que voleu actualitzar, seleccioneu els punts suspensius.

3. Seleccioneu l'opció **Edita** de la llista.

4. Seleccioneu les entitats addicionals a la llista disponible d'entitats i seleccioneu **Desa**.
