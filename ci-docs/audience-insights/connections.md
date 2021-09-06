---
title: Connexions amb altres serveis des del Customer Insights.
description: Compartiu dades amb altres serveis.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 37c5d152a4cc91a90df8db387d25923ed150e238bc6b54c54f7bba59fbd48c82
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033206"
---
# <a name="connections-preview-overview"></a>Informació general sobre les connexions (versió preliminar)

Les connexions són la clau per permetre l'ús compartit de dades al i des del Customer Insights. Cada connexió estableix l'ús compartit de dades amb un servei específic. Les connexions són la base per [configurar millores de tercers](enrichment-hub.md) i [configurar les exportacions](export-destinations.md). La mateixa connexió es pot utilitzar diverses vegades. Per exemple, una connexió al Dynamics 365 Marketing funciona per a diverses exportacions i es pot utilitzar una connexió de Leadspace per a diverses millores.

Aneu a **Administració** > **Connexions** per crear i visualitzar connexions.

La pestanya **Connexions** mostra totes les connexions actives. La llista mostra una fila per a cada connexió. 

Podeu obtenir una descripció general ràpida, una descripció i saber què podeu fer amb cada opció d'extensibilitat a la pestanya **Descobriu**.

### <a name="exports"></a>Exportacions

Només els administradors poden configurar noves connexions, però poden atorgar accés als col·laboradors perquè utilitzin connexions existents. Els administradors controlen on poden anar les dades, els col·laboradors defineixen la càrrega i la freqüència que s'ajusten a les seves necessitats. Per obtenir més informació, vegeu [Permetre que els col·laboradors utilitzin una connexió per a les exportacions](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Enriquiments

Només els administradors poden configurar noves connexions, però les connexions creades sempre estan disponibles per als administradors i per als col·laboradors. Els administradors administren les credencials i donen el consentiment per a les transferències de dades. A continuació, les connexions es poden utilitzar per a enriquiments dels administradors i els col·laboradors.

## <a name="add-a-new-connection"></a>Afegir una connexió nova

Per afegir connexions, heu de tenir [permisos d'administrador](permissions.md). Si us connecteu amb altres serveis de Microsoft, suposem que ambdós serveis són a la mateixa organització.

1. Aneu a **Administració** > **Connexions (versió preliminar)**.

1. Aneu a la pestanya **Connexions**.

1. Seleccioneu **Afegeix una connexió** per crear una connexió nova. Trieu al menú desplegable el tipus de connexió que voleu crear.

1. A la subfinestra **Configuració de la connexió**, proporcioneu els detalls necessaris. 
   1. El **Nom de visualització** i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.
   1. Els camps exactes depenen del servei amb què us connecteu. Podeu obtenir informació sobre els detalls d'un tipus de connexió específic a l'article sobre el servei de destinació.

1. Per crear la connexió, seleccioneu **Desa**.

També podeu seleccionar **Configura** en una peça de la pestanya **Descobreix**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permetre que els col·laboradors utilitzin una connexió per a les exportacions

Quan configureu o editeu una connexió d'exportació, trieu quins usuaris poden utilitzar aquesta connexió específica per definir les [exportacions](export-destinations.md). Per defecte, hi ha disponible una connexió per als usuaris que tenen una funció d'administrador. Podeu canviar aquesta opció a **Trieu qui pot utilitzar aquesta connexió** i permetre als usuaris que tenen la funció de col·laborador utilitzar aquesta connexió.

- Els col·laboradors no podran visualitzar ni editar la connexió. Només veuran el nom de visualització i el tipus en crear una exportació.
- Mitjançant l'ús compartit d'una connexió, permeteu que els col·laboradors utilitzin una connexió. Els col·laboradors veuran les connexions compartides quan configurin exportacions. Poden administrar totes les exportacions que utilitzin aquesta connexió específica.
- Podeu canviar aquesta configuració mantenint les exportacions que ja han estat definides pels col·laboradors.

## <a name="edit-a-connection"></a>Editar una connexió

1. Aneu a **Administració** > **Connexions (versió preliminar)**.

1. Aneu a la pestanya **Connexions**.

1. Seleccioneu els punts suspensius verticals de la connexió que voleu editar.

1. Seleccioneu **Editar**.

1. Canvieu els valors que voleu actualitzar i seleccioneu **Desa**.

## <a name="remove-a-connection"></a>Suprimir una connexió

Si la connexió que suprimiu s'utilitza amb enriquiments o exportacions, primer les heu de desvincular o suprimir. El quadre de diàleg de supressió us guiarà als enriquiments o exportacions rellevants. 

Els enriquiments i les exportacions desvinculats esdevenen inactius. Els reactiveu afegint-hi una altra connexió a la pàgina [Enriquiments](enrichment-hub.md) o [Exportacions](export-destinations.md).

1. Aneu a **Administració** > **Connexions (versió preliminar)**.

1. Aneu a la pestanya **Connexions**.

1. Seleccioneu els punts suspensius verticals de la connexió que voleu eliminar.

1. Seleccioneu **Suprimeix** al menú desplegable. Apareix un quadre de diàleg de confirmació.

   1. Si hi ha enriquiments o exportacions que utilitzen aquesta connexió, seleccioneu el botó per veure què utilitza la connexió.
      - **Exportacions:** podeu triar si voleu suprimir o desconnectar les exportacions per poder suprimir la connexió. Per desconnectar una exportació, els administradors poden utilitzar l'acció **Desconnecta**. Aquesta acció està disponible per a exportacions individuals i múltiples exportacions seleccionades. En desconnectar-les, conserveu la configuració de l'exportació, però no s'executarà fins que s'hi afegeixi una altra connexió.
      - **Enriquiments**: podeu triar si voleu suprimir o desactivar els enriquiments per poder suprimir la connexió. 
   1. Quan la connexió no té més dependències, torneu a **Administració** > **Connexions** i torneu a provar de suprimir la connexió.

1. Per confirmar la supressió, seleccioneu **Suprimeix**.

