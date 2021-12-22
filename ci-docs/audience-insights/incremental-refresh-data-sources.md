---
title: Actualització incremental per a fonts de dades basades en Power Query
description: Actualitzeu dades noves i actualitzades per a les fonts de dades grans basades en el Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: f614d701aeb06720a60b14549a7fe666f8fe0617
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900243"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Actualització incremental per a fonts de dades basades en el Power Query

En aquest article es discuteix com configurar l'actualització incremental per als orígens de dades en funció de Power Query.

L'actualització incremental de les fonts de dades proporciona els següents avantatges:

- **Actualitzacions més ràpides**: només s'actualitzen les dades que han canviat. Per exemple, pot ser que només actualitzeu els darrers cinc dies d'un conjunt de dades històric.
- **Major fiabilitat**: amb actualitzacions més petites, no cal mantenir connexions al sistemes d'origen volàtils durant tant de temps, la qual cosa redueix el risc de problemes de connexió.
- **Reducció del consum de recursos**: actualitzar només un subconjunt de les dades totals deriva en un ús més eficient dels recursos de computació i redueix l'impacte ambiental.

## <a name="configure-incremental-refresh"></a>Configuració de l'actualització incremental

Les conclusions del públic permeten actualitzar de manera incremental fonts de dades importades mitjançant el Power Query que admetin la ingestió incremental. Per exemple, les bases de dades de l'Azure SQL amb camps de data i hora, que indiquen quan s'han actualitzat per última vegada els registres de dades.

1. [Crear una font de dades nova basada en el Power Query](connect-power-query.md).

1. Donar un **nom** a la font de dades.

1. Seleccioneu un font de dades compatible amb l'actualització incremental, com ara la [base de dades SQL de l'Azure](/power-query/connectors/azuresqldatabase).

1. Seleccioneu les entitats o taules que voleu ingerir.

1. Completeu els passos de transformació i seleccioneu **Següent**.

1. Al quadre de diàleg **Configuració de l'actualització incremental**, seleccioneu **Configura** per obrir la **Configuració de l'actualització incremental**. Si seleccioneu **Omet**, la font de dades actualitzarà el conjunt de dades complet.
   > [!TIP]
   > També podeu aplicar l'actualització incremental més tard mitjançant l'edició d'una font de dades existent.

1. A la **Configuració de l'actualització incremental**, configurareu l'actualització incremental per a totes les entitats que heu seleccionat en crear la font de dades.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurar les entitats en una font de dades per a l'actualització incremental.":::

1. Seleccioneu una entitat i proporcioneu els detalls següents:

   - **Definiu la clau principal**: seleccioneu una clau principal per a l'entitat o la taula.
   - **Definiu el camp "darrera actualització"**: aquest camp només mostrarà els atributs del tipus data o hora. Seleccioneu un atribut que indiqui quan es van actualitzar per última vegada els registres. S'utilitzarà per identificar els registres que es troben dins del període de temps d'actualització incremental.
   - **Comprova si hi ha actualitzacions cada**: especifiqueu la freqüència que voleu per al període de temps d'actualització incremental.

1. Seleccioneu **Desa** per completar la creació de la font de dades. L'actualització inicial de les dades serà una actualització completa. Després, es produirà l'actualització de dades incremental com s'ha configurat al pas anterior.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
