---
title: Connectar un Azure Synapse font de dades (vista prèvia)
description: Utilitzeu una base de dades com Azure Synapse a font de dades en Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259786"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Connectar un Azure Synapse Analytics font de dades (vista prèvia)

Azure Synapse Analytics és un servei d'anàlisi empresarial que accelera el temps per obtenir informació sobre magatzems de dades i sistemes de big data. Azure Synapse Analytics reuneix el millor de les tecnologies SQL utilitzades en l'emmagatzematge de dades empresarials, tecnologies Spark utilitzades per a big data, Explorador de dades per a l'anàlisi de registres i sèries temporals, Pipelines per a la integració de dades i ETL/ELT, i integració profunda amb altres serveis de l'Azure com Power BI, Cosmos DB i AzureML.

Per obtenir més informació, vegeu [Azure Synapse informació general](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisits previs

> [!NOTE]
> Els espais de treball synapse que tenen [el tallafoc habilitat](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) actualment no són compatibles.
> [!IMPORTANT]
> Assegureu-vos de definir totes les **assignacions de funcions** tal com es descriuen.  

**A estadístiques** de clients:

* Teniu una funció d'administrador **al** Customer Insights. Obteniu més informació sobre [els permisos d'usuari al Customer Insights](permissions.md#add-users).

**In Azure**:

- Una subscripció activa de l'Azure.

- Si utilitzeu un compte gen2 nou Azure Data Lake Storage, el director de servei del *Customer Insights* que és "Dynamics 365 AI for Customer Insights" necessita **permisos de col·laborador** de dades blob d'emmagatzematge. Obteniu més informació sobre com [podeu connectar-vos a un Azure Data Lake Storage director de servei per al Customer Insights](connect-service-principal.md). El Data Lake Storage Gen2 **ha de tenir** habilitat l'[espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace).

- Al grup de recursos on es troba l'espai Azure Synapse de treball, el principal *del* servei que és "Dynamics 365 AI for Customer Insights" i l'usuari *per al Customer Insights* s'han d'assignar com a mínim **permisos de lector**. Per obtenir més informació, vegeu [Assignar funcions de l'Azure mitjançant el portal de l'Azure](/azure/role-based-access-control/role-assignments-portal).

- L'*usuari* necessita permisos del **Col·laborador de dades BLOB d'emmagatzematge** al compte de l'Azure Data Lake Storage Gen2 on es troben les dades i s'enllacen a l'àrea de treball de l'Azure Synapse. Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L'*[entitat gestionada per l'àrea de treball de l'Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* necessita permisos del **Col·laborador de dades BLOB d'emmagatzematge** al compte de l'Azure Data Lake Storage Gen2 on es troben les dades i s'enllacen a l'àrea de treball de l'Azure Synapse. Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A l'espai Azure Synapse de treball, el principal de *servei per al Customer Insights* que és "Dynamics 365 AI for Customer Insights" necessita la **funció d'administrador** de Synapse assignada. Per obtenir més informació, vegeu [Com configurar el control d'accés per a l'àrea de treball del Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Si l'entorn del Customer Insights emmagatzema dades pel vostre [compte Azure Data Lake Storage](own-data-lake-storage.md), l'usuari que configura la connexió necessita Azure Synapse Analytics almenys la funció de lector **integrat** al compte del Data Lake Storage. Per obtenir més informació, vegeu [Assignar funcions de l'Azure mitjançant el portal de l'Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Connecteu-vos a la base de dades del llac de dades a Azure Synapse Analytics

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Trieu el **Azure Synapse Analytics mètode (previsualització).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Quadre de diàleg per connectar-se a les dades de Synapse Analytics":::
  
1. Introduïu un **nom** per al font de dades i una descripció opcional.**·**

1. Trieu una [connexió](connections.md) disponible o Azure Synapse Analytics creeu-ne [una de nova](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Trieu una **base de dades** de l'espai de treball connectat a la connexió seleccionada Azure Synapse Analytics i seleccioneu **Següent**. Actualment, només admetem la base de dades tipus *Base de dades* Lake.

1. Seleccioneu les entitats que voleu ingerir des de la base de dades connectada i seleccioneu **Següent**.

1. Opcionalment, trieu les entitats de dades en què voleu permetre l'elaboració de perfils de dades.

1. Seleccioneu **Desa** per aplicar la vostra selecció i iniciar la ingestió de les dades del vostre font de dades recentment creat enllaçat a les taules de la base de dades Lake a Azure Synapse Analytics. S'obre **la pàgina Fonts** de dades que mostra la nova font de dades en **estat de Refresc**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

La càrrega de les dades pot tardar temps. Després d'una actualització correcta, les dades ingerides es poden revisar des de la [**pàgina Entitats**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
