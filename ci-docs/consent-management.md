---
title: Utilitzar el consentiment del client
description: Honrar les preferències de consentiment dels clients a Customer Insights mitjançant la importació de dades de consentiment.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947517"
---
# <a name="use-customer-consent"></a>Utilitzar el consentiment del client

Les normes de protecció de dades i privacitat proporcionen als individus el dret de governar com una organització utilitza les seves dades personals. Exemples d'aquestes regulacions són el Reglament General de Protecció de Dades a la Unió Europea o la Llei de privadesa del consumidor de Califòrnia als Estats Units. Aquesta normativa permet a les persones optar per no tenir les seves dades personals recollides, tractades o compartides amb tercers.  

Els clients poden optar per retirar o retenir el seu consentiment per a formes específiques de contacte. També poden sol·licitar que els desactiveu de la recopilació, l'emmagatzematge, l'ús o la venda de les seves dades personals. És important que la vostra organització respecti totes les preferències de consentiment i privadesa de tots els clients.  

Dynamics 365 Customer Insights t'ajuda a respectar les sol·licituds dels teus clients important i emmagatzemant les seves preferències com a part dels perfils de clients unificats.

Si les dades de consentiment s'emmagatzemen per separat dels vostres perfils de clients, [afegiu les vostres dades de consentiment com a font de dades noves](#import-and-unify-consent-data). El font de dades que conté les dades de consentiment s'afegeix al procés d'unificació de dades. La unificació reeixida de les dades de consentiment i els perfils dels clients condueix a perfils de clients unificats que contenen la informació de consentiment. Per als perfils de clients que ja contenen informació de consentiment, aneu directament a la secció dades [de consentiment d'ús](#use-consent-data).

## <a name="prerequisites"></a>Requisits previs

La informació següent ha d'estar disponible a les dades d'origen per unificar les dades de consentiment amb altres perfils de clients:

- Clau alternativa per assignar la informació de consentiment als perfils d'usuari de Customer Insights. Per exemple, una adreça de correu electrònic o un número de telèfon.
- Valor de consentiment per determinar l'estat del consentiment del client.

Penseu en afegir la següent *informació opcional*:

- Clau principal per actualitzar l'estat del consentiment si un client sol·licita un canvi.
- Tipus de consentiment, si hi ha més d'una manera de processar la informació del client.
- Data de consentiment o qualsevol altre tipus de dades rellevants per als seus escenaris de consentiment.

Exemple de taula d'una base de dades de consentiment simple amb múltiples opcions de consentiment:

|Identificador de consentiment (clau principal)   |Correu electrònic (clau alternativa)  |Opció de consentiment  |Valor de consentiment  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Butlletí       |  Fals       |
|2    |  holly@contoso.com       |  Actualitzacions de productes       |  Cert       |
|3    |  frank@contoso.com       |  Butlletí       | Cert        |
|4    |  frank@contoso.com       |  Actualitzacions de productes       |  Fals       |

## <a name="import-and-unify-consent-data"></a>Importar i unificar les dades de consentiment

Podeu importar dades de consentiment de la mateixa manera que ingeriu altres fonts de dades al Customer Insights. Per obtenir més informació sobre les fonts de dades admeses i sobre com importar-les, vegeu [Visió general de l'origen de dades](data-sources.md).

Per obtenir més informació sobre la unificació de les fonts de dades, vegeu Visió [general de la unificació de dades](data-unification.md).

## <a name="use-consent-data"></a>Utilitzar les dades de consentiment

Un cop les dades de consentiment formin part dels vostres perfils de clients unificats, podeu utilitzar-les a Customer Insights. Per exemple, creeu un segment amb una regla per garantir que compliu les preferències de privadesa i protecció de dades dels vostres clients. Les regles que admeten les preferències de consentiment s'utilitzen per excloure els usuaris d'un segment basat en atributs de perfil. Afegir una regla a un segment que exclou els perfils de clients que no han donat el seu consentiment per contactar.

En referència a la taula d'exemple anterior, un segment podria contenir aquesta regla:`Consent option=Newsletter & Consent value=True`. Aquesta configuració dóna lloc a un segment que respecta les preferències de contacte per enviar un butlletí de notícies.

Per obtenir més informació sobre la creació de segments, vegeu [Crear segments](segment-builder.md).

Un cop creat el segment, podeu utilitzar una de les moltes [opcions](export-destinations.md) d'exportació per utilitzar el segment en altres aplicacions.

## <a name="ensure-updated-consent-status"></a>Garantir l'estat de consentiment actualitzat

És important mantenir actualitzat l'estat de consentiment per als vostres clients. L'actualització programada del Customer Insights sempre importa l'estat més recent de les fonts de dades. Aquesta informació es processa a través de la unificació de dades i dóna lloc a perfils de clients actualitzats. Aquests perfils actualitzats s'utilitzen per actualitzar segments per assegurar-vos que treballeu amb la informació més actualitzada.

En altres paraules, assegureu-vos que les dades d'origen que s'importen al Customer Insights sempre 1555.

Per obtenir més informació, vegeu [Actualitza els segments manualment](segments.md#refresh-segments) o [configura una actualització](system.md#schedule-tab) planificada.
