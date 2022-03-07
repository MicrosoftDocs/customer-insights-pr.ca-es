---
title: Funcions i permisos
description: Informació general de funcions i permisos disponibles per als membres de l'àrea de treball.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227527"
---
# <a name="roles-and-permissions"></a>Funcions i permisos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En un espai de treball s'emmagatzemen i administren incidències i informes. Per obtenir més informació, vegeu [Crear una àrea de treball i afegir-hi membres](create-workspace.md). 

Una àrea de treball pot incloure les funcions i els permisos següents:

- Les funcions de *membre* són usuaris que poden accedir a una àrea de treball. Podeu assignar membres a l'àrea de treball i definir les seves funcions i permisos. 
- Les funcions d'*administrador* administren les àrees de treball i els entorns i configuren les conclusions d'interacció per a altres usuaris. 
- Les funcions de *col·laborador* estan orientades a analistes que no necessiten configurar informació d'interacció, però que volen crear els seus propis informes, embuts o segments.

## <a name="permissions"></a>Permisos
  
A la taula següent s'identifiquen els permisos per a cada funció. 

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
