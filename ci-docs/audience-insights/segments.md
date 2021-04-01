---
title: Crear i administrar segments
description: Creeu segments de clients per agrupar-los segons diversos atributs.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597039"
---
# <a name="create-and-manage-segments"></a>Crear i administrar segments

Els segments us permeten agrupar els clients segons atributs demogràfics, de transaccions o de comportament. Podeu utilitzar segments per orientar les campanyes promocionals, les activitats de vendes i les accions d'atenció al client per assolir els vostres objectius empresarials.

Podeu definir filtres complexos sobre l'entitat Perfil del client i les entitats relacionades. Cada segment, després del processament, crea un conjunt de registres de client que podeu exportar i on podeu prendre mesures. S'apliquen [límits de servei](service-limits.md).

Si no s'indica el contrari, tots els segments són **Segments dinàmics**, que s'actualitzen segons una planificació periòdica.

A l'exemple següent s'il·lustra l'ús de la capacitat de segmentació. Hem definit un segment per a clients que han encarregat com a mínim 500 USD de mercaderies en els últims 90 dies *i* que han participat en una trucada al servei d'atenció al client que s'ha derivat.

> [!div class="mx-imgBorder"]
> ![Diversos grups](media/segmentation-group1-2.png "Diversos grups")

## <a name="create-a-new-segment"></a>Crear un segment nou

Els segments s'administren a la pàgina **Segments**.

1. A les conclusions del públic, aneu a la pàgina **Segments**.

1. Seleccioneu **Nou** > **Segment en blanc**.

1. A la subfinestra **Segment nou**, trieu un tipus de segment i proporcioneu un **Nom**.

   Opcionalment, proporcioneu un nom de visualització i una descripció que ajudi a identificar el segment.

1. Seleccioneu **Següent** per accedir a la pàgina **Creador de segments** on definiu un grup. Un grup és un conjunt de clients.

1. Trieu l'entitat que inclou l'atribut pel qual voleu segmentar.

1. Trieu l'atribut pel qual voleu segmentar. Aquest atribut pot tenir un de quatre tipus de valors: numèric, cadena, data o booleà.

1. Trieu un operador i un valor per a l'atribut seleccionat.

   > [!div class="mx-imgBorder"]
   > ![Filtre de grup personalitzat](media/customer-group-numbers.png "Filtre de grup de client")

   |Número |Definició  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operador         |
   |4    |Valor         |

8. Si l'entitat està connectada a l'entitat de client unificada per [relacions](relationships.md), heu de definir el camí de la relació per crear un segment vàlid. Afegiu les entitats del camí de la relació fins que pugueu seleccionar l'entitat **Client: CustomerInsights** del menú desplegable. A continuació, trieu **Tots els registres** per a cada condició.

   > [!div class="mx-imgBorder"]
   > ![Camí de la relació durant la creació del segment](media/segments-multiple-relationships.png "Camí de la relació durant la creació del segment")

1. Per defecte, els segments generen una entitat de sortida que conté tots els atributs dels perfils de client que coincideixen amb els filtres definits. Si un segment es basa en entitats que no són l'entitat *Client*, podeu afegir més atributs d'aquestes entitats a l'entitat de sortida. Seleccioneu **Atributs del projecte** per triar els atributs que s'annexaran a l'entitat de sortida.  

   
   Exemple: un segment es basa en una entitat que conté dades d'activitat de client relacionades amb l'entitat *Client*. El segment cerca tots els clients que han trucat al servei d'assistència durant els darrers 60 dies. Podeu triar si voleu annexar la durada de la trucada i el nombre de trucades a tots els registres de client coincidents de l'entitat de sortida. Aquesta informació pot ser útil per enviar correus electrònics amb enllaços útils als articles d'ajuda en línia i preguntes freqüents als clients que truquen sovint.

1. Seleccioneu **Desa** per desar el segment. El segment es desa i es processa si es validen tots els requisits. Altrament, es desarà com a esborrany.

1. Seleccioneu **Torna als segments** per tornar a la pàgina **Segments**.

## <a name="manage-existing-segments"></a>Administrar segments existents

A la pàgina **Segments**, podeu visualitzar tots els segments desats i administrar-los.

Cada segment està representat per una fila que inclou informació addicional sobre el segment.

Podeu ordenar els segments en una columna seleccionant la capçalera de la columna.

Utilitzeu el quadre **Cerca** de la cantonada superior dreta per filtrar els segments.

> [!div class="mx-imgBorder"]
> ![Opcions per administrar un segment existent](media/segments-selected-segment.png "Opcions per administrar un segment existent")

