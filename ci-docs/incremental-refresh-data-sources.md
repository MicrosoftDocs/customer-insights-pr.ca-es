---
title: Actualització incremental per als Power Query orígens de dades de l'Azure Data Lake
description: Actualitzeu les dades noves i actualitzades dels orígens de dades grans basats en Power Query fonts de dades del llac de dades de l'Azure.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012013"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Actualització incremental per als Power Query orígens de dades de l'Azure Data Lake

En aquest article s'analitza com configurar l'actualització incremental per als orígens de dades basats en l'Azure Power Query Data Lake.

L'actualització incremental de les fonts de dades proporciona els següents avantatges:

- **Actualitzacions més ràpides**: només s'actualitzen les dades que han canviat. Per exemple, pot ser que només actualitzeu els darrers cinc dies d'un conjunt de dades històric.
- **Major fiabilitat**: amb actualitzacions més petites, no cal mantenir connexions al sistemes d'origen volàtils durant tant de temps, la qual cosa redueix el risc de problemes de connexió.
- **Reducció del consum de recursos**: actualitzar només un subconjunt de les dades totals deriva en un ús més eficient dels recursos de computació i redueix l'impacte ambiental.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Configura l'actualització incremental per als orígens de dades en funció de Power Query

Customer Insights permet l'actualització incremental dels orígens de dades importats a través Power Query d'aquesta ingestió incremental. Per exemple, les bases de dades de l'Azure SQL amb camps de data i hora, que indiquen quan s'han actualitzat per última vegada els registres de dades.

1. [Crea un font de dades nou basat en Power Query](connect-power-query.md).

1. Seleccioneu un font de dades compatible amb l'actualització incremental, com [ara la base de dades SQL de l'Azure](/power-query/connectors/azuresqldatabase).

1. Seleccioneu les entitats o taules que voleu ingerir.

1. Completeu els passos de transformació i seleccioneu **Següent**.

1. Al quadre de diàleg **Configuració de l'actualització incremental**, seleccioneu **Configura** per obrir la **Configuració de l'actualització incremental**. Si seleccioneu **Omet**, la font de dades actualitzarà el conjunt de dades complet.
   > [!TIP]
   > També podeu aplicar l'actualització incremental més tard mitjançant l'edició d'una font de dades existent.

1. A la **Configuració de l'actualització incremental**, configurareu l'actualització incremental per a totes les entitats que heu seleccionat en crear la font de dades.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configura la configuració d'actualització incremental.":::

1. Seleccioneu una entitat i proporcioneu els detalls següents:

   - **Definiu la clau principal**: seleccioneu una clau principal per a l'entitat o la taula.
   - **Definiu el camp "darrera actualització"**: aquest camp només mostrarà els atributs del tipus data o hora. Seleccioneu un atribut que indiqui quan es van actualitzar per última vegada els registres. S'utilitzarà per identificar els registres que es troben dins del període de temps d'actualització incremental.
   - **Comprova si hi ha actualitzacions cada**: especifiqueu la freqüència que voleu per al període de temps d'actualització incremental.

1. Seleccioneu **Desa** per completar la creació de la font de dades. L'actualització inicial de les dades serà una actualització completa. Després, es produirà l'actualització de dades incremental com s'ha configurat al pas anterior.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Configura l'actualització incremental per als orígens de dades de l'Azure Data Lake

Customer Insights permet l'actualització incremental dels orígens de dades connectats a Azure Data Lake Storage. Per utilitzar la ingestió i l'actualització incrementals d'una entitat, configureu aquesta entitat quan afegiu el font de dades del llac de dades de l'Azure o posterior en editar el font de dades. La carpeta de dades d'entitat ha de contenir les carpetes següents:

- **FullData**: Carpeta amb fitxers de dades que contenen registres inicials
- **IncrementalData**: Carpeta amb carpetes de jerarquia de data i hora en **format yyyy/mm/dd/hh** que conté les actualitzacions incrementals. **hh** representa l'hora UTC de les actualitzacions i conté les **carpetes Upserts** i **Deletes**. **Upserts** conté fitxers de dades amb actualitzacions de registres existents o registres nous. **Suprimeix** conté fitxers de dades amb registres que s'han de suprimir.

1. Quan afegiu o editeu un font de dades, aneu a la **subfinestra Atributs** de l'entitat.

1. Revisa els atributs. Assegureu-vos que un atribut de data creat o últim actualitzat estigui configurat amb un *format* dateTime **Data** i un *tipus* semàntic Calendar.Date **·**. Editeu l'atribut si cal i seleccioneu **Fet**.

1. Des de la **subfinestra Selecciona entitats**, editeu l'entitat. S'ha **seleccionat la casella de selecció d'ingestió** incremental.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Configurar les entitats en una font de dades per a l'actualització incremental.":::

   1. Navegueu fins a la carpeta arrel que conté els fitxers .csv o .parquet per a les dades completes, els augments incrementals de dades i les supressacions incrementals de dades.
   1. Introduïu l'extensió de les dades completes i els dos fitxers incrementals (\. csv o \. parquet).
   1. Seleccioneu **Desa**.

1. Per a **l'última actualització**, seleccioneu l'atribut de marca horària de data.

1. Si no està seleccionada la **clau** Primària, seleccioneu la clau principal. La clau principal és un atribut únic a l'entitat. Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls. Els atributs de tipus de dades string, integer i GUID són compatibles com a claus principals.

1. Seleccioneu **Tanca** per desar i tancar la subfinestra.

1. Continua afegint o editant el font de dades.

[!INCLUDE [footer-include](includes/footer-banner.md)]
