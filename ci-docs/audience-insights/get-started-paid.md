---
title: Crear i configurar una llicència de pagament del Customer Insights
description: Passos per obtenir una subscripció amb llicència del Dynamics 365 Customer Insights i configurar-la.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034440"
---
# <a name="get-started-with-a-paid-subscription"></a>Introducció a la subscripció de pagament

En aquest article s'explica com crear un entorn nou després que l'organització compri una subscripció del Dynamics 365 Customer Insights. Si voleu comprar el Customer Insights, les nostres opcions de contacte es mostren al [lloc web del Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Si voleu provar el servei i les característiques, vegeu [Configurar un entorn de prova](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Crear un entorn en una organització existent

Després de comprar una llicència de subscripció per al Customer Insights, l'administrador global de l'inquilí del Microsoft 365 rep un correu electrònic que el convida a crear l'entorn. Aneu a [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) per començar. 

El Customer Insights no té llicència per usuari, de manera que no es mostrarà a l'àrea de Llicències. Si esteu buscant la llicència al Centre d'administració del Microsoft 365, aneu a **Els vostres productes**. 

> [!NOTE]
> Les organitzacions poden crear *dos* entorns per a cada llicència del Customer Insights. Si la vostra organització compra més d'una llicència, poseu-vos en contacte amb el nostre [equip d'assistència tècnica](https://go.microsoft.com/fwlink/?linkid=2079641) per augmentar el nombre d'entorns disponibles. Per obtenir més informació sobre la capacitat i la capacitat de complements, baixeu la [guia de llicències del Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Per crear un entorn:

1. Al quadre de diàleg **Crea un entorn**, seleccioneu **Entorn nou**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diàleg per crear un entorn del Customer Insights nou.":::

   Recomanem començar a configurar un entorn des de zero. Tanmateix, si sou un administrador o un membre d'un entorn de prova, podeu [copiar dades d'un altre entorn](manage-environments.md#copy-the-environment-configuration) bo i triant **Copia d'un entorn existent**. Veureu una llista de tots els entorns disponibles a l'organització des d'on podeu copiar dades.

1. Proporcioneu els següents detalls:
   - **Nom**: el nom de l'entorn en qüestió. Aquest camp ja s'emplena si heu copiat des d'un entorn existent, però es pot canviar.
   - **Regió**: la regió en la qual s'implementa i s'allotja el servei.
   - **Tipus**: seleccioneu si voleu crear un entorn de producció o d'espai aïllat. Els entorns d'espai aïllat no permeten l'actualització planificada de dades i estan destinats a la implementació prèvia i les proves.
   
1. De manera opcional, podeu seleccionar **Configuració avançada**:

   - **Desa totes les dades a**: especifica on voleu emmagatzemar les dades de sortida generades amb el Customer Insights. Hi ha dues opcions: **Emmagatzematge del Customer Insights** (Azure Data Lake administrat per l'equip del Customer Insights) i **Azure Data Lake Storage** (el vostre propi Azure Data Lake Storage). Per defecte, se selecciona l'opció d'emmagatzematge al Customer Insights.

     > [!NOTE]
     > En desar les dades a l'Azure Data Lake Storage, accepteu que les dades es transferiran i s'emmagatzemaran a la ubicació geogràfica adequada per al compte d'emmagatzematge de l'Azure, que pot diferir amb la ubicació on s'emmagatzemen les dades al Dynamics 365 Customer Insights. [Més informació al Centre de confiança de Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Actualment, les entitats ingerides des dels fluxos de dades del Power BI s'emmagatzemen al Data Lake pel Microsoft Dataverse. 
     > 
     > Només admetem els comptes de l'Azure Data Lake Storage de la mateixa regió de l'Azure que heu seleccionat en crear l'entorn. 
     > 
     > Només admetem els comptes de l'Azure Data Lake Storage que tenen habilitat l'espai de noms jeràrquic.


   - Per a l'opció Azure Data Lake Storage, podeu triar entre una opció basada en recursos i una opció basada en subscripció per a l'autenticació. Per obtenir més informació, vegeu [Connectar conclusions del públic amb un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure](connect-service-principal.md). El nom del **contenidor** no es pot canviar i serà `customerinsights`.
   
   - Si voleu utilitzar [models estàndards](predictions-overview.md#out-of-box-models), configurar l'ús compartit de dades amb el Microsoft Dataverse o habilitar la ingesta de dades des de fonts de dades locals, proporcioneu l'adreça URL de l'entorn del Microsoft Dataverse a **Configura l'ús compartit de dades amb el Microsoft Dataverse i habilita les capacitats addicionals**. Seleccioneu **Habilita l'ús compartit de dades** per compartir les dades de sortida del Customer Insights amb el Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - L'ús compartit de dades amb el Microsoft Dataverse Managed Data Lake actualment no s'admet quan deseu totes les dades al vostre propi Azure Data Lake Storage.
     > - [Predicció de valors que falten d'una entitat](predictions.md) actualment no està admès quan habiliteu l'ús compartit de dades amb el Microsoft Dataverse Managed Data Lake.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Opcions de configuració per habilitar l'ús compartit de dades amb el Microsoft Dataverse.":::

   Quan es completen processos del sistema, com ara la ingestió de dades, el sistema crea les carpetes corresponents al compte d'emmagatzematge que heu especificat. Els fitxers de dades i els fitxers model.json es creen i s'afegeixen a carpetes basades en el nom del procés.

   Si creeu diversos entorns del Customer Insights i trieu desar les entitats de sortida d'aquests entorns al vostre compte d'emmagatzematge, es crearan carpetes independents per a cada entorn amb ci_<environmentid> al contenidor.

1. Seleccioneu **Crea** per configurar l'entorn. 

## <a name="configure-an-environment"></a>Configurar un entorn

Reviseu els articles següents per ajudar-vos a començar a configurar el Customer Insights. 

- [Afegiu més usuaris i assigneu permisos](permissions.md).
- [Ingeriu les fonts de dades](data-sources.md) i executeu-les a través del [procés d'unificació de dades](data-unification.md) per obtenir [perfils de client unificats](customer-profiles.md).
- [Enriquir els perfils de client unificats](enrichment-hub.md) o [executar models predictius](predictions-overview.md).
- Creeu [segments](segments.md) per agrupar clients i [mesures](measures.md) per revisar els KPI.
- Configureu [connexions](connections.md) i [exportacions](export-destinations.md) per processar subconjunts de les vostres dades en altres aplicacions.
