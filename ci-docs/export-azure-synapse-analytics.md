---
title: Exportar dades a Azure Synapse Analytics (visualització prèvia)
description: Apreneu a configurar la connexió a Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196382"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar dades a Azure Synapse Analytics (visualització prèvia)

L'Azure Synapse és un servei d'analítica que accelera el temps per obtenir informació sobre els magatzems de dades i els sistemes de macrodades. Podeu ingerir i utilitzar les dades del Customer Insights a l'[Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisits previs

> [!NOTE]
> Assegureu-vos de definir totes les **assignacions de funcions** tal com es descriuen.

- Al Customer Insights, el vostre Azure Active Directory compte d'usuari (AD) ha de tenir una funció d'administrador [...](permissions.md#assign-roles-and-permissions).

A l’Azure:

- Una subscripció activa de l'Azure.

- Si utilitzeu un compte gen2 nou Azure Data Lake Storage, el director del servei del [Customer Insights](connect-service-principal.md) té **permisos de col·laborador** de dades blob d'emmagatzematge. El Data Lake Storage Gen2 **ha de tenir** habilitat l'[espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace).

- Al grup de recursos on es troba l'espai Azure Synapse de treball, el director *del* servei i l'usuari *Azure AD amb permisos d'administració al Customer Insights* s'han d'assignar com a mínim **permisos** de [lector](/azure/role-based-access-control/role-assignments-portal).

- L'usuari *Azure AD amb permisos d'administrador al Customer Insights* té **permisos de col·laborador** de dades Blob d'emmagatzematge al Azure Data Lake Storage compte de Gen2 on es troben les dades i s'enllaça a l'espai Azure Synapse de treball. Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- La *[Azure Synapse identitat](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* administrada de l'espai de treball té **permisos Storage Blob Data Contributor** al Azure Data Lake Storage compte Gen2 on es troben les dades i s'enllaça a l'espai Azure Synapse de treball. Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A l'espai Azure Synapse de treball, el *director de servei del Customer Insights* té **assignada** la funció d'administrador [de](/azure/synapse-analytics/security/how-to-set-up-access-control) Synapse.

## <a name="set-up-connection-to-azure-synapse"></a>Configurar la connexió a Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu **Azure Synapse Analytics**.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Per defecte, només són administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccioneu o cerqueu la subscripció a la qual voleu utilitzar les dades del Customer Insights. Tan aviat com se seleccioni una subscripció, també podeu seleccionar **Àrea de treball**, **Compte d'emmagatzematge** i **Contenidor**.

1. Reviseu la privadesa i el compliment de [les](connections.md#data-privacy-and-compliance) dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa** per completar la connexió.

## <a name="configure-an-export"></a>Configurar una exportació

[!INCLUDE [export-permission-include](includes/export-permission.md)] Per configurar l'exportació amb una connexió compartida, necessiteu com a mínim **permisos de col·laborador** al Customer Insights.

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Afegeix una exportació**.

1. **Al camp Connexió per a l'exportació**, trieu una connexió de la Azure Synapse Analytics secció. Poseu-vos en contacte amb un administrador si no hi ha cap connexió disponible.

1. Proporcioneu un **Nom de visualització** recognoscible per a l'exportació i un **Nom de la base de dades**. L'exportació crearà una nova [Azure Synapse base de dades](/azure/synapse-analytics/database-designer/concepts-lake-database) del llac a l'espai de treball definit a la connexió.

1. Seleccioneu a quines entitats voleu exportar .Azure Synapse Analytics
   > [!NOTE]
   > Les fonts de dades basades en una [carpeta del model de dades comú](connect-common-data-model.md) no són compatibles.

1. Seleccioneu **Desa**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Per consultar les dades que s'han exportat a Synapse Analytics, heu d'accedir **a Storage Blob Data Reader** a l'emmagatzematge de destinació a l'espai de treball de les exportacions.

## <a name="update-an-export"></a>Actualitzar una exportació

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Edita** a l'exportació que voleu actualitzar.

   - **Afegiu** o **suprimiu** entitats de la selecció. Si les entitats se suprimeixen de la selecció, no se suprimeixen de la base de dades del Synapse Analytics. No obstant això, les actualitzacions de dades futures no actualitzaran les entitats suprimides en aquesta base de dades.

   - Si **canvieu el nom de la base de dades**, es crea una base de dades nova del Synapse Analytics. La base de dades amb el nom que s'ha configurat abans no rebrà cap actualització en actualitzacions futures.

[!INCLUDE [footer-include](includes/footer-banner.md)]
