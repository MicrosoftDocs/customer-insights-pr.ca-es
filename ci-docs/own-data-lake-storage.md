---
title: Utilitza el teu propi Azure Data Lake Storage compte Gen2
author: mukeshpo
description: Obteniu informació sobre els requisits per utilitzar el vostre propi Azure Data Lake Storage compte per emmagatzemar dades del Customer Insights.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5acb58906c1a9db54337f3b4dc2ab7891db7954e
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011921"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Utilitza el teu propi Azure Data Lake Storage compte Gen2

Dynamics 365 Customer Insights us ofereix l'opció d'emmagatzemar totes les vostres dades a [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

En desar les dades a l'emmagatzematge del data lake, accepteu que les dades es transferiran i s'emmagatzemaran a la ubicació geogràfica adequada per a aquest compte d'emmagatzematge de l'Azure. Per obtenir més informació, vegeu el [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Els administradors del Customer Insights poden [crear entorns](create-environment.md) i [especificar l'opció](create-environment.md#step-2-configure-data-storage) d'emmagatzematge de dades del procés.

## <a name="prerequisites-to-use-your-storage-account"></a>Requisits previs per utilitzar el compte d'emmagatzematge

- Azure Data Lake Storage els comptes han d'estar a la mateixa regió de l'Azure que heu seleccionat en crear l'entorn del Customer Insights. Podeu consultar la regió de l'entorn del Customer Insights a **Quant al sistema** > **·** > **d'administració**.
- L'emmagatzematge del llac de dades ha de ser Gen2 i tenir [habilitat](/azure/storage/blobs/create-data-lake-storage-account) l'espai de noms jeràrquic. Els comptes d'emmagatzematge gen1 no són compatibles.
- Un contenidor anomenat `customerinsights` ha d'existir al compte d'emmagatzematge. Heu de crear-lo abans d'utilitzar el vostre propi emmagatzematge del llac de dades a Les estadístiques del client. L'administrador que configura l'entorn del Customer Insights necessita la funció De col·laborador de dades del blob d'emmagatzematge o propietari de dades blob d'emmagatzematge al compte d'emmagatzematge o al `customerinsights` contenidor. Per obtenir més informació sobre com assignar permisos en un compte d'emmagatzematge, vegeu [Crear un compte](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) d'emmagatzematge.

## <a name="connect-customer-insights-with-your-storage-account"></a>Connectar les estadístiques del client amb el compte d'emmagatzematge

Quan creeu un entorn nou, assegureu-vos que el compte d'emmagatzematge del data lake existeixi i que es compleixin tots els requisits previs.

1. Al pas Emmagatzematge de dades durant la **creació de l'entorn**, definiu **Desa les dades** de sortida a **Azure Data Lake Storage Gen2**.
1. Trieu com voleu connectar **l'emmagatzematge**. Podeu triar entre una opció basada en recursos i una opció basada en subscripcions per a l'autenticació. Per obtenir més informació, vegeu [Connectar-se a un Azure Data Lake Storage compte mitjançant un principal de servei de l'Azure](connect-service-principal.md).
   - Per a la subscripció de **l**'Azure, trieu el **compte** Subscripció **,** Grup **de recursos i** Emmagatzematge que conté el `customerinsights` contenidor.
   - Per a **la clau** Compte, proporcioneu el **nom** del compte i la **clau** Compte per al compte Emmagatzematge del llac de dades. L'ús d'aquest mètode d'autenticació implica que se us informarà si la vostra organització gira les tecles. Heu d'actualitzar [la configuració](manage-environments.md#edit-an-existing-environment) de l'entorn amb la clau nova quan es giri.
1. Trieu si voleu utilitzar l'Azure Private Link per connectar-vos al compte d'emmagatzematge i [crear la connexió a l'enllaç](security-overview.md#private-links-tab) privat amb un procés de dos passos.

Quan es completen processos del sistema com la ingestió de dades, el sistema crea les carpetes corresponents al compte d'emmagatzematge. Els fitxers de dades i els fitxers *model.json* es creen i s'afegeixen a carpetes basades en el nom del procés.

Si creeu diversos entorns del Customer Insights i trieu de desar les entitats de sortida d'aquests entorns al vostre compte d'emmagatzematge, el Customer Insights crea carpetes independents per a cada entorn amb `ci_environmentID` al contenidor.
