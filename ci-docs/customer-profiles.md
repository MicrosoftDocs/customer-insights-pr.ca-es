---
title: Veure perfils de client
description: Consultar les dades dels clients unificats, com ara l'ús de la cerca i el filtre
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188081"
---
# <a name="view-customer-profiles"></a>Veure perfils de client

Els perfils de client estan disponibles un cop hàgiu [creat l'entitat client *unificada*](data-unification.md). La visualització combinada dels perfils de client unificats es mostra a la **pàgina Clients**. Els clients poden ser persones o organitzacions.

Aneu a la **pàgina Clients** per veure els vostres clients i els seus perfils. Cada perfil de client està representat per una peça. Utilitzeu els controls de paginació per obtenir més registres. La targeta visualitza camps de l'entitat *Client* segons es defineixi a l'**Índex de cerca i filtre**. El sistema tria l'ordre dels camps dins de cada targeta.

> [!NOTE]
> Si no veieu les peces quan seleccioneu **Clients**, l'administrador ha de definir com a [mínim un atribut](search-filter-index.md) que es pot cercar a l'índex **de** cerca i filtre.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Pàgina clients que mostra les peces de resultats.":::

Seleccioneu qualsevol de les accions següents:
- [Veure els detalls del client](#view-customer-details)
- [Gestionar l'índex](search-filter-index.md) de cerca i filtre (només per a administradors)
- [Filtra els clients](#filter-customers)
- **Expandiu targetes** o **Replega les targetes** per ampliar o reduir la informació que es mostra a la peça del client
- **Ordenar per** un atribut concret
- [Cercar clients](#search-for-customers)

  > [!NOTE]
  > Per utilitzar la cerca i el filtre, un administrador ha de configurar els atributs que es poden cercar i definir els camps filtrables mitjançant l'índex de cerca i filtre.

## <a name="search-for-customers"></a>Cercar clients

Cerqueu clients introduint un nom o algun altre atribut a la **Cerca de clients**. L'administrador defineix els atributs que es poden cercar i provenen de l'entitat client *unificada*.

> [!NOTE]
> **String** és l'únic tipus de dades que s'inclou a la cerca. Utilitzeu-lo al **camp Cerca clients** de la pàgina Clients per cercar clients.

## <a name="filter-customers"></a>Filtra els clients

Filtreu els clients pels camps Entitat de *client*. L'administrador defineix els camps filtrables.

1. A la **pàgina Clients**, seleccioneu **Mostra els filtres**. Es mostra la subfinestra Filtre.

1. Activeu les caselles que hi ha al costat dels atributs pels quals voleu filtrar els clients.

1. Per eliminar tots els filtres, seleccioneu Esborra els **filtres** o esborreu una casella de selecció al costat d'un atribut seleccionat.

1. Seleccioneu **Amaga els filtres** per tancar la subfinestra del filtre.

1. Per desar els resultats del filtre com a [segment](segments.md), seleccioneu **Desa els filtres com a segment**.
   1. Introduïu un nom per al segment.
   1. Seleccioneu **Desa** per desar el segment.
   1. Trieu si voleu executar el segment ara seleccionant **Activa o executeu-lo** **més tard**.

## <a name="view-customer-details"></a>Veure els detalls del client

A la **pàgina Clients**, seleccioneu una peça del client per veure els detalls del client seleccionat.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Pàgina de dades del client.":::

Els detalls del client inclouen:

**La peça Perfil de** client mostra els diferents valors de l'entitat Client *unificada*. Si un camp no té cap valor per al perfil de client seleccionat, no es mostrarà excepte en el camp d'adreça. La peça està estructurada en seccions:

- A la primera secció es mostra un conjunt predefinit de camps seguit de tots els camps que formen part de l'índex de cerca i filtre. Tots els camps relacionats amb l'adreça es combinen en una sola línia, cosa que es mostra fins i tot si el perfil no conté informació d'adreça.
- **Els contactes d'aquest client** es mostren en entorns per a comptes empresarials. Cada contacte es mostra amb els seus camps. Els camps buits estan amagats.
- **Els camps** addicionals mostren la resta de camps del client seleccionat, excepte els identificadors.
- **Els identificadors mostren** tots els identificadors amb el nom d'entitat corresponent. Els camps s'identifiquen com a identificadors per la seva semàntica.

**La cronologia de l'activitat** mostra dades si heu configurat [les activitats](activities.md). La visualització de cronologia conté activitats ordenades cronològicament del client seleccionat, començant per l'activitat més recent.

**Conclusions**:

- **Les mesures** es mostren si heu configurat [mesures d'atributs](measures.md) de client. Inclouen KPI calculats sobre els vostres clients per a cada client individual.

- **Interessos potencials, marques** potencials mostren si heu configurat una [marca o enriquiment per afinitat d'interessos](enrichment-microsoft.md). Representa els interessos i les afinitats potencials de les marques en funció d'altres clients el perfil dels quals sigui similar al perfil de client seleccionat.

Per tornar a la **pàgina Clients**, seleccioneu **Torna als clients**.

## <a name="next-steps"></a>Passos següents

[Afegiu més fonts de dades](data-sources.md), [enriquiu els perfils unificats](enrichment-hub.md) o [creeu segments](segments.md) per treballar amb perfils de client unificats en altres aplicacions.

[!INCLUDE [footer-include](includes/footer-banner.md)]
