---
title: Crear i editar mesures
description: Definiu mesures relacionades amb el client per analitzar i reflectir el rendiment de determinades àrees de negoci.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405166"
---
# <a name="define-and-manage-measures"></a>Definir i administrar mesures

Les **mesures** representen indicadors clau de rendiment (KPI) que reflecteixen el rendiment i la salut d'àrees de negoci específiques. Les conclusions del públic proporcionen una experiència intuïtiva per a la creació de diversos tipus de mesures, mitjançant un creador de consultes que no necessita que escriviu cap codi o que valideu les mesures manualment. Podeu fer el seguiment de les mesures de la vostra empresa a la pàgina **Inici**, veure les mesures per a clients específics a la **Targeta del client** i utilitzar les mesures per definir segments de clients a la pàgina **Segments**.

## <a name="create-a-measure"></a>Crear una mesura

Aquesta secció us guiarà a través de la creació d'una mesura des de zero. Podeu crear mesures amb dades de diverses fonts de dades connectades a través de l'entitat Client. S'apliquen [límits de servei](service-limits.md).

1. A les conclusions del públic, aneu a **Mesures**.

2. Seleccioneu **Mesura nova**.

3. Trieu el **tipus** de mesura:

   - **Atribut de client**: un únic camp per client que reflecteix una puntuació, un valor o un estat per al client. Els atributs de client es creen com a atributs d'una nova entitat generada pel sistema anomenada **Customer_Measure**.

   - **Mesura del client**: informació sobre el comportament dels clients amb un desglossament per dimensions seleccionades. Es genera una entitat nova per a cada mesura, potencialment amb diversos registres per client.

   - **Mesura empresarial**: segueix el rendiment de les empreses i la salut. Les mesures empresarials poden tenir dues sortides diferents: una sortida numèrica que es mostra a la pàgina **Inici** o a una entitat nova que trobeu a la pàgina **Entitats**.

4. Proporcioneu un **Nom** i un **Nom de visualització** opcional i, a continuació, seleccioneu **Següent**.

5. Per a la secció **Entitats**, seleccioneu la primera entitat de la llista desplegable. En aquest punt, haureu de decidir si necessitareu entitats addicionals com a part de la definició de la vostra mesura.

   > [!div class="mx-imgBorder"]
   > ![Definició de mesura](media/measure-definition.png "Definició de mesura")

   Per afegir més entitats, seleccioneu **Afegeix una entitat** i seleccioneu les entitats que voleu utilitzar per a la mesura.

   > [!NOTE]
   > Només podeu seleccionar les entitats que tenen relacions amb l'entitat inicial. Per obtenir més informació sobre la definició de relacions, vegeu [Relacions](relationships.md).

6. Opcionalment, podeu configurar variables. A la secció **Variables**, seleccioneu **Variable nova**.

   Les variables són càlculs que es fan a cadascun dels registres seleccionats. Per exemple, la summa de vendes en punt de venda (POS) i en línia per a cadascun dels registres dels vostres clients.

7. Proporcioneu un **Nom** per a la variable.

8. A l'àrea **Expressió**, trieu un camp amb el qual començar el càlcul.

9. Escriviu una expressió a l'àrea **Expressió** mentre trieu més camps per incloure'ls al càlcul.

   > [!NOTE]
   > Actualment, només s'admeten expressions aritmètiques. A més, el càlcul de variables no està admès per a entitats de diferents [camins d'entitat](relationships.md).

10. Seleccioneu **Fet**.

11. A la secció **Definició de la mesura**, definireu la manera com s'afegeixen les entitats escollides i de les variables calculades a una nova entitat o atribut de mesura.

12. Seleccioneu **Dimensió nova**. Podeu pensar en una dimensió com a funció *Agrupa per*. La sortida de dades de l'entitat o l'atribut de mesura s'agruparà per totes les dimensions definides.

    > [!div class="mx-imgBorder"]
    > ![Triar el cicle d'agregació](media/measures-businessreport-measure-definition2.png "Triar el cicle d'agregació")

    Seleccioneu o introduïu la informació següent com a part de la definició de la dimensió:

    - **Entitat**: si definiu una entitat Mesura, hauria d'incloure com a mínim un atribut. Si definiu un atribut Mesura, només inclourà un atribut per defecte. Aquesta selecció és l'elecció de l'entitat que inclou aquest atribut.
    - **Camp**: trieu l'atribut específic que s'ha d'incloure a l'entitat o l'atribut de mesura.
    - **Dipòsit**: trieu si voleu agregar dades diàriament, mensualment o anualment. Només es tracta d'una selecció obligatòria si heu seleccionat un atribut de tipus de data.
    - **Com a**: defineix el nom del camp nou.
    - **Nom de visualització**: defineix el nom de visualització del camp.

    > [!NOTE]
    > La mesura empresarial es desarà com una entitat de número únic i es mostrarà a la pàgina **Inici**, tret que afegiu més dimensions a la mesura. Després d'afegir més dimensions, la mesura *no* es mostrarà a la pàgina **Inici**.

13. Opcionalment, afegiu funcions d'agregació. Qualsevol agregació que creeu resulta en un valor nou a l'entitat o l'atribut de mesura. Les funcions d'agregació admeses són: **Mínim**, **Màxim**, **Mitjana**, **Mediana**, **Suma**, **Recompte únic**, **Primer** (pren el primer registre d'un valor de dimensió) i **Últim** (pren l'últim registre afegit a un valor de dimensió).

14. Seleccioneu **Desa** per aplicar els canvis a la mesura.

## <a name="manage-your-measures"></a>Administrar les mesures

Un cop creada com a mínim una mesura, apareixerà una llista de mesures a la pàgina **Mesures**.

Trobareu informació sobre el tipus de mesura, el creador, la data i l'hora de la creació, la data i l'hora de la darrera edició, l'estat (si la mesura està activa, inactiva o amb errors) i la data i l'hora de la darrera actualització. Quan seleccioneu una mesura de la llista, podeu veure una visualització prèvia de la seva sortida.

Per actualitzar totes les mesures al mateix temps, seleccioneu **Actualitza-ho tot** sense seleccionar una mesura concreta.

> [!div class="mx-imgBorder"]
> ![Accions per administrar mesures individuals](media/measure-actions.png "Accions per administrar mesures individuals")

De manera alternativa, seleccioneu una mesura de la llista i feu una de les accions següents:

- Seleccioneu el nom de la mesura per veure'n els detalls.
- **Editeu** la configuració de la mesura.
- **Canvieu el nom** de la mesura.
- **Suprimiu** la mesura.
- Seleccioneu els punts suspensius (...) i, a continuació, **Actualitza** per iniciar el procés d'actualització per a la mesura.
- Seleccioneu els punts suspensius (...) i després **Baixa** per obtenir un fitxer .CSV de la mesura.

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.

## <a name="next-step"></a>Pas següent

Podeu utilitzar les mesures existents per crear el primer segment de client a la pàgina **Segments**. Per obtenir més informació, vegeu [Segments](segments.md).