L'acció següent està disponible quan seleccioneu un segment:

- **Visualitzar** els detalls del segment, incloent-hi la tendència de recompte de membres per obtenir la visualització prèvia dels membres del segment.
- **Editar** el segment per canviar-ne les propietats.
- **Crear un duplicat** d'un segment. Podeu editar-ne les propietats immediatament o simplement desar el duplicat.
- **Actualitzar** el segment per incloure-hi les dades més recents.
- **Activar** o **desactivar** el segment. Els segments tenen dos estats possibles: actiu o inactiu. Aquests estats són útils en editar un segment. Per als segments inactius, la definició del segment existeix però encara no conté cap client. Quan s'activa un segment, el seu estat canvia d'"inactiu" a "actiu" i comença a cercar clients que coincideixin amb la definició del segment. Si es configura una [actualització planificada](system.md#schedule-tab), els segments inactius tenen l'**estat** **Omès**, indicant que ni tan sols s'ha intentat una actualització. Quan s'activi un segment inactiu, s'actualitzarà i s'inclourà en les actualitzacions programades.
  Alternativament, podeu utilitzar la funcionalitat **Planifica més tard** al desplegable **Activa o desactiva** per especificar una data i hora futura per a l'activació i la desactivació d'un segment concret.
- **Canviar el nom** del segment.
- **Baixar** la llista de membres com a fitxer .CSV.
- L'opció **Afegeix a** envia la llista d'identificadors de clients al segment per al processament en una altra aplicació.
- **Suprimir** el segment.

## <a name="refresh-segments"></a>Actualitzar els segments

Per actualitzar tots els segments a la vegada, seleccioneu **Actualitza-ho tot** a la pàgina **Segments**; o bé, podeu actualitzar un o diversos segments quan els seleccioneu i trieu **Actualitza** a les opcions. O bé, podeu configurar una actualització periòdica a la planificació a **Administració** > **Sistema** > **Planificació**.

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.

## <a name="download-and-export-segments"></a>Baixar i exportar segments

Podeu baixar els segments en un fitxer CSV o exportar-lo al Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Baixar els segments a un fitxer CSV

1. A les conclusions del públic, aneu a la pàgina **Segments**.

2. Seleccioneu els punts suspensius de la peça d'un segment específic.

3. Seleccioneu **Baixa com a CSV** a la llista desplegable d'accions.

### <a name="export-segments-to-dynamics-365-sales"></a>Exportar segments al Dynamics 365 Sales

Abans d'exportar els segments al Dynamics 365 Sales, un administrador ha de [crear la destinació d'exportació](export-destinations.md) per al Dynamics 365 Sales.

1. A les conclusions del públic, aneu a la pàgina **Segments**.

2. Seleccioneu els punts suspensius de la peça d'un segment específic.

3. Seleccioneu **Afegeix a** de la llista desplegable d'accions i seleccioneu la destinació d'exportació a la qual voleu enviar les dades.

## <a name="draft-mode-for-segments"></a>Mode d'esborrany per a segments

Si no es compleixen tots els requisits per processar un segment, podeu desar el segment com a esborrany i accedir-hi des de la pàgina **Segments**.

Es desarà com a segment inactiu i no es podrà activar fins que sigui vàlid.

## <a name="add-more-conditions-to-a-group"></a>Afegir més condicions a un grup

Per afegir més condicions a un grup, podeu utilitzar dos operadors lògics:

- Operador **AND**: cal complir ambdues condicions com a part del procés de segmentació. Aquesta opció és més útil quan definiu les condicions entre diverses entitats diferents.

