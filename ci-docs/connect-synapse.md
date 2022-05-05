---
title: Ingereix les dades de Azure Synapse Analytics
description: Utilitzeu una base de dades com a Azure Synapse font de dades al Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642274"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Connectar un Azure Synapse font de dades (previsualització)

Azure Synapse Analytics És un servei d'anàlisi empresarial que accelera el temps per obtenir estadístiques a través de magatzems de dades i sistemes de big data. Azure Synapse Analytics reuneix el millor de les tecnologies SQL utilitzades en l'emmagatzematge de dades empresarials, tecnologies Spark utilitzades per a big data, Data Explorer per a l'anàlisi de registres i sèries temporals, pipelines per a la integració de dades i ETL / ELT, i una integració profunda amb altres serveis de l'Azure com Power BI, Cosmos DB i AzureML.

Per obtenir més informació, vegeu [Azure Synapse visió general](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisits previs

S'han de complir els requisits previs següents per configurar la connexió des de Dynamics 365 Customer Insights a Azure Synapse.

> [!IMPORTANT]
> Assegureu-vos de definir totes les **assignacions de funcions** tal com es descriuen.  

## <a name="prerequisites-in-customer-insights"></a>Requisits previs al Customer Insights

* Teniu una funció d'administrador **a** Customer Insights. Obteniu més informació sobre els [permisos d'usuari a l'Insights](permissions.md#assign-roles-and-permissions) del client.

A l’Azure: 

- Una subscripció activa de l'Azure.

- Si utilitzeu un compte Gen2 nou Azure Data Lake Storage, el principal de *servei del Customer Insights necessita* permisos **del col·laborador de** dades blob d'emmagatzematge. Obteniu més informació sobre com [podeu connectar-vos a Azure Data Lake Storage un director de servei per al Customer Insights](connect-service-principal.md). El Data Lake Storage Gen2 **ha de tenir** habilitat l'[espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace).

- Al grup de recursos on es troba l'àrea Azure Synapse de treball, cal assignar almenys *permisos del lector* al *principal responsable* del servei i a l'usuari **del Customer Insights**. Per obtenir més informació, vegeu [Assignar funcions de l'Azure mitjançant el portal de l'Azure](/azure/role-based-access-control/role-assignments-portal).

- L'*usuari* necessita permisos del **Col·laborador de dades BLOB d'emmagatzematge** al compte de l'Azure Data Lake Storage Gen2 on es troben les dades i s'enllacen a l'àrea de treball de l'Azure Synapse. Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L'*[entitat gestionada per l'àrea de treball de l'Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* necessita permisos del **Col·laborador de dades BLOB d'emmagatzematge** al compte de l'Azure Data Lake Storage Gen2 on es troben les dades i s'enllacen a l'àrea de treball de l'Azure Synapse. Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A l'àrea Azure Synapse de treball, el principal de *servei del Customer Insights* necessita **assignada la funció d'administrador del** Sinapsi. Per obtenir més informació, vegeu [Com configurar el control d'accés per a l'àrea de treball del Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Connecta't a bases de dades del llac de dades a Azure Synapse Analytics

1. Aneu a **Dades** > **Fonts de dades**.

1. Seleccioneu **Afegeix una font de dades**.

1. Trieu el **Azure Synapse Analytics mètode (Previsualització).**

1. Proporcioneu un **Nom** per a la font de dades i seleccioneu **Següent** per crear la font de dades. 

1. Trieu una [connexió](connections.md) disponible o creeu-ne Azure Synapse Analytics una de nova.

1. Trieu una **base de dades** del llac de l'àrea de treball connectada a la connexió seleccionada Azure Synapse Analytics i seleccioneu **Següent**.

1. Seleccioneu les entitats que voleu ingerir des de la base de dades connectada. 

1. Opcionalment, trieu les entitats de dades per permetre l'elaboració de perfils de dades. 

1. Seleccioneu **Desa** per aplicar la selecció i iniciar la ingestió de les dades de la font de dades recentment creada enllaçada a les taules de la base de dades de Lake al Azure Synapse Analytics.
