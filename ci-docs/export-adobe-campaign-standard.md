---
title: Exportar segments del Customer Insights a Adobe Estàndard de campanya (visualització prèvia)
description: Obteniu informació sobre com podeu utilitzar els segments del Customer Insights a Adobe l'estàndard de campanya.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195508"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Exportar segments del Customer Insights a Adobe Estàndard de campanya (visualització prèvia)

Exporta segments orientats a públics rellevants a Adobe l'estàndard de campanya.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de procés dels passos que es descriuen en aquest article.":::

## <a name="prerequisites"></a>Requisits previs

- Una Adobe llicència estàndard de campanya.
- Un [nom de compte i una clau de compte](/azure/storage/blobs/create-data-lake-storage-account) de l'Azure Blob Storage. Per trobar el nom i la clau, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Informació general de Campaign

Per entendre millor com podeu utilitzar segments del Customer Insights a Adobe Experience Platform, vegem una campanya de mostra fictícia.

Suposem que la vostra empresa ofereix un servei mensual basat en subscripció als seus clients dels Estats Units. Voleu identificar els clients les subscripcions dels qual s'han de renovar en els propers vuit dies però que encara no han renovat la seva subscripció. Per mantenir aquests clients, us recomanem que els envieu una oferta promocional per correu electrònic mitjançant l'Adobe Campaign Standard.

En aquest exemple, volem executar la campanya promocional de correu electrònic d'un cop. En aquest article no es cobreix el cas d'ús de l'execució de la campanya més d'una vegada. Tanmateix, les estadístiques de client i Adobe l'estàndard de campanya també es poden configurar perquè funcionin per a un escenari de campanya recurrent.

## <a name="identify-your-target-audience"></a>Identificar el públic destinatari

En el nostre escenari, assumim que les adreces de correu electrònic dels clients estan disponibles al Customer Insights i es van analitzar les seves preferències promocionals per identificar els membres del segment.

El [segment que heu definit al Customer Insights](segments.md) s'anomena **ChurnProneCustomers** i teniu previst enviar a aquests clients la promoció per correu electrònic.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la pàgina de segments amb el segment ChurnProneCustomers creat.":::

El correu electrònic d'oferta que voleu enviar inclourà el nom, el cognom i la data de finalització de la subscripció del client. Informa els clients sobre el descompte que obtindran si renoven la subscripció abans que finalitzi.

## <a name="export-your-target-audience"></a>Exportar el públic destinatari

### <a name="set-up-connection-to-adobe-campaign"></a>Configurar la connexió a la Adobe campanya

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Adobe Campanya**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduïu el **nom** del compte, **la clau** del compte i **el contenidor** del vostre compte de Blob Storage.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuració del compte d'emmagatzematge.":::

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa** per completar la connexió.

### <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Adobe Campaign. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Introduïu un nom per a l'exportació.

1. Trieu el segment que voleu exportar. En aquest exemple, és **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfície d'usuari de selecció de segments amb el segment ChurnProneCustomers seleccionat.":::

1. Seleccioneu **Següent**.

1. Assigneu els **camps d'origen** del segment Estadístiques de client als noms de camp Objectiu **de** l'esquema Adobe de perfil estàndard de campanya.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Assignació de camps per al connector de l'Adobe Campaign Standard.":::

   Si voleu afegir més atributs, seleccioneu **Afegeix un atribut**. El nom de destinació pot ser diferent del nom del camp d'origen, de manera que encara podeu assignar la sortida del segment des del Customer Insights fins a Adobe l'estàndard de campanya si els camps no tenen el mateix nom als dos sistemes.

   > [!NOTE]
   > L'adreça electrònica s'utilitza com a camp d'identitat, però podeu utilitzar qualsevol altre identificador del perfil de client per assignar dades a Adobe Estàndard de campanya.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Assegureu-vos que el nombre de registres del segment exportat es troba dins del límit permès de la llicència de l'Adobe Campaign Standard.

Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge blob de l'Azure que heu configurat anteriorment. El camí de la carpeta següent es crea automàticament al contenidor: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configuració de l'Adobe Campaign Standard

Els segments exportats contenen les columnes que heu seleccionat en configurar l'exportació. Aquestes dades es poden utilitzar per [crear perfils a l'Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Per utilitzar el segment a Adobe l'estàndard de campanya, [amplieu l'esquema](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) del perfil a Adobe l'estàndard de campanya per incloure dos camps addicionals.

En el nostre exemple, aquests camps són Nom del segment i Data del segment. Utilitzarem aquests camps per identificar els perfils de l'Adobe Campaign Standard que volem dirigir per a aquesta campanya.

Si no hi ha cap altre registre a Adobe l'estàndard de campanya, que no sigui el que importareu, ometeu aquest pas.

## <a name="import-data-into-adobe-campaign-standard"></a>Importació de dades a l'Adobe Campaign Standard

Importeu les dades de públic preparades del Customer Insights a Adobe l'estàndard de campanya per [crear perfils mitjançant un flux de treball](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

El flux de treball d'importació de la imatge següent s'ha configurat per executar-se cada vuit hores i cercar segments exportats del Customer Insights (.csv fitxer a l'Emmagatzematge blob de l'Azure). El flux de treball extreu el contingut del fitxer .csv en un ordre de columnes especificat. Aquest flux de treball s'ha creat per realitzar la gestió bàsica d'errors i assegurar-vos que cada registre té una adreça electrònica abans d'hidratar les dades a l'Adobe Campaign Standard. El flux de treball també extreu el nom del segment del nom del fitxer abans d'actualitzar-lo a les dades de perfil de l'Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla d'un flux de treball d'importació de la interfície d'usuari de l'Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperació del públic a l'Adobe Campaign Standard

Un cop importades les dades a Adobe Campaign Standard, [creeu un flux de treball](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [consulteu](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) els clients en funció del nom del segment i de la data del segment per seleccionar els perfils identificats per a la nostra campanya d'exemple.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear i enviar el correu electrònic amb l'Adobe Campaign Standard

Creeu el contingut del correu electrònic i, a continuació, [proveu i envieu](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) el correu electrònic.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Correu electrònic d'exemple amb oferta de renovació de l'Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
