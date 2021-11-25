---
title: Ingerir dades a través d'un connector del Power Query
description: Connectors per a fonts de dades basades en el Power Query.
ms.date: 11/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 5d54d33c235e646644e8874e5b0c28898dcff11a
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732206"
---
# <a name="connect-to-a-power-query-data-source"></a>Connectar-se a una font de dades del Power Query

El Power Query ofereix un ampli conjunt de connectors per ingerir dades. La majoria d'aquests connectors són compatibles amb Dynamics 365 Customer Insights. Afegir fonts de dades basades en connectors del Power Query generalment implica els passos indicats a la secció següent. Tot i això, en funció del connector que utilitzeu, es requereix informació diferent. Per a més informació, vegeu la documentació sobre connectors individuals a la [Referència de connectors del Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crear una font de dades nova

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Trieu el mètode **Importa dades** i seleccioneu **Següent**.

1. Proporcioneu un **Nom** per a la font de dades i seleccioneu **Següent** per crear la font de dades. Directrius del nom: 
   - Comenceu per una lletra.
   - Utilitzeu només lletres i xifres. Els caràcters especials i els espais no estan permesos.
   - Utilitzeu entre 3 i 64 caràcters.

1. Seleccioneu un dels [connectors disponibles](#available-power-query-data-sources). Per aquest exemple, seleccionem el connector **Text/CSV**.

1. Introduïu els detalls necessaris a **Configuració de la connexió** per al connector seleccionat i seleccioneu **Següent** per veure una previsualització de les dades.

1. Seleccioneu **Transforma les dades**. En aquest pas, afegireu entitats a la vostra font de dades. Les entitats són conjunts de dades. Si teniu una base de dades que inclou diversos conjunts de dades, cada conjunt de dades és la seva pròpia entitat.

1. El diàleg **Power Query: edita les consultes** permet revisar i refinar les dades. Les entitats que els sistemes han identificat a la font de dades seleccionada apareixen a la subfinestra esquerra.

   > [!div class="mx-imgBorder"]
   > ![Quadre de diàleg Edita les consultes.](media/data-manager-configure-edit-queries.png "Quadre de diàleg Edita les consultes")

1. També podeu transformar les dades. Seleccioneu una entitat per editar o transformar. Utilitzeu les opcions de la finestra del Power Query per aplicar transformacions. Cada transformació apareix a **Passos aplicats**. El Power Query proporciona nombroses opcions de transformació incorporades. Per a més informació, vegeu [Transformacions del Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Per afegir entitats addicionals a la font de dades, seleccioneu **Obtén les dades** al quadre de diàleg **Edita les consultes**.

   Aquestes transformacions són molt recomanables:

   - Si esteu ingerint dades d'un fitxer CSV, la primera fila sovint conté capçaleres. Aneu a **Transforma la taula** i seleccioneu **Utilitza les capçaleres com a primera fila**.
   - Assegureu-vos que el tipus de dades s'ha establert correctament.

1. Seleccioneu **Desa** a la part inferior de la finestra de Power Query per desar les transformacions. Després de desar-la, trobareu la vostra font de dades a **Dades** > **Fonts de dades**.

1. A la pàgina **Fonts de dades**, veureu que la nova font de dades té l'estat **S'està actualitzant**.

## <a name="available-power-query-data-sources"></a>Fonts de dades del Power Query disponibles

Vegeu la [Referència de connectors del Power Query](/power-query/connectors/) per veure una llista actualitzada de connectors que podeu seleccionar per importar dades al Customer Insights. 

Els connectors amb una marca de selecció a la columna **Customer Insights (fluxos de dades)** estan disponibles per crear noves fonts de dades basades en el Power Query. Reviseu la documentació d'un connector específic per obtenir més informació sobre els seus prerequisits, limitacions i altres detalls.

## <a name="edit-power-query-data-sources"></a>Editar les fonts de dades del Power Query

> [!NOTE]
> Pot ser que no es puguin fer canvis en les fonts de dades que s'estan utilitzant actualment en un dels processos del'aplicació(*segmentació*, *coincidència* o *combinació*, per exemple). 
>
> Mitjançant la pàgina **Configuració**, podeu fer el seguiment del progrés de cadascun dels processos actius. Quan es completi un procés, podeu tornar a la pàgina **Fonts de dades** i fer els canvis que vulgueu.

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2. Seleccioneu els punts suspensius verticals al costat de la font de dades voleu canviar i seleccioneu **Edita** al menú desplegable.

   > [!div class="mx-imgBorder"]
   > ![Opció Edita.](media/edit-option-data-sources.png "Opció Edita")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Apliqueu els canvis i transformacions al diàleg **Power Query: edita les consultes** tal com es descriu a la secció [Crear una nova font de dades](#create-a-new-data-source).

4. Seleccioneu **Desa** al Power Query després de completar les vostres edicions per desar els canvis.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
