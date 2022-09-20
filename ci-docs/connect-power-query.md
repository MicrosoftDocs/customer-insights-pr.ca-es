---
title: Connectar-se a un Power Query font de dades (conté vídeo)
description: Ingereix dades a través d'un Power Query connector (conté vídeo).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6a25e332bafab414c9def4e1e6b461139dd24ea6
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463253"
---
# <a name="connect-to-a-power-query-data-source"></a>Connectar-se a un Power Query font de dades

Power Query ofereix un ampli conjunt de connectors per ingerir dades. La majoria d'aquests connectors estan admesos pel Dynamics 365 Customer Insights.

L'addició de fonts de dades basades Power Query en connectors generalment segueix els passos descrits en aquesta secció. Tot i això, en funció del connector que utilitzeu, es requereix informació diferent. Per obtenir més informació, vegeu la documentació sobre connectors individuals a la referència del [Power Query connector](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crear una font de dades nova

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Seleccioneu **Microsoft Power Query**.

1. Proporcioneu un **nom** i una descripció opcionals **per** al font de dades i seleccioneu **Següent**.

1. Seleccioneu un dels [connectors disponibles](#available-power-query-data-sources). En aquest exemple, seleccionem el **connector Text/CSV**.

1. Introduïu els detalls necessaris a **Configuració de la connexió** per al connector seleccionat i seleccioneu **Següent** per veure una previsualització de les dades.

1. Seleccioneu **Transforma les dades**.

1. El **Power Query diàleg - Edita consultes** us permet revisar i refinar les dades. Les entitats que els sistemes han identificat a la font de dades seleccionada apareixen a la subfinestra esquerra.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Quadre de diàleg Edita les consultes":::

1. També podeu transformar les dades. Seleccioneu una entitat per editar o transformar. Utilitzeu les opcions de la Power Query finestra per aplicar transformacions. Cada transformació es mostra a Passos **aplicats**. Power Query proporciona nombroses [opcions de transformació](/power-query/power-query-what-is-power-query#transformations) predefinides.

   Us recomanem que utilitzeu les transformacions següents:

   - Si esteu ingerint dades d'un fitxer CSV, la primera fila sovint conté capçaleres. Aneu a **Transforma** i seleccioneu **Utilitza la primera fila com a capçaleres**.
   - Assegureu-vos que el tipus de dades s'ha establert correctament. Per exemple, per als camps de data, seleccioneu un tipus de data.

1. Per afegir entitats addicionals al font de dades al quadre de diàleg Edita **consultes**, aneu a **Inici** i seleccioneu **Obtén dades**. Repetiu els passos 5-10 fins que hàgiu afegit totes les entitats d'aquest font de dades. Si teniu una base de dades que inclou diversos conjunts de dades, cada conjunt de dades és la seva pròpia entitat.

1. Seleccioneu **Desa**. S'obre **la pàgina Fonts** de dades que mostra la nova font de dades en **estat de Refresc**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

La càrrega de les dades pot tardar temps. Després d'una actualització correcta, les dades ingerides es poden revisar des de la [**pàgina Entitats**](entities.md).

> [!CAUTION]
>
> - Un font de dades basat en crear Power Query un [flux de dades a Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). No canvieu el nom d'un flux de dades al centre d'administració Power Platform que s'utilitza al Customer Insights. El canvi de nom d'un flux de dades causa problemes amb les referències entre el font de dades del Customer Insights i el flux de Dataverse dades.
> - Les avaluacions simultànies per a Power Query les fonts de dades del Customer Insights tenen els mateixos [límits d'actualització que els fluxos de dades en PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Si una actualització de dades falla perquè ha arribat al límit d'avaluació, us recomanem que ajusteu la planificació d'actualització de cada flux de dades per assegurar-vos que les fonts de dades no es processin alhora.

### <a name="available-power-query-data-sources"></a>Fonts de dades disponibles Power Query

Vegeu la referència [Power Query del](/power-query/connectors/) connector per obtenir una llista de connectors que podeu utilitzar per importar dades al Customer Insights.

Els connectors amb una marca de verificació a la columna Estadístiques de **clients (Dataflows)** estan disponibles per crear fonts de dades noves basades en Power Query. Reviseu la documentació d'un connector específic per obtenir més informació sobre els requisits previs, [les limitacions de](/power-query/power-query-online-limits) consulta i altres detalls.

## <a name="add-data-from-on-premises-data-sources"></a>Afegir dades des de fonts de dades locals

La ingestió de dades de fonts de dades local s'admet en funció Microsoft Power Platform dels fluxos de dades (PPDF). Podeu habilitar els fluxos de dades al Customer Insights [proporcionant l'adreça URL Microsoft Dataverse de l'entorn](create-environment.md) en configurar l'entorn.

Les fonts de dades que es creen després d'associar un Dataverse entorn amb el Customer Insights utilitzen [Power Platform fluxos](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) de dades per defecte. Els fluxos de dades admeten la connectivitat local mitjançant l'ús de la passarel·la de dades. Podeu suprimir i tornar a crear fonts de dades que existien abans que s'associés Dataverse un [entorn mitjançant passarel·les de dades local](/data-integration/gateway/service-gateway-app).

Les passarel·les de dades d'un entorn existent o Power BI existent Power Apps seran visibles i les podeu reutilitzar al Customer Insights si la passarel·la de dades i l'entorn del Customer Insights es troben a la mateixa regió de l'Azure. La pàgina de fonts de dades mostra enllaços per anar a l'entorn del Microsoft Power Platform on podeu visualitzar i configurar passarel·les de dades locals.

> [!IMPORTANT]
> Assegureu-vos que les passarel·les estiguin actualitzades a la versió més recent. Podeu instal·lar una actualització i reconfigurar una passarel·la des d'un indicador que es mostra directament a la pantalla de la passarel·la o [descarregar la versió més recent](https://powerapps.microsoft.com/downloads/). Si no utilitzeu la versió més recent de la passarel·la, l'actualització del flux de dades falla amb missatges d'error com **ara La paraula clau no és compatible: propietats de configuració. Nom del paràmetre: paraula clau**.
>
> Els errors amb local passarel·les de dades del Customer Insights sovint són causats per problemes de configuració. Per obtenir més informació sobre la resolució de problemes de passarel·les de dades, vegeu [Resolució de problemes de la passarel·la de](/data-integration/gateway/service-gateway-tshoot) dades local.

## <a name="edit-power-query-data-sources"></a>Editar Power Query les fonts de dades

> [!NOTE]
> És possible que no sigui possible fer canvis a les fonts de dades que s'estan utilitzant actualment en un dels processos de l'aplicació (segmentació o unificació de dades, per exemple).
>
> A la **pàgina Configuració**, podeu fer un seguiment del progrés de cadascun dels processos actius. Quan es completi un procés, podeu tornar a la pàgina **Fonts de dades** i fer els canvis que vulgueu.

1. Aneu a **Dades** > **Fonts de dades**.

1. Al costat de la font de dades voleu actualitzar, seleccioneu **Edita**.

1. Apliqueu els canvis i les transformacions al quadre de **Power Query diàleg - Edita consultes** tal com es descriu a la [secció Crea un font de dades](#create-a-new-data-source) nou.

1. Seleccioneu **Desa** per aplicar els canvis i tornar a la **pàgina Fonts** de dades.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
