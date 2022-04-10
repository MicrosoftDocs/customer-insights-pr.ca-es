---
title: Connector del Power BI
description: Apreneu com utilitzar el connector del Dynamics 365 Customer Insights al Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: dccc069a355725bae09c1fece9292b9aee374e6d
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225503"
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

   ![Navegador del connector del Power BI.](media/power-bi-navigator.png "Navegador del connector del Power BI")

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

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Errors als camps de data en carregar entitats al Power BI Desktop

En carregar entitats que contenen camps amb un format de data com MM/DD/YYYY, podeu trobar errors a causa de formats de configuració regional no coincidents. Aquest desajust es produeix quan el fitxer del Power BI Desktop està definit en una configuració regional que no és l'anglès (Estats Units), perquè els camps de data de les conclusions del públic es desen en format estatunidenc.

El fitxer del Power BI Desktop té una configuració regional única que s'aplica en recuperar dades. Per fer que aquests camps de data s'interpretin correctament, definiu la configuració regional del fitxer .BPI a Anglès (Estats Units). [Obteniu informació sobre com podeu canviar la configuració regional d'un fitxer del Power BI Desktop](/power-bi/fundamentals/supported-languages-countries-regions.md#choose-the-locale-for-importing-data-into-power-bi-desktop).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
