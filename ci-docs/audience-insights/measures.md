---
title: Crear i administrar mesures
description: Definiu mesures per analitzar i reflectir el rendiment del vostre negoci.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887928"
---
# <a name="define-and-manage-measures"></a>Definir i administrar mesures

Les mesures us ajuden a comprendre millor els comportaments dels clients i el rendiment empresarial. Miren els valors rellevants dels [perfils unificats](data-unification.md). Per exemple, una empresa vol veure la *despesa total per client* per comprendre l'historial de compra del client individual o mesurar les *vendes totals de l'empresa* per comprendre els ingressos a nivell agregat de tot el negoci.  

Les mesures es creen mitjançant el creador de mesures, una plataforma de consulta de dades amb diversos operadors i opcions d'assignació simples. Permet filtrar les dades, agrupar els resultats, detectar [rutes de relació d'entitats](relationships.md) i obtenir una visualització prèvia de la sortida.

Utilitzeu el creador de mesures per planificar activitats empresarials consultant dades de clients i extreure informació. Per exemple, la creació d'una mesura de *despesa total per client* i *retorn total per client* ajuda a identificar un grup de clients amb una despesa alta però amb un retorn alt. Podeu [crear un segment](segments.md) per dirigir les pròximes accions recomanades. 

## <a name="build-your-own-measure-from-scratch"></a>Crear una mesura pròpia des de zero

Aquesta secció us guia al llarg de la creació d'una nova mesura des de zero. Podeu crear una mesura amb atributs de dades a partir d'entitats de dades que tenen una relació configurada per connectar-se a l'entitat Client. 

1. A les conclusions del públic, aneu a **Mesures**.

1. Seleccioneu **Crea** i trieu **Crea'n una de pròpia**.

1. Seleccioneu **Edita el nom** i proporcioneu un **nom** per a la mesura. 
   > [!NOTE]
   > Si la vostra nova configuració de mesura només té dos camps, per exemple, CustomerID i un càlcul, la sortida s'afegirà com una columna nova a l'entitat generada pel sistema anomenada Customer_Measure. I podreu veure el valor de la mesura al perfil de client unificat. Altres mesures generaran les seves pròpies entitats.

1. A l'àrea de configuració, trieu la funció d'agregació al menú desplegable **Seleccioneu una funció**. Les funcions d'agregació inclouen: 
   - **Suma**
   - **Mitjana**
   - **Recompte**
   - **Compta únics**
   - **Màx**
   - **Min**
   - **Primer**: pren el primer valor del registre de dades
   - **Últim**: pren l'últim valor que s'ha afegit al registre de dades

   :::image type="content" source="media/measure-operators.png" alt-text="Operadors per a càlculs de mesures.":::

1. Seleccioneu **Afegeix un atribut** per seleccionar les dades que necessiteu per crear aquesta mesura.
   
   1. Seleccioneu la pestanya **Atributs**. 
   1. Entitat de dades: trieu l'entitat que inclou l'atribut que voleu mesurar. 
   1. Atribut de dades: trieu l'atribut que voleu utilitzar a la funció d'agregació per calcular la mesura. Només podeu seleccionar un atribut cada vegada.
   1. Per seleccionar un atribut de dades d'una mesura existent, seleccioneu la pestanya **Mesures**. O bé podeu cercar una entitat o un nom de mesura. 
   1. Seleccioneu **Afegeix** per afegir l'atribut seleccionat a la mesura.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleccioneu un atribut que voleu utilitzar en els càlculs.":::

1. Per crear mesures més complexes, podeu afegir més atributs o utilitzar operadors matemàtics a la funció de mesura.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Creeu una mesura complexa amb operadors matemàtics.":::

1. Per afegir filtres, seleccioneu el **Filtre** a l'àrea de configuració. 
  
   1. A la secció **Afegeix un atribut** de la subfinestra **Filtres**, seleccioneu l'atribut que voleu utilitzar per crear filtres.
   1. Definiu els operadors de filtre per definir el filtre per a cada atribut seleccionat.
   1. Seleccioneu **Aplica** per afegir els filtres a la mesura.

1. Per afegir dimensions, seleccioneu **Dimensió** a l'àrea de configuració. Les dimensions es mostraran com a columnes a l'entitat de sortida de mesura.
   1. Seleccioneu **Edita les dimensions** per afegir atributs de dades pels quals voleu agrupar els valors de mesura. Per exemple, ciutat o gènere. Per defecte, la dimensió *CustomerID* se selecciona per crear *mesures del nivell del client*. Si voleu crear *mesures de nivell de negoci*, podeu suprimir la dimensió per defecte.
   1. Seleccioneu **Fet** per afegir les dimensions a la mesura.

1. Si hi ha valors a les dades que heu de substituir per un enter, per exemple, substituir *nul* per *0*, seleccioneu **Regles**. Configureu la regla i assegureu-vos que trieu només els nombres enters com a substituts.

