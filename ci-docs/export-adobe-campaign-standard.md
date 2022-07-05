---
title: Exportar segments de Customer Insights a l'estàndard Adobe de campanya (visualització prèvia)
description: Obteniu informació sobre com utilitzeu els segments del Customer Insights a l'estàndard Adobe de campanya.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082339"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Exportar segments de Customer Insights a l'estàndard Adobe de campanya (visualització prèvia)

Com a usuari de Dynamics 365 Customer Insights, és possible que hàgiu creat segments per fer que les vostres campanyes de màrqueting siguin més eficients orientant-vos a públics rellevants. Per utilitzar un segment del Customer Insights i d'aplicacions Adobe Experience Platform com Adobe Campaign Standard, heu de seguir alguns passos que s'indiquen en aquest article.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de procés dels passos que es descriuen en aquest article.":::

## <a name="prerequisites"></a>Requisits previs

- Llicència del Dynamics 365 Customer Insights
- Llicència de l'Adobe Campaign Standard
- Compte de l'Emmagatzematge blob de l'Azure

## <a name="campaign-overview"></a>Informació general de Campaign

Per entendre millor com podeu utilitzar els segments de Customer Insights al Adobe Experience Platform, vegem una campanya d'exemple fictícia.

Suposem que la vostra empresa ofereix un servei mensual basat en subscripció als seus clients dels Estats Units. Voleu identificar els clients les subscripcions dels qual s'han de renovar en els propers vuit dies però que encara no han renovat la seva subscripció. Per mantenir aquests clients, us recomanem que els envieu una oferta promocional per correu electrònic mitjançant l'Adobe Campaign Standard.

En aquest exemple, volem executar la campanya promocional de correu electrònic d'un cop. En aquest article no es cobreix el cas d'ús de l'execució de la campanya més d'una vegada. Tanmateix, les estadístiques del client i Adobe l'estàndard de campanya també es poden configurar per funcionar per a un escenari de campanya recurrent.

## <a name="identify-your-target-audience"></a>Identificar el públic destinatari

En el nostre escenari, assumim que les adreces de correu electrònic dels clients estan disponibles i s'han analitzat les seves preferències promocionals per identificar els membres del segment.

El [segment que heu definit a Customer Insights](segments.md) s'anomena **ChurnProneCustomers** i teniu previst enviar a aquests clients la promoció de correu electrònic.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la pàgina de segments amb el segment ChurnProneCustomers creat.":::

El correu electrònic d'oferta que voleu enviar inclourà el nom, el cognom i la data de finalització de la subscripció del client. Informa els clients sobre el descompte que obtindran si renoven la subscripció abans que finalitzi.

## <a name="export-your-target-audience"></a>Exportar el públic destinatari

### <a name="configure-a-connection"></a>Configurar una connexió

Amb el nostre públic objectiu identificat, podem configurar l'exportació a un compte d'emmagatzematge blob de l'Azure.

1. A l'informació del client, aneu a **Connexions d'administració** > **·**.

