---
title: Connectar-se a una carpeta del Common Data Model amb un compte de l'Azure Data Lake
description: Treballeu amb dades del Common Data Model mitjançant l'Azure Data Lake Storage.
ms.date: 09/29/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: c12603b9ed8a814356a0f8d0137e97afc749b87c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609930"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Connexió a dades al Azure Data Lake Storage

Ingereix dades per Dynamics 365 Customer Insights utilitzar el teu Azure Data Lake Storage compte Gen2. La ingestió de dades pot ser completa o incremental.

## <a name="prerequisites"></a>Requisits previs

- La ingestió de dades admet Azure Data Lake Storage *exclusivament comptes Gen2*. No podeu utilitzar els comptes del Data Lake Storage Gen1 per ingerir dades.

- El Azure Data Lake Storage compte ha de tenir [habilitat l'espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace). Les dades s'han d'emmagatzemar en un format de carpeta jeràrquica que defineixi la carpeta arrel i tingui subcarpetes per a cada entitat. Les subcarpetes poden tenir dades completes o carpetes de dades incrementals.

- Per autenticar-vos amb una entitat de servei de l'Azure, assegureu-vos que aquesta s'hagi configurat al vostre inquilí. Per obtenir més informació, vegeu [Connectar-se a un Azure Data Lake Storage compte gen2 amb un director de servei de l'Azure](connect-service-principal.md).

- El Azure Data Lake Storage que voleu connectar i ingerir dades ha d'estar a la mateixa regió de l'Azure que l'entorn Dynamics 365 Customer Insights. No s'admet la connexió a una carpeta del Common Data Model procedent d'un llac de dades d'una regió diferent de l'Azure. Per conèixer la regió de l'Azure de l'entorn, aneu a Sistema **d'administració** > **Quant** > **a** Estadístiques del client.

- Les dades emmagatzemades en els serveis en línia es poden emmagatzemar en una ubicació diferent d'on es processen o emmagatzemen les dades.Dynamics 365 Customer InsightsEn importar o connectar-vos a les dades emmagatzemades als serveis en línia, accepteu que les dades es puguin transferir i emmagatzemar amb Dynamics 365 Customer Insights. [Obteniu més informació al Centre de confiança de Microsoft](https://www.microsoft.com/trust-center).

- El director del servei del Customer Insights ha d'estar en una de les funcions següents per accedir al compte d'emmagatzematge. Per obtenir més informació, vegeu [Concessió de permisos al director del servei per accedir al compte](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account) d'emmagatzematge.
  - Lector de dades de Blob de l'emmagatzematge
  - Propietari de dades de Blob de l'emmagatzematge
  - Col·laborador de dades de Blob d'emmagatzematge

- L'usuari que configura la connexió font de dades necessita menys permisos de col·laborador de dades Blob d'emmagatzematge al compte d'emmagatzematge.

- Les dades del Data Lake Storage han de seguir l'estàndard common data model per a l'emmagatzematge de les vostres dades i tenir el model de dades comú manifest per representar l'esquema dels fitxers de dades (*.csv o *.parquet). El manifest ha de proporcionar els detalls de les entitats, com ara les columnes d'entitat i els tipus de dades, i la ubicació del fitxer de dades i el tipus de fitxer. Per obtenir més informació, vegeu [el manifest Del model de dades comú](/common-data-model/sdk/manifest). Si el manifest no està present, els usuaris administradors amb accés Storage Blob Data Owner o Storage Blob Data Contributor poden definir l'esquema en ingerir les dades.

## <a name="recommendations"></a>Recomanacions

Per obtenir un rendiment òptim, el Customer Insights recomana que la mida d'una partició sigui d'1 GB o menys i que el nombre de fitxers de partició d'una carpeta no superi els 1000.

## <a name="connect-to-azure-data-lake-storage"></a>Connectar a l’Azure Data Lake Storage

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Seleccioneu **Emmagatzematge del data lake de l'Azure**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Quadre de diàleg per introduir els detalls de la connexió per a l'Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Introduïu un **nom** per al font de dades i una descripció opcional.**·** El nom identifica de manera única el font de dades i es fa referència en processos aigües avall i no es pot canviar.

1. Trieu una de les opcions següents per connectar **l'emmagatzematge mitjançant**. Per obtenir més informació, vegeu [Connectar el Customer Insights a un Azure Data Lake Storage compte de Gen2 amb un director de servei de l'Azure](connect-service-principal.md).

   - **Recurs de l'Azure**: introduïu l'identificador **de** recurs. Opcionalment, si voleu ingerir dades d'un compte d'emmagatzematge mitjançant un Azure Private Link, seleccioneu **Habilita l'enllaç** privat. Per obtenir més informació, vegeu [Enllaços](security-overview.md#set-up-an-azure-private-link) privats.
   - **Subscripció de** l'Azure: seleccioneu la **subscripció** i, a continuació, el **grup** de recursos i **el compte** d'emmagatzematge. Opcionalment, si voleu ingerir dades d'un compte d'emmagatzematge mitjançant un Azure Private Link, seleccioneu **Habilita l'enllaç** privat. Per obtenir més informació, vegeu [Enllaços](security-overview.md#set-up-an-azure-private-link) privats.
  
   > [!NOTE]
   > Necessiteu un dels rols següents al contenidor o al compte d'emmagatzematge per crear el font de dades:
   >
   >  - Storage Blob Data Reader és suficient per llegir des d'un compte d'emmagatzematge i ingerir les dades al Customer Insights.
   >  - L'emmagatzematge Blob Data Contributor o Owner és necessari si voleu editar els fitxers de manifest directament al Customer Insights.  
  
1. Trieu el nom del **contenidor** que conté les dades i l'esquema (fitxer model.json o manifest.json) per importar dades i seleccioneu **Següent**.
   > [!NOTE]
   > Els fitxers model.json o manifest.json associats amb una altra font de dades de l'entorn no es mostraran a la llista. No obstant, un mateix fitxer model.json o manifest.json es pot utilitzar per a fonts de dades de diversos entorns.

1. Per crear un esquema nou, aneu a [Crea un fitxer](#create-a-new-schema-file) d'esquema nou.

1. Per utilitzar un esquema existent, aneu a la carpeta que conté el fitxer model.json o manifest.cdm.json. Podeu cercar dins d'un directori per trobar el fitxer.

1. Seleccioneu el fitxer json i seleccioneu **Següent**. Es mostra una llista d'entitats disponibles.

   :::image type="content" source="media/review-entities.png" alt-text="Quadre de diàleg d'una llista d'entitats a seleccionar":::

1. Seleccioneu les entitats que voleu incloure.

   :::image type="content" source="media/ADLS_required.png" alt-text="Quadre de diàleg que mostra Necessari per a la clau primària":::

   > [!TIP]
   > Per editar una entitat en una interfície d'edició JSON, seleccioneu l'entitat i, a continuació, **Editeu el fitxer d'esquema**. Feu canvis i seleccioneu **Desa**.

1. Per a les entitats seleccionades que requereixen una ingestió incremental, **Visualitzacions obligatòries** a **Actualització incremental**. Per a cadascuna d'aquestes entitats, vegeu [Configurar una actualització incremental per a les fonts](incremental-refresh-data-sources.md) de dades de l'Azure Data Lake.

1. Per a les entitats seleccionades en què no s'ha definit una clau principal, **Obligatori** es mostra sota **clau primària**. Per a cadascuna d'aquestes entitats:
   1. Seleccioneu **Obligatori**. Es mostra la **subfinestra Edita l'entitat**.
   1. Trieu la **tecla** Principal. La clau principal és un atribut únic per a l'entitat. Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls. Els atributs de tipus de dades String, Integer i GUID s'admeten com a claus principals.
   1. Opcionalment, canvieu el patró de partició.
   1. Seleccioneu **Tanca** per desar i tancar la subfinestra.

1. Seleccioneu el nombre d'atributs **de** cada entitat inclosa. Es **mostra la pàgina Administra els atributs**.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Quadre de diàleg per seleccionar l'elaboració de perfils de dades.":::

   1. Creeu atributs nous, editeu o suprimiu els existents. Podeu canviar el nom, el format de les dades o afegir un tipus semàntic.
   1. Per habilitar l'anàlisi i altres capacitats, seleccioneu **Perfils** de dades per a tota l'entitat o per a atributs específics. Per defecte, no s'habilita cap entitat per a la perfilació de dades.
   1. Seleccioneu **Fet**.

1. Seleccioneu **Desa**. S'obre **la pàgina Fonts** de dades que mostra la nova font de dades en **estat de Refresc**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

La càrrega de les dades pot tardar temps. Després d'una actualització correcta, les dades ingerides es poden revisar des de la [**pàgina Entitats**](entities.md).

### <a name="create-a-new-schema-file"></a>Crear un fitxer d'esquema nou

1. Seleccioneu **Fitxer d'esquema nou**.

1. Introduïu un nom per al fitxer i seleccioneu **Desa**.

1. Seleccioneu **Entitat** nova. Es **mostra la subfinestra Entitat** nova.

1. Introduïu el nom de l'entitat i trieu la ubicació Fitxers **de dades**.
   - **Múltiples fitxers** .csv o .parquet: navegueu fins a la carpeta arrel, seleccioneu el tipus de patró i introduïu l'expressió.
   - **Fitxers d'.csv o .parquet**: Navegueu fins al fitxer .csv o .parquet i seleccioneu-lo.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Quadre de diàleg per crear una entitat nova amb la ubicació dels fitxers de dades ressaltada.":::

1. Seleccioneu **Desa**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Quadre de diàleg per definir o generar automàticament atributs.":::

1. Seleccioneu **definir els atributs** per afegir manualment els atributs o bé generar-los **automàticament**. Per definir els atributs, introduïu un nom, seleccioneu el format de dades i el tipus semàntic opcional. Per als atributs generats automàticament:

   1. Un cop generats automàticament els atributs, seleccioneu **Revisa els atributs**. Es **mostra la pàgina Administra els atributs**.

   1. Assegureu-vos que el format de dades sigui correcte per a cada atribut.

   1. Per habilitar l'anàlisi i altres capacitats, seleccioneu **Perfils** de dades per a tota l'entitat o per a atributs específics. Per defecte, no s'habilita cap entitat per a la perfilació de dades.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Quadre de diàleg per seleccionar l'elaboració de perfils de dades.":::

   1. Seleccioneu **Fet**. Es mostra la **pàgina Selecciona entitats**.

1. Continueu afegint entitats i atributs, si escau.

1. Un cop afegides totes les entitats, seleccioneu **Inclou** per incloure les entitats a la font de dades ingestió.

   :::image type="content" source="media/ADLS_required.png" alt-text="Quadre de diàleg que mostra Necessari per a la clau primària":::

1. Per a les entitats seleccionades que requereixen una ingestió incremental, **Visualitzacions obligatòries** a **Actualització incremental**. Per a cadascuna d'aquestes entitats, vegeu [Configurar una actualització incremental per a les fonts](incremental-refresh-data-sources.md) de dades de l'Azure Data Lake.

1. Per a les entitats seleccionades en què no s'ha definit una clau principal, **Obligatori** es mostra sota **clau primària**. Per a cadascuna d'aquestes entitats:
   1. Seleccioneu **Obligatori**. Es mostra la **subfinestra Edita l'entitat**.
   1. Trieu la **tecla** Principal. La clau principal és un atribut únic per a l'entitat. Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls. Els atributs de tipus de dades String, Integer i GUID s'admeten com a claus principals.
   1. Opcionalment, canvieu el patró de partició.
   1. Seleccioneu **Tanca** per desar i tancar la subfinestra.

1. Seleccioneu **Desa**. S'obre **la pàgina Fonts** de dades que mostra la nova font de dades en **estat de Refresc**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

La càrrega de les dades pot tardar temps. Després d'una actualització correcta, les dades ingerides es poden revisar des de la [**pàgina Entitats**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Editar un Azure Data Lake Storage font de dades

Podeu actualitzar el compte Connecta't a l'emmagatzematge *mitjançant l'opció*. Per obtenir més informació, vegeu [Connectar el Customer Insights a un Azure Data Lake Storage compte de Gen2 amb un director de servei de l'Azure](connect-service-principal.md). Per connectar-vos a un contenidor diferent del vostre compte d'emmagatzematge o canviar el nom de compte, [creeu una connexió de font de dades nova](#connect-to-azure-data-lake-storage).

1. Aneu a **Dades** > **Fonts de dades**.

1. Al costat de la font de dades voleu actualitzar, seleccioneu **Edita**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Quadre de diàleg per editar l'Azure Data Lake font de dades.":::

1. Canvieu qualsevol de les dades següents:

   - **Descripció**
   - **Connecteu l'emmagatzematge mitjançant** la informació de connexió. Quan actualitzeu la connexió, no podreu canviar la informació del **Contenidor**.
      > [!NOTE]
      > S'ha d'assignar una de les funcions següents al compte d'emmagatzematge o al contenidor:
        > - Lector de dades de Blob de l'emmagatzematge
        > - Propietari de dades de Blob de l'emmagatzematge
        > - Col·laborador de dades de Blob d'emmagatzematge

   - **Habiliteu l'enllaç** privat si voleu ingerir dades d'un compte d'emmagatzematge mitjançant un Enllaç privat de l'Azure. Per obtenir més informació, vegeu [Enllaços](security-overview.md#set-up-an-azure-private-link) privats.

1. Seleccioneu **Següent**.
1. Canvieu alguna de les opcions següents:
   - Aneu a un fitxer model.json o manifest.json diferent amb un conjunt diferent d'entitats del contenidor.
   - Per afegir entitats addicionals a la ingestió, seleccioneu **Entitat nova**.
   - Per suprimir les entitats ja seleccionades si no hi ha dependències, seleccioneu l'entitat i **Suprimeix**.
      > [!IMPORTANT]
      > Si hi ha dependències en el fitxer model.json o manifest.json i el conjunt d'entitats, veureu un missatge d'error i no podreu seleccionar un fitxer model.json o manifest.json diferent. Suprimiu aquestes dependències abans de canviar el fitxer model.json o manifest.json o creeu una font de dades nou amb el fitxer model.json o manifest.json que voleu utilitzar per evitar la supressió de les dependències.
   - Per canviar la ubicació del fitxer de dades o la clau principal, seleccioneu **Edita**.
   - Per canviar les dades d'ingestió incremental, vegeu [Configurar una actualització incremental per a les fonts](incremental-refresh-data-sources.md) de dades de l'Azure Data Lake.
   - Canvieu només el nom de l'entitat perquè coincideixi amb el nom de l'entitat al fitxer .json.

     > [!NOTE]
     > Conserveu sempre el nom de l'entitat al Customer Insights igual que el nom de l'entitat dins del fitxer model.json o manifest.json després de la ingestió. El Customer Insights valida tots els noms d'entitat amb el model.json o manifest.json durant cada actualització del sistema. Si es canvia un nom d'entitat dins del Customer Insights o fora, es produeix un error perquè el Customer Insights no pot trobar el nom d'entitat nou al fitxer .json. Si un nom d'entitat ingerit s'ha canviat accidentalment, editeu el nom de l'entitat al Customer Insights perquè coincideixi amb el nom del fitxer .json.

1. Seleccioneu **Atributs** per afegir o canviar atributs, o per habilitar l'elaboració de perfils de dades. A continuació, seleccioneu **Fet**.

1. Feu clic **a Desa** per aplicar els canvis i tornar a la **pàgina Fonts** de dades.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Motius habituals d'errors d'ingestió o dades corruptes

Durant la ingestió de dades, alguns dels motius més habituals pels quals un registre es pot considerar corrupte són:

- Els tipus de dades i els valors de camp no coincideixen entre el fitxer d'origen i l'esquema
- El nombre de columnes del fitxer d'origen no coincideix amb l'esquema
- Els camps contenen caràcters que fan que les columnes s'esbiaixin en comparació amb l'esquema esperat. Per exemple: cometes amb format incorrecte, cometes sense marcar, caràcters de línia nova o caràcters amb pestanyes.
- Falten fitxers de partició
- Si hi ha columnes datetime/datetimeoffset, el seu format s'ha d'especificar a l'esquema si no segueix el format estàndard.

### <a name="schema-or-data-type-mismatch"></a>Desajustament d'esquemes o tipus de dades

Si les dades no s'ajusten a l'esquema, el procés d'ingestió es completa amb errors. Corregiu les dades d'origen o l'esquema i torneu a ingerir les dades.

### <a name="partition-files-are-missing"></a>Falten fitxers de partició

- Si la ingestió s'ha realitzat correctament sense cap registre corrupte, però no podeu veure cap dada, editeu el fitxer model.json o manifest.json per assegurar-vos que les particions estiguin especificades. A continuació, [refresqueu el font de dades](data-sources.md#refresh-data-sources).

- Si la ingestió de dades es produeix al mateix temps que les fonts de dades s'actualitzen durant una actualització automàtica de la planificació, és possible que els fitxers de partició estiguin buits o que no estiguin disponibles per al Processament del Client Insights. Per alinear-vos amb la planificació d'actualització ascendent, canvieu la planificació [d'actualització](schedule-refresh.md) del sistema o la planificació d'actualització del font de dades. Alineeu el temps perquè les actualitzacions no es produeixin totes alhora i proporcioneu les dades més recents que es processaran al Customer Insights.

### <a name="datetime-fields-in-the-wrong-format"></a>Camps de data en un format incorrecte

Els camps de data de l'entitat no estan en formats ISO 8601 ni en-US. El format de data predeterminat al Customer Insights és el format en-US. Tots els camps de data d'una entitat han d'estar en el mateix format. El Customer Insights admet altres formats sempre que les anotacions o trets es facin al nivell d'origen o d'entitat del model o manifest.json. Per exemple:

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  En un manifest.json, el format datetime es pot especificar al nivell d'entitat o al nivell d'atribut. Al nivell d'entitat, utilitzeu "exhibitsTraits" a l'entitat del *.manifest.cdm.json per definir el format datetime. Al nivell d'atribut, utilitzeu "appliedTraits" a l'atribut de entityname.cdm.json.

**Manifest.json a nivell d'entitat**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json al nivell d'atribut**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
