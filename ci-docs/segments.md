---
title: Descripció general dels segments
description: Informació general sobre els segments i com crear-ne i administrar-los.
ms.date: 05/20/2022
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
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246281"
---
# <a name="segments-overview"></a>Descripció general dels segments

Els segments us permeten agrupar els clients segons atributs demogràfics, de transaccions o de comportament. Podeu utilitzar segments per orientar les campanyes promocionals, les activitats de vendes i les accions d'atenció al client per assolir els vostres objectius empresarials.

Els perfils de clients que coincideixen amb els filtres d'una definició de segment s'anomenen *membres* d'un segment. S'apliquen [límits de servei](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Creació d’un segment

Trieu com crear un segment en funció del vostre públic objectiu.

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

- Segments complexos amb creador de segments: creeu-ne [un de propi](segment-builder.md)
- Segments senzills amb un operador: [segment ràpid](segment-quick.md)
- Manera basada en intel·ligència artificial per trobar clients similars: [clients similars](find-similar-customer-segments.md)
- Suggeriments basats en mesures o atributs basats en IA: [segments suggerits basats en mesures](suggested-segments.md)
- Suggeriments basats en activitats: [segments suggerits segons l'activitat del client](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

- Segments senzills o complexos amb creador de segments: creeu-ne [un de propi](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Administrar segments existents

Aneu a la **pàgina Segments** per veure els segments que heu creat, el seu estat i estat, el nombre de membres i l'última vegada que es van actualitzar les dades. Podeu ordenar la llista de segments per qualsevol columna o utilitzar el quadre de cerca per trobar el segment que voleu gestionar.

Seleccioneu un segment per veure les accions disponibles.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segment seleccionat amb la llista desplegable d'opcions i opcions disponibles." lightbox="media/segments-selected-segment.png":::

- [**Visualitzeu**](#view-segment-details) els detalls del segment, inclosa la tendència del recompte de membres i una previsualització dels membres del segment.
- **Baixar** la llista de membres com a fitxer .CSV.
- **Editar** el segment per canviar-ne les propietats.
- **Crear un duplicat** d'un segment. Podeu editar-ne les propietats immediatament o desar-ne el duplicat.
- [**Actualitzeu**](#refresh-segments) el segment per incloure les dades més recents.
- **Activar** o **desactivar** el segment. Els segments inactius no s'actualitzaran durant una [actualització](schedule-refresh.md) programada i tindran l'estat **com** a **Omès**, cosa que indica que ni tan sols s'ha intentat actualitzar. Els segments actius s'actualitzen en funció del seu tipus: estàtic o dinàmic.
- **Feu estàtic** o **Feu dinàmic** el tipus de segment. Els segments estàtics s'han d'actualitzar manualment. Els segments dinàmics s'actualitzen automàticament durant l'actualització del sistema.
- [**Cerqueu clients**](find-similar-customer-segments.md) similars del segment.
- **Canviar el nom** del segment.
- **Etiqueta** per gestionar les [etiquetes](work-with-tags-columns.md#manage-tags) del segment.
- [**Gestioneu les exportacions**](#export-segments) per veure els segments relacionats amb l'exportació i gestionar-los. [Més informació sobre les exportacions](export-destinations.md)
- **Suprimir** el segment.
- **Columnes** per [personalitzar les columnes](work-with-tags-columns.md#customize-columns) que es mostren.
- **Filtrar** per [filtrar a les etiquetes](work-with-tags-columns.md#filter-on-tags).
- **Nom** de cerca per cercar per nom de segment.

## <a name="view-segment-details"></a>Veure detalls del segment

A la **pàgina Segments**, seleccioneu un segment per veure l'historial de processament i segmentar els membres.

A la part superior de la pàgina s'inclou una gràfica de tendències que visualitza els canvis al recompte de membres. Passeu el cursor per sobre dels punts de dades per veure el recompte de membres en una data concreta. Canvieu el període de temps de la visualització.

:::image type="content" source="media/segment-time-range.png" alt-text="Interval de temps del segment.":::

La part inferior conté una llista dels membres del segment.

> [!NOTE]
> Els camps que apareixen en aquesta llista es basen en els atributs de les entitats del vostre segment.
>
>La llista és una visualització prèvia dels membres del segment coincidents i mostra els primers 100 registres del segment per tal que pugueu avaluar-lo ràpidament i revisar-ne les definicions si cal. Per veure tots els registres coincidents, [exporta el segment](export-destinations.md).

## <a name="refresh-segments"></a>Actualitzar els segments

Els segments es poden actualitzar amb una planificació automàtica o actualitzar-los manualment sota demanda. Per actualitzar manualment un o més segments, selecciona'ls i selecciona **Actualitza**.

Per [programar una actualització](schedule-refresh.md) automàtica, aneu a **Planificació del sistema d'administració** > **·** > **·**. S'apliquen les regles següents:

- Tots els segments amb el tipus **Dinàmica** o **Expansió s'actualitzaran** automàticament a la cadència establerta. Un cop finalitzada l'actualització, l'Estat **indica** si hi ha hagut algun problema en actualitzar el segment. L'última **actualització** mostra una marca de temps de l'última actualització reeixida. Si es produeix un error, seleccioneu l'error per veure els detalls sobre el que ha passat.
- Els segments amb el tipus **Estàtic** *no* s'actualitzaran automàticament. L'última **actualització** mostra una marca de temps de l'última vegada que el segment estàtic es va executar o refrescar manualment.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segments

Exporta segments a altres aplicacions per utilitzar-les encara més. Exporta un segment des de la pàgina de segments o la [pàgina](export-destinations.md) Exporta.

1. Aneu a la **pàgina Segments** i seleccioneu el segment que voleu exportar.

1. Seleccioneu **Gestiona les exportacions**. S'obre la pàgina **Exportacions (versió preliminar) per al segment**. Visualitzeu totes les exportacions configurades agrupades per si contenen el segment actual o no.

   1. Per afegir el segment seleccionat a una exportació, **editeu** l'exportació respectiva per seleccionar el segment corresponent i deseu. En entorns per a clients individuals, seleccioneu l'exportació a la llista i seleccioneu **Afegeix un segment** per obtenir el mateix resultat.

   1. Per crear una exportació nova amb el segment seleccionat, seleccioneu **Afegeix l'exportació**. Per obtenir més informació sobre la creació d'exportacions, vegeu [Configurar una exportació nova](export-destinations.md#set-up-a-new-export).

1. Seleccioneu **Enrere** per tornar a la pàgina principal per als segments.

## <a name="track-usage-of-a-segment"></a>Fer un seguiment de l'ús d'un segment

Si utilitzeu segments en aplicacions basades en la mateixa Microsoft Dataverse organització connectada amb el Customer Insights, podeu fer un seguiment de l'ús d'un segment. Per [als segments del Customer Insights utilitzats en els recorreguts del client del Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), el sistema us informa sobre l'ús d'aquest segment.

Quan editeu un segment que s'utilitza a l'entorn del Customer Insights o en una recorregut del client al Màrqueting, un bàner del creador de [segments](segment-builder.md) us informa sobre les dependències. Inspeccioneu els detalls de dependències directament des del bàner o seleccionant **Ús** al creador de segments.

La **subfinestra Ús** del segment mostra els detalls sobre l'ús d'aquest segment en aplicacions basades en Dataverse dades. Per als segments utilitzats en els recorreguts del client, trobareu un enllaç per inspeccionar el recorregut al Màrqueting on s'utilitza aquest segment. Si teniu permisos per accedir a l'aplicació Marketing, consulteu-ne més detalls.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Subfinestra lateral amb detalls de l'ús del segment al creador de segments.":::

El sistema us informa sobre l'ús d'un segment de seguiment quan intenteu suprimir-lo. Si el segment que esteu a punt de suprimir s'utilitza en una recorregut del client al Màrqueting, aquest recorregut s'aturarà per a tots els usuaris del segment. Si el viatge forma part d'una campanya de màrqueting, la supressió afectarà la mateixa campanya. Tot i això, encara podeu suprimir el segment malgrat els advertiments.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Quadre de diàleg per confirmar la supressió de segments quan s'utilitza un segment en una Dataverse aplicació.":::

### <a name="supported-apps"></a>Aplicacions admeses

Actualment es fa un seguiment de l'ús a les aplicacions basades en següents Dataverse:

- [Recorreguts del client al Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
