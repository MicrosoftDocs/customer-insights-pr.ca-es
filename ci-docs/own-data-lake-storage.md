---
title: Utilitza el teu propi Azure Data Lake Storage compte de Gen2
author: mukeshpo
description: Obteniu informació sobre els requisits per utilitzar el vostre propi Azure Data Lake Storage compte per emmagatzemar dades del Customer Insights.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304369"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Utilitza el teu propi Azure Data Lake Storage compte de Gen2

Dynamics 365 Customer Insights et dóna l'opció d'emmagatzemar totes les teves dades en [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). En desar dades al Data Lake Storage, accepteu que les dades es transferiran i s'emmagatzemaran a la ubicació geogràfica adequada per a aquest compte d'emmagatzematge de l'Azure. Per obtenir més informació, vegeu [Centre de confiança de Microsoft](https://www.microsoft.com/trust-center).

Els administradors del Customer Insights poden [crear entorns](create-environment.md) i [especificar l'opció](create-environment.md#step-2-configure-data-storage) d'emmagatzematge de dades en el procés.

## <a name="prerequisites"></a>Requisits previs

- Azure Data Lake Storage els comptes han d'estar a la mateixa regió de l'Azure que heu seleccionat en crear l'entorn del Customer Insights. Per conèixer la regió de l'entorn, aneu a **Administració Sobre** > **el sistema** > **a** Estadístiques del client.
- El compte del Data Lake Storage ha de ser Gen2. Els comptes d'emmagatzematge de l'Azure Data Lake Gen1 no són compatibles.
- El compte del Data Lake Storage ha de tenir [habilitat](/azure/storage/blobs/data-lake-storage-namespace) l'espai de noms jeràrquic.
- Un contenidor anomenat `customerinsights` ha d'existir al compte d'emmagatzematge. Creeu-lo abans d'utilitzar el vostre propi Data Lake Storage al Customer Insights.
- L'administrador que configura l'entorn del Customer Insights necessita la funció De col·laborador de dades blob d'emmagatzematge o Propietari de dades blob d'emmagatzematge al compte d'emmagatzematge o al `customerinsights` contenidor. Per obtenir més informació sobre l'assignació de permisos en un compte d'emmagatzematge, vegeu [Crear un compte](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) d'emmagatzematge.

## <a name="connect-customer-insights-with-your-storage-account"></a>Connectar el Customer Insights amb el compte d'emmagatzematge

Quan creeu un entorn nou, assegureu-vos que el compte del Data Lake Storage existeixi i que es compleixin tots els requisits previs.

1. Al pas Emmagatzematge de dades durant la creació de l'entorn **·**, definiu **Desa les dades** de sortida a **Azure Data Lake Storage Gen2**.
1. Tria com pots connectar **l'espai d'emmagatzematge**. Podeu triar entre una opció basada en recursos i una opció basada en subscripció per a l'autenticació. Per obtenir més informació, vegeu [Connexió a un Azure Data Lake Storage compte mitjançant un director de servei de l'Azure](connect-service-principal.md).
   - Per a **la subscripció** de l'Azure, trieu el **compte** subscripció **,** grup **de recursos i** Emmagatzematge que conté el `customerinsights` contenidor.
   - Per obtenir **la clau** del compte, proporcioneu el **nom** del compte i la **clau** del compte del Data Lake Storage. L'ús d'aquest mètode d'autenticació implica que se us informa si l'organització gira les claus. Heu d'actualitzar [la configuració](manage-environments.md#edit-an-existing-environment) de l'entorn amb la clau nova quan es gira.
1. Trieu si voleu utilitzar l'Azure Private Link per connectar-vos al compte d'emmagatzematge i [crear la connexió a Private Link](security-overview.md#set-up-an-azure-private-link).

Quan es completen processos del sistema com la ingestió de dades, el sistema crea les carpetes corresponents al compte d'emmagatzematge. Els fitxers de dades i els fitxers model.json es creen i s'afegeixen a carpetes basades en el nom del procés.

Si creeu diversos entorns del Customer Insights i trieu de desar les entitats de sortida d'aquests entorns al vostre compte d'emmagatzematge, el Customer Insights crea carpetes independents per a cada entorn amb `ci_environmentID` al contenidor.
