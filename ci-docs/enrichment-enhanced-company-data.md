---
title: Enriquir perfils d'empresa amb dades d'empresa millorades
description: Enriquir i normalitzar les dades de l'empresa amb els models de Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054236"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Enriquir perfils d'empresa amb dades d'empresa millorades

Utilitzeu els models de Microsoft i les dades recopilades de l'empresa per corregir, complementar i estandarditzar els perfils de l'empresa. Utilitzarem el [format](/common-data-model/schema/core/applicationcommon/account) common data model per obtenir una millor precisió i estadístiques.

També [podeu millorar les dades de l'empresa sobre fonts](data-sources-enrichment.md) de dades per millorar la precisió de la coincidència en el procés d'unificació de dades.

Per a les empreses públiques dels Estats Units, hi ha informació com ara ingressos, marques d'accions, indústria i molt més.  

## <a name="how-we-enhance-company-data"></a>Com millorem les dades de l'empresa

El nostre model passa per un procés de dos passos per millorar el perfil de l'empresa. En primer lloc, es normalitza el nom de l'empresa. Per exemple, *Microsoft Corp* serà corregit i estandarditzat a *Microsoft Corporation*. Intenta trobar una coincidència en les dades compilades de l'empresa de Microsoft. Si es troba una coincidència, enriquim el perfil de l'empresa amb informació de les dades recopilades de l'empresa, inclòs el nom de l'empresa.

### <a name="example"></a>Exemple

És possible que la informació de l'empresa no segueixi un format estandarditzat i contingui errors ortogràfics. El model intenta solucionar aquests problemes i crear informació coherent.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Limitacions

El model no:

- Confirmar la identitat de l'empresa. No verifiquem si l'entrada és una organització existent o que una empresa utilitza la sortida com a nom estàndard.
- Cobrir de manera integral les empreses a nivell mundial. Les dades recopilades de Microsoft tenen cobertura global, però ofereixen la major cobertura a Austràlia, Canadà, Regne Unit i els Estats Units.
- Estandarditzar les adreces de l'empresa a nivell mundial. Actualment donem suport a l'estandardització d'adreces en aquests països o regions: Austràlia, Canadà, França, Alemanya, Itàlia, Japó, Regne Unit i Estats Units.
- Garantir l'exactitud o frescor de les dades. Com que la informació de l'empresa sovint canvia, no podem garantir que les dades millorades de l'empresa proporcionades siguin sempre exactes o actualitzades.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment** i seleccioneu la pestanya **Descobreix**.

1. Seleccioneu **Enriqueix les meves dades** a la peça de dades **de l'empresa** millorada.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Peça d'enriquiment al centre d'enriquiment per a dades de l'empresa.":::

1. Reviseu la visió general i, a continuació, seleccioneu **Següent**.

1. Seleccioneu el **conjunt de dades del client** i trieu el perfil o el segment que voleu enriquir. L'entitat *Client* enriqueix tots els vostres perfils de clients, mentre que un segment enriqueix només els perfils de clients continguts en aquest segment.

1. Seleccioneu quin tipus de camps dels perfils de l'empresa voleu utilitzar per fer coincidir amb les dades compilades de l'empresa de Microsoft. Aquesta selecció afectarà els camps d'assignació als quals teniu accés al pas següent.

1. Seleccioneu **Següent**.

1. Assigneu els camps de l'empresa a les dades de l'empresa de Microsoft. Per obtenir una precisió més alta de coincidència, afegiu més camps.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Pas d'assignació de dades en configurar un enriquiment d'empresa.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un **nom** per a l'enriquiment i l'entitat **Sortida**.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

1. Seleccioneu **Executa** per iniciar el procés d'enriquiment o a prop per tornar a la **pàgina Enriquiments**.

## <a name="view-enrichment-results"></a>Veure resultats d'enriquiment

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Targeta general

La **fitxa general de clients** mostra detalls sobre la cobertura de l'enriquiment

- **Empreses processades i canviades**: El nombre de perfils d'empresa de clients que s'han enriquit amb èxit.
- **Empreses processades i no modificades**: Nombre de perfils d'empresa de clients que s'han reconegut però no canviat. Això sol passar quan les dades d'entrada són vàlides i no es poden millorar amb l'enriquiment.
- **Empreses no processades i no modificades**: nombre de perfils d'empresa de clients que no s'han reconegut. Això sol passar per a les dades d'entrada que no són vàlides o no són compatibles amb l'enriquiment.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
