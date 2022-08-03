---
title: Actualització incremental per a Power Query les fonts de dades de l'Azure Data Lake
description: Actualitzeu les dades noves i actualitzades per a grans fonts de dades basades en Power Query fonts de dades del llac de dades de l'Azure o de l'Azure.
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
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207125"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Actualització incremental per a Power Query les fonts de dades de l'Azure Data Lake

L'actualització incremental per a fonts de dades basades Power Query en o Azure Data Lake proporciona els avantatges següents:

- **Actualitzacions més ràpides**: només s'actualitzen les dades que han canviat. Per exemple, pot ser que només actualitzeu els darrers cinc dies d'un conjunt de dades històric.
- **Major fiabilitat**: amb actualitzacions més petites, no cal mantenir connexions al sistemes d'origen volàtils durant tant de temps, la qual cosa redueix el risc de problemes de connexió.
- **Reducció del consum de recursos**: actualitzar només un subconjunt de les dades totals deriva en un ús més eficient dels recursos de computació i redueix l'impacte ambiental.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Configurar l'actualització incremental per a les fonts de dades en funció de Power Query

El Customer Insights permet actualitzar incrementalment les fonts de dades importades a través Power Query d'aquesta ingestió incremental. Per exemple, les bases de dades de l'Azure SQL amb camps de data i hora, que indiquen quan s'han actualitzat per última vegada els registres de dades.

1. [Crea un nou font de dades basat en Power Query](connect-power-query.md).

1. Seleccioneu un font de dades que admeti l'actualització incremental, com [ara la base de dades de l'Azure SQL](/power-query/connectors/azuresqldatabase).

1. Seleccioneu les entitats o taules que voleu ingerir.

1. Completeu els passos de transformació i seleccioneu **Següent**.

1. Al quadre de diàleg **Configuració de l'actualització incremental**, seleccioneu **Configura** per obrir la **Configuració de l'actualització incremental**. Si seleccioneu **Omet**, la font de dades actualitzarà el conjunt de dades complet.
   > [!TIP]
   > També podeu aplicar l'actualització incremental més tard mitjançant l'edició d'una font de dades existent.

1. A la **Configuració de l'actualització incremental**, configurareu l'actualització incremental per a totes les entitats que heu seleccionat en crear la font de dades.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configureu els paràmetres d'actualització incremental.":::

1. Seleccioneu una entitat i proporcioneu els detalls següents:

   - **Definiu la clau principal**: seleccioneu una clau principal per a l'entitat o la taula.
   - **Definiu el camp "darrera actualització"**: aquest camp només mostrarà els atributs del tipus data o hora. Seleccioneu un atribut que indiqui quan es van actualitzar per última vegada els registres. S'utilitzarà per identificar els registres que es troben dins del període de temps d'actualització incremental.
   - **Comprova si hi ha actualitzacions cada**: especifiqueu la freqüència que voleu per al període de temps d'actualització incremental.

1. Seleccioneu **Desa** per completar la creació de la font de dades. L'actualització inicial de les dades serà una actualització completa. Després, es produirà l'actualització de dades incremental com s'ha configurat al pas anterior.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Configuració de l'actualització incremental per a les fonts de dades de l'Azure Data Lake

El Customer Insights permet actualitzar incrementalment les fonts de dades connectades a Azure Data Lake Storage. Per utilitzar la ingestió incremental i l'actualització d'una entitat, configureu aquesta entitat quan afegiu l'Azure Data Lake font de dades o posterior quan editeu el font de dades. La carpeta de dades de l'entitat ha de contenir les carpetes següents:

- **FullData**: Carpeta amb fitxers de dades que contenen registres inicials
- **IncrementalData**: Carpeta amb carpetes jeràrquiques de data/hora en format aaaa **/mm/dd/hh** que conté les actualitzacions incrementals. **hh** representa l'hora UTC de les actualitzacions i conté les **carpetes Upserts** **i** Deletes. **Upserts** conté fitxers de dades amb actualitzacions de registres existents o registres nous. **Suprimeix** conté fitxers de dades amb registres que s'han d'eliminar.

1. Quan afegiu o editeu un font de dades, aneu a la **subfinestra Atributs** de l'entitat.

1. Reviseu els atributs. Assegureu-vos que un atribut de data creat o darrera actualització estigui configurat amb un *format dateTime* **Data i un** tipus *Semàntic* Calendar.Date **·**. Editeu l'atribut si cal i seleccioneu **Fet**.

1. Des de la **subfinestra Selecciona entitats**, editeu l'entitat. La **casella d'ingestió** incremental està marcada.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Configurar les entitats en una font de dades per a l'actualització incremental.":::

   1. Navegueu fins a la carpeta arrel que conté els fitxers .csv o .parquet per obtenir dades completes, augments de dades incrementals i supressions incrementals de dades.
   1. Introduïu l'extensió per a les dades completes i els dos fitxers incrementals (\. csv o \. parquet).
   1. Per .csv fitxers, seleccioneu el delimitador de columnes i si voleu la primera fila del fitxer com a capçalera de columna.
   1. Seleccioneu **Desa**.

1. Per a **La darrera actualització**, seleccioneu l'atribut marca de temps de la data.

1. Si no se selecciona la **clau** principal, seleccioneu la clau principal. La clau principal és un atribut únic per a l'entitat. Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls. Els atributs de tipus de dades String, Integer i GUID s'admeten com a claus principals.

1. Seleccioneu **Tanca** per desar i tancar la subfinestra.

1. Continueu afegint o editant el font de dades.

[!INCLUDE [footer-include](includes/footer-banner.md)]
