---
title: Enriquiment de la millora de l'adreça (conté vídeo)
description: Enriquiu i normalitzeu la informació de les adreces dels perfils dels clients amb els models de Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: b4fef3b5e30e1cac4e5cb4401498f2f0981a409e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642197"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enriquiment de perfils de clients amb adreces millorades

Les adreces de les dades poden ser desestructurades, incompletes o incorrectes. Utilitzeu els models de Microsoft per normalitzar i enriquir les adreces en el [format del model de dades comú](/common-data-model/schema/core/applicationcommon/address) per obtenir una millor precisió i informació.

També [podeu enriquir les adreces de les](data-sources-enrichment.md) fonts de dades per millorar la precisió de la coincidència en el procés d'unificació de dades. 

## <a name="how-we-enhance-addresses"></a>Com potenciem les adreces

El nostre model passa per un procés de dos passos per millorar una adreça. En primer lloc, analitza l'adreça per identificar-ne els components i els posa en un format estructurat. A continuació, utilitzem l'IA per corregir, completar i estandarditzar els valors de l'adreça.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Exemple

La informació de l'adreça pot tenir un format no estàndard i contenir errors ortogràfics. El model pot solucionar aquests problemes i crear adreces coherents en perfils de clients unificats.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Limitacions

Les adreces millorades només funcionen amb els valors que ja existeixen a les dades de l'adreça ingerida. El model no: 

1. Verifica si l'adreça és vàlida.
2. Verifica si algun dels valors, com ara els codis postals o els noms de carrers, són vàlids.
3. Canvia els valors que no reconeix.

El model utilitza tècniques basades en l'aprenentatge automàtic per millorar les adreces. Tot i que apliquem un llindar d'alta confiança per a quan el model canvia un valor d'entrada, com qualsevol model basat en l'aprenentatge automàtic, no es garanteix la precisió del 100 per cent.

## <a name="supported-countries-or-regions"></a>Països o regions admesos

Actualment admetem adreces enriquides en aquests països o regions: 

- Austràlia
- Canadà
- França
- Alemanya
- Itàlia
- Japó
- Regne Unit
- Estats Units

Les adreces han de contenir un valor de país o de regió. No processem adreces per a països o regions que no són compatibles i adreces que no tenen cap país o regió proporcionat.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment**.

1. Seleccioneu **Enriqueix les meves dades** a la peça **Adreces millorades**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de pantalla de la peça Adreces millorades.":::

1. Seleccioneu el **Conjunt de dades de client** i trieu l'entitat que conté les adreces que voleu enriquir. Podeu seleccionar l'entitat *Client* per enriquir les adreces de tots els perfils de client o seleccionar una entitat de segment per enriquir les adreces només als perfils de client que conté aquest segment.

1. Seleccioneu com es formaten les adreces al conjunt de dades. Trieu **Adreça d'un sol atribut** si les adreces de les dades utilitzen un únic camp. Trieu **Adreça de diversos atributs** si les adreces de les dades utilitzen més d'un camp de dades.

   > [!NOTE]
   > El país o regió és obligatori a les adreces d'un sol atribut i de diversos atributs. Les adreces que no continguin valors de país o regió vàlids o admesos no s'enriquiran.

1.  Assigneu els camps d'adreça de l'entitat de client unificada.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Pàgina d'assignació de camp d'adreça millorada.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un nom per a l'enriquiment i per a l'entitat de sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres. També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab). El temps de processament depèn de la mida de les dades dels clients.

Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**. A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.

Podeu veure una mostra de les dades enriquides a la peça de visualització prèvia **de** clients enriquits. Seleccioneu **Veure més** i seleccioneu la **pestanya Dades** per accedir a una visualització detallada de cada perfil enriquit.

### <a name="overview-card"></a>Targeta general

La targeta de visió general mostra detalls sobre la cobertura de l'enriquiment. 

* **Adreces processades i canviades**: nombre de perfils de clients amb adreces que s'han enriquit correctament.

* **Adreces processades i no canviades**: nombre de perfils de clients amb adreces reconegudes però no modificades. Normalment passa quan les dades d'entrada són vàlides i no es poden millorar amb l'enriquiment.

* **Adreces no processades i no modificades**: nombre de perfils amb adreces que no s'han reconegut. Normalment per a dades d'entrada que no són vàlides o no són compatibles amb l'enriquiment.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]