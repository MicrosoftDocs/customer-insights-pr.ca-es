---
title: Configuració del sistema a les conclusions del públic
description: Coneixeu la configuració del sistema per a capacitat de conclusions del públic del Dynamics 365 Customer Insights.
ms.date: 10/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3ce767939b8fedf676dc569ede47104ecfe930dd
ms.sourcegitcommit: cd9f9a9d3da71c5420ef5c4c6ead91bc820d17a9
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/19/2021
ms.locfileid: "7651828"
---
# <a name="system-configuration"></a>Configuració del sistema

La pàgina **Sistema** inclou les pestanyes següents:
- [Estat d'execució](#status-tab)
- [Planifica](#schedule-tab)
- [Ús de l'API](#api-usage-tab)
- [Quant a](#about-tab)
- [General](#general-tab)
- [Seguretat](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Pestanyes de configuració de la pàgina del sistema.":::

## <a name="status-tab"></a>Pestanya Estat

La **pestanya Estat** us permet fer un seguiment del progrés de la ingesta de dades, les exportacions de dades i altres processos de producte importants. Reviseu la informació d'aquesta pestanya per garantir la integritat dels processos actius.

Aquesta pestanya inclou taules amb estat i informació de processament per a diversos processos. Cada taula fa el seguiment del **Nom** de la tasca i l'entitat corresponent, l'**Estat** de l'execució més recent i la data de l'**Última actualització**.

Per visualitzar els detalls de les darreres execucions de les tasques, seleccioneu-ne el nom.

### <a name="status-types"></a>Tipus d'estat

Hi ha sis tipus d'estat per a les tasques. Els tipus d'estat següents també es mostren a les pàgines *Coincidència*, *Combinació*, *Fonts de dades*, *Segments*, *Mesures*, *Enriquiment*, *Activitats* i *Prediccions*:

- **Processament**: la tasca està en curs. L'estat pot canviar a Correcta o Error.
- **Correcta**: s'ha completat correctament la tasca.
- **Omesa:** s'ha omès la tasca. Un o diversos processos descendents dels quals depèn aquesta tasca s'han omès o no s'han completat.
- **Error**: el processament de la tasca ha fallat.
- **Cancel·lada:** l'usuari ha cancel·lat el processament abans d'haver acabat.
- **Cua**: el processament està a la cua i s'iniciarà quan s'hagin completat totes les tasques prèvies. Per obtenir més informació, vegeu [Normes d'actualització](#refresh-policies).

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

Podeu canviar la llengua i el format de país/regió a la pestanya **General**.

El Customer Insights [admet diverses llengües](/dynamics365/get-started/availability). L'aplicació utilitza la vostra preferència d'idioma per mostrar elements com ara el menú, el text de l'etiqueta i els missatges del sistema en el vostre idioma preferit.

Les dades importades i la informació que heu introduït manualment no estan traduïdes.

### <a name="update-the-settings"></a>Actualitzar la configuració

Per canviar la llengua preferida, trieu una **llengua** al menú desplegable.

Per canviar el format preferit per a les dates, l'hora i els números, utilitzeu el menú desplegable **Format de país o de regió**. Es mostra una visualització prèvia de format en aquest camp. El sistema suggerirà automàticament una opció per triar quan trieu un idioma nou.

Seleccioneu **Desa** per confirmar les seleccions.

## <a name="api-usage-tab"></a>Pestanya Ús de l'API

Cerqueu detalls sobre l'ús de l'API en temps real i vegeu quins esdeveniments s'han produït en un període de temps determinat. Trieu el període de temps al menú desplegable **Seleccioneu un període de temps**. 

L'**ús de l'API** conté tres seccions: 
- **Trucades de l'API**: un gràfic que mostra el nombre agregat de trucades a l'API en el període de temps seleccionat.

- **Transferència de dades**: un gràfic que mostra la quantitat de dades que s'han transferit a través de l'API en el període de temps seleccionat.

-  **Operacions**: una taula amb files per a cada operació de l'API disponible i detalls sobre l'ús de les operacions. Podeu seleccionar un nom d'operació per anar a la [referència de l'API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Les operacions que utilitzen la [ingesta de dades en temps real](real-time-data-ingestion.md) contenen un botó amb un símbol de binocles per visualitzar l'ús de l'API en temps real. Seleccioneu el botó per obrir una subfinestra lateral amb detalls per a l'ús de l'API en temps real a l'entorn actual.   
   Utilitzeu el quadre **Agrupa per** a la subfinestra **Ús de l'API en temps real** per triar com es presenten millor les interaccions en temps real. Podeu agrupar les dades per mètode de l'API, nom complet de l'entitat (entitat ingerida), creat per (origen de la incidència), resultat (correcte o error) o codis d'error. Les dades estan disponibles com a gràfic d'historial i com a taula.

## <a name="security-tab"></a>Pestanya Seguretat

La pestanya **Seguretat** us permet enllaçar i administrar el vostre propi [magatzem de claus de l'Azure](/azure/key-vault/general/basic-concepts) a l'entorn.
El magatzem de claus dedicat es pot utilitzar per escenificar i utilitzar els secrets en el límit de compliment de l'organització. Les conclusions del públic poden utilitzar els secrets de l'Azure Key Vault per [configurar connexions](connections.md) amb sistemes de tercers.

Per obtenir més informació, vegeu [Portar el vostre propi magatzem de claus de l'Azure](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]