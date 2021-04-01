---
title: Exportar les dades del Customer Insights a l'Adobe Campaign Standard
description: Més informació sobre com utilitzar els segments d'informació sobre el públic a l'Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596303"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Utilitzar els segments del Customer Insights a l'Adobe Campaign Standard (versió preliminar)

Com a usuari de la informació sobre el públic del Dynamics 365 Customer Insights, pot ser que hàgiu creat segments per fer que les campanyes de màrqueting siguin més eficients adreçant-vos a públics rellevants. Per utilitzar un segment de la informació sobre el públic a l'Adobe Experience Platform i aplicacions com ara l'Adobe Campaign Standard, heu de seguir alguns passos que s'indiquen en aquest article.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de procés dels passos que es descriuen en aquest article.":::

## <a name="prerequisites"></a>Requisits previs

-   Llicència del Dynamics 365 Customer Insights
-   Llicència de l'Adobe Campaign Standard
-   Compte de l'Emmagatzematge blob de l'Azure

## <a name="campaign-overview"></a>Informació general de la campanya

Per comprendre millor com podeu utilitzar els segments de la informació sobre el públic a l'Adobe Experience Platform, plantegem una campanya d'exemple fictícia.

Suposem que la vostra empresa ofereix un servei mensual basat en subscripció als seus clients dels Estats Units. Voleu identificar els clients les subscripcions dels qual s'han de renovar en els propers vuit dies però que encara no han renovat la seva subscripció. Per mantenir aquests clients, heu d'enviar-los una oferta promocional per correu electrònic, mitjançant l'Adobe Campaign Standard.

En aquest exemple, volem executar la campanya promocional de correu electrònic d'un cop. En aquest article no es cobreix el cas d'ús de l'execució de la campanya més d'una vegada. No obstant això, la informació sobre el públic i l'Adobe Campaign Standard es poden configurar per treballar també per a un escenari de campanya periòdica.

## <a name="identify-your-target-audience"></a>Identificar el públic destinatari

Al nostre escenari, suposem que les adreces electròniques dels clients estan disponibles a la informació sobre el públic i s'han analitzat les seves preferències promocionals per identificar els membres del segment.

El [segment que heu definit a la informació sobre el públic](segments.md) s'anomena **ChurnProneCustomers** i voleu enviar a aquests clients la promoció per correu electrònic.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la pàgina de segments amb el segment ChurnProneCustomers creat.":::

El correu electrònic d'oferta que voleu enviar inclourà el nom, el cognom i la data de finalització de la subscripció del client. Informa els clients sobre el descompte que obtindran si renoven la subscripció abans que finalitzi.

## <a name="export-your-target-audience"></a>Exportar el públic destinatari

Un cop identificat el públic destinatari, podem configurar l'exportació des de la informació sobre el públic a un compte de l'Emmagatzematge blob de l'Azure.

1. A les conclusions del públic, aneu a **Administració** > **Destinacions d'exportació**.

1. A la peça **Adobe Campaign**, seleccioneu **Configura**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Peça de configuració per a l'Adobe Campaign Standard.":::

1. Proporcioneu un **Nom de visualització** per a aquesta nova destinació d'exportació i, a continuació, introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte d'Emmagatzematge blob de l'Azure al qual voleu exportar el segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuració del compte d'emmagatzematge."::: 

   - Per obtenir més informació sobre com trobar el nom i la clau del compte de l'emmagatzematge blob de l'Azure, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).

   - Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccioneu **Següent**.

1. Trieu el segment que voleu exportar. En aquest exemple, és **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfície d'usuari de selecció de segments amb el segment ChurnProneCustomers seleccionat.":::

1. Seleccioneu **Següent**.

1. Ara assignem els camps **Origen** del segment d'informació del públic als noms de camp de **Destinació** de l'esquema de perfils de l'Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Assignació de camps per al connector de l'Adobe Campaign Standard.":::

   Si voleu afegir més atributs, seleccioneu **Afegeix un atribut**. El nom de destinació pot ser diferent del nom del camp d'origen per tal que pugueu assignar la sortida del segment de la informació del públic a l'Adobe Campaign Standard encara que els camps no tinguin el mateix nom als dos sistemes.

   > [!NOTE]
   > L'adreça electrònica s'utilitza com a camp d'identitat, però podeu utilitzar qualsevol altre identificador del perfil del client de la informació del públic per assignar dades a l'Adobe Campaign Standard.

1. Seleccioneu **Desa**.

Després de desar la destinació de l'exportació, la trobareu a **Administració** > **Exportacions** > **Les meves destinacions d'exportació**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Captura de pantalla amb la llista d'exportacions i alguns segments d'exemple destacats.":::

Ara podeu [exportar el segment a petició](export-destinations.md#export-data-on-demand). L'exportació també s'executarà amb cada [actualització planificada](system.md).

> [!NOTE]
> Assegureu-vos que el nombre de registres del segment exportat es troba dins del límit permès de la llicència de l'Adobe Campaign Standard.

Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge blob de l'Azure que heu configurat anteriorment. Al contenidor es crea automàticament el camí de carpeta següent:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurar l'Adobe Campaign Standard

Quan s'exporta un segment de la informació del públic, conté les columnes que heu seleccionat en definir la destinació d'exportació al pas anterior. Aquestes dades es poden utilitzar per [crear perfils a l'Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Per utilitzar el segment a l'Adobe Campaign Standard, hem d'ampliar l'esquema de perfil de l'Adobe Campaign Standard per incloure-hi dos camps addicionals. Apreneu a [ampliar el recurs de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) amb camps nous a l'Adobe Campaign Standard.

Al nostre exemple, aquests camps són *Nom del segment i Data del segment (opcional).*

Utilitzarem aquests camps per identificar els perfils de l'Adobe Campaign Standard als quals volem adreçar aquesta campanya.

Si no hi ha cap altre registre a l'Adobe Campaign Standard a banda del que importareu, podeu ometre aquest pas.

## <a name="import-data-into-adobe-campaign-standard"></a>Importar dades a l'Adobe Campaign Standard

Ara que tot està al seu lloc, hem d'importar les dades del públic preparades des de la informació del públic a l'Adobe Campaign Standard per crear perfils. Apreneu a [importar perfils a l'Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) utilitzant un flux de treball.

El flux de treball d'importació de la imatge següent s'ha configurat per executar-se cada 8 hores i cerca segments d'informació del públic exportats (fitxer .csv a l'Azure Blob Storage). El flux de treball extreu el contingut del fitxer .csv en un ordre de columnes especificat. Aquest flux de treball s'ha creat per realitzar la gestió bàsica d'errors i assegurar que cada registre té una adreça electrònica abans de transmetre les dades a l'Adobe Campaign Standard. El flux de treball també extreu el nom del segment del nom de fitxer abans d'actualitzar les dades de perfil d'ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla d'un flux de treball d'importació a la interfície d'usuari de l'Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperar el públic a l'Adobe Campaign Standard

Quan les dades s'importen a l'Adobe Campaign Standard, [podeu crear un flux de treball](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) els clients per *Nom del segment* i *Data del segment* per seleccionar els perfils que s'han identificat per a la campanya d'exemple.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear i enviar el correu electrònic mitjançant l'Adobe Campaign Standard

Creeu el contingut del correu electrònic i, a continuació, [proveu i envieu](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) el correu electrònic.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Correu electrònic d'exemple amb oferta de renovació de l'Adobe Campaign Standard.":::