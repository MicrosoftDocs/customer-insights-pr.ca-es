---
title: Millora de dades de l'empresa
description: Enriquir i normalitzar les dades de l'empresa amb els models de Microsoft.
ms.date: 11/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: d11700c87f31cedc40d32b201251d8a9e2e2c312
ms.sourcegitcommit: dfc4843cc78857f1e3ca49d7b938e3ba77969169
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/15/2021
ms.locfileid: "7813907"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Enriquiment de perfils d'empresa amb dades d'empresa millorades

Utilitzeu els models de Microsoft i les dades de l'empresa compilades per corregir, complementar i estandarditzar els perfils de la vostra empresa. Utilitzarem el [format common data model](/common-data-model/schema/core/applicationcommon/account) per obtenir una millor precisió i informació.

## <a name="how-we-enhance-company-data"></a>Com millorar les dades de l'empresa

El nostre model passa per un procés de dos passos per millorar el perfil de l'empresa. En primer lloc, es normalitza el nom de l'empresa. Per exemple, *Microsoft Corp* serà corregit i estandarditzat a *Microsoft Corporation*. Intenta trobar una coincidència en les dades recopilades de Microsoft. Si es troba una coincidència, enriquim el perfil de l'empresa amb informació de les dades de l'empresa recopilades, inclòs el nom de l'empresa.


### <a name="example"></a>Exemple

És possible que la informació de la vostra empresa no segueixi un format estandarditzat i contingui errors ortogràfics. El model intenta solucionar aquests problemes i crear informació coherent.

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

Hi ha algunes limitacions amb les dades millorades. Els elements de la llista següent no són compatibles amb el model.

1.  Confirmar la identitat de l'empresa. No verifiquem si l'entrada és una organització existent o que una empresa utilitza la sortida com a nom estàndard.
2.  Cobreix de forma integral a les empreses a nivell mundial. Les dades de Microsoft recopilades tenen cobertura global, però ofereixen la major cobertura a Austràlia, Canadà, Regne Unit i els Estats Units.
3.  Estandarditzar les adreces de l'empresa a nivell mundial. Actualment donem suport a l'estandardització d'adreces en aquests països o regions: Austràlia, Canadà, França, Alemanya, Itàlia, Japó, Regne Unit i Estats Units.
4.  Garantir l'exactitud o frescor de les dades. Atesa que la informació empresarial sovint canvia, no podem garantir que les dades de l'empresa millorades proporcionades siguin sempre exactes o actualitzades.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment**.

1. Seleccioneu **Enriqueix les meves dades a la fitxa de dades de** **l'empresa** millorada.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Rajola d'enriquiment al centre d'enriquiment de dades de l'empresa.":::

1. Seleccioneu el **Conjunt de dades de client** i trieu l'entitat que conté les adreces que voleu enriquir. Podeu seleccionar l'entitat *Client* per enriquir les adreces de tots els perfils de client o seleccionar una entitat de segment per enriquir les adreces només als perfils de client que conté aquest segment.

1. Seleccioneu quin tipus de camps s'han d'utilitzar per combinar amb les dades d'empresa compilades de Microsoft. Aquesta selecció afectarà els camps d'assignació als quals teniu accés al pas següent.

1.  Assigneu els camps de l'empresa des de l'entitat client unificada. Com més identificadors de clau i camps assigneu, més probabilitats hi ha d'una taxa de coincidència més alta.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Pas d'assignació de dades en configurar un enriquiment d'empresa.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un nom per a l'enriquiment i per a l'entitat de sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres. També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab). El temps de processament depèn de la mida de les dades dels clients.

Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**. A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.

Per accedir a una visualització detallada de cada perfil enriquit, seleccioneu **Visualitza les dades enriquides**.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
