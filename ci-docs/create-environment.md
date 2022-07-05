---
title: 'Com: Crear un nou entorn'
description: Passos per crear entorns al Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 62969527ceed906ff06fb9be90b972496323ce0a
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052733"
---
# <a name="how-to-create-a-new-environment"></a>Com: Crear un nou entorn

Després [de comprar una llicència de subscripció per a Dynamics 365 Customer Insights](paid-license.md), l'administrador global de l'inquilí Microsoft 365 rep un correu electrònic que els convida a crear l'entorn. Aneu a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) per començar. En aquest escenari, podeu anar directament al [pas 1: proporcioneu informació bàsica](#step-1-provide-basic-information).

Després de crear el primer entorn, l'administrador global de l'inquilí Microsoft 365 pot [afegir usuaris de la seva organització com a administradors](permissions.md). A partir d'ara, aquests administradors poden gestionar usuaris i entorns. Si la vostra organització compra més d'una llicència per al Customer Insights, [poseu-vos en contacte amb el nostre equip](https://go.microsoft.com/fwlink/?linkid=2079641) d'assistència per augmentar el nombre d'entorns disponibles. Per obtenir més informació sobre la capacitat i la capacitat de complement, reviseu la guia [de llicències del](https://go.microsoft.com/fwlink/?LinkId=866544) Dynamics 365.

> [!TIP]
> Si voleu provar el servei, vegeu [Configurar un entorn de prova](trial-signup.md).

## <a name="prerequisites"></a>Requisits previs

Necessiteu [permisos](permissions.md) d'administrador al Customer Insights per crear o administrar entorns.

## <a name="start-the-environment-creation-process"></a>Iniciar el procés de creació de l'entorn

1. Obriu el selector d'entorns i seleccioneu **+ Nou**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleccioneu el selector d'entorn.":::

1. Seguiu l'experiència guiada descrita a les seccions següents per proporcionar tota la informació necessària per a un entorn nou. Si heu configurat un entorn abans, també [podeu copiar la configuració](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Pas 1: Proporcioneu informació bàsica

Al pas **Informació bàsica**, trieu si voleu crear un entorn des de zero o [copiar les dades d'un altre entorn](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diàleg per crear un entorn del Customer Insights nou.":::

Proporcioneu els següents detalls:

- **Nom**: el nom de l'entorn en qüestió. Aquest camp ja s'emplena si heu copiat des d'un entorn existent, però es pot canviar.
- **Trieu la vostra empresa**: trieu el públic principal del nou entorn. Podeu treballar amb consumidors individuals (d'empresa a consumidor) o amb [comptes empresarials](work-with-business-accounts.md) (d'empresa a empresa). Si la vostra organització fa negocis principalment amb individus, com ara un minorista o una cafeteria, trieu consumidors individuals. En cas que el vostre públic principal siguin altres empreses, com ara un fabricant d'automòbils o una empresa de paper, trieu comptes d'empresa.
- **Tipus**: seleccioneu si voleu crear un entorn de producció o d'espai aïllat. Els entorns d'espai aïllat no permeten l'actualització planificada de dades i estan destinats a la implementació prèvia i les proves. Els entorns aïllats utilitzen el mateix públic principal que l'entorn de producció seleccionat actualment.
- **Regió**: la regió en la qual s'implementa i s'allotja el servei. Per [utilitzar el vostre propi Azure Data Lake Storage compte](own-data-lake-storage.md) o [connectar-vos a una organització Microsoft Dataverse existent](customer-insights-dataverse.md), l'entorn del Customer Insights ha d'estar a la mateixa regió.

## <a name="step-2-configure-data-storage"></a>Pas 2: configurar l'emmagatzematge de dades

**Al pas Emmagatzematge de** dades, trieu on emmagatzemar les dades del Customer Insights.

Hi ha dues opcions que pots triar:

- **Emmagatzematge** del Customer Insights: l'equip de Customer Insights gestiona l'emmagatzematge de dades. És l'opció predeterminada i, tret que hi hagi requisits específics per emmagatzemar dades al vostre propi compte d'emmagatzematge, us recomanem que utilitzeu aquesta opció.
- **Azure Data Lake Storage**: especifiqueu el vostre propi Azure Data Lake Storage compte per emmagatzemar les dades perquè tingueu un control total on s'emmagatzemen les dades. Per obtenir més informació, consulta [Utilitzar el teu propi Azure Data Lake Storage compte](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Trieu l'opció preferida per emmagatzemar les vostres dades.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Pas 3: connectar al Microsoft Dataverse

El pas del **Microsoft Dataverse** us permet connectar el Customer Insights al vostre entorn del Dataverse. Compartiu dades per Dataverse utilitzar-les amb aplicacions empresarials basades en Dataverse, com ara el Dynamics 365 Marketing o les aplicacions basades en models a Power Apps.


Deixeu aquest camp buit si no teniu el vostre propi Dataverse entorn i en crearem un per a vosaltres.

Per obtenir més informació, vegeu [Treballar amb les dades del Customer Insights al Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="l'ús compartit de dades amb Microsoft Dataverse l'habilitació automàtica per a entorns nous de xarxa.":::

### <a name="step-4-finalize-the-settings"></a>Pas 4: finalitzar la configuració

**Al pas Revisa**, passem per tota la configuració especificada. Quan tot es vegi completat, seleccioneu **Crea** per configurar l'entorn.

Podeu canviar part de la configuració més endavant. Per obtenir més informació, vegeu [Administrar entorns](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Treballar amb el nou entorn

Reviseu els articles següents per començar a configurar el Customer Insights:

- [Afegiu més usuaris i assigneu permisos](permissions.md).
- [Ingeriu les fonts de dades](data-sources.md) i executeu-les a través del [procés d'unificació de dades](data-unification.md) per obtenir [perfils de client unificats](customer-profiles.md).
- [Enriquir els perfils de client unificats](enrichment-hub.md) o [executar models predictius](predictions-overview.md).
- [Creeu segments](segments.md) per agrupar clients i [mesures](measures.md) per revisar els KPI.
- [Configureu connexions](connections.md) i [exportacions](export-destinations.md) per processar subconjunts de les vostres dades en altres aplicacions.

## <a name="copy-the-environment-configuration"></a>Copia la configuració de l'entorn

Com a administrador, podeu triar copiar la configuració des d'un entorn existent quan en creeu un de nou.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla de les opcions de configuració de la configuració de l'entorn.":::

Veureu una llista de tots els entorns disponibles a l'organització des d'on podeu copiar dades.

Es copia la configuració següent:

- Orígens de dades importats a través de Power Query
- Configuració de la unificació de dades
- Segments
- Mesures
- Relacions
- Activitats
- Cerca i filtra l'índex
- Exportacions
- Planificació d'actualització
- Enriquiments
- Models predicció
- Assignacions de funcions

## <a name="set-up-a-copied-environment"></a>Configurar un entorn copiat

Quan copieu la configuració de l'entorn, heu de passar per alguns passos addicionals per confirmar les credencials:

- Perfils de client. En primer lloc, autenticeu i ingerireu les vostres fonts de dades i executeu la unificació de dades per tornar a crear els perfils de client.
- Credencials de la font de dades. Heu de proporcionar les credencials per a cada font de dades per autenticar i actualitzar les fonts de dades manualment.
- Orígens de dades de la carpeta Common Data Model i Dataverse. Heu de crear aquestes fonts de dades manualment amb el mateix nom que a l'entorn d'origen.
- Secrets de connexió que s'utilitzen per a exportacions i enriquiments. Cal reautenticar les connexions i després reactivar els enriquiments i les exportacions.

Veureu un missatge de confirmació quan s'hagi creat l'entorn copiat. Seleccioneu **Ves a les fonts de dades** per veure la llista de fonts de dades.

Totes les fonts de dades mostraran l'estat **Credencials obligatòries**. Editeu les fonts de dades i introduïu les credencials per actualitzar-les.

:::image type="content" source="media/data-sources-copied.png" alt-text="Llista de fonts de dades que s'han copiat i que necessiten autenticació.":::

Després d'actualitzar les fonts de dades, aneu a **Dades** > **Unifica**. Aquí trobareu la configuració de l'entorn d'origen. Editeu-les segons calgui o seleccioneu **Executa** per iniciar el procés d'unificació de dades i crear l'entitat de client unificada.

Quan la unificació de dades hagi finalitzat, aneu a **Mesures** i **Segments** per actualitzar-los també.

Abans de reactivar les exportacions i els enriquiments, aneu a **Connexions** > **d'administració** per tornar a autenticar les connexions del vostre entorn nou.

[!INCLUDE [footer-include](includes/footer-banner.md)]
