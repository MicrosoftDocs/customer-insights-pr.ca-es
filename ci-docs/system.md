---
title: Configuració del sistema
description: Més informació sobre la configuració del sistema al Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 0ef84d8e286d8135eb8938e72f1319925e948bed
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050659"
---
# <a name="system-configuration"></a>Configuració del sistema

Per accedir a les configuracions del sistema, aneu al **sistema** > **d'administració** per visualitzar una llista de tasques i processos del sistema.

La pàgina **Sistema** inclou les pestanyes següents:
- [Estat d'execució](#status-tab)
- [Planifica](#schedule-tab)
- [Ús de l'API](#api-usage-tab)
- [Quant a](#about-tab)
- [General](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Pestanyes de configuració de la pàgina del sistema.":::

## <a name="status-tab"></a>Pestanya Estat

La **pestanya** Estat us permet fer un seguiment del progrés de les tasques, la ingestió de dades, les exportacions de dades i diversos altres processos importants de productes. Reviseu la informació d'aquesta pestanya per assegurar la integritat de les vostres tasques i processos actius.

Aquesta pestanya inclou taules amb estat i informació de processament per a diversos processos. Cada taula fa el seguiment del **Nom** de la tasca i l'entitat corresponent, l'**Estat** de l'execució més recent i la data de l'**Última actualització**. Podeu veure els detalls de les últimes diverses carreres seleccionant el nom de la tasca o del procés. 

Seleccioneu l'estat que hi ha al costat de la tasca o del procés a la **columna Estat** per obrir la subfinestra Detalls **del** progrés.

   :::image type="content" source="media/system-progress-details.png" alt-text="Subfinestra de detalls del progrés del sistema":::

### <a name="status-definitions"></a>Definicions d'estat

El sistema utilitza els estats següents per a tasques i processos:

|Estat d'execució  |Definició  |
|---------|---------|
|Cancel·lada |L'usuari ha cancel·lat el processament abans d'acabar-lo.   |
|Erroni   |L'ingestió de dades ha trobat errors.         |
|Error  |El processament ha fallat.  |
|No s'ha iniciat   |La font de dades no té encara dades ingerides o encara es troben en mode d'esborrany.         |
|S’està processant  |La tasca o el procés està en curs.  |
|S'està actualitzant    |La ingestió de dades està en curs. Per cancel·lar aquesta operació, seleccioneu **Deixa d'actualitzar** a la columna **Accions**. Si atureu l'actualització d'una font de dades, es revertirà a l'últim estat d'actualització.       |
|Omès  |S'ha omès la tasca o el procés. Un o diversos processos descendents dels quals depèn aquesta tasca s'han omès o no s'han completat.|
|Correcte  |La tasca o el procés s'han completat correctament. Per a les fonts de dades, indica que les dades s'han ingerit correctament si s'esmenta un temps a la **columna Actualització**.|
|A la cua | El processament està a la cua i s'iniciarà un cop s'hagin completat totes les tasques i processos originals. Per obtenir més informació, vegeu [Actualitza els processos](#refresh-processes).|

### <a name="refresh-processes"></a>Actualitza els processos

L'actualització de les tasques i els processos s'executa segons la [planificació](#schedule-tab) configurada. 

|Processar  |Descripció  |
|---------|---------|
|Activitat  |S'executa manualment (actualització d'una sola hora). Depèn del procés de fusió. Les estadístiques depenen del seu processament.|
|Enllaç de l'anàlisi |S'executa manualment (actualització d'una sola hora). Depèn dels segments.  |
|Preparació de l'anàlisi |S'executa manualment (actualització d'una sola hora). Depèn dels segments.  |
|Preparació de les dades   |Necessita una entitat per executar-se. Font de dades entitats depenen de la ingestió. Les entitats enriquides depenen d'enriquiments. L'entitat Client depèn de la combinació.  |
|Fonts de dades   |No depèn de cap altre procés. La coincidència depèn de la finalització correcta d'aquest procés.  |
|Enriquiments   |S'executa manualment (actualització d'una sola hora). Depèn del procés de fusió. |
|Exporta destinacions |S'executa manualment (actualització d'una sola hora). Depèn dels segments.  |
|Informació detallada |S'executa manualment (actualització d'una sola hora). Depèn dels segments.  |
|Intel·ligència   |Depèn de la fusió.   |
|Coincidència |Depèn del processament de les fonts de dades que s'utilitzen a la definició de la concordança.      |
|Mesures  |S'executa manualment (actualització d'una sola hora). Depèn del procés de fusió.  |
|Combinació   |Depèn de la finalització correcta del procés de coincidència. Els segments, les mesures, l'enriquiment, la cerca, les activitats, les prediccions i la preparació de dades depenen de la finalització correcta d'aquest procés.   |
|Perfils   |S'executa manualment (actualització d'una sola hora). Depèn del procés de fusió. |
|Cercar   |S'executa manualment (actualització d'una sola hora). Depèn del procés de fusió. |
|Segments  |S'executa manualment (actualització d'una sola hora). Depèn del procés de fusió. Les estadístiques depenen del seu processament.|
|Sistema   |Depèn de la finalització correcta del procés de coincidència. Els segments, les mesures, l'enriquiment, la cerca, les activitats, les prediccions i la preparació de dades depenen de la finalització correcta d'aquest procés.   |
|User  |S'executa manualment (actualització d'una sola hora). Depèn de les entitats.  |

