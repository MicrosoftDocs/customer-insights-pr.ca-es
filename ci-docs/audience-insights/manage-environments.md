---
title: Crear i administrar entorns
description: Apreneu a registrar-vos al servei i a administrar entorns.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 309b2a900e50727ffa655fc6b5fe728ea55ba5bf
ms.sourcegitcommit: 626d485dae1e001e63e4d4bf78f6770766822ba0
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/06/2021
ms.locfileid: "7892372"
---
# <a name="manage-environments"></a>Gestionar entorns

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Canvi d'entorn

Seleccioneu el control **Entorn** a la part superior dreta de la pàgina per canviar d'entorns.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de pantalla del control per canviar d'entorn.":::

Els administradors poden [crear](create-environment.md) i administrar entorns.

## <a name="edit-an-existing-environment"></a>Editar un entorn existent

Podeu editar alguns dels detalls dels entorns existents.

1.  Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

2.  Seleccioneu la icona **Edita**.

3. Al quadre **Edita l'entorn** podeu actualitzar la configuració de l'entorn.

Per obtenir més informació sobre la configuració de l'entorn, vegeu [Crear un entorn nou](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Connectar a l’Microsoft Dataverse
   
El pas del **Microsoft Dataverse** us permet connectar el Customer Insights al vostre entorn del Dataverse.

Per utilitzar [models de predicció estàndard](predictions-overview.md#out-of-box-models) , configureu l'ús compartit de dades amb el Dataverse. O podeu habilitar la ingesta de dades des de fonts de dades locals, proporcionant l'adreça URL de l'entorn del Microsoft Dataverse que administra l'organització. Seleccioneu **Habilita l'ús compartit de dades** per compartir les dades de sortida del Customer Insights amb el llac de dades administrat del Dataverse.

> [!IMPORTANT]
> Customer Insights i Dataverse han d'estar a la mateixa regió per habilitar l'ús compartit de dades.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Opcions de configuració per habilitar l'ús compartit de dades amb el Microsoft Dataverse.":::

> [!NOTE]
> El Customer Insights no admet els escenaris d'ús compartit de dades següents:
> - Si deseu totes les dades al vostre propi Azure Data Lake Storage, no podreu habilitar l'ús compartit de dades amb un llac de dades administrat pel Dataverse .
> - Si habiliteu l'ús compartit de dades amb el Dataverse, no podreu [crear valors previstos o que falten en una entitat](predictions.md).

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

- Fonts de dades de la carpeta del Model de dades comú i del llac de dades administrat pel Dataverse. Haureu de crear aquestes fonts de dades manualment amb el mateix nom que a l'entorn d'origen.

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
