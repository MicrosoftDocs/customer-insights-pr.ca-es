---
title: Exportar incidències refinades
description: Com s'exporten incidències refinades i incidències de base.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d062e2982c1041454b083630404f2b68f0da9669
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232876"
---
# <a name="export-events"></a>Exportar incidències

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Una incidència representa el comportament de l'usuari. Registra quan un usuari visualitza una pàgina (incidència de visualització) o interactua amb el contingut (incidència d'acció). Quan podeu decidir quines propietats de les dades voleu que es visualitzin en un informe, aquesta visualització virtual de les dades s'anomena *incidència refinada*. Per obtenir més informació, vegeu [Crear i modificar incidències](refined-events.md).

- Podeu exportar incidències i incidències refinades a un emmagatzematge extern. 
- Les exportacions són una seqüència de dades enviades. No podeu recarregar la seqüència. 
- Les exportacions tenen esquemes fixos. Si afegiu propietats personalitzades a una incidència, no s'inclouran. Haureu de crear una exportació nova.

## <a name="prerequisites"></a>Requisits previs

Abans de configurar una exportació, heu de tenir accés i una subscripció activa al portal de l'Azure. Necessitareu la informació del compte d'emmagatzematge durant el procés d'exportació. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Crea un compte de l'Azure Data Lake Storage Gen 2

1. Inicieu sessió al portal de l'Azure i [creeu un compte d'emmagatzematge nou](/azure/storage/common/storage-account-create). 

1. Assegureu-vos d'habilitar l'**Espai de nom jeràrquic** a la pestanya **Avançat**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Habiliteu l'espai de nom jeràrquic a la pestanya avançat.":::

1. Un cop implementada, aneu al compte d'emmagatzematge creat recentment. A la subfinestra de navegació, seleccioneu **Configuració** > **Claus d'accés**. 

1. Copieu el **Nom de compte** i la **Clau** per utilitzar-los en crear una exportació nova.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Claus d'accés a un compte d'emmagatzematge.":::

## <a name="export-events"></a>Exporta esdeveniments

Hi ha dues maneres d'obrir el quadre de diàleg **Exporta les incidències**: 
- Aneu a **Dades** > **Exportacions** i seleccioneu **Exportació nova**.
- Aneu a **Dades** > **Esdeveniments**, seleccioneu **Més [...]** al costat de l'esdeveniment que voleu exportar i seleccioneu **Exporta** al menú desplegable. 

:::image type="content" source="media/new-export.png" alt-text="Creeu un projecte nou.":::

Us guiarem pels passos que cal seguir per crear una exportació:

1. Proporcioneu un **Nom d'exportació** i, a continuació, seleccioneu **Següent**.

1. A la llista desplegable **Selecció d'esdeveniments**, trieu els esdeveniments base i els esdeveniments refinats que voleu incloure a l'exportació. 

1. A la secció **Estructura de fitxers**, seleccioneu la cadència (horària o diària) per crear fitxers nous a l'emmagatzematge de destinació i, a continuació, seleccioneu **Següent**. Les incidències s'exporten contínuament tan bon punt arriben.

1. Al quadre de diàleg **Trieu el format**, seleccioneu el format de l'exportació. Trieu entre els formats **Common Data Model**, **CSV** i **JSON**. Per utilitzar l'exportació amb altres aplicacions del Dynamics 365, us recomanem el format **Common Data Model**.

1. Al quadre de diàleg **Trieu la destinació**, especifiqueu la ubicació de l'Azure Data Lake Storage Gen 2.
    1. El **nom de compte d'ADLS Gen 2** és el nom del compte d'emmagatzematge al qual voleu desar l'exportació. 
    1. La **ruta de la carpeta** defineix on s'ha d'emmagatzemar l'exportació al sistema de fitxers i l'estructura de directoris del compte d'emmagatzematge.
    1. La **clau compartida** està disponible des del portal de l'Azure per al compte d'emmagatzematge.

1. Reviseu i confirmeu les vostres seleccions per acabar.

## <a name="view-and-manage-exports"></a>Visualitzar i administrar exportacions

Un cop hàgiu configurat una exportació, aneu **Dades** > **Exportacions** per visualitzar-la. Seleccioneu **Més [...]** de qualsevol exportació existent per editar-la o suprimir-la.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
