---
title: Connectar dades del Common Data Model a un compte de l'Azure Data Lake
description: Treballeu amb dades del Common Data Model mitjançant l'Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 93871f8029053d4ed4a116d3af3550b7684ee11ea8633e937138245e193a44e6
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033114"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Connectar-se a una carpeta del Common Data Model amb un compte de l'Azure Data Lake

En aquest article es proporciona informació sobre com ingerir dades d'una carpeta del Common Data Model mitjançant el compte Gen2 de l'Azure Data Lake Storage.

## <a name="important-considerations"></a>Consideracions importants

- Les dades de l'Azure Data Lake han de seguir l'estàndard Common Data Model. La resta de formats no s'admeten en aquest moment.

- La ingestió de dades només és compatible amb els comptes d'emmagatzematge *Gen2* de l'Azure Data Lake. No és possible utilitzar comptes d'emmagatzematge Gen1 de l'Azure Data Lake per ingerir dades.

- Per autenticar-vos amb una entitat de servei de l'Azure, assegureu-vos que aquesta s'hagi configurat al vostre inquilí. Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md).

- L'Azure Data Lake amb el que us voleu connectar i del que voleu ingerir dades s'ha de trobar a la mateixa regió de l'Azure que l'entorn de Dynamics 365 Customer Insights. No s'admet la connexió a una carpeta del Common Data Model procedent d'un llac de dades d'una regió diferent de l'Azure. Per conèixer la regió de l'Azure de l'entorn, aneu a **Administració** > **Sistema** > **Quant a** a les conclusions del públic.

- Les dades emmagatzemades als serveis en línia es poden emmagatzemar en una ubicació diferent de la ubicació on es processen o s'emmagatzemen al Dynamics 365 Customer Insights. En importar o connectar-vos a les dades emmagatzemades en un servei en línia, accepteu que les dades es poden transferir i emmagatzemar-se amb el Dynamics 365 Customer Insights.  [Més informació al Centre de confiança de Microsoft](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Connecta't a una carpeta del Common Data Model

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Seleccioneu **Connecta't a una carpeta del Common Data Model**, introduïu un **Nom** per a la font de dades i, a continuació, seleccioneu **Següent**. Directrius del nom: 
   - Comenceu per una lletra.
   - Utilitzeu només lletres i xifres. Els caràcters especials i els espais no estan permesos.
   - Utilitzeu entre 3 i 64 caràcters.

1. Per a l'autenticació, podeu triar entre utilitzar una opció basada en recursos i una basada en subscripcions. Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md). Introduïu la informació del **Contenidor** i seleccioneu **Següent**.
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

1. Obtindreu una llista d'entitats disponibles al fitxer model.json o manifest.json seleccionat. Podeu revisar i seleccionar a la llista d'entitats disponibles i seleccioneu **Desa**. Totes les entitats seleccionades s'ingeriran des de la nova font de dades.
   > [!div class="mx-imgBorder"]
   > ![Quadre de diàleg que mostra una llista d'entitats des d'un fitxer model.json.](media/review-entities.png)

8. Indiqueu per a quines entitats de dades voleu habilitar la perfilació de dades i seleccioneu **Desa**. La generació de perfils de dades habilita les anàlisis i altres capacitats. Podeu seleccionar tota l'entitat, amb la qual cosa se seleccionen tots els atributs de l'entitat, o bé seleccionar determinats atributs de la vostra elecció. Per defecte, no s'habilita cap entitat per a la perfilació de dades.
   > [!div class="mx-imgBorder"]
   > ![Quadre de diàleg on es mostra una perfilació de dades.](media/dataprofiling-entities.png)

9. Després de desar les seleccions, s'obre la pàgina **Fonts de dades**. Ara hauríeu de veure la connexió de la carpeta del Common Data Model com a font de dades.

> [!NOTE]
> Un fitxer model.json o manifest.json només pot associar-se amb una font de dades del mateix entorn. No obstant, un mateix fitxer model.json o manifest.json es pot utilitzar per a fonts de dades de diversos entorns.

## <a name="edit-a-common-data-model-folder-data-source"></a>Editar la font de dades d'una carpeta del Common Data Model

És possible actualitzar la clau d'accés al compte d'emmagatzematge que conté la carpeta del Common Data Model. També podeu canviar el fitxer model.json o manifest.json. Per connectar-vos a un contenidor diferent del vostre compte d'emmagatzematge o canviar el nom de compte, [creeu una connexió de font de dades nova](#connect-to-a-common-data-model-folder).

1. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.

2. Al costat de la font de dades que voleu actualitzar, seleccioneu els punts suspensius.

3. Seleccioneu l'opció **Edita** de la llista.

4. Opcionalment, actualitzeu la **Clau d'accés** i seleccioneu **Següent**.

   ![Diàleg per editar i actualitzar una clau d'accés per a una font de dades existent.](media/edit-access-key.png)

5. Com a alternativa, podeu actualitzar-la des d'una connexió de clau de compte a una connexió basada en recursos o en subscripcions. Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md). Quan actualitzeu la connexió, no podreu canviar la informació del **Contenidor**.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]