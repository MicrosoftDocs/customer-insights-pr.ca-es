---
title: Connectar-se a una carpeta del Common Data Model amb un compte de l'Azure Data Lake
description: Treballeu amb dades del Common Data Model mitjançant l'Azure Data Lake Storage.
ms.date: 05/30/2022
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
ms.openlocfilehash: b1cdcb46df17d722ad49d361ae4c7ab34c83eeb1
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082255"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Connexió a dades al Azure Data Lake Storage

Ingereix les dades per Dynamics 365 Customer Insights utilitzar el teu Azure Data Lake Storage compte Gen2. La ingestió de dades pot ser total o incremental.

## <a name="prerequisites"></a>Requisits previs

- La ingestió de dades admet Azure Data Lake Storage *exclusivament els comptes gen2*. No podeu utilitzar els comptes De Data Lake Storage Gen1 per ingerir dades.

- El Azure Data Lake Storage compte ha de tenir [habilitat l'espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace). Les dades s'han d'emmagatzemar en un format de carpeta jeràrquica que defineixi la carpeta arrel i tingui subcarpetes per a cada entitat. Les subcarpetes poden tenir dades completes o carpetes de dades incrementals.

- Per autenticar-vos amb una entitat de servei de l'Azure, assegureu-vos que aquesta s'hagi configurat al vostre inquilí. Per obtenir més informació, vegeu [Connectar-se a un Azure Data Lake Storage compte Gen2 amb un principal de servei de l'Azure](connect-service-principal.md).

- Les Azure Data Lake Storage dades des de les que voleu connectar i ingerir han d'estar a la mateixa regió de l'Azure que l'entorn Dynamics 365 Customer Insights. No s'admet la connexió a una carpeta del Common Data Model procedent d'un llac de dades d'una regió diferent de l'Azure. Per conèixer la regió de l'Azure de l'entorn, aneu a Quant al **sistema** > **d'administració** > **Quant** al Customer Insights.

- Les dades emmagatzemades en els serveis en línia es poden emmagatzemar en una ubicació diferent d'on es processen o emmagatzemen les dades al Dynamics 365 Customer Insights.En importar o connectar-vos a les dades emmagatzemades en serveis en línia, accepteu que les dades es puguin transferir i emmagatzemar amb Dynamics 365 Customer Insights. [Més informació al Microsoft Trust Center](https://www.microsoft.com/trust-center).

- El principal del servei del Customer Insights ha d'estar en una de les funcions següents per accedir al compte d'emmagatzematge. Per obtenir més informació, consulta [Concedir permisos al director del servei per accedir al compte](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account) d'emmagatzematge.
  - Lector de dades de Blob de l'emmagatzematge
  - Propietari de dades de Blob de l'emmagatzematge
  - Col·laborador de dades de Blob d'emmagatzematge

- Les dades del vostre emmagatzematge de data lake han de seguir l'estàndard common data model per a l'emmagatzematge de les vostres dades i tenir el model de dades comú manifest per representar l'esquema dels fitxers de dades (*.csv o *.parquet). El manifest ha de proporcionar els detalls de les entitats, com ara columnes d'entitat i tipus de dades, i la ubicació i el tipus de fitxer de dades. Per obtenir més informació, vegeu [el manifest Del model de dades comú](/common-data-model/sdk/manifest). Si el manifest no està present, els usuaris administradors amb el propietari de dades del blob d'emmagatzematge o l'accés al contributor de dades blob d'emmagatzematge poden definir l'esquema en ingerir les dades.

## <a name="connect-to-azure-data-lake-storage"></a>Connectar a l’Azure Data Lake Storage

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Seleccioneu **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Quadre de diàleg per introduir els detalls de la connexió per al llac de dades de l'Azure." lightbox="media/data_sources_ADLS.png":::

1. Introduïu un **nom** per a la font de dades i una descripció **opcional**. El nom identifica de manera única el font de dades i fa referència en processos aigües avall i no es pot canviar.

1. Trieu una de les opcions següents per **connectar l'emmagatzematge mitjançant.** Per obtenir més informació, vegeu [Connect Customer Insights a un Azure Data Lake Storage compte gen2 amb un principal de servei de](connect-service-principal.md) l'Azure.

   - **Azure resource**: Introduïu l'identificador **de recurs**. Opcionalment, si voleu ingerir dades d'un compte d'emmagatzematge a través d'un enllaç privat de l'Azure, seleccioneu **Habilita l'enllaç** privat. Per obtenir més informació, vegeu [Enllaços privats](security-overview.md#private-links-tab).
   - **Subscripció a** l'Azure: seleccioneu la **subscripció** i, a continuació, el grup **de recursos i** el **compte** d'emmagatzematge. Opcionalment, si voleu ingerir dades d'un compte d'emmagatzematge a través d'un enllaç privat de l'Azure, seleccioneu **Habilita l'enllaç** privat. Per obtenir més informació, vegeu [Enllaços privats](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Necessiteu una de les funcions següents al contenidor o al compte d'emmagatzematge per crear el font de dades:
   >
   >  - El lector de dades blob d'emmagatzematge és suficient per llegir des d'un compte d'emmagatzematge i ingerir les dades al Customer Insights. 
   >  - Es requereix el col·laborador o propietari de dades de Blob d'emmagatzematge si voleu editar els fitxers de manifest directament a Customer Insights.  
  
1. Trieu el nom del **contenidor** que conté les dades i l'esquema (fitxer model.json o manifest.json) des del qual voleu importar dades i seleccioneu **Endavant**.
   > [!NOTE]
   > Els fitxers model.json o manifest.json associats amb una altra font de dades de l'entorn no es mostraran a la llista. No obstant, un mateix fitxer model.json o manifest.json es pot utilitzar per a fonts de dades de diversos entorns.

1. Per crear un esquema nou, aneu a [Crea un fitxer](#create-a-new-schema-file) d'esquema nou.

1. Per utilitzar un esquema existent, aneu a la carpeta que conté el fitxer model.json o manifest.cdm.json. Podeu cercar dins d'un directori per trobar el fitxer.

1. Seleccioneu el fitxer json i seleccioneu **Següent**. Es mostra una llista d'entitats disponibles.

   :::image type="content" source="media/review-entities.png" alt-text="Quadre de diàleg d'una llista d'entitats a seleccionar":::

1. Seleccioneu les entitats que voleu incloure.

   :::image type="content" source="media/ADLS_required.png" alt-text="Quadre de diàleg que mostra la clau necessària per a la clau primària":::

   > [!TIP]
   > Per editar les entitats d'una interfície d'edició JSON, seleccioneu **Mostra més** > **edita el fitxer** d'esquema. Feu canvis i seleccioneu **Desa**.

1. Per a les entitats seleccionades que requereixen ingestió incremental, **es mostra** a **Actualització incremental**. Per a cadascuna d'aquestes entitats, vegeu [Configurar una actualització incremental per als orígens de dades de l'Azure Data Lake](incremental-refresh-data-sources.md).

1. Per a les entitats seleccionades on no s'ha definit una clau principal, **Es mostra** a **La clau** Principal. Per a cadascuna d'aquestes entitats:
   1. Seleccioneu **Necessari**. Es **mostra el tauler Edita l'entitat**.
   1. Trieu la **clau principal**. La clau principal és un atribut únic a l'entitat. Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls. Els atributs de tipus de dades string, integer i GUID són compatibles com a claus principals.
   1. Opcionalment, canvieu el patró de particions.
   1. Seleccioneu **Tanca** per desar i tancar el plafó.

1. Seleccioneu el nombre d'atributs **per** a cada entitat inclosa. Es **visualitza la pàgina Administra els atributs**.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Quadre de diàleg per seleccionar l'elaboració de perfils de dades.":::

   1. Crea atributs nous, edita o suprimeix atributs existents. Podeu canviar el nom, el format de les dades o afegir un tipus semàntic.
   1. Per habilitar l'anàlisi i altres capacitats, seleccioneu **Perfilat de** dades per a tota l'entitat o per a atributs específics. Per defecte, no s'habilita cap entitat per a la perfilació de dades.
   1. Seleccioneu **Fet**.

1. Seleccioneu **Desa**. S'obre **la pàgina Orígens** de dades que mostra la nova font de dades a **l'estat** d'actualització.

### <a name="create-a-new-schema-file"></a>Crea un fitxer d'esquema nou

1. Seleccioneu **Un fitxer d'esquema nou**.

1. Introduïu un nom per al fitxer i seleccioneu **Desa**.

1. Seleccioneu **Una entitat** nova. Es **mostra el tauler Entitat** nova.

1. Introduïu el nom de l'entitat i trieu la ubicació dels **fitxers de dades**.
   - **Diversos fitxers** .csv o .parquet: navegueu fins a la carpeta arrel, seleccioneu el tipus de patró i introduïu l'expressió.
   - **Fitxers d'un sol .csv o .parquet**: Navegueu fins al fitxer .csv o .parquet i seleccioneu-lo.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Quadre de diàleg per crear una entitat nova amb la ubicació dels fitxers de dades ressaltada.":::

1. Seleccioneu **Desa**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Quadre de diàleg per definir o generar automàticament atributs.":::

1. Seleccioneu **defineix els atributs** per afegir manualment els atributs o seleccioneu **genera'ls** automàticament. Per definir els atributs, introduïu un nom, seleccioneu el format de dades i el tipus semàntic opcional. Per als atributs generats automàticament:

   1. Després de generar els atributs automàticament, seleccioneu **Revisa els atributs**. Es **visualitza la pàgina Administra els atributs**.

   1. Assegureu-vos que el format de les dades sigui correcte per a cada atribut.

   1. Per habilitar l'anàlisi i altres capacitats, seleccioneu **Perfilat de** dades per a tota l'entitat o per a atributs específics. Per defecte, no s'habilita cap entitat per a la perfilació de dades.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Quadre de diàleg per seleccionar l'elaboració de perfils de dades.":::

   1. Seleccioneu **Fet**. Es **visualitza la pàgina Selecciona les** entitats.

1. Continueu afegint entitats i atributs, si escau.

1. Després d'afegir totes les entitats, seleccioneu **Inclou** per incloure les entitats a la font de dades la ingestió.

   :::image type="content" source="media/ADLS_required.png" alt-text="Quadre de diàleg que mostra la clau necessària per a la clau primària":::

1. Per a les entitats seleccionades que requereixen ingestió incremental, **es mostra** a **Actualització incremental**. Per a cadascuna d'aquestes entitats, vegeu [Configurar una actualització incremental per als orígens de dades de l'Azure Data Lake](incremental-refresh-data-sources.md).

1. Per a les entitats seleccionades on no s'ha definit una clau principal, **Es mostra** a **La clau** Principal. Per a cadascuna d'aquestes entitats:
   1. Seleccioneu **Necessari**. Es **mostra el tauler Edita l'entitat**.
   1. Trieu la **clau principal**. La clau principal és un atribut únic a l'entitat. Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls. Els atributs de tipus de dades string, integer i GUID són compatibles com a claus principals.
   1. Opcionalment, canvieu el patró de particions.
   1. Seleccioneu **Tanca** per desar i tancar el plafó.

1. Seleccioneu **Desa**. S'obre **la pàgina Orígens** de dades que mostra la nova font de dades a **l'estat** d'actualització.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Editar un Azure Data Lake Storage font de dades

Podeu actualitzar el *compte Connecta't a l'emmagatzematge mitjançant l'opció*. Per obtenir més informació, vegeu [Connect Customer Insights a un Azure Data Lake Storage compte gen2 amb un principal de servei de](connect-service-principal.md) l'Azure. Per connectar-vos a un contenidor diferent del vostre compte d'emmagatzematge o canviar el nom de compte, [creeu una connexió de font de dades nova](#connect-to-azure-data-lake-storage).

1. Aneu a **Dades** > **Fonts de dades**.

1. Al costat de la font de dades que voleu actualitzar, seleccioneu **Edita**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Quadre de diàleg per editar l'font de dades del llac de dades de l'Azure.":::

1. Canvia qualsevol de les informacions següents:

   - **Descripció**
   - **Connecteu l'emmagatzematge mitjançant** i la informació de connexió. Quan actualitzeu la connexió, no podreu canviar la informació del **Contenidor**.
      > [!NOTE]
      > S'ha d'assignar una de les funcions següents al compte d'emmagatzematge o al contenidor:
        > - Lector de dades de Blob de l'emmagatzematge
        > - Propietari de dades de Blob de l'emmagatzematge
        > - Col·laborador de dades de Blob d'emmagatzematge

   - **Habiliteu l'enllaç** privat si voleu ingerir dades d'un compte d'emmagatzematge a través d'un enllaç privat de l'Azure. Per obtenir més informació, vegeu [Enllaços privats](security-overview.md#private-links-tab).

1. Seleccioneu **Següent**.
1. Canvia qualsevol de les següents:
   - Aneu a un altre fitxer model.json o manifest.json amb un conjunt diferent d'entitats del contenidor.
   - Per afegir entitats addicionals per ingerir, seleccioneu **Entitat nova**.
   - Per suprimir les entitats ja seleccionades si no hi ha dependències, seleccioneu l'entitat i **Suprimeix**.
      > [!IMPORTANT]
      > Si hi ha dependències en el fitxer model.json o manifest.json i el conjunt d'entitats, veureu un missatge d'error i no podreu seleccionar un fitxer model.json o manifest.json diferent. Suprimiu aquestes dependències abans de canviar el fitxer model.json o manifest.json o creeu una font de dades nou amb el fitxer model.json o manifest.json que voleu utilitzar per evitar la supressió de les dependències.
   - Per canviar la ubicació del fitxer de dades o la clau principal, seleccioneu **Edita**.
   - Per canviar les dades d'ingestió incrementals, vegeu [Configurar una actualització incremental per als orígens de dades de l'Azure Data Lake](incremental-refresh-data-sources.md)

1. Seleccioneu **Atributs** per afegir o canviar atributs o per habilitar l'elaboració de perfils de dades. A continuació, seleccioneu **Fet**.

1. Feu clic **a Desa** per aplicar els canvis i tornar a la **pàgina Orígens** de dades.
