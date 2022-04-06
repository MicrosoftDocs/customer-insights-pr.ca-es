---
title: Veure perfils de client
description: Obtingueu una visualització combinada de les dades unificades del client.
ms.date: 09/30/2021
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
ms.openlocfilehash: 074d84eff65d52b083fff6c161282d4fafa1af85
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523710"
---
# <a name="customer-profiles"></a>Perfils de client

A la pàgina **Clients** es mostra una visualització combinada dels perfils de client unificats. Els perfils de client estan disponibles un cop hàgiu [creat l'entitat Client unificada](data-unification.md). La pàgina us permet cercar clients i definir l'índex per a la cerca.

Els clients poden ser persones o organitzacions. Cada perfil de client està representat per una peça. Utilitzeu els controls de paginació per obtenir més registres. La targeta visualitza camps de l'entitat *Client* segons es defineixi a l'**Índex de cerca i filtre**. L'ordre dels camps dins de cada targeta és escollit pel sistema.

Seleccioneu una peça per veure les dades del client seleccionat en una pàgina dedicada anomenada [Pàgina de detalls del client](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Pàgina Clients que mostra les peces de resultats](media/customers-page-result-tiles-B2C.png "Pàgina Clients que mostra les peces de resultats")

> [!NOTE]
> Si no podeu veure les peces quan seleccioneu **Clients** en la navegació, l'administrador ha de [definir com a mínim un atribut que es pugui cercar](search-filter-index.md) a l'**índex de cerca i filtre**.

## <a name="search-for-customers"></a>Cercar clients

Cerqueu clients introduint un nom o algun altre atribut al quadre de cerca. La cerca només funciona dins de l'entitat _Client_ creada durant el procés d'unificació de dades.

Com a administrador, podeu configurar els atributs que es poden cercar amb la pàgina **Índex de cerca i filtre**. Per obtenir més informació, aneu a [Administrar l'índex de cerca i filtre](search-filter-index.md).

## <a name="filter-customers"></a>Filtra els clients

Podeu filtrar els clients pels camps de l'entitat _Client_. De forma similar a la cerca, l'administrador primer haurà de definir els camps com a filtrables mitjançant la pàgina **Índex de cerca i filtre**.

1. Seleccioneu **Mostra els filtres** a la pàgina **Clients**.

1. Activeu les caselles que hi ha al costat dels atributs pels quals voleu filtrar els clients.

1. Per suprimir els filtres, seleccioneu **Esborra els filtres** a la pàgina **Clients**.

## <a name="customer-details-page"></a>Pàgina Detalls del client

Seleccioneu qualsevol de les peces del client per obrir la **pàgina Detalls del client**. Aquesta visualització conté informació unificada del client seleccionat. Els detalls del client inclouen el contingut següent:

**Peça del perfil del client**: aquesta peça mostra els diferents valors de l'entitat _Client_ unificada. Si un camp no té cap valor per al perfil de client seleccionat, no es mostrarà. La peça està estructurada en seccions:  
  - A la primera secció es mostra un conjunt predefinit de camps seguit de tots els camps que formen part de l'índex de cerca i filtre. Tots els camps relacionats amb adreces es combinen en una única línia si el perfil conté aquests camps. 
  - **Contactes d'aquest client**: als entorns dels comptes empresarials, veureu tots els contactes relacionats d'aquest client com la segona secció. Cada contacte es mostra amb els seus camps. Els camps buits estan amagats.
  - **Camps addicionals**: mostra la resta de camps del client seleccionat, tret dels identificadors. 
  - **ID**: mostra tots els ID sota el nom de l'entitat corresponent. Els camps s'identifiquen com a ID per la seva semàntica, la qual cosa els classifica per categories com a tals.

**Cronologia d'activitat**: mostra dades si heu configurat activitats. La visualització de cronologia conté activitats ordenades cronològicament del client seleccionat, començant per l'activitat més recent. Per obtenir més informació, aneu a [Activitats del client](activities.md).

**Conclusions**:  
  - **Mesures**: mostra si heu configurat una o més mesures d'atributs del client. Inclouen KPI calculats sobre els vostres clients per a cada client individual. Per obtenir més informació, aneu a [Definir i administrar mesures](measures.md).

  - **Interessos potencials, marques potencials**: mostra si heu configurat un enriquiment d'afinitat de marca o interès. Representa els interessos i les afinitats potencials de les marques en funció d'altres clients el perfil dels quals sigui similar al perfil de client seleccionat. Per obtenir més informació, aneu a [Enriquir els perfils de clients amb afinitats de marca i d'interès](enrichment-microsoft.md).

Per tornar a la pàgina de cerca de clients, seleccioneu **Torna als clients**.

## <a name="next-steps"></a>Passos següents

[Afegiu més fonts de dades](data-sources.md), [enriquiu els perfils unificats](enrichment-hub.md) o [creeu segments](segments.md) per treballar amb perfils de client unificats en altres aplicacions.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
