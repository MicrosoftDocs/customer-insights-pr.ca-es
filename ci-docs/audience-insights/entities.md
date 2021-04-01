---
title: Entitats i conjunts de dades
description: Visualitzeu dades de la pàgina Entitats.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596395"
---
# <a name="entities-in-audience-insights"></a>Entitats a les conclusions del públic

Després de [configurar les fonts de dades](data-sources.md), aneu a la pàgina **Entitats** per avaluar la qualitat de les dades que heu ingerit. Les entitats es consideren conjunts de dades. Diverses capacitats del Dynamics 365 Customer Insights es construeixen al voltant d'aquestes entitats. Revisar-les amb atenció us pot ajudar a validar la sortida d'aquestes funcions.

A la pàgina **Entitats** s'enumeren entitats i inclou diverses columnes:

- **Nom**: nom de l'entitat de dades. Si veieu un símbol d'advertiment al costat del nom d'una entitat, vol dir que les dades de l'entitat no s'han carregat correctament.
- **Font**: tipus de font de dades que ha ingerit l'entitat
- **Creat per**: nom de la persona que ha creat l'entitat
- **Data de creació**: data i hora de creació de l'entitat
- **Actualitzat per**: nom de la persona que ha actualitzat l'entitat
- **Última actualització**: data i hora de l'última vegada que es va actualitzar l'entitat
- **Darrera actualització**: data i hora de l'última actualització de les dades

## <a name="exploring-a-specific-entitys-data"></a>Explorar les dades d'una entitat concreta

Seleccioneu una entitat per explorar els diferents camps i registres inclosos dins d'aquesta entitat.

> [!div class="mx-imgBorder"]
> ![Seleccioneu una entitat](media/data-manager-entities-data.png "Seleccioneu una entitat")

- La pestanya **Dades** està seleccionada per defecte i mostra una taula amb detalls sobre els registres individuals de l'entitat.

> [!div class="mx-imgBorder"]
> ![Taula de camps](media/data-manager-entities-fields.PNG "Taula de camps")

- A la pestanya **Camps** es mostra una taula per revisar els detalls de l'entitat seleccionada, com ara els noms de camp, els tipus de dades i els tipus. A la columna **Tipus** es mostren els tipus associats del Common Data Model, els quals són identificats automàticament pel sistema o [assignats manualment](map-entities.md) pels usuaris. Són tipus semàntics que poden diferir dels tipus de dades dels atributs; per exemple, el camp *Correu electrònic* següent té un tipus de dades *Text*, però el seu tipus del Common Data Model (semàntic) comú pot ser *Email* o *EmailAddress*.

> [!NOTE]
> Ambdues taules mostren només una mostra de les dades de l'entitat. Per visualitzar el conjunt de dades complet, aneu a la pàgina **Fonts de dades**, seleccioneu una entitat, seleccioneu **Edita** i, a continuació, visualitzeu les dades d'aquesta entitat amb l'editor del Power Query com s'explica a [Fonts de dades](data-sources.md).

Per obtenir més informació sobre les dades que s'ingereixen a l'entitat, la columna **Resum** us ofereix algunes característiques importants de les dades, com ara valors inexistents, valor que falten, valors únics, recomptes i distribucions, segons s'apliqui a les vostres dades.

Seleccioneu la icona del gràfic per veure el resum de les dades.

> [!div class="mx-imgBorder"]
> ![Símbol de resum](media/data-manager-entities-summary.png "Taula de resum de dades")

### <a name="next-step"></a>Pas següent

Vegeu el tema [Unificar](data-unification.md) per obtenir més informació sobrecom podeu *assignar*, *combinar* i *fusionar* les dades ingerides.


[!INCLUDE[footer-include](../includes/footer-banner.md)]