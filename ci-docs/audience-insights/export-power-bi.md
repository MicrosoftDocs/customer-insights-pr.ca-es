---
title: Connector del Power BI
description: Apreneu com utilitzar el connector del Dynamics 365 Customer Insights al Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596027"
---
# <a name="connector-for-power-bi-preview"></a>Connector del Power BI (versió preliminar)

Creeu visualitzacions per a les dades amb el Power BI Desktop. Genereu informació addicional i creeu informes amb les dades del client unificades.

## <a name="prerequisites"></a>Requisits previs

- Teniu perfils de client unificats.
- L'última versió del [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) està instal·lada a l'ordinador. [Més informació sobre el Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurar el connector per al Power BI

1. Al Power BI Desktop, seleccioneu **Fitxer** > **Obtén dades**.

1. Seleccioneu **Mostra'n més** i cerqueu **Dynamics 365 Customer Insights**

1. Seleccioneu **Connecta**.

1. **Inicieu la sessió** amb el mateix compte d'organització que utilitzeu per al Customer Insights i seleccioneu **Connecta**.
   > [!NOTE]
   > El compte que indiqueu en aquest pas s'utilitza per obtenir dades del Customer Insights i no ha de ser el mateix amb què heu iniciat la sessió al Power BI. Per restablir el compte que s'utilitza per a l'obtenció de les dades, obriu el Power BI i aneu a **Fitxer** > **Opcions** > **Configuració** > **Configuració de fonts de dades**. A la llista de fonts de dades, seleccioneu **Inici de sessió del Dynamics 365 Customer Insights** i seleccioneu **Esborra els permisos**.  

1. Al quadre de diàleg **Navegador**. podeu veure la llista de tots els entorns als quals teniu accés. Expandiu un entorn i obriu qualsevol de les carpetes (entitats, mesures, segments i enriquiments). Per exemple, obriu la carpeta **Entitats** per veure totes les entitats que podeu importar.

   ![Navegador del connector del Power BI](media/power-bi-navigator.png "Navegador del connector del Power BI")

1. Activeu les caselles de selecció que hi ha al costat de les entitats que voleu incloure i **Carrega**. Podeu seleccionar diverses entitats de diversos entorns.

1. Veureu un quadre de diàleg de càrrega mentre les entitats es carreguen. Un cop carregades totes les entitats seleccionades, podeu utilitzar les capacitats del Power BI per visualitzar les dades.

## <a name="large-data-sets"></a>Conjunts de dades grans

El connector del Customer Insights per al Power BI està dissenyat per funcionar amb els conjunts de dades que contenen fins a 1 milió de perfils de clients. La importació de conjunts de dades més grans pot funcionar, però tarda molta estona. A més, el procés podria esgotar el temps d'espera a causa de les limitacions del Power BI. Per obtenir més informació, vegeu [Power BI: recomanacions per a conjunts de dades grans](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Treballar amb un subconjunt de dades

Considereu la possibilitat de treballar amb un subconjunt de les dades. Per exemple, podeu crear [segments](segments.md) en comptes d'exportar tots els registres de client al Power BI.

## <a name="troubleshooting"></a>Solució de problemes

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>L'entorn del Customer Insights no es mostra al Power BI

Els entorns que tenen més d'una [relació](relationships.md) definida entre dues entitats idèntiques a les conclusions del públic no estaran disponible al connector del Power BI.

Podeu identificar i suprimir les relacions duplicades.

1. A les conclusions del públic, aneu a **Dades** > **Relacions** a l'entorn que falta al Power BI.
2. Identificar les relacions duplicades:
   - Comproveu si hi ha més d'una relació definida entre les mateixes dues entitats.
   - Comproveu si s'ha creat una relació entre dues entitats que estan incloses al procés d'unificació. Hi ha una relació implícita que es defineix entre totes les entitats incloses al procés d'unificació.
3. Suprimiu les relacions duplicades identificades.

Després de la supressió de les relacions duplicades, proveu de tornar a configurar el connector del Power BI. L'entorn hauria d'estar disponible ara.

[!INCLUDE[footer-include](../includes/footer-banner.md)]