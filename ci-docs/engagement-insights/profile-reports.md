---
title: Habilitar informes immediats
description: Com es creen informes de perfil immediats agrupats segons el gènere, l'edat i el país o la regió d'origen.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486108"
---
# <a name="out-of-box-profile-reports"></a>Informes de perfil immediats

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un informe és una col·lecció de visualitzacions de dades que us ajuden a comprendre com es comporten els usuaris. En connectar-vos als coneixements d'interacció del Customer Insights, els coneixements d'interacció poden mostrar un informe amb informació sobre els perfils de client unificats. Aquest informe inclou el nombre de perfils que teniu, agrupats segons el gènere, l'edat i la ubicació geogràfica.

## <a name="prerequisites"></a>Requisits previs

L'entorn dels coneixements del públic ha d'emmagatzemar dades en un compte de l'Azure Data Lake Storage administrat pel client.

Si utilitzeu una versió de prova de la capacitat dels coneixements del públic o un entorn d'un llac de dades administrat del Customer Insights, [poseu-vos en contacte amb nosaltres](https://go.microsoft.com/fwlink/?linkid=2145734) per obtenir assistència.  


## <a name="enable-the-customer-profile-report"></a>Habilitar l'informe de perfil de client

Un administrador de l'entorn ha d'[enllaçar informació sobre els compromisos i el públic](integrate-audience-insights-engagement-insights.md).

Després d'especificar els detalls de la connexió, l'administrador pot atorgar accés a altres usuaris de l'organització per veure l'informe. L'administrador de l'entorn que configura la connexió té accés a l'informe automàticament. 

Un cop completada la connexió, la característica **Perfils** estarà disponible a la subfinestra de navegació esquerra. 

- Per veure l'informe, aneu a **Descobrir** > **Perfils**.

L'informe **Perfils** conté visualitzacions sobre el gènere, l'edat i la ubicació geogràfica dels perfils de clients connectats.

:::image type="content" source="media/customer-profiles.png" alt-text="Informe de perfil de client.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]