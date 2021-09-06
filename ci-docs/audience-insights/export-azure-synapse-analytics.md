---
title: Exportar dades del Customer Insights a l'Azure Synapse Analytics
description: Apreneu a configurar la connexió amb l'Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f206043298bdbf8a84b0ef37b47a43290653beba7d3d0e8b807ec74513614aa8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031921"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar dades a l'Azure Synapse Analytics (versió preliminar)

L'Azure Synapse és un servei d'analítica que accelera el temps per obtenir informació sobre els magatzems de dades i els sistemes de macrodades. Podeu ingerir i utilitzar les dades del Customer Insights a l'[Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisits previs

S'han de complir els requisits previs següents per configurar la connexió del Customer Insights a l'Azure Synapse.

> [!NOTE]
> Assegureu-vos de definir totes les **assignacions de funcions** tal com es descriuen.  

## <a name="prerequisites-in-customer-insights"></a>Requisits previs al Customer Insights

* Teniu una funció d'**Administrador** als coneixements del públic. Més informació quant a [la configuració de permisos d'usuari als coneixements del públic](permissions.md#assign-roles-and-permissions)

A l’Azure: 

- Una subscripció activa de l'Azure.

- Si s'utilitza un compte de l'Azure Data Lake Storage Gen2 nou, l'*entitat de seguretat del servei per als coneixements del públic* necessita permisos de **Col·laborador de dades BLOB d'emmagatzematge**. Obteniu més informació sobre com [podeu connectar-vos a un compte de l'Azure Data Lake Storage Gen2 amb l'enitat de seguretat del servei de l'Azure per als coneixements del públic](connect-service-principal.md). El Data Lake Storage Gen2 **ha de tenir** habilitat l'[espai de noms jeràrquic](/azure/storage/blobs/data-lake-storage-namespace).

- Al grup de recursos on es troba l'àrea de treball de l'Azure Synapse, l'*entitat de seguretat del servei* i l'*usuari per als coneixements del públic* han de tenir assignats com a mínim permisos de **Lector**. Per obtenir més informació, vegeu [Assignar funcions de l'Azure mitjançant el portal de l'Azure](/azure/role-based-access-control/role-assignments-portal).

- L'*usuari* necessita permisos del **Col·laborador de dades BLOB d'emmagatzematge** al compte de l'Azure Data Lake Storage Gen2 on es troben les dades i s'enllacen a l'àrea de treball de l'Azure Synapse. Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L'*[entitat gestionada per l'àrea de treball de l'Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* necessita permisos del **Col·laborador de dades BLOB d'emmagatzematge** al compte de l'Azure Data Lake Storage Gen2 on es troben les dades i s'enllacen a l'àrea de treball de l'Azure Synapse. Obteniu més informació sobre [com podeu utilitzar el portal de l'Azure per assignar una funció de l'Azure per accedir a les dades BLOB i de la cua](/azure/storage/common/storage-auth-aad-rbac-portal) i [els permisos del col·laborador de dades BLOB d'emmagatzematge](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A l'àrea de treball de l'Azure Synapse, l'*entitat de seguretat del servei per als coneixements del públic* necessita la funció **Administrador del Synapse** assignada. Per obtenir més informació, vegeu [Com configurar el control d'accés per a l'àrea de treball del Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configurar la connexió i exportar a l'Azure Synapse

### <a name="configure-a-connection"></a>Configurar una connexió

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix una connexió** i trieu **Azure Synapse Analytics** o seleccioneu **Configuració** a la peça de l'**Azure Synapse Analytics** per configurar la connexió.

1. Doneu a la connexió un nom reconeixible al camp Nom de visualització. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Trieu qui pot utilitzar aquesta connexió. Si no feu cap acció, el valor per defecte serà Administradors. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccioneu o cerqueu la subscripció a la qual voleu utilitzar les dades del Customer Insights. Tan aviat com se seleccioni una subscripció, també podeu seleccionar **Àrea de treball**, **Compte d'emmagatzematge** i **Contenidor**.

1. Seleccioneu **Desa** per desar la connexió.

### <a name="configure-an-export"></a>Configurar una exportació

Podeu configurar aquesta exportació si teniu accés a una connexió d'aquest tipus. Per obtenir més informació, vegeu [permisos necessaris per configurar una exportació](export-destinations.md#set-up-a-new-export).

1. Vés a **Dades** > **Exportacions**.

1. Per crear una exportació nova, seleccioneu **Afegeix una exportació**.

1. Al camp **Connexió per a l'exportació**, trieu una connexió de la secció **Azure Synapse Analytics**. Si no veieu aquest nom de secció, no hi ha cap [connexió](connections.md) d'aquest tipus disponible per a vós.

1. Proporcioneu un **Nom de visualització** recognoscible per a l'exportació i un **Nom de la base de dades**.

1. Seleccioneu les entitats que voleu exportar a l'Azure Synapse Analytics.
   > [!NOTE]
   > Les fonts de dades basades en una [carpeta del model de dades comú](connect-common-data-model.md) no són compatibles.

2. Seleccioneu **Desa**.

Si deseu una exportació, no s'executarà l'exportació immediatament.

L'exportació s'executa amb cada [actualització planificada](system.md#schedule-tab). També podeu [exportar dades segons demanda](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Actualitzar una exportació

1. Vés a **Dades** > **Exportacions**.

1. Seleccioneu **Edita** a l'exportació que voleu actualitzar.

   - **Afegiu** o **suprimiu** entitats de la selecció. Si les entitats se suprimeixen de la selecció, no se suprimeixen de la base de dades del Synapse Analytics. No obstant això, les actualitzacions de dades futures no actualitzaran les entitats suprimides en aquesta base de dades.

   - Si **canvieu el nom de la base de dades**, es crea una base de dades nova del Synapse Analytics. La base de dades amb el nom que s'ha configurat abans no rebrà cap actualització en actualitzacions futures.
