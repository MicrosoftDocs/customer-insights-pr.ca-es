---
title: Exportar incidències refinades
description: Com s'exporten incidències refinades i incidències de base.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032373"
---
# <a name="export-events"></a>Exportar incidències

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Una incidència representa el comportament de l'usuari. Registra quan un usuari visualitza una pàgina (incidència de visualització) o interactua amb el contingut (incidència d'acció). Quan podeu decidir quines propietats de les dades voleu que es visualitzin en un informe, aquesta visualització virtual de les dades s'anomena *incidència refinada*. 

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

Hi ha dues maneres d'exportar incidències: 
- Aneu a **Dades** > **Exportacions** i seleccioneu **Exportació nova**.
- Aneu a **Dades** > **Esdeveniments**, seleccioneu **Més [...]** al costat de l'esdeveniment que voleu exportar i seleccioneu **Exporta** al menú desplegable. 

Us guiarem pels passos que cal seguir per crear una exportació:

1. Proporcioneu un **Nom d'exportació**.

1. A la llista desplegable **Selecció d'esdeveniments**, trieu els esdeveniments base i els esdeveniments refinats que voleu incloure a l'exportació. 

1. A **Estructura dels fitxers**, seleccioneu la cadència per crear fitxers nous a l'emmagatzematge de destinació. Les incidències s'exporten contínuament tan bon punt arriben.

1. Seleccioneu el format de l'exportació. Podeu triar entre el format **model de dades comú**, **CSV** i **JSON**. Per utilitzar l'exportació amb altres aplicacions del Dynamics 365, us recomanem que utilitzeu el format del model de dades comú.

1. Al pas **Tria la destinació**, especifiqueu la ubicacó de l'Azure Data Lake Storage Gen 2.
    1. El **nom de compte d'ADLS Gen 2** és el nom del compte d'emmagatzematge al qual voleu desar l'exportació. 
    1. La **ruta de la carpeta** defineix on s'ha d'emmagatzemar l'exportació al sistema de fitxers i l'estructura de directoris del compte d'emmagatzematge.
    1. La **clau compartida** està disponible des del portal de l'Azure per al compte d'emmagatzematge.

1. Reviseu i confirmeu les seleccions.

## <a name="view-and-manage-exports"></a>Visualitzar i administrar exportacions

Un cop hàgiu configurat una exportació, aneu **Dades** > **Exportacions** per visualitzar-la. Seleccioneu **Més [...]** de qualsevol exportació existent per editar-la o suprimir-la.


[!INCLUDE[footer-include](../includes/footer-banner.md)]