---
title: Combinar entitats a la unificació de dades
description: Combineu entitats per crear perfils de client unificats.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268490"
---
# <a name="merge-entities"></a>Combinar entitats

La fase de combinació és l'última fase en el procés d'unificació de dades. La seva finalitat és la conciliació de dades contradictòries. Alguns exemples de dades contradictòries són un nom del client que es troba en dos dels vostres conjunts de dades, però apareix una mica diferent a cadascun d'ells ("Grant Marshall" o "Grant Marshal") o un número de telèfon que difereix en el format (617-803-091X versus 617803091X). La combinació d'aquests punts de dades conflictius es fa per atribut.

Després de completar la [fase de coincidència](match-entities.md), podeu iniciar la fase de combinació seleccionant la peça **Combinació** a la pàgina **Unifica**.

## <a name="review-system-recommendations"></a>Revisar les recomanacions del sistema

A la pàgina **Combinació**, podeu triar i excloure els atributs per combinar a l'entitat de perfil del client unificat (resultat del procés de configuració). El sistema combina automàticament alguns atributs.

### <a name="view-merged-attributes"></a>Visualitzar els atributs combinats

Per visualitzar els atributs que s'inclouen en un dels atributs combinats automàticament, seleccioneu aquest atribut combinat. Els dos atributs que componen aquest atribut combinat es mostren en dues files noves sota l'atribut combinat.

> [!div class="mx-imgBorder"]
> ![Seleccionar un atribut combinat](media/configure-data-merge-profile-attributes.png "Seleccionar un atribut combinat")

### <a name="separate-merged-attributes"></a>Separar atributs combinats

Per separar o deixar de combinar qualsevol dels atributs combinats automàticament, cerqueu l'atribut a la taula **Atributs de perfil**.

1. Seleccioneu el botó de punts suspensius (...).
  
2. A la llista desplegable, seleccioneu **Separa els camps**.

### <a name="remove-merged-attributes"></a>Suprimir atributs combinats

Per excloure un atribut de l'entitat de perfil de client final, cerqueu-la a la taula **Atributs del perfil**.

1. Seleccioneu el botó de punts suspensius (...).
  
2. A la llista desplegable, seleccioneu **No combinis**.

   L'atribut es desplaça a la secció **Suprimit del registre de client**.

## <a name="manually-add-a-merged-attribute"></a>Afegir manualment un atribut combinat

Per afegir un atribut combinat, aneu a la pàgina **Combinació**.

1. Seleccioneu **Afegeix un atribut combinat**.

2. Proporcioneu un **Nom** per identificar-lo a la pàgina **Combinació** més endavant.

3. Opcionalment, proporcioneu un **Nom de visualització** per mostrar a l'entitat de perfil de client unificat.

4. Configureu **Selecció d'atributs duplicats** per seleccionar els atributs que voleu combinar de les entitats coincidents. També podeu cercar atributs.

5. Definiu la **Classificació segons la importància** per donar prioritat un atribut per sobre dels altres. Per exemple, si l'entitat *WebAccountCSV* inclou les dades més precises sobre l'atribut *Noms complet*, podríeu donar prioritat a aquesta entitat sobre *ContactCSV* seleccionant *WebAccountCSV*. Com a resultat, *WebAccountCSV* es desplaça a la primera prioritat, mentre que *ContactCSV* es desplaça a la segona prioritat en obtenir valors per a l'atribut *Nom complet*.

## <a name="run-your-merge"></a>Executar la combinació

Ja sigui si combineu els atributs manualment o deixeu que el sistema els combini, sempre podeu executar la combinació. A la pàgina **Combinació**, seleccioneu **Executa** per iniciar el procés.

> [!div class="mx-imgBorder"]
> ![Desa i executa la combinació de dades](media/configure-data-merge-save-run.png "Desa i executa la combinació de dades")

Per fer canvis addicionals i tornar a executar el pas, podeu cancel·lar una combinació en curs. Seleccioneu **S'està actualitzant...** i seleccioneu **Cancel·la la feina** a la subfinestra lateral que es mostra.

Després que el text **S'està actualitzant...** canviï a **Correcte**, la combinació s'ha completat i ha resolt les contradiccions de les dades d'acord amb les normes que heu definit. Els atributs combinats i no combinats s'inclouen a l'entitat del perfil unificat. Els atributs exclosos no s'inclouen a l'entitat del perfil unificat.

Si no fos la primera vegada que executeu una combinació correctament, tots els processos posteriors, incloent-hi l'enriquiment, la segmentació i les mesures es tornaran a executar automàticament. Després de tornar a executar tots els processos posteriors, els perfils del client reflecteixen els canvis que heu fet.

> [!TIP]
> Hi ha [sis tipus d'estat](system.md#status-types) per a les tasques o processos. A més, la majoria de processos [depenen d'altres processos posteriors](system.md#refresh-policies). Podeu seleccionar l'estat d'un procés per veure els detalls del progrés de tota la feina. Després de seleccionar **Visualitza els detalls** per a una de les tasques de la feina, trobareu informació addicional: temps de processament, l'última data de processament i tots els errors i advertiments associats a la tasca.

## <a name="next-step"></a>Pas següent

Configureu [Activitats](activities.md), [Enriquiment](enrichment-microsoft-graph.md) o [Relacions](relationships.md) per obtenir més informació sobre els clients.

Si ja heu configurat activitats, enriquiment o relacions o si heu definit segments, es processaran automàticament per utilitzar les darreres dades dels clients.




[!INCLUDE[footer-include](../includes/footer-banner.md)]