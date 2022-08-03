---
title: Connector del Power BI (visualització prèvia)
description: Apreneu com utilitzar el connector del Dynamics 365 Customer Insights al Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196658"
---
# <a name="power-bi-connector-preview"></a>Connector del Power BI (visualització prèvia)

Creeu visualitzacions per a les vostres dades amb l'escriptori Microsoft Power BI. Genereu informació addicional i creeu informes amb les dades del client unificades.

## <a name="prerequisites"></a>Requisits previs

- Perfils de clients unificats.
- L'última versió del [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) està instal·lada a l'ordinador. [Més informació sobre el Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurar el connector per al Power BI

1. Al Power BI Desktop, seleccioneu **Fitxer** > **Obtén dades**.

1. Seleccioneu **Mostra'n més** i cerqueu **Dynamics 365 Customer Insights**

1. Seleccioneu **Connecta**.

1. **Inicieu la sessió** amb el mateix compte d'organització que utilitzeu per al Customer Insights i seleccioneu **Connecta**.
   > [!NOTE]
   > El compte que indiqueu en aquest pas s'utilitza per obtenir dades del Customer Insights i no ha de ser el mateix amb què heu iniciat la sessió al Power BI. Per restablir el compte que s'utilitza per a l'obtenció de les dades, obriu el Power BI i aneu a **Fitxer** > **Opcions** > **Configuració** > **Configuració de fonts de dades**. A la llista de fonts de dades, seleccioneu **Inici de sessió del Dynamics 365 Customer Insights** i seleccioneu **Esborra els permisos**.  

1. Al quadre de **diàleg Navegador**, visualitzeu la llista de tots els entorns als quals teniu accés. Expandiu un entorn i obriu qualsevol de les carpetes (entitats, mesures, segments i enriquiments). Per exemple, obriu la carpeta **Entitats** per veure totes les entitats que podeu importar.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Navegador del connector del Power BI.":::

1. Activeu les caselles de selecció que hi ha al costat de les entitats que voleu incloure i **Carrega**. Podeu seleccionar diverses entitats de diversos entorns.

   Es mostra un quadre de diàleg de càrrega mentre es carreguen les entitats. Un cop carregades totes les entitats seleccionades, utilitzeu les capacitats de Power BI visualitzar les dades.

## <a name="large-data-sets"></a>Conjunts de dades grans

El connector del Customer Insights per al Power BI està dissenyat per funcionar amb els conjunts de dades que contenen fins a 1 milió de perfils de clients. La importació de conjunts de dades més grans pot funcionar, però triga molt de temps i podria esgotar el temps a causa de Power BI les limitacions. Per obtenir més informació, vegeu [Power BI: recomanacions per a conjunts de dades grans](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Treballar amb un subconjunt de dades

Considereu la possibilitat de treballar amb un subconjunt de les dades. Per exemple, creeu [segments](segments.md) en lloc d'exportar tots els registres de client a Power BI.

## <a name="troubleshooting"></a>Solució de problemes

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>L'entorn del Customer Insights no es mostra al Power BI

Els entorns que tinguin més d'una [relació](relationships.md) definida entre dues entitats idèntiques al Customer Insights no estaran disponibles al Power BI connector.

Identificar i eliminar les relacions duplicades.

1. Aneu a **Relacions** > **de dades** sobre l'entorn en Power BI què us falten.
1. Identificar les relacions duplicades:
   - Comproveu si hi ha més d'una relació definida entre les mateixes dues entitats.
   - Comproveu si s'ha creat una relació entre dues entitats que estan incloses al procés d'unificació. Hi ha una relació implícita que es defineix entre totes les entitats incloses al procés d'unificació.
1. Suprimiu les relacions duplicades identificades.

Després de la supressió de les relacions duplicades, proveu de tornar a configurar el connector del Power BI.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Errors als camps de data en carregar entitats al Power BI Desktop

Quan carregueu entitats que contenen camps amb un format de data, com ara MM/DD/AAAA, és possible que trobeu errors a causa de formats de configuració regional que no coincideixen. Aquest desajustament es produeix quan el Power BI Desktop fitxer està definit en una altra configuració regional que no sigui Anglès (Estats Units), perquè els camps de data del Customer Insights es desen en format dels EUA.

El fitxer del Power BI Desktop té una configuració regional única que s'aplica en recuperar dades. Per corregir els errors de data, [definiu la configuració regional del fitxer . Fitxer BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) a l'anglès (Estats Units).

[!INCLUDE [footer-include](includes/footer-banner.md)]
