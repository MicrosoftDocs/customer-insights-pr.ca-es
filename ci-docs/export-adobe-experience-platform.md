---
title: Exportar dades del Customer Insights a l'Adobe Experience Platform
description: Obteniu informació sobre com podeu utilitzar els segments del Customer Insights al Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 42a4e0c6bce67a63b449a541299620ef2f4a3259
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642395"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Utilitzar segments del Customer Insights a l'Adobe Experience Platform (versió preliminar)

Com a usuari de Dynamics 365 Customer Insights, és possible que hàgiu creat segments per fer que les vostres campanyes de màrqueting siguin més eficients orientant-vos a públics rellevants. Per utilitzar un segment del Customer Insights i d'aplicacions Adobe Experience Platform com Adobe Campaign Standard, heu de seguir alguns passos que s'indiquen en aquest article.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de procés dels passos que es descriuen en aquest article.":::

## <a name="prerequisites"></a>Requisits previs

-   Llicència del Dynamics 365 Customer Insights
-   Llicència del Adobe Experience Platform
-   Llicència de l'Adobe Campaign Standard
-   Compte de l'Emmagatzematge blob de l'Azure

## <a name="campaign-overview"></a>Informació general de la campanya

Per entendre millor com podeu utilitzar els segments de Customer Insights al Adobe Experience Platform, vegem una campanya d'exemple fictícia.

Suposem que la vostra empresa ofereix un servei mensual basat en subscripció als seus clients dels Estats Units. Voleu identificar els clients les subscripcions dels qual s'han de renovar en els propers vuit dies però que encara no han renovat la seva subscripció. Per mantenir aquests clients, us recomanem que els envieu una oferta promocional per correu electrònic mitjançant l'Adobe Experience Platform.

En aquest exemple, volem executar la campanya promocional de correu electrònic d'un cop. En aquest article no es cobreix el cas d'ús de l'execució de la campanya més d'una vegada.

## <a name="identify-your-target-audience"></a>Identificar el públic destinatari

En el nostre escenari, assumim que les adreces de correu electrònic dels clients estan disponibles a Customer Insights i s'han analitzat les seves preferències promocionals per identificar els membres del segment.

El [segment que heu definit a Customer Insights](segments.md) s'anomena **ChurnProneCustomers** i teniu previst enviar a aquests clients la promoció de correu electrònic.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la pàgina de segments amb el segment ChurnProneCustomers creat.":::

El correu electrònic d'oferta que voleu enviar inclourà el nom, el cognom i la data de finalització de la subscripció del client. Informa els clients sobre el descompte que obtindran si renoven la subscripció abans que finalitzi.

## <a name="export-your-target-audience"></a>Exportar el públic destinatari

Amb el nostre públic objectiu identificat, podem configurar l'exportació de Customer Insights a un compte d'emmagatzematge blob de l'Azure.

### <a name="configure-a-connection"></a>Configurar una connexió

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Emmagatzematge de blob de l'Azure** o seleccioneu **Configura** a la peça **Emmagatzematge de blob de l'Azure** per configurar la connexió.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Peça de configuració de l'Emmagatzematge blob de l'Azure."::: 

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte d'emmagatzematge blob al qual voleu exportar el segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuració del compte d'emmagatzematge."::: 
   
    - Per obtenir més informació sobre com trobar el compte i la clau del compte de l'emmagatzematge blob, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).
    - Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccioneu **Desa** per completar la connexió. 

### <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió a la secció Emmagatzematge blob de l'Azure. Si no veieu aquest nom de secció, no hi ha disponible cap connexió d'aquest tipus.

1. Trieu el segment que voleu exportar. En aquest exemple, és **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfície d'usuari de selecció de segments amb el segment ChurnProneCustomers seleccionat.":::

1. Seleccioneu **Desa**.

Després de desar la destinació d'exportació, la trobeu a **Dades** > **Exportacions**.

Ara podeu [exportar el segment a petició](export-destinations.md#run-exports-on-demand). L'exportació també s'executarà amb cada [actualització planificada](system.md).

> [!NOTE]
> Assegureu-vos que el nombre de registres del segment exportat es troba dins del límit permès de la llicència de l'Adobe Campaign Standard.

Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge blob de l'Azure que heu configurat anteriorment. Al contenidor es crea automàticament el camí de carpeta següent:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

El *model.json* de les entitats exportades resideix al nivell *%ExportDestinationName%*.

Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir el model de dades d'experiència (XDM) a l'Adobe Experience Platform

Abans que les dades exportades del Customer Insights es puguin utilitzar al Adobe Experience Platform, hem de definir l'esquema Model de dades d'experiència i [configurar les dades per al perfil de client en temps real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Apreneu [què és l'XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i compreneu els [conceptes bàsics de la composició de l'esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importeu dades al Adobe Experience Platform

Ara que tot està al seu lloc, hem d'importar les dades de públic preparades de Customer Insights a Adobe Experience Platform.

En primer lloc, [creeu una connexió d'origen d'emmagatzematge blob de l'Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Després de definir la connexió d'origen, [configureu un flux de](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) dades per a una connexió per lots d'emmagatzematge en el núvol per importar la sortida del segment de Customer Insights a Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Crear un públic a l'Adobe Campaign Standard

Per enviar el correu electrònic per a aquesta campanya, utilitzarem l'Adobe Campaign Standard. Després d'importar les dades a l'Adobe Experience Platform, hem de [crear un públic](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) a l'Adobe Campaign Standard amb les dades de l'Adobe Experience Platform.


Obteniu informació sobre com [utilitzar el creador de segments](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) a l'Adobe Campaign Standard per definir un públic basat en les dades de l'Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear i enviar el correu electrònic amb l'Adobe Campaign Standard

Creeu el contingut del correu electrònic i, a continuació, [proveu i envieu](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) el correu electrònic.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Correu electrònic d'exemple amb oferta de renovació de l'Adobe Campaign Standard.":::
