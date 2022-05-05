---
title: Crear entorns al Customer Insights
description: Passos per crear entorns amb una subscripció amb llicència per al Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0efda9d2997bcfd069b6d2445b69d159d7d3e59b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642217"
---
# <a name="create-an-environment-in-customer-insights"></a>Crear un entorn a Customer Insights

En aquest article s'explica com crear un entorn nou després que l'organització compri una subscripció del Dynamics 365 Customer Insights. 

Les organitzacions poden crear diversos entorns per a cada llicència del Customer Insights. Si la vostra organització compra més d'una llicència, [poseu-vos en contacte amb el nostre equip d'assistència](https://go.microsoft.com/fwlink/?linkid=2079641) per augmentar el nombre d'entorns disponibles. Per obtenir més informació sobre la capacitat i la capacitat de complement, reviseu la guia de llicències del [Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Si voleu provar el servei, vegeu [Configurar un entorn de prova](trial-signup.md).

## <a name="create-a-new-environment"></a>Creació d'un entorn nou

Després de comprar una llicència de subscripció per al Customer Insights, l'administrador global de l'inquilí Microsoft 365 rep un correu electrònic que el convida a crear l'entorn. Aneu a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) per començar. 

Una experiència guiada us ajuda a fer els passos necessaris per recopilar tota la informació per a un entorn nou. Necessiteu [permisos](permissions.md) d'administrador al Customer Insights per crear o administrar entorns.

1. Obriu el selector d'entorns i seleccioneu **+ Nou**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleccioneu el selector d'entorn.":::

1. Seguiu l'experiència guiada que es dona a les seccions següents.

### <a name="step-1-provide-environment-information"></a>Pas 1: proporcioneu informació de l'entorn

Al pas **Informació bàsica**, trieu si voleu crear un entorn des de zero o [copiar les dades d'un altre entorn](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diàleg per crear un entorn del Customer Insights nou.":::

Proporcioneu els següents detalls:
   - **Nom**: el nom de l'entorn en qüestió. Aquest camp ja s'emplena si heu copiat des d'un entorn existent, però es pot canviar.
   - **Trieu la vostra empresa**: trieu el públic principal del nou entorn. Podeu treballar amb consumidors individuals (d'empresa a consumidor) o amb [comptes empresarials](work-with-business-accounts.md) (d'empresa a empresa).
   - **Tipus**: seleccioneu si voleu crear un entorn de producció o d'espai aïllat. Els entorns d'espai aïllat no permeten l'actualització planificada de dades i estan destinats a la implementació prèvia i les proves. Els entorns aïllats utilitzen el mateix públic principal que l'entorn de producció seleccionat actualment.
   - **Regió**: la regió en la qual s'implementa i s'allotja el servei.

### <a name="step-2-configure-data-storage"></a>Pas 2: configurar l'emmagatzematge de dades

**Al pas Emmagatzematge de** dades, trieu on emmagatzemar les dades del Customer Insights.

Hi ha dues opcions: **Emmagatzematge del Customer Insights** (Azure Data Lake administrat per l'equip del Customer Insights) i **Azure Data Lake Storage** (el vostre propi Azure Data Lake Storage). Per defecte, se selecciona l'opció d'emmagatzematge al Customer Insights.

:::image type="content" source="media/data-storage-environment.png" alt-text="Trieu el Azure Data Lake Storage per emmagatzemar les vostres dades.":::

En desar les dades a l'Azure Data Lake Storage, accepteu que les dades es transferiran i s'emmagatzemaran a la ubicació geogràfica adequada per a aquest compte d'emmagatzematge de l'Azure. Aquesta ubicació pot diferir d'on s'emmagatzemen les dades al Dynamics 365 Customer Insights. Més informació al [Centre de confiança de Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> El Customer Insights actualment admet els següents serveis:
> - Entitats ingerides de fluxos de dades del Power BI que s'emmagatzemen en un Data Lake administrat pel Microsoft Dataverse.  
> - Els comptes del Azure Data Lake Storage de la mateixa regió de l'Azure que heu seleccionat en crear l'entorn.
> - Azure Data Lake Storage comptes que són Gen2 i tenen *habilitat l'espai de* noms jeràrquic. Els comptes d'emmagatzematge de l'Azure Data Lake Gen1 no són compatibles.

Per a l'opció Azure Data Lake Storage, podeu triar entre una opció basada en recursos i una opció basada en subscripció per a l'autenticació. Per obtenir més informació, vegeu [Connectar-se a un compte de l'Azure Data Lake Storage mitjançant l'entitat de servei de l'Azure](connect-service-principal.md). Un contenidor anomenat `customerinsights` ha d'existir al compte d'emmagatzematge.

Quan es completen processos del sistema, com ara la ingesta de dades, el sistema crea les carpetes corresponents al compte d'emmagatzematge que heu especificat. Els fitxers de dades i els fitxers *model.json* es creen i s'afegeixen a carpetes basades en el nom del procés.

Si creeu diversos entorns del Customer Insights i trieu de desar les entitats de sortida d'aquests entorns al vostre compte d'emmagatzematge, el Customer Insights crea carpetes independents per a cada entorn amb `ci_environmentID` al contenidor.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Pas 3: connectar al Microsoft Dataverse
   
El pas del **Microsoft Dataverse** us permet connectar el Customer Insights al vostre entorn del Dataverse.

Proporcioneu el vostre propi Microsoft Dataverse entorn per compartir dades (perfils i estadístiques) amb aplicacions empresarials basades en, com ara Dataverse el Dynamics 365 Marketing o aplicacions basades en models a Power Apps. Deixeu aquest camp buit si no teniu el vostre propi Dataverse entorn i us en proporcionarem un.

La connexió amb el vostre Dataverse entorn també us [permet ingerir dades de local orígens de dades mitjançant Power Platform fluxos de dades i passarel·les](data-sources.md#add-data-from-on-premises-data-sources). També podeu utilitzar [models](predictions-overview.md?tabs=b2c#out-of-box-models) de predicció des de la caixa connectant-vos a un Dataverse entorn.

> [!IMPORTANT]
> 1. Customer Insights i Dataverse han d'estar a la mateixa regió per habilitar l'ús compartit de dades.
> 1. Heu de tenir una funció d'administrador global a l'entorn Dataverse. Comproveu si aquest [Dataverse entorn està associat](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinats grups de seguretat i assegureu-vos que esteu afegit a aquests grups de seguretat.
> 1. No hi ha cap entorn del Customer Insights existent associat amb aquest Dataverse entorn. Obteniu informació sobre com [podeu suprimir una connexió existent amb un Dataverse entorn](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="l'ús compartit de dades amb Microsoft Dataverse l'automàtic habilitat per a instàncies noves de xarxa.":::

Per obtenir més informació sobre l'habilitació de l'ús compartit Microsoft Dataverse de dades des del vostre, Azure Data Lake Storage vegeu [Connectar-vos a Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

El Customer Insights no admet els escenaris d'ús compartit de dades següents:
- Si habiliteu l'ús compartit de dades amb el Dataverse, no podreu [crear valors previstos o que falten en una entitat](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Pas 4: finalitzar la configuració

Al pas **Revisió**, reviseu totes les opcions de configuració especificades. Quan tot es vegi completat, seleccioneu **Crea** per configurar l'entorn. 

També podeu canviar la majoria de les opcions de configuració més endavant. Per obtenir més informació, vegeu [Administrar entorns](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Treballar amb el nou entorn

Reviseu els articles següents per començar a configurar el Customer Insights: 

- [Afegiu més usuaris i assigneu permisos](permissions.md).
- [Ingeriu les fonts de dades](data-sources.md) i executeu-les a través del [procés d'unificació de dades](data-unification.md) per obtenir [perfils de client unificats](customer-profiles.md).
- [Enriquir els perfils de client unificats](enrichment-hub.md) o [executar models predictius](predictions-overview.md).
- [Creeu segments](segments.md) per agrupar clients i [mesures](measures.md) per revisar els KPI.
- [Configureu connexions](connections.md) i [exportacions](export-destinations.md) per processar subconjunts de les vostres dades en altres aplicacions.