---
title: Configuració del sistema a les conclusions del públic
description: Coneixeu la configuració del sistema per a capacitat de conclusions del públic del Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405167"
---
# <a name="system-configuration"></a>Configuració del sistema

La pàgina **Sistema** inclou quatre pestanyes: **Estat**, **Planificació**, **Quant a** i **General**.

> [!div class="mx-imgBorder"]
> ![Pàgina del sistema](media/system-tabs.png "Pàgina del sistema")

## <a name="status-tab"></a>Pestanya Estat

La pestanya **Estat** us permet fer un seguiment del progrés de la ingestió de dades, exportacions de dades i diversos processos del producte importants. Reviseu la informació d'aquesta pestanya per garantir la integritat dels processos actius.

Aquesta pestanya inclou taules d'estat per a **Fonts de dades**, **Processos del sistema** i **Preparació de dades**. Cada taula fa el seguiment del **Nom** de la tasca i l'entitat corresponent, l'**Estat** de l'execució més recent i la data de l'**Última actualització**.

Per visualitzar els detalls de les darreres execucions de les tasques, seleccioneu-ne el nom.

### <a name="status-types"></a>Tipus d'estat

Hi ha sis tipus d'estat per a les tasques. Els tipus d'estat següents també es mostren a les pàgines *Coincidència*, *Combinació*, *Fonts de dades*, *Segments*, *Mesures*, *Enriquiment*, *Activitats* i *Prediccions*:

- **Processament**: la tasca està en curs. L'estat pot canviar a Correcta o Error.
- **Correcta**: s'ha completat correctament la tasca.
- **Omesa:** s'ha omès la tasca. Un o diversos processos descendents dels quals depèn aquesta tasca s'han omès o no s'han completat.
- **Error**: el processament de la tasca ha fallat.
- **Cancel·lada:** l'usuari ha cancel·lat el processament abans d'haver acabat.
- **A la cua**: el processament està a la cua i començarà una vegada s'hagin completat totes les tasques posteriors. Per obtenir més informació, vegeu [Normes d'actualització](#refresh-policies).

### <a name="refresh-policies"></a>Normes d'actualització

En aquesta llista es mostren les normes d'actualització per a cadascun dels processos principals:

- **Fonts de dades**: s'executa segons la [planificació configurada](#schedule-tab). No depèn de cap altre procés. La coincidència depèn de la finalització correcta d'aquest procés.
- **Coincidència**: s'executa segons la [planificació configurada](#schedule-tab). Depèn del processament de les fonts de dades que s'utilitzen a la definició de la concordança. La combinació depèn de la finalització correcta d'aquest procés.
- **Combinació**: s'executa segons la [planificació configurada](#schedule-tab). Depèn de la finalització correcta del procés de coincidència. Els segments, les mesures, l'enriquiment, la cerca, les activitats, les prediccions i la preparació de dades depenen de la finalització correcta d'aquest procés.
- **Segments**: s'executa manualment (l'actualització en un sol temps) i d'acord amb la [planificació configurada](#schedule-tab). Depèn de la combinació. Les estadístiques depenen del seu processament.
- **Mesures**: s'executa manualment (l'actualització en un sol temps) i d'acord amb la [planificació configurada](#schedule-tab). Depèn de la combinació.
- **Activitats**: s'executa manualment (l'actualització en un sol temps) i d'acord amb la [planificació configurada](#schedule-tab). Depèn de la combinació.
- **Enriquiment**: s'executa manualment (l'actualització en un sol temps) i d'acord amb la [planificació configurada](#schedule-tab). Depèn de la combinació.
- **Cerca**: s'executa manualment (l'actualització en un sol temps) i d'acord amb la [planificació configurada](#schedule-tab). Depèn de la combinació.
- **Preparació de dades**: s'executa segons la [planificació configurada](#schedule-tab). Depèn de la combinació.
- **Informació**: s'executa manualment (l'actualització en un sol temps) i d'acord amb la [planificació configurada](#schedule-tab). Depèn dels segments.

Seleccioneu l'estat d'una tasca per veure els detalls del progrés de tota la feina en què es trobava. Les normes d'actualització anteriors us poden ajudar a comprendre què podeu fer per tractar una tasca **Omesa** o **A la cua**.

## <a name="schedule-tab"></a>Pestanya Planificació

Utilitzeu la pestanya **Planificació** per planificar les actualitzacions automàtiques de totes les [fonts de dades ingerides](data-sources.md). Les actualitzacions automàtiques us ajuden a garantir que les actualitzacions de les fonts de dades es reflecteixin als perfils del client unificat.

1. A les conclusions del públic, aneu a **Administració** > **Sistema** i seleccioneu la pestanya **Planificació**.

2. L'estat per defecte de l'actualització planificada és **Desactivada**. Per habilitar les actualitzacions planificades, canvieu el commutador a la part superior de la pantalla a **Activat**.

3. Trieu entre les actualitzacions **Setmanals** (per defecte) i **Diàries**. Si intenteu planificar actualitzacions setmanals, seleccioneu un o diversos dies en què voleu executar l'actualització.

4. Definiu el **Fus horari** i, a continuació, utilitzeu el menú desplegable **Hora** per definir l'hora d'actualització. Quan hàgiu acabat, trieu **Defineix**. Si voleu planificar diverses actualitzacions en un sol dia, seleccioneu **Afegeix una altra hora**.

5. Seleccioneu **Desa** per aplicar els canvis.

## <a name="about-tab"></a>Pestanya Quant a

La pestanya **Quant a** conté el **Nom de visualització** de l'organització, l'**Identificador de l'entorn** actiu, la **Regió** i l'**Identificador de sessió**. Si teniu més d'un entorn de treball, haureu de donar a cadascun un nom de visualització de fàcil identificació.

## <a name="general-tab"></a>Pestanya General

Hi ha dues opcions a la pestanya **General**, **Llengua** i **Format de país o de regió**.

L'aplicació [admet diversos idiomes](supported-languages.md). Per canviar la llengua preferida, trieu una **llengua** al menú desplegable.

Per canviar el format preferit per a les dates, l'hora i els números, utilitzeu el menú desplegable **Format de país o de regió**. Es mostra una visualització prèvia de format en aquest camp. El sistema suggerirà automàticament una opció per triar quan trieu un idioma nou.

Seleccioneu **Desa** per confirmar les seleccions.

## <a name="api-usage-tab"></a>Pestanya Ús de l'API

Cerqueu detalls sobre l'ús de l'API en temps real i consulteu quins esdeveniments s'han produït en un interval de temps determinat. Per obtenir més informació, vegeu [Ingestió de dades en temps real](real-time-data-ingestion.md).
