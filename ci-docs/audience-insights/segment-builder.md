---
title: Crear i administrar segments
description: Creeu segments de clients per agrupar-los segons diversos atributs.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064925"
---
# <a name="create-and-manage-segments"></a>Crear i administrar segments

Definiu filtres complexos per a l'entitat de client unificada i les entitats relacionades. Cada segment, després del processament, crea un conjunt de registres de client que podeu exportar i on podeu prendre mesures. Els segments s'administren a la pàgina **Segments**. 

A l'exemple següent s'il·lustra l'ús de la capacitat de segmentació. Hem definit un segment per a clients que han encarregat com a mínim 500 USD de mercaderies en els últims 90 dies *i* que han participat en una trucada al servei d'atenció al client que s'ha derivat.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captura de pantalla de la IU de creador de segments amb dos grups que especifiquen un segment de client.":::

## <a name="create-a-new-segment"></a>Crear un segment nou

Hi ha diverses maneres de crear un segment nou. Aquesta secció descriu com es crea un *segment en blanc* des de zero. També podeu crear un *segment ràpid* basat en entitats existents o utilitzar els models d'aprenentatge automàtic per obtenir *segments suggerits*. Més informació: [Informació general dels segments](segments.md).

En crear un segment, podeu desar un esborrany. Es desarà com un segment inactiu i no es podrà activar fins que s'hagi acabat amb una configuració vàlida.

1. Aneu a la pàgina **Segments**.

1. Seleccioneu **Nou** > **Segment en blanc**.

1. A la subfinestra **Segment nou**, trieu un tipus de segment:

   - Els **segments dinàmics** [s'actualitzen](segments.md#refresh-segments) segons una planificació periòdica.
   - Els **segments estàtics** s'executen un cop es creen.

1. Proporcioneu un **Nom d'entitat de sortida** per al segment. Opcionalment, proporcioneu un nom de visualització i una descripció que ajudi a identificar el segment.

1. Seleccioneu **Següent** per accedir a la pàgina **Creador de segments** on definiu un grup. Un grup és un conjunt de clients.

1. Trieu l'entitat que inclou l'atribut pel qual voleu segmentar.

1. Trieu l'atribut pel qual voleu segmentar. Aquest atribut pot tenir un de quatre tipus de valors: numèric, cadena, data o booleà.

1. Trieu un operador i un valor per a l'atribut seleccionat.

   > [!div class="mx-imgBorder"]
   > ![Filtre de grup personalitzat](media/customer-group-numbers.png "Filtre de grup de client")

   |Nombre |Definició  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operador         |
   |4    |Valor         |

   1. Per afegir més condicions a un grup, podeu utilitzar dos operadors lògics:

      - Operador **AND**: cal complir ambdues condicions com a part del procés de segmentació. Aquesta opció és més útil quan definiu les condicions entre diverses entitats diferents.

      - Operador **OR**: una de les condicions ha de complir-se com a part del procés de segmentació. Aquesta opció és més útil quan definiu diverses condicions per a la mateixa entitat.

      > [!div class="mx-imgBorder"]
      > ![Operador OR quan s'ha de complir qualsevol condició](media/segmentation-either-condition.png "Operador OR quan s'ha de complir qualsevol condició")

      Actualment és possible imbricar un operador **OR** en un operador **AND**, però no a l'inrevés.

   1. Cada grup coincideix amb el conjunt de clients. Podeu combinar grups per incloure els clients necessaris per al cas empresarial.    
   Seleccioneu **Afegeix un grup**.

      > [!div class="mx-imgBorder"]
      > ![Afegir un grup a un grup de clients](media/customer-group-add-group.png "Afegir un grup a un grup de clients")

   1. Seleccioneu un dels operadors de conjunts: **Union**, **Intersect** o **Except**.

   > [!div class="mx-imgBorder"]
   > ![Afegir una unió a un grup de clients](media/customer-group-union.png "Afegir una unió a un grup de clients")

   - **Unió** uneix els dos grups.

   - **Intersecció** solapa els dos grups. Només es conserven al grup unificat les dades *que siguin comunes* a tots dos grups.

   - **Excepte** combina els dos grups. Només es conserven les dades del grup A que *no siguin comunes* a les dades del grup B.

1. Si l'entitat està connectada a l'entitat de client unificada per [relacions](relationships.md), heu de definir el camí de la relació per crear un segment vàlid. Afegiu les entitats del camí de la relació fins que pugueu seleccionar l'entitat **Client: CustomerInsights** del menú desplegable. A continuació, trieu **Tots els registres** per a cada pas.

   > [!div class="mx-imgBorder"]
   > ![Camí de la relació durant la creació del segment](media/segments-multiple-relationships.png "Camí de la relació durant la creació del segment")

1. Per defecte, els segments generen una entitat de sortida que conté tots els atributs dels perfils de client que coincideixen amb els filtres definits. Si un segment es basa en entitats que no són l'entitat *Client*, podeu afegir més atributs d'aquestes entitats a l'entitat de sortida. Seleccioneu **Atributs del projecte** per triar els atributs que s'annexaran a l'entitat de sortida.  
  
   Exemple: un segment es basa en una entitat que conté dades d'activitat de client relacionades amb l'entitat *Client*. El segment cerca tots els clients que han trucat al servei d'assistència durant els darrers 60 dies. Podeu triar si voleu annexar la durada de la trucada i el nombre de trucades a tots els registres de client coincidents de l'entitat de sortida. Aquesta informació pot ser útil per enviar correus electrònics amb enllaços útils als articles d'ajuda en línia i preguntes freqüents als clients que truquen sovint.

   > [!NOTE]
   > - Els atributs previstos només funcionen per a les entitats que tenen una relació d'un a diversos amb l'entitat de client. Per exemple, un client pot tenir diverses subscripcions.
   > - Només podeu preveure els atributs d'una entitat que s'utilitza a cada grup de consulta de segment que esteu creant.
   > - Els atributs previstos es factoritzen quan s'utilitzen operadors de conjunts.

1. Seleccioneu **Desa** per desar el segment. El segment es desa i es processa si es validen tots els requisits. Altrament, es desarà com a esborrany.

1. Seleccioneu **Torna als segments** per tornar a la pàgina **Segments**.



## <a name="quick-segments"></a>Segments ràpids

Els segments ràpids us permeten crear segments senzills amb un sol operador ràpidament per obtenir informació més ràpida.

1. A la pàgina **Segments**, seleccioneu **Crea** > **Crea de**.

   - Seleccioneu l'opció **Perfils** per crear un segment que es basi en l'entitat de *client unificat*.
   - Seleccioneu l'opció **Mesures** per crear un segment en les mesures que heu creat anteriorment.
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

## <a name="next-steps"></a>Passos següents

[Exporteu un segment](export-destinations.md) i exploreu la [targeta del client](customer-card-add-in.md) i els [connectors](export-power-bi.md) per obtenir informació al nivell del client.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
