---
title: Utilitzar perfils unificats al Dynamics 365 Marketing
description: Obteniu informació sobre com podeu integrar perfils i segments unificats amb el Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054420"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>Utilitzar perfils de client unificats al Dynamics 365 Marketing

[El Dynamics 365 Marketing](/dynamics365/marketing/overview) eleva les experiències dels clients, cosa que us permet orquestrar viatges personalitzats a través de tots els punts de contacte per enfortir les relacions i fidelitzar-vos. L'aplicació Dynamics 365 Marketing funciona perfectament amb el Dynamics 365 Sales i Dynamics 365 Customer Insights Microsoft Teams altres productes i us permet prendre decisions més ràpides i millors utilitzant el poder de les dades i la IA.

Si connecteu les dades del Customer Insights amb el Màrqueting, podeu fer el:

- Orienteu els anuncis als perfils i segments de clients unificats. Això us permet involucrar tots els clients, independentment de la ubicació de les dades del client.
- Base contingut dinàmic (com ara tokens personalitzats) en correus electrònics, SMS i notificacions automàtiques sobre mesures com l'estat de fidelització, la data de renovació de la subscripció, compte principal o qualsevol altra mesura que hàgiu capturat al perfil unificat de Customer Insights.
- Carregueu les dades del Màrqueting al Customer Insights i combineu-les amb dades dels clients d'altres fonts.
- Apliqueu eines de neteja, enriquiment i coincidència difusa del Customer Insights.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Utilitzar perfils de clients enriquits en màrqueting en temps real

El màrqueting en temps real us permet crear [activadors](/dynamics365/marketing/real-time-marketing-custom-triggers) personalitzats que inicien recorreguts del client en funció de qualsevol acció del client. Com més personalitzades siguin les teves dades, més rellevants i personalitzats seran els teus viatges. Això és el que fa que la combinació de Màrqueting i Customer Insights sigui tan potent. Podeu [unificar dades](data-unification.md) de qualsevol font i, a continuació, utilitzar-les per alimentar recorreguts de clients hiperpersona personalitzats.

Més informació: [utilitzeu els perfils i segments del Customer Insights en màrqueting en temps real](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Utilitzar segments unificats amb recorreguts de clients sortints

Customer Insights us permet refinar les dades de moltes fonts i combinar-les en segments de clients agregats. En [connectar el Customer Insights amb el màrqueting](export-dynamics365-marketing.md) sortint, aquests segments apareixeran *automàticament i* s'actualitzaran automàticament al dissenyador recorregut del client.

Més informació: [utilitzeu segments del Dynamics 365 Customer Insights Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Treu dades de la teva Azure Data Lake Storage

No us limiteu a l'emmagatzematge en el núvol si voleu utilitzar les dades del Customer Insights amb el Màrqueting. Si ja teniu la vostra pròpia Azure Data Lake Storage configuració, podeu connectar-vos amb el Customer Insights i, a continuació, compartir les dades amb l'aplicació Màrqueting tal com ho faríeu amb una configuració basada en el núvol.

Més informació: [activa l'ús compartit de dades amb Dataverse el teu Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
