---
title: Cercar i filtrar perfils de client
description: Trobeu ràpidament informació sobre els perfils de client unificats i filtreu-los per atributs especificats.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 35bfd6530b9b80a4b0ec8ff992d9014534721907
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642346"
---
# <a name="customer-profiles-search--filter-index"></a>Perfils de client: índex de cerca i filtratge

El resultat d'unificar les dades dels clients és una entitat de perfil de client que proporciona una visualització unificada a la base de clients total. Per [cercar ràpidament informació sobre un client o un grup de clients determinat](customer-profiles.md), podeu configurar les funcionalitats **Cerca** i **Filtre** a la pàgina **Clients**. Seguiu llegint per obtenir més informació sobre com els administradors poden editar els atributs a la pàgina **Índex de cerca i filtre**, que estan disponibles per als usuaris per cercar i filtrar.

   :::image type="content" source="media/search-filter.png" alt-text="Filtre de cerca":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Afegir camps i especificar atributs

Si és la primera vegada que definiu els atributs que es poden cercar com a administrador, primer heu de definir els camps indexats. Us suggerim que trieu tots els atributs pels quals els usuaris puguin cercar i filtrar els clients a la pàgina **Clients**. Només podeu especificar els atributs que hi ha a l'entitat de perfil de client que heu creat durant el procés d'unificació de dades.

1. Obriu la pàgina **Clients** i seleccioneu **Cerca i filtra l'índex**.

2. Seleccioneu **+ Afegeix** per especificar els camps indexats.

3. Seleccioneu els atributs de la llista que voleu afegir com a camps indexats. Sempre podeu afegir més atributs seleccionant **Afegeix**. Per suprimir els atributs seleccionats, també podeu seleccionar el símbol **Suprimeix**.

## <a name="explore-the-indexed-customer-fields-table"></a>Explorar la taula de camps de client indexats

La següent informació es presenta a la taula.

- **Nom**: representa el nom de l'atribut tal com es mostra a l'entitat de perfil del client.
- **Tipus de dades**: especifica si el tipus de dades és una cadena, un número o una data.
- **Inclòs a la cerca**: especifica si aquest atribut es pot utilitzar per cercar clients a la pàgina **Clients** mitjançant el camp **Cerca**.
- **Afegeix un filtre**: control per definir com es pot utilitzar aquest atribut per filtrar a la pàgina **Clients**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Editar les opcions de filtratge per a un atribut determinat

El menú **Filtre** de la pàgina **Clients** pot incloure un nombre variable de nivells d'atribut (per exemple, diferents grups d'edat pels quals filtrar els clients).

1. Seleccioneu **Afegeix un filtre** per a un atribut determinat a la pàgina **Índex de cerca i filtre**. Podeu definir el nombre de resultats i l'ordre en el qual s'organitzaran. En funció del tipus de dades de l'atribut, apareixerà una dels subfinestres següents.

- Atributs de cadena: especifiqueu el nombre de resultats que voleu a la subfinestra **Opcions del filtre de cadena** i la norma d'ordre per la qual s'organitzaran.

- Atributs numèrics: especifiqueu els intervals inclosos a la subfinestra **Opcions del filtre de nombre** i la norma d'ordre per la qual s'organitzaran.

- Atributs de data: especifiqueu els intervals inclosos a la subfinestra **Opcions del filtre de data** i la norma d'ordre per la qual s'organitzaran.

2. Seleccioneu **Desa** per aplicar els canvis.

3. Seleccioneu **Executa** una vegada que estigueu a punt per aplicar la configuració. Un cop processats els canvis, els trobareu a les [targetes de client de la pàgina Client](customer-profiles.md). 

## <a name="next-steps"></a>Passos següents

Reviseu la [pàgina de perfils unificats](customer-profiles.md) per cercar perfils o utilitzar els camps indexats per veure un subconjunt de tots els perfils unificats.


[!INCLUDE [footer-include](includes/footer-banner.md)]
