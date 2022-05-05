---
title: Connectar dades del Common Data Model a un compte de l'Azure Data Lake
description: Treballeu amb dades del Common Data Model mitjançant l'Azure Data Lake Storage.
ms.date: 01/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: eeb6b9d97be5f9c0b9f6cbd6dbc6985559a1cd9d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642268"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Connectar-se a una carpeta del Common Data Model amb un compte de l'Azure Data Lake

En aquest article s'ofereix informació sobre com ingerir dades Dynamics 365 Customer Insights des d'una carpeta del Model de dades comú mitjançant el vostre Azure Data Lake Storage compte Gen2.

## <a name="important-considerations"></a>Consideracions importants

- Les dades de l'Azure Data Lake han de seguir l'estàndard Common Data Model. La resta de formats no s'admeten en aquest moment.

- La ingestió de dades només és compatible amb els comptes d'emmagatzematge *Gen2* de l'Azure Data Lake. No és possible utilitzar comptes d'emmagatzematge Gen1 de l'Azure Data Lake per ingerir dades.

- El compte d'emmagatzematge de l'Azure Data Lake ha de tenir [habilitat l'espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace).

- Per autenticar-vos amb una entitat de servei de l'Azure, assegureu-vos que aquesta s'hagi configurat al vostre inquilí. Per obtenir més informació, vegeu [Connectar-se a un Azure Data Lake Storage compte Gen2 amb un principal de servei de l'Azure](connect-service-principal.md).

- L'Azure Data Lake amb el que us voleu connectar i del que voleu ingerir dades s'ha de trobar a la mateixa regió de l'Azure que l'entorn de Dynamics 365 Customer Insights. No s'admet la connexió a una carpeta del Common Data Model procedent d'un llac de dades d'una regió diferent de l'Azure. Per conèixer la regió de l'Azure de l'entorn, aneu a **AdminSystemAbout** > **·** > **al** Customer Insights.

- Les dades emmagatzemades en els serveis en línia es poden emmagatzemar en una ubicació diferent d'on es processen o emmagatzemen les dades al Dynamics 365 Customer Insights.En importar o connectar-vos a les dades emmagatzemades en serveis en línia, accepteu que les dades es puguin transferir i emmagatzemar amb Dynamics 365 Customer Insights. [Més informació al Microsoft Trust Center](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Connecta't a una carpeta del Common Data Model

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Seleccioneu **Emmagatzematge del llac de dades de l'Azure** i introduïu un **nom** per a la font de dades i, a continuació, seleccioneu **Endavant**.

   - Si se us demana, seleccioneu un dels conjunts de dades d'exemple que pertanyen a la vostra indústria i, a continuació, seleccioneu **Endavant**. 

1. Per a l'autenticació, podeu triar entre utilitzar una opció basada en recursos i una basada en subscripcions. Per obtenir més informació, vegeu [Connectar-se a un Azure Data Lake Storage compte Gen2 amb un principal de servei de l'Azure](connect-service-principal.md). Introduïu l'adreça del **servidor, seleccioneu** Inicia la **sessió i seleccioneu** Endavant **.**
   > [!div class="mx-imgBorder"]
   > ![Quadre de diàleg per introduir nous detalls de connexió a l'Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Necessiteu una de les funcions següents al contenidor o al compte d'emmagatzematge abans descrit per poder connectar-vos i crear una font de dades:
   >  - Lector de dades de Blob de l'emmagatzematge
   >  - Propietari de dades de Blob de l'emmagatzematge
   >  - Col·laborador de dades de Blob d'emmagatzematge

1. Al diàleg **Seleccioneu una carpeta del Common Data Model**, seleccioneu el fitxer model.json o manifest.json del que voleu importar les dades i seleccioneu **Següent**.
   > [!NOTE]
   > Els fitxers model.json o manifest.json associats amb una altra font de dades de l'entorn no es mostraran a la llista.

1. Veureu una llista d'entitats disponibles al fitxer model.json o manifest.json seleccionat. Revisa i selecciona-ho a la llista d'entitats disponibles i selecciona **Desa**. Totes les entitats seleccionades s'ingeriran des de la nova font de dades.
   > [!div class="mx-imgBorder"]
   > ![Quadre de diàleg que mostra una llista d'entitats des d'un fitxer model.json.](media/review-entities.png)

8. Indiqueu quines entitats de dades voleu habilitar l'elaboració de perfils de dades i, a continuació, seleccioneu **Desa**. La generació de perfils de dades habilita les anàlisis i altres capacitats. Podeu seleccionar tota l'entitat, amb la qual cosa se seleccionen tots els atributs de l'entitat, o bé seleccionar determinats atributs de la vostra elecció. Per defecte, no s'habilita cap entitat per a la perfilació de dades.
   > [!div class="mx-imgBorder"]
   > ![Quadre de diàleg on es mostra una perfilació de dades.](media/dataprofiling-entities.png)

9. Després de desar les seleccions, s'obre la pàgina **Fonts de dades**. Ara hauríeu de veure la connexió de la carpeta del Common Data Model com a font de dades.

> [!NOTE]
> Un fitxer model.json o manifest.json només pot associar-se amb una font de dades del mateix entorn. No obstant, un mateix fitxer model.json o manifest.json es pot utilitzar per a fonts de dades de diversos entorns.

## <a name="edit-a-common-data-model-folder-data-source"></a>Editar la font de dades d'una carpeta del Common Data Model

És possible actualitzar la clau d'accés al compte d'emmagatzematge que conté la carpeta del Common Data Model. També podeu canviar el fitxer model.json o manifest.json. Per connectar-vos a un contenidor diferent del vostre compte d'emmagatzematge o canviar el nom de compte, [creeu una connexió de font de dades nova](#connect-to-a-common-data-model-folder).

1. Aneu a **Dades** > **Fonts de dades**.

2. Al costat de la font de dades que voleu actualitzar, seleccioneu els punts suspensius.

3. Seleccioneu l'opció **Edita** de la llista.

4. Opcionalment, actualitzeu la **Clau d'accés** i seleccioneu **Següent**.

   ![Diàleg per editar i actualitzar una clau d'accés per a una font de dades existent.](media/edit-access-key.png)

5. Com a alternativa, podeu actualitzar-la des d'una connexió de clau de compte a una connexió basada en recursos o en subscripcions. Per obtenir més informació, vegeu [Connectar-se a un Azure Data Lake Storage compte Gen2 amb un principal de servei de l'Azure](connect-service-principal.md). Quan actualitzeu la connexió, no podreu canviar la informació del **Contenidor**.
   > [!div class="mx-imgBorder"]

   > ![Quadre de diàleg per introduir els detalls de connexió a l'Azure Data Lake a un compte d'emmagatzematge existent.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Necessiteu una de les funcions següents al contenidor o al compte d'emmagatzematge abans descrit per poder connectar-vos i crear una font de dades:
   >  - Lector de dades de Blob de l'emmagatzematge
   >  - Propietari de dades de Blob de l'emmagatzematge
   >  - Col·laborador de dades de Blob d'emmagatzematge


6. Opcionalment, trieu un fitxer model.json o manifest.json diferent amb un conjunt d'entitats diferent del contenidor.

7. També podeu seleccionar més entitats per ingerir. També podeu suprimir les entitats que ja estan seleccionades si no hi ha cap dependència.

   > [!IMPORTANT]
   > Si hi ha dependències en el fitxer model.json o manifest.json i el conjunt d'entitats, veureu un missatge d'error i no podreu seleccionar un fitxer model.json o manifest.json diferent. Suprimiu aquestes dependències abans de canviar el fitxer model.json o manifest.json o creeu una font de dades nou amb el fitxer model.json o manifest.json que voleu utilitzar per evitar la supressió de les dependències.

8. També podeu seleccionar més atributs o entitats per habilitar-hi la perfilació de dades o inhabilitar els que ja hagueu seleccionat.   


[!INCLUDE [footer-include](includes/footer-banner.md)]