Seleccioneu l'estat d'un procés per veure els detalls de progrés de tota la feina en què es trobava. Els processos d'actualització anteriors poden ajudar a entendre què podeu fer per adreçar-vos a una **tasca o** procés o a la cua **o omès.**

## <a name="schedule-tab"></a>Pestanya Planificació

Utilitzeu la pestanya **Planificació** per planificar les actualitzacions automàtiques de totes les [fonts de dades ingerides](data-sources.md). Les actualitzacions automàtiques us ajuden a garantir que les actualitzacions de les fonts de dades es reflecteixin als perfils del client unificat.

> [!NOTE]
> Les fonts de dades gestionades per vosaltres actualitzeu-les a les seves pròpies planificacions. Per planificar l'actualització dels orígens de dades gestionats per vosaltres, configureu la configuració d'actualització d'aquesta font de dades específica des de la **pàgina Orígens** de dades.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Configuració d'actualització del flux de dades.":::

1. Aneu al **sistema** > **d'administració** i seleccioneu la **pestanya Planificació**.

2. L'estat per defecte de l'actualització planificada és **Desactivada**. Per habilitar les actualitzacions planificades, canvieu el commutador a la part superior de la pantalla a **Activat**.

3. Trieu entre les actualitzacions **Setmanals** (per defecte) i **Diàries**. Si intenteu planificar actualitzacions setmanals, seleccioneu un o diversos dies en què voleu executar l'actualització.

4. Definiu el **Fus horari** i, a continuació, utilitzeu el menú desplegable **Hora** per definir l'hora d'actualització. Quan hàgiu acabat, trieu **Defineix**. Si voleu planificar diverses actualitzacions en un sol dia, seleccioneu **Afegeix una altra hora**.

5. Seleccioneu **Desa** per aplicar els canvis.

## <a name="about-tab"></a>Pestanya Quant a

La pestanya **Quant a** conté el **Nom de visualització** de l'organització, l'**Identificador de l'entorn** actiu, la **Regió** i l'**Identificador de sessió**. Si teniu més d'un entorn de treball, haureu de donar a cadascun un nom de visualització de fàcil identificació.

## <a name="general-tab"></a>Pestanya General

Podeu canviar la llengua i el format de país/regió a la pestanya **General**.

Customer Insights [admet molts idiomes](/dynamics365/get-started/availability). L'aplicació utilitza la vostra preferència d'idioma per mostrar elements com ara el menú, el text de l'etiqueta i els missatges del sistema en el vostre idioma preferit.

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

   Les operacions que utilitzen [la ingestió](real-time-data-ingestion.md) de dades en temps real contenen un botó amb un símbol binocular per veure l'ús de l'API en temps real. Seleccioneu el botó per obrir una subfinestra lateral amb detalls per a l'ús de l'API en temps real a l'entorn actual.   
   Utilitzeu el quadre **Agrupa per** a la subfinestra **Ús de l'API en temps real** per triar com es presenten millor les interaccions en temps real. Podeu agrupar les dades per mètode de l'API, nom complet de l'entitat (entitat ingerida), creat per (origen de la incidència), resultat (correcte o error) o codis d'error. Les dades estan disponibles com a gràfic d'historial i com a taula.


[!INCLUDE [footer-include](includes/footer-banner.md)]
