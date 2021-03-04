---
title: Veure perfils de client
description: Obtingueu una visualització combinada de les dades unificades del client.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a5d928ae518f3cb1afbf8e2b197e51b27665f6e0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269732"
---
# <a name="customer-profiles"></a>Perfils de client

A la pàgina **Clients** es mostra una visualització combinada dels clients basada en les dades de perfil recopilades de [les diferents fonts de dades](data-sources.md). Els perfils de client estaran disponibles un cop [hàgiu creat l'entitat Client unificada](data-unification.md). Assegureu-vos de completar el procés d'unificació de dades per obtenir visualitzacions més riques dels clients. La pàgina també us permet cercar clients.

Els clients poden ser persones o organitzacions (visualització prèvia). Cada client o perfil d'organització està representat per una peça. Seleccioneu una peça per veure informació addicional sobre aquest client o organització en concret. Utilitzeu els controls de pàgina de la part inferior de la pàgina per veure registres addicionals.

> [!div class="mx-imgBorder"] 
> ![Perfils de client B2C](media/profiles-customers.png "Perfils de client B2C")

Organitzacions (visualització prèvia)
> [!div class="mx-imgBorder"] 
> ![Perfils de client B2B](media/profile-customers-b2b.png "Perfils de client B2B")

> [!NOTE]
> Si no podeu veure les peces del en seleccionar **Clients** a la navegació, l'administrador ha de [definir com a mínim un atribut que es pugui cercar](search-filter-index.md) a l'**Índex de cerca i filtratge**.

## <a name="search-for-customers"></a>Cercar clients

Cerqueu clients introduint un nom o algun altre atribut al quadre de cerca. La cerca només funciona dins de l'entitat Perfil de client creada durant el procés d'unificació de dades.

Com a administrador, podeu configurar els atributs que es poden cercar amb la pàgina **Índex de cerca i filtre**. Per obtenir més informació, vegeu [Administrar l'índex de cerca i filtre](search-filter-index.md).

## <a name="filter-customers"></a>Filtrar clients

Podeu filtrar clients pels camps de l'entitat Perfil de client. De forma similar a la cerca, l'administrador primer haurà de definir els camps com a filtrables mitjançant la pàgina **Índex de cerca i filtre**.

1. Seleccioneu **Filtra** a la pàgina **Clients**.

2. Activeu les caselles que hi ha al costat dels atributs pels quals voleu filtrar els clients.

   > [!div class="mx-imgBorder"] 
   > ![Perfils de client](media/profiles-customers3.png "Perfils de client")

3. Per suprimir els filtres, seleccioneu **Esborra els filtres** a la pàgina **Clients**.

##  <a name="customer-details-page"></a>Pàgina Detalls del client

Seleccioneu qualsevol de les peces del client per obrir la **pàgina Detalls del client**. Aquesta visualització conté informació unificada del client seleccionat.

Els detalls del client inclouen:

-   **Peça del perfil del client:** En aquesta peça es mostren els diferents valors de l'entitat unificada del perfil del client. Entre aquests detalls s'inclouen l'adreça de correu electrònic, el nom, la ciutat, etc. 

-   **Possibles interessos, possibles marques:** Mostra si heu configurat un enriquiment principal. Representa els possibles interessos i afinitats per a les marques que podria tenir un client amb un perfil semblant a aquest client. Per obtenir més informació, vegeu [Enriquir els perfils de clients amb afinitats de marca i interès](enrichment-microsoft-graph.md).

-   **Mesures:** Mostra si heu configurat una o més mesures d'un tipus concret: mesures d'atribut de client. Inclouen KPI calculats sobre els vostres clients per a cada client individual. Per obtenir més informació, vegeu [Definir i administrar mesures](measures.md).

-   **Cronologia d'activitat:** Mostra si heu configurat activitats. La visualització de cronologia conté activitats d'aquest client ordenades cronològicament, començant per l'activitat més recent. Per obtenir més informació, vegeu [Activitats del client](activities.md).

Seleccioneu **Torna als clients** per tornar a la pàgina de cerca de clients.

## <a name="next-steps"></a>Passos següents

[Afegiu més fonts de dades](data-sources.md) o [creeu segments de client](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]