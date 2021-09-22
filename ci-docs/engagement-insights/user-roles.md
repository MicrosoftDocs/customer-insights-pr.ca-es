---
title: Funcions i permisos
description: Informació general de funcions i permisos disponibles per als membres de l'àrea de treball.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036681"
---
# <a name="roles-and-permissions"></a>Funcions i permisos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Una àrea de treball és com emmagatzemeu i administreu incidències i informes. Un membre és un usuari que pot accedir a una àrea de treball. Podeu assignar membres a l'àrea de treball i definir les seves funcions i permisos. Les funcions d'administrador administren les àrees de treball i els entorns i configuren les conclusions d'interacció per a altres usuaris. Les funcions de col·laborador estan dirigides a analistes que no necessiten configurar les conclusions d'interacció, però volen crear els seus propis informes, embuts de conversió o segments.

## <a name="permissions"></a>Permisos
  
El gràfic següent identifica permisos per a cada funció. 

| Permís | Administrador de l'entorn | Administrador de l'àrea de treball | Col·laborador de l'entorn | Col·laborador de l'àrea de treball | 
|--|--|--|--|--|
| Creeu entorns (l'autor es converteix automàticament en l'administrador de l'entorn) | X* | X* | X* | X* |  
| Configureu l'entorn (membres de l'entorn, suprimiu l'entorn) | X |  |  |  |  
| Creeu àrees de treball | X |  |  |  |  
| Configurar les àrees de treball (membres de l'àrea de treball, suprimir l'àrea de treball) | X | X |  |  |  
| Configureu incidències i incidències refinades | X | X | |  |  
| Visualitzeu incidències i incidències refinades de l'àrea de treball | X | X | |  |  
| Visualitzeu recursos de l'àrea de treball (informes, segments i mètriques)| X | X | X | X |  
| Creació d'informes personalitzats i embuts de conversió | X | X | X | X |  
| Crear mètriques i dimensions base| X | X |  |  |  
| Crear segments| X | X | X | X |  

*Només es poden crear entorns de prova amb la versió preliminar. 

## <a name="add-members"></a>Addició de membres

Podeu afegir o suprimir membres d'àrees de treball i d'entorns. Per obtenir més informació, vegeu [Entorns i àrees de treball](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