1. Si hi ha diversos rutes entre l'entitat de dades assignada i l'entitat *Client*, heu de triar un dels [camins de relació d'entitat](relationships.md) identificats. Els resultats de la mesura poden variar en funció del camí seleccionat. 
   1. Seleccioneu **Preferències de les dades** i trieu el camí de l'entitat que s'utilitzarà per identificar la mesura. Si només hi ha un camí a l'entitat *Client*, aquest control no es mostrarà.
   1. Seleccioneu **Fet** per aplicar la vostra selecció. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleccioneu la ruta d'entitat de la mesura.":::

1. Per afegir més càlculs per a la mesura, seleccioneu **Càlcul nou**. Només podeu utilitzar les entitats al mateix camí d'entitat per als càlculs nous. Més càlculs es mostraran com a columnes noves a l'entitat de sortida de mesura.

1. Seleccioneu **...** en el càlcul per **duplicar**, **canviar el nom** o **suprimir** un càlcul d'una mesura.

1. A l'àrea **Visualització prèvia**, veureu l'esquema de dades de l'entitat de sortida de mesura, incloent-hi els filtres i dimensions. La visualització prèvia reacciona dinàmicament als canvis a la configuració.

1. Seleccioneu **Executa** per calcular els resultats de la mesura configurada. Seleccioneu **Desa i tanca** si voleu mantenir la configuració actual i executar la mesura més endavant.

1. Aneu a **Mesures** per veure la mesura que s'ha creat recentment a la llista.

## <a name="use-a-template-to-build-a-measure"></a>Utilitzar una plantilla per crear una mesura

Podeu utilitzar plantilles predefinides de mesures que s'utilitzen habitualment per crear-les. Les descripcions detallades de les plantilles i una experiència guiada us ajuden a crear una mesura de manera eficient. Les plantilles es creen a partir de dades assignades de l'entitat *Activitat unificada*. Per tant, assegureu-vos que heu configurat [activitats de client](activities.md) abans de crear una mesura a partir d'una plantilla.

Plantilles de mesura disponibles: 
- Valor de transacció mitjà (ATV)
- Valor total de la transacció
- Mitjana d'ingressos diaris
- Mitjana d'ingressos anuals
- Recompte de transaccions
- Punts de fidelitat obtinguts
- Punts de fidelitat bescanviats
- Balanç de punts de fidelitat
- Vida del client activa
- Duració de la subscripció a la fidelitat
- Temps des de l'última compra

Al procediment següent es descriuen els passos per crear una mesura nova mitjançant una plantilla.

1. A les conclusions del públic, aneu a **Mesures**.

1. Seleccioneu **Crea** i seleccioneu **Tria una plantilla**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de pantalla del menú desplegable quan es crea una mesura nova amb la plantilla destacada.":::

1. Cerqueu la plantilla que s'ajusti a les vostres necessitats i seleccioneu **Tria la plantilla**.

1. Reviseu les dades necessàries i seleccioneu **Introducció** si teniu totes les dades col·locades.

1. A la subfinestra **Edita el nom**, definiu el nom de la mesura i l'entitat de sortida. 

1. Seleccioneu **Fet**.

1. A la secció **Definiu el període de temps**, definiu el període de temps de les dades que voleu utilitzar. Trieu si voleu que la mesura nova cobreixi tot el conjunt de dades seleccionant **Tot el temps**. O si voleu que la mesura se centri en un **Període de temps específic**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de pantalla que mostra la secció de període de temps en configurar una mesura a partir d'una plantilla.":::

1. A la secció següent, seleccioneu **Afegeix dades** per triar les activitats i assignar les dades corresponents de l'entitat *Activitat unificada*.

    1. Pas 1 de 2: a **Tipus d'activitat**, trieu el tipus d'entitat que voleu utilitzar. Per a les **Activitats**, seleccioneu les entitats que voleu assignar.
    1. Pas 2 de 2: trieu l'atribut de l'entitat *Activitat unificada* per al component que requereix la fórmula. Per exemple, per al valor de Transacció mitjana, és l'atribut que representa el Valor de transacció. Per a la **Marca horària de l'activitat**, trieu l'atribut de l'entitat Activitat unificada que representi la data i l'hora de l'activitat.
   
1. Un cop l'assignació de dades s'ha completat, podeu veure l'estat com a **Completat** i el nom de les activitats i els atributs assignats.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captura de pantalla d'una configuració de plantilla de mesura completada.":::

1. Ara podeu seleccionar **Executa** per calcular els resultats de la mesura. Per refinar-la més tard, seleccioneu **Desa l'esborrany**.

## <a name="manage-your-measures"></a>Administrar les mesures

Podeu consultar la llista de mesures a la pàgina **Mesures**.

Trobareu informació sobre el tipus de mesura, l'autor, la data de creació, l'estat i l'estat. Quan seleccioneu una mesura de la llista, podeu obtenir una visualització prèvia de la sortida i baixar un fitxer .CSV.

Per actualitzar totes les mesures al mateix temps, seleccioneu **Actualitza-ho tot** sense seleccionar una mesura concreta.

> [!div class="mx-imgBorder"]
> ![Accions per administrar mesures individuals](media/measure-actions.png "Accions per administrar mesures individuals")

Seleccioneu una mesura de la llista per a les opcions següents:

- Seleccioneu el nom de la mesura per veure'n els detalls.
- **Editeu** la configuració de la mesura.
- **Actualitzeu** la mesura segons les dades més recents.
- **Canvieu el nom** de la mesura.
- **Suprimiu** la mesura.
- **Activeu** o **desactiveu-la**. Les mesures inactives no s'actualitzaran durant una [actualització planificada](system.md#schedule-tab).

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.

## <a name="next-step"></a>Pas següent

Podeu utilitzar mesures existents per crear un [segment de client](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]