1. Seleccioneu **Afegeix una connexió** i trieu **Adobe Campaign** per configurar la connexió o seleccioneu **Configuració** a la peça **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Peça de configuració per a l'Adobe Campaign Standard.":::

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Introduïu el **Nom de compte**, la **Clau del compte** i el **Contenidor** del compte d'Emmagatzematge blob de l'Azure al qual voleu exportar el segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuració del compte d'emmagatzematge."::: 

   - Per obtenir més informació sobre com trobar el nom i la clau del compte de l'emmagatzematge blob de l'Azure, vegeu [Administrar la configuració del compte d'emmagatzematge al portal de l'Azure](/azure/storage/common/storage-account-manage).

   - Per obtenir més informació sobre com crear un contenidor , vegeu [Crear un contenidor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccioneu **Desa** per completar la connexió.

### <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [Permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció Adobe Campaign. Si no veieu aquest nom de secció, no hi ha disponible cap connexió d'aquest tipus.

1. Trieu el segment que voleu exportar. En aquest exemple, és **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfície d'usuari de selecció de segments amb el segment ChurnProneCustomers seleccionat.":::

1. Seleccioneu **Següent**.

1. Ara assignem els camps d'origen **del** segment Customer Insights als noms de camps de destinació **de** l'esquema de perfil Estàndard de Adobe campanya.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Assignació de camps per al connector de l'Adobe Campaign Standard.":::

   Si voleu afegir més atributs, seleccioneu **Afegeix un atribut**. El nom de destinació pot ser diferent del nom del camp d'origen, de manera que encara podeu assignar la sortida del segment de Customer Insights a Adobe Campaign Standard si els camps no tenen el mateix nom als dos sistemes.

   > [!NOTE]
   > L'adreça electrònica s'utilitza com a camp d'identitat, però podeu utilitzar qualsevol altre identificador del perfil de client per assignar dades a l'estàndard Adobe de campanya.

1. Seleccioneu **Desa**.

Després de desar la destinació d'exportació, la trobeu a **Dades** > **Exportacions**.

Ara podeu [exportar el segment a petició](export-destinations.md#run-exports-on-demand). L'exportació també s'executarà amb cada [actualització planificada](system.md).

> [!NOTE]
> Assegureu-vos que el nombre de registres del segment exportat es troba dins del límit permès de la llicència de l'Adobe Campaign Standard.

Les dades exportades s'emmagatzemen al contenidor d'emmagatzematge blob de l'Azure que heu configurat anteriorment. Al contenidor es crea automàticament el camí de carpeta següent:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemple: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configuració de l'Adobe Campaign Standard

Els segments exportats contenen les columnes que heu seleccionat mentre definiu la destinació d'exportació del pas anterior. Aquestes dades es poden utilitzar per [crear perfils a l'Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Per utilitzar el segment a l'Adobe Campaign Standard, hem d'ampliar l'esquema de perfil de l'Adobe Campaign Standard perquè inclogui dos camps addicionals. Obteniu informació sobre com [ampliar el recurs de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) amb camps nous a l'Adobe Campaign Standard.

Al nostre exemple, aquests camps són *Nom del segment i Data del segment (opcional)*.

Utilitzarem aquests camps per identificar els perfils de l'Adobe Campaign Standard que volem dirigir per a aquesta campanya.

Si no hi ha cap altre registre a l'Adobe Campaign Standard, que no sigui el que voleu importar, podeu ometre aquest pas.

## <a name="import-data-into-adobe-campaign-standard"></a>Importació de dades a l'Adobe Campaign Standard

Ara que tot està al seu lloc, hem d'importar les dades de públic preparades de Customer Insights a Adobe l'estàndard de campanya per crear perfils. Obteniu informació [sobre com importar perfils de l'Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) amb un flux de treball.

El flux de treball d'importació de la imatge següent s'ha configurat per executar-se cada vuit hores i cercar segments exportats del Customer Insights (.csv fitxer a l'Emmagatzematge blob de l'Azure). El flux de treball extreu el contingut del fitxer .csv en un ordre de columnes especificat. Aquest flux de treball s'ha creat per realitzar la gestió bàsica d'errors i assegurar-vos que cada registre té una adreça electrònica abans d'hidratar les dades a l'Adobe Campaign Standard. El flux de treball també extreu el nom del segment del nom del fitxer abans d'actualitzar-lo a les dades de perfil de l'Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla d'un flux de treball d'importació de la interfície d'usuari de l'Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperació del públic a l'Adobe Campaign Standard

Un cop importades les dades a l'Adobe Campaign Standard, [podeu crear un flux de treball](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) els clients segons el *nom del segment* i la *data del segment* per seleccionar els perfils identificats per a la nostra campanya d'exemple.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear i enviar el correu electrònic amb l'Adobe Campaign Standard

Creeu el contingut del correu electrònic i, a continuació, [proveu i envieu](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) el correu electrònic.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Correu electrònic d'exemple amb oferta de renovació de l'Adobe Campaign Standard.":::
