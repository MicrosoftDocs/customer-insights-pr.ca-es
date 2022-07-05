---
title: Connectar un Azure Synapse font de dades (previsualització)
description: Utilitzeu una base de dades com a Azure Synapse font de dades al Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052687"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Connectar un Azure Synapse Analytics font de dades (previsualització)

Azure Synapse Analytics És un servei d'anàlisi empresarial que accelera el temps per obtenir estadístiques a través de magatzems de dades i sistemes de big data. Azure Synapse Analytics reuneix el millor de les tecnologies SQL utilitzades en l'emmagatzematge de dades empresarials, tecnologies Spark utilitzades per a big data, Data Explorer per a l'anàlisi de registres i sèries temporals, pipelines per a la integració de dades i ETL / ELT, i una integració profunda amb altres serveis de l'Azure com Power BI, Cosmos DB i AzureML.

Per obtenir més informació, vegeu [Azure Synapse visió general](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisits previs

> [!IMPORTANT]
> Assegureu-vos de definir totes les **assignacions de funcions** tal com es descriuen.  

**A Customer Insights**:

* Teniu una funció d'administrador **a** Customer Insights. Obteniu més informació sobre els [permisos d'usuari a l'Insights del client](permissions.md#assign-roles-and-permissions).

**In Azure**:

- Una subscripció activa de l'Azure.

- Si utilitzeu un compte Gen2 nou Azure Data Lake Storage, el principal de *servei del Customer Insights necessita* permisos **del col·laborador de** dades blob d'emmagatzematge. Obteniu més informació sobre com [podeu connectar-vos a Azure Data Lake Storage un director de servei per al Customer Insights](connect-service-principal.md). El Data Lake Storage Gen2 **ha de tenir** habilitat l'[espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace).

- Al grup de recursos on es troba l'àrea Azure Synapse de treball, cal assignar almenys *permisos del lector* al *principal responsable* del servei i a l'usuari **del Customer Insights**. Per obtenir més informació, vegeu [Assignar funcions de l'Azure mitjançant el portal de l'Azure](/azure/role-based-access-control/role-assignments-portal).

- L'*usuari* necessita permisos del **Col·laborador de dades BLOB d'emmagatzematge** al compte de l'Azure Data Lake Storage Gen2 on es troben les dades i s'enllacen a l'àrea de treball de l'Azure Synapse. Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L'*[entitat gestionada per l'àrea de treball de l'Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* necessita permisos del **Col·laborador de dades BLOB d'emmagatzematge** al compte de l'Azure Data Lake Storage Gen2 on es troben les dades i s'enllacen a l'àrea de treball de l'Azure Synapse. Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A l'àrea Azure Synapse de treball, el principal de *servei del Customer Insights* necessita **assignada la funció d'administrador del** Sinapsi. Per obtenir més informació, vegeu [Com configurar el control d'accés per a l'àrea de treball del Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Connecta't a la base de dades del data lake a Azure Synapse Analytics

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Trieu el **Azure Synapse Analytics mètode (Previsualització).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Quadre de diàleg per connectar-se a les dades de Synapse Analytics":::
  
1. Introduïu un **nom** per a la font de dades i una descripció **opcional**.

1. Trieu una [connexió](connections.md) disponible o creeu-ne Azure Synapse Analytics una de nova.

1. Trieu una **base de dades** de l'àrea de treball connectada a la connexió seleccionada Azure Synapse Analytics i seleccioneu **Següent**. Actualment, només admetem la base de dades tipus *lake database*.

1. Seleccioneu les entitats que voleu ingerir de la base de dades connectada i seleccioneu **Endavant**.

1. Opcionalment, trieu les entitats de dades per permetre l'elaboració de perfils de dades.

1. Seleccioneu **Desa** per aplicar la selecció i iniciar la ingestió de les dades de la font de dades recentment creada enllaçada a les taules de la base de dades de Lake al Azure Synapse Analytics. S'obre **la pàgina Orígens** de dades que mostra la nova font de dades a **l'estat** d'actualització.
