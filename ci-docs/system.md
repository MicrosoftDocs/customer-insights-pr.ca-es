---
title: Veure la configuració del sistema
description: Més informació sobre la configuració del sistema al Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246235"
---
# <a name="view-system-configuration"></a>Veure la configuració del sistema

Visualitzeu la informació del sistema, l'estat del sistema i l'ús de l'API.

## <a name="view-api-usage"></a>Veure l'ús de l'API

Consulteu els detalls sobre l'ús de l'API en temps real i vegeu quins esdeveniments han passat en un període de temps determinat.

1. Aneu a **Sistema d'administració** > **i** seleccioneu la pestanya Ús de l'API **·**.

1. **Seleccioneu un període de** temps per visualitzar-lo.

   La **pàgina d'ús de l'API** conté tres seccions:

   - **Trucades de l'API**: un gràfic que mostra el nombre agregat de trucades a l'API en el període de temps seleccionat.
   - **Transferència de dades**: un gràfic que mostra la quantitat de dades que s'han transferit a través de l'API en el període de temps seleccionat.
   - **Operacions**: una taula amb files per a cada operació de l'API disponible i detalls sobre l'ús de les operacions. Seleccioneu un nom d'operació per anar a [la referència](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) de l'API.

   Les operacions que utilitzen [la ingestió](real-time-data-ingestion.md) de dades en temps real contenen un símbol binocular per veure l'ús de l'API en temps real.

   1. Seleccioneu els prismàtics per obrir la subfinestra d'ús de l'API **en** temps real que conté els detalls d'ús de l'operació.
   1. **Seleccioneu un període de** temps per visualitzar-lo.
   1. Utilitzeu grup **per quadre per** triar com presentar millor les vostres interaccions en temps real. Agrupeu les dades per mètode API, nom qualificat d'entitat **(entitat ingerida),** Creat per **(origen de l'esdeveniment),** Resultat **(èxit o fracàs) o** Codis **d'error.** **·** Les dades estan disponibles com a gràfic d'historial i com a taula.

## <a name="view-system-information"></a>Veure la informació del sistema

Visualitzeu el nom de visualització de l'entorn, l'identificador, la regió, el tipus i l'identificador de sessió.

1. Aneu a **Sistema d'administració** > **i** seleccioneu la **pestanya Quant a**.

1. Per visualitzar l'idioma i el país/regió, seleccioneu la **pestanya General**.

### <a name="update-preferred-language-or-countryregion"></a>Actualitzar l'idioma o el país o la regió preferits

El Customer Insights [admet molts idiomes](/dynamics365/get-started/availability). L'aplicació utilitza la vostra preferència d'idioma per mostrar elements com ara el menú, el text de l'etiqueta i els missatges del sistema en el vostre idioma preferit.

Les dades importades i la informació que heu introduït manualment no estan traduïdes.

1. Aneu a **Sistema d'administració** > **i** seleccioneu la **pestanya General**.

1. Per canviar la llengua preferida, trieu una **llengua** al menú desplegable.

1. Per canviar el format preferit per a les dates, l'hora i els números, utilitzeu el menú desplegable **Format de país o de regió**. Es mostra una previsualització de format. El sistema suggereix automàticament una selecció quan trieu un idioma nou.

1. Seleccioneu **Desa**.

## <a name="view-system-status"></a>Visualitza l'estat del sistema

Feu un seguiment del progrés de les tasques, la ingestió de dades, les exportacions de dades i diversos altres processos importants de productes. Reviseu la informació per garantir la integritat de les vostres tasques i processos actius.

1. Aneu a **Sistema d'administració** > **i** seleccioneu la **pestanya Estat**.

   Visualització d'informació d'estat i processament per a diversos processos. Visualitzeu el **nom** de la tasca, l'estat **de la** seva execució més recent i quan es va **actualitzar per última vegada**.

1. Per veure els detalls de les darreres execucions, seleccioneu la tasca o el nom del procés.

1. Per veure els detalls del progrés d'una tasca, seleccioneu l'estat. Es mostra **la subfinestra Detalls** del progrés.

   :::image type="content" source="media/system-progress-details.png" alt-text="Subfinestra detalls del progrés del sistema":::