- Operador **OR**: una de les condicions ha de complir-se com a part del procés de segmentació. Aquesta opció és més útil quan definiu diverses condicions per a la mateixa entitat.

   > [!div class="mx-imgBorder"]
   > ![Operador OR quan s'ha de complir qualsevol condició](media/segmentation-either-condition.png "Operador OR quan s'ha de complir qualsevol condició")

Actualment és possible imbricar un operador **OR** en un operador **AND**, però no a l'inrevés.

## <a name="combine-multiple-groups"></a>Combinar diversos grups

Cada grup produeix un conjunt específic de clients. Podeu combinar aquests grups per incloure els clients necessaris per al cas empresarial.

1. A les conclusions del públic, aneu a la pàgina **Segments** i seleccioneu un segment.

2. Seleccioneu **Afegeix un grup**.

   > [!div class="mx-imgBorder"]
   > ![Afegir un grup a un grup de clients](media/customer-group-add-group.png "Afegir un grup a un grup de clients")

3. Seleccioneu un dels operadors de conjunt següents: **Unió**, **Intersecció** o **Excepció**.

   > [!div class="mx-imgBorder"]
   > ![Afegir una unió a un grup de clients](media/customer-group-union.png "Afegir una unió a un grup de clients")

   Seleccioneu un operador de conjunt per definir un grup nou. Deseu diversos grups per determinar quines dades es conserven:

   - **Unió** uneix els dos grups.

   - **Intersecció** solapa els dos grups. Només es conserven al grup unificat les dades *que siguin comunes* a tots dos grups.

   - **Excepte** combina els dos grups. Només es conserven les dades del grup A que *no siguin comunes* a les dades del grup B.

## <a name="view-processing-history-and-segment-members"></a>Visualitzar l'historial de processament i els membres del segment

Podeu veure les dades consolidades d'un segment revisant-ne els detalls.

A la pàgina **Segments**, seleccioneu el segment que voleu revisar.

A la part superior de la pàgina s'inclou una gràfica de tendències que visualitza els canvis al recompte de membres. Passeu el cursor per sobre dels punts de dades per veure el recompte de membres en una data concreta.

Podeu actualitzar el període de temps de la visualització.

> [!div class="mx-imgBorder"]
> ![Interval de temps del segment](media/segment-time-range.png "Interval de temps del segment")

La part inferior conté una llista dels membres del segment.

> [!NOTE]
> Els camps que apareixen en aquesta llista es basen en els atributs de les entitats del vostre segment.
>
>La llista és una visualització prèvia dels membres del segment coincidents i mostra els primers 100 registres del segment per tal que pugueu avaluar-lo ràpidament i revisar-ne les definicions si cal. Per veure tots els registres coincidents, heu d'[exportar el segment](export-destinations.md).

## <a name="quick-segments"></a>Segments ràpids

A banda del creador de segments, hi ha un altre mètode per crear segments. Els segments ràpids permeten la creació de segments simples (amb un únic operador) amb rapidesa i informació instantània.

1. A la pàgina **Segments**, seleccioneu **Nou** > **Crea ràpidament des de**.

   - Seleccioneu l'opció **Perfils** per crear un segment que es basi en l'entitat Client unificada.
   - Seleccioneu l'opció **Mesures** per crear un segment sobre cada tipus d'atribut de client de les mesures que heu creat prèviament a la pàgina **Mesures**.
   - Seleccioneu l'opció **Intel·ligència** per crear un segment sobre una de les entitats de sortida que heu generat mitjançant les funcionalitats **Prediccions** o **Models personalitzats**.

2. Al quadre de diàleg **Crea un segment ràpid**, seleccioneu un atribut del desplegable **Camp**.

3. El sistema proporcionarà alguna informació addicional que us ajudarà a crear millors segments dels vostres clients.
   - Per als camps categòrics, mostrarem 10 comptes de clients principals. Seleccioneu un **Valor** i seleccioneu **Revisa**.

   - Per a un atribut numèric, el sistema mostrarà quin valor de l'atribut queda en el percentil de cada client. Trieu un **Operador** i un **Valor** i, a continuació, seleccioneu **Revisa**.

4. El sistema us proporcionarà una **Mida de segment aproximada**. Podeu triar si voleu generar el segment que heu definit o, en primer lloc, tornar a examinar-lo per aconseguir una mida diferent del segment.

    > [!div class="mx-imgBorder"]
    > ![Nom i estimació per a un segment ràpid](media/quick-segment-name.png "Nom i estimació per a un segment ràpid")

5. Proporcioneu un **Nom** per al segment. Opcionalment, proporcioneu un **Nom de visualització**.

6. Seleccioneu **Desa** per crear el segment.

7. Quan el segment s'hagi acabat de processar, podeu visualitzar-lo com qualsevol altre segment que hàgiu creat.

Per a les situacions següents, aconsellem utilitzar el creador de segments en comptes de la funció de segments recomanats:

- Crear segments amb filtres en camps categòrics on l'operador és diferent de l'operador **És**
- Crear segments amb filtres en camps numèrics on l'operador és diferent d'**Entre**, **Més gran que** i **Més petit que**
- Crear segments amb filtres en camps de tipus de data

## <a name="next-steps"></a>Passos següents

[Exporteu un segment](export-destinations.md) i exploreu la [targeta del client](customer-card-add-in.md) i els [connectors](export-power-bi.md) per obtenir informació al nivell del client.


[!INCLUDE[footer-include](../includes/footer-banner.md)]