---
title: Exportar les dades del Customer Insights a l'Adobe Experience Platform
description: Més informació sobre com utilitzar els segments d'informació sobre el públic a l'Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596257"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Utilitzar els segments del Customer Insights a l'Adobe Experience Platform (versió preliminar)

Com a usuari de la informació sobre el públic del Dynamics 365 Customer Insights, pot ser que hàgiu creat segments per fer que les campanyes de màrqueting siguin més eficients adreçant-vos a públics rellevants. Per utilitzar un segment de la informació sobre el públic a l'Adobe Experience Platform i aplicacions com ara l'Adobe Campaign Standard, heu de seguir alguns passos que s'indiquen en aquest article.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de procés dels passos que es descriuen en aquest article.":::

## <a name="prerequisites"></a>Requisits previs

-   Llicència del Dynamics 365 Customer Insights
-   Llicència de l'Adobe Experience Platform
-   Llicència de l'Adobe Campaign Standard
-   Compte de l'Emmagatzematge blob de l'Azure

## <a name="campaign-overview"></a>Informació general de la campanya

Per comprendre millor com podeu utilitzar els segments de la informació sobre el públic a l'Adobe Experience Platform, plantegem una campanya d'exemple fictícia.

Suposem que la vostra empresa ofereix un servei mensual basat en subscripció als seus clients dels Estats Units. Voleu identificar els clients les subscripcions dels qual s'han de renovar en els propers vuit dies però que encara no han renovat la seva subscripció. Per mantenir aquests clients, heu d'enviar-los una oferta promocional per correu electrònic, mitjançant l'Adobe Experience Platform.

En aquest exemple, volem executar la campanya promocional de correu electrònic d'un cop. En aquest article no es cobreix el cas d'ús de l'execució de la campanya més d'una vegada.

## <a name="identify-your-target-audience"></a>Identificar el públic destinatari

Al nostre escenari, suposem que les adreces electròniques dels clients estan disponibles a la informació sobre el públic i s'han analitzat les seves preferències promocionals per identificar els membres del segment.

El [segment que heu definit a la informació sobre el públic](segments.md) s'anomena **ChurnProneCustomers** i voleu enviar a aquests clients la promoció per correu electrònic.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la pàgina de segments amb el segment ChurnProneCustomers creat.":::

El correu electrònic d'oferta que voleu enviar inclourà el nom, el cognom i la data de finalització de la subscripció del client. Informa els clients sobre el descompte que obtindran si renoven la subscripció abans que finalitzi.

## <a name="export-your-target-audience"></a>Exportar el públic destinatari

Un cop identificat el públic destinatari, podem configurar l'exportació des de la informació sobre el públic a un compte de l'Emmagatzematge blob de l'Azure.

1. A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.

1. A la peça **Emmagatzematge blob de l'Azure**, seleccioneu **Configura**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Peça de configuració de l'Emmagatzematge blob de l'Azure.":::

1. Proporcioneu un **Nom de visualització** per a aquesta nova destinació d'exportació i, a continuació, introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte d'Emmagatzematge blob de l'Azure al qual voleu exportar el segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuració del compte d'emmagatzematge."::: 

   - Per obtenir més informació sobre com trobar el nom i la clau del compte de l'emmagatzematge blob de l'Azure, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).

   - Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccioneu **Següent**.

1. Trieu el segment que voleu exportar. En aquest exemple, és **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfície d'usuari de selecció de segments amb el segment ChurnProneCustomers seleccionat.":::

1. Seleccioneu **Desa**.

Després de desar la destinació de l'exportació, la trobareu a **Administració** > **Exportacions** > **Les meves destinacions d'exportació**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Captura de pantalla amb la llista d'exportacions i alguns segments d'exemple destacats.":::

Ara podeu [exportar el segment a petició](export-destinations.md#export-data-on-demand). L'exportació també s'executarà amb cada [actualització planificada](system.md).

> [!NOTE]
> Assegureu-vos que el nombre de registres del segment exportat es troba dins del límit permès de la llicència de l'Adobe Campaign Standard.

Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge blob de l'Azure que heu configurat anteriorment. Al contenidor es crea automàticament el camí de carpeta següent:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

El *model.json* de les entitats exportades resideix al nivell *%ExportDestinationName%*.

Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir el model de dades d'experiència (XDM) a l'Adobe Experience Platform

Abans que les dades exportades des de la informació sobre el públic es puguin utilitzar a l'Adobe Experience Platform, hem de definir l'esquema del Model de dades d'experiència i [configurar les dades del perfil de client en temps real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Apreneu [què és l'XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i compreneu els [conceptes bàsics de la composició de l'esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importar dades a l'Adobe Experience Platform

Ara que tot està al seu lloc, hem d'importar les dades del públic preparades des de la informació del públic a l'Adobe Experience Platform.

En primer lloc, [creeu una connexió d'origen d'emmagatzematge blob de l'Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Després de definir la connexió d'origen, [configureu un flux de dades](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) per a una connexió per lots d'emmagatzematge en el núvol per importar la sortida del segment de la informació sobre el públic a l'Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Crear un públic a l'Adobe Campaign Standard

Per enviar el correu electrònic d'aquesta campanya, utilitzarem l'Adobe Campaign Standard. Després d'importar les dades a l'Adobe Experience Platform, hem de [crear un públic](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) a l'Adobe Campaign Standard utilitzant les dades de l'Adobe Experience Platform.

Apreneu a [utilitzar el constructor de segments](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) a l'Adobe Campaign Standard per definir un públic a partir de les dades de l'Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear i enviar el correu electrònic mitjançant l'Adobe Campaign Standard

Creeu el contingut del correu electrònic i, a continuació, [proveu i envieu](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) el correu electrònic.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Correu electrònic d'exemple amb oferta de renovació de l'Adobe Campaign Standard.":::