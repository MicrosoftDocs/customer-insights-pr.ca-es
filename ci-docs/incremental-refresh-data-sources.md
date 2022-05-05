---
title: Actualització incremental per als Power Query orígens de dades basats en
description: Actualitza les dades noves i actualitzades dels orígens de dades grans en funció del Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642376"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Actualització incremental per als orígens de dades basats en Power Query

En aquest article s'analitza com configurar l'actualització incremental per als orígens de dades en funció de Power Query.

L'actualització incremental de les fonts de dades proporciona els següents avantatges:

- **Actualitzacions més ràpides**: només s'actualitzen les dades que han canviat. Per exemple, pot ser que només actualitzeu els darrers cinc dies d'un conjunt de dades històric.
- **Major fiabilitat**: amb actualitzacions més petites, no cal mantenir connexions al sistemes d'origen volàtils durant tant de temps, la qual cosa redueix el risc de problemes de connexió.
- **Reducció del consum de recursos**: actualitzar només un subconjunt de les dades totals deriva en un ús més eficient dels recursos de computació i redueix l'impacte ambiental.

## <a name="configure-incremental-refresh"></a>Configurar l'actualització incremental

Customer Insights permet l'actualització incremental dels orígens de dades importats a través Power Query d'aquesta ingestió incremental. Per exemple, les bases de dades de l'Azure SQL amb camps de data i hora, que indiquen quan s'han actualitzat per última vegada els registres de dades.

1. [Crea un font de dades nou basat en Power Query](connect-power-query.md).

1. Donar un **nom** a la font de dades.

1. Seleccioneu una font de dades que admeti l'actualització incremental, com [ara la base de dades SQL de l'Azure](/power-query/connectors/azuresqldatabase).

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
