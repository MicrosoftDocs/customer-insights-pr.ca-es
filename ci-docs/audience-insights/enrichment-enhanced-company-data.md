---
title: Millora de dades de l'empresa
description: Enriquir i normalitzar les dades de l'empresa amb els models de Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 693e2f410a77cbf2e87ff0132ce963aab7e8e3e4
ms.sourcegitcommit: 4c9db6c124d7244e7e8bb2f8bfdc697523781c31
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "8010877"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Enriquiment de perfils d'empresa amb dades d'empresa millorades

Utilitzeu els models de Microsoft i les dades recopilades de l'empresa per corregir, complementar i estandarditzar els perfils de l'empresa. Utilitzarem el [format](/common-data-model/schema/core/applicationcommon/account) common data model per obtenir una millor precisió i estadístiques.

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

Hi ha algunes limitacions amb les dades millorades. Els elements de la llista següent no són compatibles amb el model.

1.  Confirmar la identitat de l'empresa. No verifiquem si l'entrada és una organització existent o que una empresa utilitza la sortida com a nom estàndard.
2.  Cobrir de manera integral les empreses a nivell mundial. Les dades recopilades de Microsoft tenen cobertura global, però ofereixen la major cobertura a Austràlia, Canadà, Regne Unit i els Estats Units.
3.  Estandarditzar les adreces de l'empresa a nivell mundial. Actualment donem suport a l'estandardització d'adreces en aquests països o regions: Austràlia, Canadà, França, Alemanya, Itàlia, Japó, Regne Unit i Estats Units.
4.  Garantir l'exactitud o frescor de les dades. Com que la informació de l'empresa sovint canvia, no podem garantir que les dades millorades de l'empresa proporcionades siguin sempre exactes o actualitzades.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. Aneu a **Dades** > **Enriquiment**.

1. Seleccioneu **Enriqueix les meves dades** a la peça de dades **de l'empresa** millorada.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Peça d'enriquiment al centre d'enriquiment per a dades de l'empresa.":::

1. Seleccioneu el **Conjunt de dades de client** i trieu l'entitat que conté les adreces que voleu enriquir. Podeu seleccionar l'entitat *Client* per enriquir les adreces de tots els perfils de client o seleccionar una entitat de segment per enriquir les adreces només als perfils de client que conté aquest segment.

1. Seleccioneu quin tipus de camps dels perfils de l'empresa s'han d'utilitzar per fer coincidir amb les dades compilades de l'empresa de Microsoft. Aquesta selecció afectarà els camps d'assignació als quals teniu accés al pas següent.

1.  Assigneu els camps d'empresa des de l'entitat de client unificada. Com més identificadors i camps de clau assigneu, més probabilitats hi ha d'una taxa de coincidència més alta.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Pas d'assignació de dades en configurar un enriquiment d'empresa.":::

1. Seleccioneu **Següent** per completar l'assignació de camp.

1. Proporcioneu un nom per a l'enriquiment i per a l'entitat de sortida.

1. Seleccioneu **Desa l'enriquiment** després de revisar les opcions.

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Per iniciar el procés d'enriquiment, seleccioneu **Executa** a la barra d'ordres. També podeu deixar que el sistema executi l'enriquiment automàticament com a part d'una [actualització planificada](system.md#schedule-tab). El temps de processament depèn de la mida de les dades dels clients.

Després de completar el procés d'enriquiment, podeu revisar les dades dels perfils de clients acabats d'enriquir a **Els meus enriquiments**. A més, trobareu l'hora de l'última actualització i el nombre de perfils enriquits.

Podeu veure una mostra de les dades enriquides a la peça de visualització prèvia **de** clients enriquits. Seleccioneu **Veure més** i seleccioneu la **pestanya Dades** per accedir a una visualització detallada de cada perfil enriquit.

### <a name="overview-card"></a>Targeta general

La targeta de visió general mostra detalls sobre la cobertura de l'enriquiment. 

* **Empreses processades i canviades**: El nombre de perfils d'empresa de clients que s'han enriquit amb èxit.

* **Empreses processades i no modificades**: Nombre de perfils d'empresa de clients que s'han reconegut però no canviat. Això sol passar quan les dades d'entrada són vàlides i no es poden millorar amb l'enriquiment.

* **Empreses no processades i no modificades**: El nombre de perfils d'empresa de clients que no han estat reconeguts. Això sol passar per a les dades d'entrada que no són vàlides o no són compatibles amb l'enriquiment.

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