1. Per veure els detalls del progrés de totes les tasques, seleccioneu **Flux de treball** complet.

### <a name="status-definitions"></a>Definicions d'estat

El sistema utilitza els següents estats per a tasques i processos:

|Estat d'execució  |Definició  |
|---------|---------|
|Cancel·lada |L'usuari ha cancel·lat la tasca o el procés abans que finalitzi.   |
|Erroni   |La tasca o el procés es van trobar amb errors.         |
|Error  |La tasca o el procés ha fallat.  |
|No s'ha iniciat   |Font de dades encara no ha ingerit dades o la tasca encara està en mode esborrany.         |
|S’està processant  |La tasca o procés està en curs.  |
|S'està actualitzant    |La tasca o procés està en curs. Per cancel·lar aquesta operació, seleccioneu **Actualitza** i **Cancel·la la feina**. Aturar l'actualització d'una tasca o procés el revertirà al seu últim estat d'actualització.       |
|Omès  |S'ha omès la tasca o el procés. Un o diversos processos descendents dels quals depèn aquesta tasca s'han omès o no s'han completat.|
|Correcte  |Tasca o procés completat amb èxit. En el cas de les fonts de dades, indica que les dades s'han ingerit correctament si s'esmenta un temps a la **columna Actualitza**.|
|A la cua | El processament està en cua i s'iniciarà un cop finalitzades totes les tasques i processos ascendents. Per obtenir més informació, vegeu [Actualització dels processos](#refresh-processes).|

### <a name="refresh-processes"></a>Processos d'actualització

L'actualització de tasques i processos s'executa segons la [planificació](schedule-refresh.md) configurada.

|Processar  |Descripció  |
|---------|---------|
|Activitat  |S'executa manualment (refresca una sola vegada). Depèn del procés de fusió. Les estadístiques depenen del seu processament.|
|Enllaç de l'anàlisi |S'executa manualment (refresca una sola vegada). Depèn dels segments.  |
|Preparació de l'anàlisi |S'executa manualment (refresca una sola vegada). Depèn dels segments.  |
|Preparació de les dades   |Necessita una entitat per executar-se. Font de dades entitats depenen de la ingestió. Les entitats enriquides depenen dels enriquiments. L'entitat Client depèn de la combinació.  |
|Fonts de dades   |No depèn de cap altre procés. La coincidència depèn de la finalització correcta d'aquest procés.  |
|Enriquiments   |S'executa manualment (refresca una sola vegada). Depèn del procés de fusió. |
|Destinacions d'exportació |S'executa manualment (refresca una sola vegada). Depèn dels segments.  |
|Informació detallada |S'executa manualment (refresca una sola vegada). Depèn dels segments.  |
|Intel·ligència   |Depèn de la fusió.   |
|Coincidència |Depèn del processament de les fonts de dades que s'utilitzen a la definició de la concordança.      |
|Mesures  |S'executa manualment (refresca una sola vegada). Depèn del procés de fusió.  |
|Combinació   |Depèn de la finalització correcta del procés de coincidència. Els segments, les mesures, l'enriquiment, la cerca, les activitats, les prediccions i la preparació de dades depenen de la finalització correcta d'aquest procés.   |
|Perfils   |S'executa manualment (refresca una sola vegada). Depèn del procés de fusió. |
|Cercar   |S'executa manualment (refresca una sola vegada). Depèn del procés de fusió. |
|Segments  |S'executa manualment (refresca una sola vegada). Depèn del procés de fusió. Les estadístiques depenen del seu processament.|
|Sistema   |Depèn de la finalització correcta del procés de coincidència. Els segments, les mesures, l'enriquiment, la cerca, les activitats, les prediccions i la preparació de dades depenen de la finalització correcta d'aquest procés.   |
|User  |S'executa manualment (refresca una sola vegada). Depèn de les entitats.  |

Seleccioneu l'estat d'un procés per veure els detalls del progrés de tota la feina en què es trobava. Els processos d'actualització anteriors us poden ajudar a entendre què podeu fer per abordar una **tasca o procés omès** o **en** cua.


[!INCLUDE [footer-include](includes/footer-banner.md)]
