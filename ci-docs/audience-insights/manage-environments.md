---
title: Crear i administrar entorns
description: Apreneu a registrar-vos al servei i a administrar entorns.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034165"
---
# <a name="manage-environments"></a>Gestionar entorns

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Canvi d'entorn

Seleccioneu el control **Entorn** a la part superior dreta de la pàgina per canviar d'entorns.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de pantalla del control per canviar d'entorn.":::

Els administradors poden [crear](get-started-paid.md) i administrar entorns.

## <a name="edit-an-existing-environment"></a>Editar un entorn existent

Podeu editar alguns dels detalls dels entorns existents.

1.  Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

2.  Seleccioneu la icona **Edita**.

3. Al quadre **Edita l'entorn**, podeu actualitzar el **nom de visualització** de l'entorn, però no podeu canviar la **regió** ni el **tipus**.

4. Si un entorn està configurat per emmagatzemar dades a l'Azure Data Lake Storage, podeu actualitzar la **Clau de compte**. No obstant això, no podeu canviar el **Nom del compte** ni el del **Contenidor**.

5. Com a alternativa, podeu canviar d'una connexió basada en claus de comptes a una connexió basada en recursos o en subscripcions. Un cop actualitzada, no podreu tornar a la clau de compte després de l'actualització. Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md). Quan actualitzeu la connexió, no podreu canviar la informació del **Contenidor**.

6. O bé, podeu proporcionar una URL d'entorn del Microsoft Dataverse a **Configurar l'ús compartit de dades amb el Microsoft Dataverse i habilitar capacitats addicionals**. Aquestes capacitats utilitzen l'ús compartit de dades amb aplicacions i solucions basades en el Microsoft Dataverse, la ingestió de dades des de fonts de dades locals o [prediccions](predictions.md). Seleccioneu **Habilita l'ús compartit de dades** per compartir les dades de sortida del Customer Insights amb el Microsoft Dataverse Managed Data Lake.

   > [!NOTE]
   > - L'ús compartit de dades amb el Microsoft Dataverse Managed Data Lake actualment no s'admet quan deseu totes les dades al vostre propi Azure Data Lake Storage.
   > - Actualment no s'admeten la [predicció dels valors que falten en una entitat](predictions.md) ni els informes del Power BI Embedded a les conclusions del públic (si estan habilitades al vostre entorn) quan habiliteu l'ús compartit de dades amb el llac de dades administrat pel Microsoft Dataverse.

   Després d'habilitar l'ús compartit de dades amb el Microsoft Dataverse, s'inicia una actualització completa única de les fonts de dades i altres processos. Si actualment els processos s'executen, no veieu l'opció per habilitar l'ús compartit de dades amb el Microsoft Dataverse. Espereu que aquests processos es completin o cancel·lin per habilitar l'ús compartit de dades. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opcions de configuració per habilitar l'ús compartit de dades amb el Microsoft Dataverse.":::
   
   Quan executeu processos, com ara la ingestió de dades o la creació de segments, les carpetes corresponents es crearan al compte d'emmagatzematge que hagueu especificat anteriorment. Els fitxers de dades i els fitxers model.json es crearan i s'afegiran a les subcarpetes respectives, en funció del procés que executeu.

## <a name="copy-the-environment-configuration"></a>Copia la configuració de l'entorn

Quan creeu un entorn nou, podeu triar copiar la configuració des d'un entorn existent. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla de les opcions de configuració de la configuració de l'entorn.":::

Veureu una llista de tots els entorns disponibles a l'organització des d'on podeu copiar dades.

Es copia la configuració següent:

- Fonts de dades ingerides/importades
- Configuració d'unificació de dades (assignar, coincidir, combinar)
- Segments
- Mesures
- Relacions
- Activitats
- Cerca i filtra l'índex
- Destinacions d'exportació
- Actualització planificada
- Enriquiments
- Administració de models
- Assignacions de funcions

Les dades següents *no* es copien:

- Perfils de client.
- Credencials de la font de dades. Haureu de proporcionar les credencials de cada font de dades i actualitzar manualment les fonts de dades.
- Fonts de dades de la carpeta del Common Data Model i el Data Lake administrat pel Dataverse. Haureu de crear aquestes fonts de dades manualment amb el mateix nom que a l'entorn d'origen.

Quan copieu un entorn, veureu un missatge de confirmació que s'ha creat l'entorn nou. Seleccioneu **Ves a les fonts de dades** per veure la llista de fonts de dades.

Totes les fonts de dades mostraran l'estat **Credencials obligatòries**. Editeu les fonts de dades i introduïu les credencials per actualitzar-les.

:::image type="content" source="media/data-sources-copied.png" alt-text="Llista de fonts de dades que s'han copiat i que necessiten autenticació.":::

Després d'actualitzar les fonts de dades, aneu a **Dades** > **Unifica**. Aquí trobareu la configuració de l'entorn d'origen. Editeu-les segons calgui o seleccioneu **Executa** per iniciar el procés d'unificació de dades i crear l'entitat de client unificada.

Quan la unificació de dades hagi finalitzat, aneu a **Mesures** i **Segments** per actualitzar-los també.

## <a name="reset-an-existing-environment"></a>Restablir un entorn existent

Com a administrador, podeu restablir un entorn en estat buit en el cas que vulgueu suprimir totes les configuracions i eliminar la informació ingerida.

1.  Seleccioneu el selector **Entorn** a la capçalera de l'aplicació. 

2.  Seleccioneu l'entorn que voleu restablir i seleccioneu els punts suspensius (**...**). 

3. Trieu l'opció **Reinicialitza**. 

4.  Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Restableix**.

## <a name="delete-an-existing-environment"></a>Suprimir un entorn existent

Com a administrador, podeu suprimir un entorn que administreu.

1.  Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

2.  Seleccioneu l'entorn que voleu restablir i seleccioneu els punts suspensius (**...**). 

3. Trieu l'opció **Suprimeix**. 

4.  Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Suprimeix**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
