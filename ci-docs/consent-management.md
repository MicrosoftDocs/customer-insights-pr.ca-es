---
title: Utilitzeu el consentiment del client
description: Respectar les preferències de consentiment dels clients al Customer Insights mitjançant la importació de dades de consentiment.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6c951219410b55adc34691f677158b574cea1e01
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245683"
---
# <a name="use-customer-consent"></a>Utilitzeu el consentiment del client

La normativa de protecció de dades i privacitat proporciona a les persones el dret de governar com una organització utilitza les seves dades personals. Exemples d'aquestes regulacions són el Reglament General de Protecció de Dades de la Unió Europea o la Llei de Privacitat del Consumidor de Califòrnia als Estats Units. Aquesta normativa permet a les persones optar per no tenir les seves dades personals recopilades, tractades o compartides amb tercers.  

Els clients poden optar per retirar o retenir el seu consentiment per a formes específiques de contacte. També poden sol·licitar que els doneu de baixa de la recopilació, l'emmagatzematge, l'ús o la venda de les seves dades personals. És important que la vostra organització respecti el consentiment i les preferències de privadesa de tots els clients.  

Dynamics 365 Customer Insights us ajuda a respectar les sol·licituds dels vostres clients important i emmagatzemant les seves preferències com a part dels perfils de clients unificats.

Si les dades de consentiment s'emmagatzemen separadament dels vostres perfils de client, [afegiu les vostres dades de consentiment com a nova font de dades](#import-and-unify-consent-data). La font de dades que conté les dades de consentiment s'afegeix al procés d'unificació de dades. La unificació reeixida de les dades de consentiment i dels perfils de clients condueix a perfils de clients unificats que contenen la informació de consentiment. Per als perfils de clients que ja contenen informació de consentiment, aneu directament a la secció dades [de consentiment d'ús](#use-consent-data).

## <a name="prerequisites"></a>Requisits previs

La informació següent ha d'estar disponible a les dades d'origen per unificar les dades de consentiment amb altres perfils de clients:

- Clau alternativa per assignar la informació de consentiment als perfils d'usuari al Customer Insights. Per exemple, una adreça de correu electrònic o un número de telèfon.
- Valor del consentiment per determinar l'estat del consentiment del client.

Penseu a afegir la informació opcional *següent*:

- Clau principal per actualitzar l'estat de consentiment si un client sol·licita un canvi.
- Tipus de consentiment, si hi ha més d'una manera de processar la informació del client.
- Data de consentiment o qualsevol altre tipus de dades rellevants per als seus escenaris de consentiment.

Taula d'exemple d'una base de dades de consentiment senzilla amb múltiples opcions de consentiment:

|Identificador de consentiment (clau principal)   |Correu electrònic (clau alternativa)  |Opció consentiment  |Valor del consentiment  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Butlletí       |  Fals       |
|2    |  holly@contoso.com       |  Actualitzacions de productes       |  Cert       |
|3    |  frank@contoso.com       |  Butlletí       | Cert        |
|4    |  frank@contoso.com       |  Actualitzacions de productes       |  Fals       |

## <a name="import-and-unify-consent-data"></a>Importar i unificar dades de consentiment

Importeu les dades de consentiment de la mateixa manera que ingeriu altres fonts de dades al Customer Insights. Per obtenir més informació sobre les fonts de dades admeses i sobre com importar-les, vegeu [Informació general de les fonts de dades](data-sources.md).

Per obtenir més informació sobre com unificar les fonts de dades, vegeu [Informació general](data-unification.md) de la unificació de dades.

## <a name="use-consent-data"></a>Utilitzar les dades de consentiment

Quan les dades de consentiment formin part dels vostres perfils de client unificats, podeu utilitzar-les al Customer Insights. Per exemple, creeu un segment amb una regla per assegurar-vos que compliu les preferències de privadesa i protecció de dades dels vostres clients. Les regles que admeten les preferències de consentiment s'utilitzen per excloure usuaris d'un segment basat en atributs de perfil. Afegiu una regla a un segment que exclou els perfils de clients que no han donat el consentiment per contactar.

Fent referència a la taula de mostra anterior, un segment podria contenir aquesta regla:`Consent option=Newsletter & Consent value=True`. Aquesta configuració dóna com a resultat un segment que respecta les preferències de contacte per enviar un butlletí de notícies.

Per obtenir més informació sobre els segments de construcció, vegeu [Crear segments](segment-builder.md).

Un cop creat el segment, podeu utilitzar una de les moltes [opcions](export-destinations.md) d'exportació per utilitzar el segment en altres aplicacions.

## <a name="ensure-updated-consent-status"></a>Garantir l'estat de consentiment actualitzat

És important mantenir actualitzat l'estat de consentiment per als vostres clients. L'actualització programada al Customer Insights sempre importa l'estat més recent de les fonts de dades. A continuació, aquesta informació es processa mitjançant la unificació de dades i dóna com a resultat perfils de clients actualitzats. Aquests perfils actualitzats s'utilitzen per actualitzar els segments per assegurar-vos que treballeu amb la informació més actualitzada.

Dit d'una altra manera, assegureu-vos que les dades d'origen que s'importen al Customer Insights tinguin sempre la informació més recent.

Per obtenir més informació, vegeu [Actualitza els segments manualment](segments.md#refresh-segments) o [configura una actualització](schedule-refresh.md) programada.

[!INCLUDE [footer-include](includes/footer-banner.md)]
