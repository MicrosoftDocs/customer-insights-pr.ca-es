---
title: Segments a Customer Insights
description: Informació general sobre els segments i com crear-ne i administrar-los.
ms.date: 03/30/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 9791e971387eb7db91ed7c4e4fe76552656013ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642340"
---
# <a name="segments-overview"></a>Descripció general dels segments

Els segments us permeten agrupar els clients segons atributs demogràfics, de transaccions o de comportament. Podeu utilitzar segments per orientar les campanyes promocionals, les activitats de vendes i les accions d'atenció al client per assolir els vostres objectius empresarials.

Els perfils de client que coincideixen amb els filtres d'una definició de segment es coneixen com a *membres* d'un segment. S'apliquen [límits de servei](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Crear un segment nou

Hi ha diverses maneres de crear un segment nou: 

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

- Segment complex amb el creador de segments: [Creeu el vostre propi segment](segment-builder.md#create-a-new-segment) 
- Segments senzills amb un operador: [segment ràpid](segment-builder.md#quick-segments) 
- Forma amb tecnologia d'IA per trobar clients semblants: [clients semblants](find-similar-customer-segments.md) 
- Suggeriments amb tecnologia d'IA basats en mesures o atributs: [segments suggerits per millorar mesures](suggested-segments.md) 
- Suggeriments basats en activitats: [segments suggerits segons l'activitat del client](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

- Segment complex amb el creador de segments: [Creeu el vostre propi segment](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Administrar segments existents

Aneu a la **pàgina Segments** per visualitzar tots els segments desats i gestionar-los.

Cada segment està representat per una fila que inclou informació addicional sobre el segment.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segment seleccionat amb la llista desplegable d'opcions i opcions disponibles." lightbox="media/segments-selected-segment.png":::

Les accions següents estan disponibles quan seleccioneu un segment:

- **Visualitzar** els detalls del segment, incloent-hi la tendència de recompte de membres per obtenir la visualització prèvia dels membres del segment.
- **Baixar** la llista de membres com a fitxer .CSV.
- **Editar** el segment per canviar-ne les propietats.
- **Crear un duplicat** d'un segment. Podeu editar-ne les propietats immediatament o simplement desar el duplicat.
- **Actualitzar** el segment per incloure-hi les dades més recents.
- **Activar** o **desactivar** el segment. Per als segments inactius, la definició del segment existeix però encara no conté cap client. Un segment actiu cerca clients que coincideixin amb la definició del segment. Si es configura una [actualització planificada](system.md#schedule-tab), els segments inactius tenen l'**estat** **Omès**, indicant que ni tan sols s'ha intentat una actualització. Quan s'activi un segment inactiu, s'actualitzarà i s'inclourà en les actualitzacions programades.
  Alternativament, podeu utilitzar la funcionalitat **Planifica més tard** al desplegable **Activa o desactiva** per especificar una data i hora futura per a l'activació i la desactivació d'un segment concret.
- **[Trobar clients](find-similar-customer-segments.md)** similars del segment.
- **Canviar el nom** del segment.
- **Etiqueta** per [administrar etiquetes](work-with-tags-columns.md#manage-tags) per al segment.
- **Baixar** la llista de membres com a fitxer .CSV.
- **Administreu exportacions** per veure el segment relacionat amb les exportacions i administrar-les. [Més informació sobre les exportacions](export-destinations.md)
- **Suprimir** el segment.
- **Columnes** per [personalitzar les columnes](work-with-tags-columns.md#customize-columns) que es mostren.
- **Filtra-ho** per filtrar a [les etiquetes](work-with-tags-columns.md#filter-on-tags).
- **Nom** de cerca per cercar pel nom del segment.

## <a name="refresh-segments"></a>Actualitzar els segments

Per actualitzar tots els segments a la vegada, seleccioneu **Actualitza-ho tot** a la pàgina **Segments**; o bé, podeu actualitzar un o diversos segments quan els seleccioneu i trieu **Actualitza** a les opcions. O bé, podeu configurar una actualització periòdica a la planificació a **Administració** > **Sistema** > **Planificació**. Quan es configura una actualització periòdica, s'apliquen les regles següents:
- Tots els segments amb el tipus **Dinàmic** o **Expansió s'actualitzaran** automàticament a la cadència establerta. Quan s'ha completat l'actualització, l'estat **indica** si hi ha hagut algun problema en actualitzar el segment. L'última **actualització** mostra una marca horària de l'última actualització correcta. Si es produeix un error, seleccioneu l'error per veure els detalls sobre el que ha passat.
- Els segments amb el tipus **Estàtic** *no* s'actualitzaran automàticament. L'últim **refrescat** mostra una marca horària de l'última vegada que els segments estàtics s'han executat o s'actualitzen manualment.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segments

Podeu exportar un segment des de la pàgina de segments o des de la [pàgina d'exportació](export-destinations.md). 

1. Aneu a la pàgina **Segments**.

1. Seleccioneu **Mostra'n més [...]** al segment que voleu exportar.

1. Seleccioneu **Administra les exportacions** a la llista desplegable d'accions.

1. S'obre la pàgina **Exportacions (versió preliminar) per al segment**. Podeu veure totes les exportacions configurades agrupades per si contenen el segment actual o no.

   1. Per afegir el segment seleccionat a una exportació, **editeu** l'exportació respectiva per seleccionar el segment corresponent i deseu. En entorns de clients individuals, en lloc d'això podeu seleccionar l'exportació a la llista i seleccionar **Afegeix un segment** per obtenir el mateix resultat.

   1. Per crear una exportació nova amb el segment seleccionat, seleccioneu **Afegeix l'exportació**. Per obtenir més informació sobre la creació d'exportacions, vegeu [Configurar una exportació nova](export-destinations.md#set-up-a-new-export).

1. Seleccioneu **Enrere** per tornar a la pàgina principal per als segments.

## <a name="view-processing-history-and-segment-members"></a>Visualitzar l'historial de processament i els membres del segment

Podeu veure les dades consolidades d'un segment revisant-ne els detalls.

A la pàgina **Segments**, seleccioneu el segment que voleu revisar.

A la part superior de la pàgina s'inclou una gràfica de tendències que visualitza els canvis al recompte de membres. Passeu el cursor per sobre dels punts de dades per veure el recompte de membres en una data concreta.

Podeu actualitzar el període de temps de la visualització.

> [!div class="mx-imgBorder"]
> ![Interval de temps del segment.](media/segment-time-range.png "Interval de temps del segment")

La part inferior conté una llista dels membres del segment.

> [!NOTE]
> Els camps que apareixen en aquesta llista es basen en els atributs de les entitats del vostre segment.
>
>La llista és una visualització prèvia dels membres del segment coincidents i mostra els primers 100 registres del segment per tal que pugueu avaluar-lo ràpidament i revisar-ne les definicions si cal. Per veure tots els registres coincidents, heu d'[exportar el segment](export-destinations.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
