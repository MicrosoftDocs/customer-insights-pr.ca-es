---
title: Creació d'un entorn nou
description: Passos per crear entorns en Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304231"
---
# <a name="create-a-new-environment"></a>Creació d'un entorn nou

Després [de comprar una llicència de subscripció per a Dynamics 365 Customer Insights](paid-license.md), l'administrador global de l'inquilí Microsoft 365 rep un correu electrònic que els convida a crear l'entorn. Aneu a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) per començar. En aquest escenari, comenceu pel [pas 1: proporcioneu informació bàsica](#step-1-provide-basic-information).

Un cop creat el primer entorn, l'administrador global de l'inquilí Microsoft 365 pot [afegir usuaris de la seva organització com a administradors](permissions.md). Aquests administradors poden gestionar usuaris i entorns. Si la vostra organització compra més d'una llicència per al Customer Insights, [poseu-vos en contacte amb el nostre equip d'assistència](https://go.microsoft.com/fwlink/?linkid=2079641) per augmentar el nombre d'entorns disponibles. Per obtenir més informació sobre la capacitat i la capacitat de complement, reviseu la [guia](https://go.microsoft.com/fwlink/?LinkId=866544) de llicències del Dynamics 365. Un cop tingueu la capacitat de crear entorns addicionals, aneu a [Inicia el procés](#start-the-environment-creation-process) de creació de l'entorn.

> [!TIP]
> Si voleu provar el servei, vegeu [Configurar un entorn de prova](trial-signup.md).

## <a name="prerequisites"></a>Requisits previs

[Permisos](permissions.md) d'administrador al Customer Insights

## <a name="start-the-environment-creation-process"></a>Iniciar el procés de creació de l'entorn

1. Obriu el selector d'entorns i seleccioneu **+ Nou**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleccioneu el selector d'entorn.":::

1. Seguiu l'experiència guiada descrita a les seccions següents per proporcionar tota la informació necessària per a un nou entorn.

## <a name="step-1-provide-basic-information"></a>Pas 1: proporcioneu informació bàsica

1. Trieu si voleu crear un entorn des de zero o copiar dades d'un altre entorn. [La còpia de dades d'un altre entorn](#copy-the-environment-configuration) requereix passos addicionals.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diàleg per crear un entorn del Customer Insights nou.":::

1. Proporcioneu els següents detalls:

   - **Nom**: Nom d'aquest entorn. Aquest camp ja s'emplena si heu copiat des d'un entorn existent, però es pot canviar.
   - **Tria la teva empresa**: públic principal de l'entorn nou: consumidors individuals (B-to-C) o [comptes](work-with-business-accounts.md) d'empresa (de B a B). Si la vostra organització fa negocis principalment amb particulars, com ara un minorista o una cafeteria, trieu consumidors individuals. Si el vostre públic principal són altres empreses, com ara un fabricant d'automòbils o una empresa de paper, trieu comptes empresarials.
   - **Tipus**: Tipus d'entorn: producció o sandbox. Els entorns d'espai aïllat no permeten l'actualització planificada de dades i estan destinats a la implementació prèvia i les proves. Els entorns aïllats utilitzen el mateix públic principal que l'entorn de producció seleccionat actualment.
   - **Regió**: Regió en la qual es desplega i s'allotja el servei. Per [utilitzar el vostre propi Azure Data Lake Storage compte](own-data-lake-storage.md) o [connectar-vos a una organització Microsoft Dataverse existent](customer-insights-dataverse.md), l'entorn del Customer Insights ha d'estar a la mateixa regió.

1. Seleccioneu **Següent**.

## <a name="step-2-configure-data-storage"></a>Pas 2: configurar l'emmagatzematge de dades

1. Trieu on voleu emmagatzemar les dades del Customer Insights:

   - **Emmagatzematge** del Customer Insights: l'emmagatzematge de dades es gestiona automàticament. És l'opció predeterminada i, tret que hi hagi requisits específics per emmagatzemar dades al vostre propi compte d'emmagatzematge, us recomanem que utilitzeu aquesta opció.
   - **Azure Data Lake Storage**: El vostre propi Azure Data Lake Storage compte per emmagatzemar les dades de manera que tingueu un control total on s'emmagatzemen les dades. Seguiu els passos de la secció [Utilitza el teu propi Azure Data Lake Storage compte](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Trieu l'opció preferida per emmagatzemar les vostres dades.":::

1. Seleccioneu **Següent**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Pas 3: connectar al Microsoft Dataverse

Si teniu un Dataverse entorn, connecteu el Customer Insights. Compartiu dades per Dataverse utilitzar-les amb aplicacions empresarials basades Dataverse en, com ara el Dynamics 365 Marketing o aplicacions basades en models a Power Apps.

1. Seguiu els passos de [Treballa amb dades del Customer Insights a Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="compartició de dades amb Microsoft Dataverse habilitat automàticament per a entorns nets nous.":::

1. Seleccioneu **Següent**.

## <a name="step-4-finalize-the-settings"></a>Pas 4: finalitzar la configuració

Reviseu la configuració especificada. Quan tot es vegi completat, seleccioneu **Crea** per configurar l'entorn.

Per canviar algunes de les opcions de configuració més endavant, vegeu [Administrar entorns](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Treballar amb el nou entorn

Reviseu els articles següents per començar a configurar el Customer Insights:

- [Afegiu més usuaris i assigneu permisos](permissions.md).
- [Ingeriu les fonts de dades](data-sources.md) i executeu-les a través del [procés d'unificació de dades](data-unification.md) per obtenir [perfils de client unificats](customer-profiles.md).
- [Enriquir els perfils de client unificats](enrichment-hub.md) o [executar models predictius](predictions-overview.md).
- [Creeu segments](segments.md) per agrupar clients i [mesures](measures.md) per revisar els KPI.
- [Configureu connexions](connections.md) i [exportacions](export-destinations.md) per processar subconjunts de les vostres dades en altres aplicacions.

## <a name="copy-the-environment-configuration"></a>Copia la configuració de l'entorn

Com a administrador, si decidiu copiar la configuració d'un entorn existent, seleccioneu de la llista de tots els entorns disponibles de l'organització.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla de les opcions de configuració de la configuració de l'entorn.":::

Es copia la configuració següent:

- Fonts de dades importades mitjançant Power Query
- Configuració d'unificació de dades
- Segments
- Mesures
- Relacions
- Activitats
- Cerca i filtra l'índex
- Exportacions
- Planificació d'actualització
- Enriquiments
- Predicció models
- Assignacions de funcions

### <a name="set-up-a-copied-environment"></a>Configurar un entorn copiat

Quan copieu la configuració de l'entorn, es mostra un missatge de confirmació quan s'ha creat l'entorn copiat. Seguiu els passos següents per confirmar les credencials.

1. Seleccioneu **Ves a les fonts de dades** per veure la llista de fonts de dades. Totes les fonts de dades mostren **credencials Estat obligatori**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Llista de fonts de dades que s'han copiat i que necessiten autenticació.":::

1. Editeu les fonts de dades i introduïu les credencials per actualitzar-les. Fonts de dades de la carpeta Common Data Model i Dataverse s'han de crear manualment amb el mateix nom que a l'entorn d'origen.

1. Després d'actualitzar les fonts de dades, aneu a **Dades** > **Unifica**. Aquí trobareu la configuració de l'entorn d'origen. Editeu-los segons calgui o unifiqueu **Unify** > **perfils de client i dependències** per iniciar el procés d'unificació de dades i crear l'entitat de client unificada.

   > [!TIP]
   > Per a comptes i contactes, seleccioneu **Unificar comptes** > **Unificar perfils i dependències**.

1. Quan s'hagi completat la unificació de dades, aneu a **Mesures** i **segments** per actualitzar-los.

1. Aneu a **Connexions** > **d'administració** per tornar a autenticar les connexions de l'entorn nou.

1. Aneu a **Enriquiment de** > **dades** i **Exportacions** > **de dades** per reactivar-les.

[!INCLUDE [footer-include](includes/footer-banner.md)]
