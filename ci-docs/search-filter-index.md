---
title: Gestionar l'índex de cerca i filtre dels perfils de clients
description: Trobeu ràpidament informació sobre els perfils de client unificats i filtreu-los per atributs especificats.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187897"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Gestionar l'índex de cerca i filtre dels perfils de clients

El resultat d'unificar les dades dels vostres clients és una *entitat de client* que proporciona una visualització unificada a la vostra base de clients total. Perquè els usuaris trobin ràpidament [informació sobre un client o grup de clients](customer-profiles.md) específics, un administrador ha de configurar les **capacitats de cerca** i **filtre** per a la **pàgina Clients**.

   :::image type="content" source="media/search-filter.png" alt-text="Filtre de cerca":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definir atributs que es poden cercar i camps indexats

Si és la primera vegada que definiu els atributs cercables com a administrador, definiu primer els camps indexats. Us suggerim que trieu tots els atributs pels quals els usuaris puguin cercar i filtrar els clients a la pàgina **Clients**. Només es poden especificar els atributs que existeixen a l'entitat *client* creada durant el procés d'unificació de dades.

1. Aneu a **Clients** i seleccioneu **Cerca i índex** de filtres.

1. Seleccioneu **+ Afegeix**.

1. Seleccioneu els atributs de la llista que voleu afegir com a camps indexats i feu clic a **Aplica**.

1. Per afegir més atributs, selecciona **Afegeix**. Per suprimir un atribut seleccionat, seleccioneu-lo i, a continuació, **Suprimeix**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Pàgina d'índex de cerca i filtre.":::

1. Seleccioneu **Executa** un cop estigueu a punt per aplicar la configuració de cerca i filtre. Un cop processats els canvis, visualitza'ls a les [targetes de client de la pàgina](customer-profiles.md) Client.

## <a name="define-filtering-options-for-a-given-attribute"></a>Definir les opcions de filtratge d'un atribut determinat

Configureu els camps que es poden utilitzar per filtrar els clients a la **pàgina Clients**.

1. Aneu a **Clients** i seleccioneu **Cerca i índex** de filtres.

1. Seleccioneu un atribut i **Afegeix un filtre**. Definir el nombre de resultats i l'ordre en què s'organitzaran. Segons el tipus de dades de l'atribut, apareixerà una de les subfinestres següents.

   - Atributs de tipus string: especifiqueu el nombre de resultats desitjats a la **subfinestra Filtre string** i la política d'ordre per la qual s'organitzaran.

   - Atributs de tipus numèric: especifiqueu els intervals inclosos a la **subfinestra Filtre de números** i la política d'ordre per la qual s'organitzaran.

   - Atributs de tipus de data: especifiqueu els intervals inclosos a la **subfinestra Filtre de data** i la política de comandes per la qual s'organitzaran.

1. Seleccioneu **D'acord**. Repetiu-ho per a tots els atributs que vulgueu filtrar.

1. Seleccioneu **Executa** un cop estigueu a punt per aplicar la configuració de cerca i filtre. Un cop processats els canvis, visualitza'ls a les [targetes de client de la pàgina](customer-profiles.md) Client.

## <a name="view-indexed-customer-fields"></a>Veure camps de clients indexats

La **pàgina Índex de cerca i filtre** mostra la informació següent:

- **Nom**: representa el nom de l'atribut tal com apareix a l'entitat *Client*.
- **Tipus de dades**: especifica si el tipus de dades és una cadena, un número o una data.
- **Inclòs a la cerca**: especifica si aquest atribut es pot utilitzar per cercar clients a la pàgina **Clients** mitjançant el camp **Cerca**.
- **Afegeix un filtre**: control per definir com es pot utilitzar aquest atribut per filtrar a la pàgina **Clients**.

## <a name="next-steps"></a>Passos següents

Reviseu la [pàgina de perfils unificats](customer-profiles.md) per cercar perfils o utilitzar els camps indexats per veure un subconjunt de tots els perfils unificats.

[!INCLUDE [footer-include](includes/footer-banner.md)]
