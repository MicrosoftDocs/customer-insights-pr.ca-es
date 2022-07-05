---
title: Connecta't a una Power Query font de dades (conté vídeo)
description: Ingereix les dades a través d'un Power Query connector (conté vídeo).
ms.date: 06/13/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6736b253e3a7e652f92f61bc44bfb31ca69be31a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082171"
---
# <a name="connect-to-a-power-query-data-source"></a>Connecta't a un Power Query font de dades

Power Query ofereix un ampli conjunt de connectors per ingerir dades. La majoria d'aquests connectors estan admesos pel Dynamics 365 Customer Insights.

L'addició de fonts de dades basades en Power Query connectors generalment segueix els passos descrits en aquesta secció. Tot i això, en funció del connector que utilitzeu, es requereix informació diferent. Per obtenir més informació, vegeu la documentació sobre connectors individuals a la referència del [Power Query connector](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crear una font de dades nova

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Seleccioneu **Microsoft Power Query**.

1. Proporcioneu un **nom** i una descripció opcional **per** al font de dades i seleccioneu **Endavant**.

1. Seleccioneu un dels [connectors disponibles](#available-power-query-data-sources). En aquest exemple, seleccionem el **connector Text/CSV**.

1. Introduïu els detalls necessaris a **Configuració de la connexió** per al connector seleccionat i seleccioneu **Següent** per veure una previsualització de les dades.

1. Seleccioneu **Transforma les dades**. En aquest pas, afegireu entitats a la vostra font de dades. Les entitats són conjunts de dades. Si teniu una base de dades que inclou diversos conjunts de dades, cada conjunt de dades és la seva pròpia entitat.

1. El **Power Query diàleg - Edita les consultes** us permet revisar i refinar les dades. Les entitats que els sistemes han identificat a la font de dades seleccionada apareixen a la subfinestra esquerra.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Quadre de diàleg Edita les consultes":::

1. També podeu transformar les dades. Seleccioneu una entitat per editar o transformar. Utilitzeu les opcions de la Power Query finestra per aplicar transformacions. Cada transformació s'enumera a **Passos aplicats**. Power Query proporciona nombroses opcions de transformació preconstrulades. Per a més informació, vegeu [Power Query Transformacions](/power-query/power-query-what-is-power-query#transformations).

   Us recomanem que utilitzeu les transformacions següents:

   - Si esteu ingerint dades d'un fitxer CSV, la primera fila sovint conté capçaleres. Aneu a **Transforma** i seleccioneu **Utilitza la primera fila com a capçaleres**.
   - Assegureu-vos que el tipus de dades s'ha establert correctament. Per exemple, per als camps de data, seleccioneu un tipus de data.

1. Per afegir entitats addicionals a la font de dades al diàleg Edita les **consultes**, aneu a **Inici** i seleccioneu **Obtén dades**. Repetiu els passos 6-10 fins que hàgiu afegit totes les entitats per a aquest font de dades.

1. Seleccioneu **Desa**. S'obre **la pàgina Orígens** de dades que mostra la nova font de dades a **l'estat** d'actualització.

### <a name="available-power-query-data-sources"></a>Orígens de dades disponibles Power Query

Consulteu la referència [Power Query del](/power-query/connectors/) connector per obtenir una llista dels connectors que podeu utilitzar per importar dades al Customer Insights.

Els connectors amb una marca de selecció a la **columna Del Customer Insights (Dataflows)** estan disponibles per crear fonts de dades noves basades en Power Query. Reviseu la documentació d'un connector específic per obtenir més informació sobre els seus requisits previs, [limitacions de](/power-query/power-query-online-limits) consulta i altres detalls.

## <a name="add-data-from-on-premises-data-sources"></a>Afegir dades des de fonts de dades locals

S'admet la ingestió de dades de local orígens de dades en funció dels Microsoft Power Platform fluxos de dades (PPDF). Podeu habilitar els fluxos de dades a Customer Insights [proporcionant l'ADREÇA URL Microsoft Dataverse de l'entorn](create-environment.md) en configurar l'entorn.

Els orígens de dades que es creen després d'associar un Dataverse entorn amb el Customer Insights utilitzen [Power Platform els fluxos de](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) dades per defecte. Els fluxos de dades admeten la connectivitat local mitjançant l'ús de la passarel·la de dades. Podeu suprimir i recrear els orígens de dades que existien abans que s'associés Dataverse un [entorn mitjançant local passarel·les](/data-integration/gateway/service-gateway-app) de dades.

Les passarel·les de dades d'un entorn existent del Power BI o el Power Apps seran visibles i es poden reutilitzar al Customer Insights. La pàgina de fonts de dades mostra enllaços per anar a l'entorn del Microsoft Power Platform on podeu visualitzar i configurar passarel·les de dades locals.

> [!IMPORTANT]
> Assegureu-vos que les passarel·les s'actualitzin a la versió més recent. Podeu instal·lar una actualització i reconfigurar una passarel·la des d'un indicador que es mostra directament a la pantalla de la passarel·la o [descarregar la versió més recent](https://powerapps.microsoft.com/downloads/). Si no utilitzeu la versió més recent de la passarel·la, l'actualització del flux de dades falla amb missatges d'error com **La paraula clau no és compatible: propietats de configuració. Nom del paràmetre: paraula clau**.

## <a name="edit-power-query-data-sources"></a>Edita els Power Query orígens de dades

> [!NOTE]
> Pot ser que no es puguin fer canvis en les fonts de dades que s'estan utilitzant actualment en un dels processos del'aplicació(*segmentació*, *coincidència* o *combinació*, per exemple).
>
> A la **pàgina Configuració**, podeu fer un seguiment del progrés de cadascun dels processos actius. Quan es completi un procés, podeu tornar a la pàgina **Fonts de dades** i fer els canvis que vulgueu.

1. Aneu a **Dades** > **Fonts de dades**.

1. Al costat de la font de dades que voleu actualitzar, seleccioneu **Edita**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Aplica els canvis i les transformacions al **Power Query diàleg - Edita les consultes** tal com es descriu a la [secció Crea una font de dades](#create-a-new-data-source) nova.

1. Seleccioneu **Desa** després Power Query de completar les modificacions per desar els canvis.
