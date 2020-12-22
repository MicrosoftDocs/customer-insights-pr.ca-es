---
title: Crear i administrar entorns
description: Apreneu a registrar-vos al servei i a administrar entorns.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644121"
---
# <a name="manage-environments"></a>Gestionar entorns

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

En aquest article s'explica com crear una organització nova i com proveir un entorn.

## <a name="sign-up-and-create-an-organization"></a>Registrar-se i crear una organització

1. Aneu al lloc web del [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Seleccioneu **Introducció**.

3. Trieu l'escenari preferit de registre i seleccioneu l'enllaç corresponent.

4. Accepteu els termes i condicions i seleccioneu **Continua** per començar a crear l'organització.

5. Després de crear l'entorn, se us redirigirà al [Customer Insights](https://home.ci.ai.dynamics.com).

6. Utilitzeu l'entorn de demostració per explorar l'aplicació o creeu un entorn nou amb els passos de la secció següent.

7. Després d'especificar la configuració de l'entorn, seleccioneu **Crea**.

8. Un cop creat correctament l'entorn, s'iniciarà la vostra sessió.

## <a name="create-an-environment-in-an-existing-organization"></a>Crear un entorn en una organització existent

Hi ha dues maneres de crear un nou entorn. Podeu especificar una configuració completament nova o bé podeu copiar alguns ajustaments de configuració des d'un entorn existent.

Per crear un entorn:

1. Seleccioneu el símbol **Configuració** a la capçalera de l'aplicació.

1. Seleccioneu **Nou entorn**.

   > [!div class="mx-imgBorder"]
   > ![Configuració de l'entorn](media/environment-settings-dialog.png)

1. En el diàleg **Crea un nou entorn**, seleccioneu **Nou entorn**.

   Si voleu [copiar les dades de l'entorn actual](#additional-considerations-for-copy-configuration-preview), seleccioneu **Copia d'un entorn existent**. Veureu una llista de tots els entorns disponibles a l'organització des d'on podeu copiar dades.

1. Proporcioneu els següents detalls:
   - **Nom**: el nom de l'entorn en qüestió. Aquest camp ja s'emplena si heu copiat des d'un entorn existent, però es pot canviar.
   - **Regió**: la regió en la qual s'implementa i s'allotja el servei.
   - **Tipus**: seleccioneu si voleu crear un entorn de producció o espai aïllat.

2. De manera opcional, podeu seleccionar **Configuració avançada**:

   - **Desa totes les dades a**: especifica on voleu emmagatzemar les dades de sortida generades amb el Customer Insights. Tindreu dues opcions: **Emmagatzematge del Customer Insights** (un Azure Data Lake gestionat per l'equip del Customer Insights) i **Azure Data Lake Storage Gen2** (el vostre propi Azure Data Lake Storage). Per defecte, se selecciona l'opció d'emmagatzematge al Customer Insights.

   > [!NOTE]
   > En desar les dades a l'Azure Data Lake Storage, accepteu que les dades es transferiran i s'emmagatzemaran a la ubicació geogràfica adequada per al compte d'emmagatzematge de l'Azure, que pot diferir amb la ubicació on s'emmagatzemen les dades al Dynamics 365 Customer Insights. [Més informació al Centre de confiança de Microsoft.](https://www.microsoft.com/trust-center)
   >
   > Actualment, les entitats ingerides sempre s'emmagatzemen al llac de dades gestionat pel Customer Insights.
   > Només s'admeten comptes d'emmagatzematge Gen2 de l'Azure Data Lake de la mateixa regió de l'Azure que la que vau seleccionar en crear l'entorn.
   > Només admetem comptes d'emmagatzematge de l'Azure Data Lake gen2 habilitats per a l'espai de noms jeràrquic (HNS).

   - En el caso de l'opció Gen2 de l'Azure Data Lake Storage, podeu triar entre utilitzar una opció basada en recursos i una basada en subscripcions per a l'autenticació. Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md). El nom del **Contenidor** no es pot canviar i serà "customerinsights".
   
   - Si voleu utilitzar [prediccions](predictions.md), introduïu l'adreça URL de la instància del Common Data Service al camp **Adreça del servidor** a **Utilitza les prediccions**.

   Quan executeu processos, com ara la ingestió de dades o la creació de segments, les carpetes corresponents es crearan al compte d'emmagatzematge que hagueu especificat anteriorment. Els fitxers de dades i els fitxers model.json es crearan i s'afegiran a les respectives subcarpetes en funció del procés que executeu.

   Si creeu diversos entorns del Customer Insights i trieu desar les entitats de sortida d'aquests entorns al vostre compte d'emmagatzematge, es crearan carpetes independents per a cada entorn amb ci_<environmentid> al contenidor.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Consideracions addicionals per a la configuració de la còpia (versió preliminar)

Es copia la configuració següent:

- Configuracions de característiques
- Fonts de dades importades o ingerides
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

*No* es copia la configuració següent:

- Perfils de client.
- Credencials de la font de dades. Haureu de proporcionar les credencials de cada font de dades i actualitzar manualment les fonts de dades.
- Fonts de dades de la carpeta del Common Data Model i un llac administrat del Common Data Service. Haureu de crear aquestes fonts de dades manualment amb el mateix nom que a l'entorn d'origen.

Quan copieu un entorn, veureu un missatge de confirmació que s'ha creat l'entorn nou. Seleccioneu **Ves a les fonts de dades** per veure la llista de fonts de dades.

Totes les fonts de dades mostraran l'estat **Credencials obligatòries**. Editeu les fonts de dades i introduïu les credencials per actualitzar-les.

> [!div class="mx-imgBorder"]
> ![Fonts de dades copiades](media/data-sources-copied.png)

Després d'actualitzar les fonts de dades, aneu a **Dades** > **Unifica**. Aquí trobareu la configuració de l'entorn d'origen. Editeu-les segons calgui o seleccioneu **Executa** per iniciar el procés d'unificació de dades i crear l'entitat de client unificada.

Quan la unificació de dades hagi finalitzat, aneu a **Mesures** i **Segments** per actualitzar-los també.

## <a name="edit-an-existing-environment"></a>Editar un entorn existent

Podeu editar alguns dels detalls dels entorns existents.

1. Aneu a **Administració** > **Sistema** > **Quant a**.

2. Seleccioneu **Editar**.

3. Podeu actualitzar el **Nom de visualització** de l'entorn, però no podeu canviar la **Regió** ni el **Tipus**.

4. Si es configura un entorn per emmagatzemar dades a l'Azure Data Lake Storage Gen2, podeu actualitzar la **Clau del compte**. No obstant això, no podeu canviar el **Nom del compte** ni el del **Contenidor**.

5. Com a alternativa, podeu canviar d'una connexió basada en claus de comptes a una connexió basada en recursos o en subscripcions. Un cop actualitzada, no podreu tornar a la clau de compte després de l'actualització. Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md). Quan actualitzeu la connexió, no podreu canviar la informació del **Contenidor**.

## <a name="reset-an-existing-environment"></a>Restablir un entorn existent

Podeu restablir un entorn en estat buit en el cas que vulgueu suprimir totes les configuracions i eliminar la informació ingerida.

1.  Aneu a **Administració** > **Sistema** > **Quant a**.

2.  Seleccioneu **Restableix**. 

3.  Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Restableix**.


## <a name="delete-an-existing-environment"></a>Suprimir un entorn existent

1. Aneu a **Administració** > **Sistema** > **Quant a**.

1. Seleccioneu **Suprimeix**.

1. Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Suprimeix**.
