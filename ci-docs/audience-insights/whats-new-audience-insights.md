---
title: Característiques noves i previstes
description: Informació sobre les noves característiques, millores i correccions d'errors.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547660"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novetats de la capacitat de conclusions del públic del Dynamics 365 Customer Insights

Estem molt contents d'anunciar les nostres actualitzacions més recents. En aquest article es resumeixen les característiques de versió preliminar pública, millores de disponibilitat general i actualitzacions de característiques. Per veure els plans de característiques a llarg termini, doneu una ullada als [plans de llançament del Dynamics 365 i el Power Platform](/dynamics365/release-plans/).

Implementarem les actualitzacions per regió. Per tant, algunes regions poden veure les característiques abans que altres. Si no s'especifica de manera diferent, no cal que feu cap acció i actualitzarem l'aplicació automàticament sense temps d'inactivitat.

> [!TIP]
> Per enviar i votar peticions de característiques i suggeriments de productes, aneu al [Portal d'idees de l'aplicació del Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Actualitzacions de març del 2022

Les actualitzacions de març de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="liveramp-abilitec-enrichment-preview"></a>Enriquiment liveRamp AbiliTec (Preview)

LiveRamp proporciona resolució d'identitat i consolidació de dades de clients. Podeu assignar identificadors personals a les vostres dades de client al gràfic d'identitat d'AbiliTec i rebre identificadors d'AbiliTec. A continuació, podeu utilitzar aquests identificadors per a una millor unificació de les dades dels clients.

Per obtenir més informació, vegeu [Enriqueix els perfils de clients amb dades d'identitat de LiveRamp (Previsualització)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organitzar segments i mesures amb etiquetes i filtres
Si la vostra organització manté molts segments o mesures, trobar el correcte de vegades pot sentir-se desafiant. Aquesta nova característica us permet organitzar llistes mitjançant etiquetes i columnes. Ajuda a trobar dades de forma ràpida i senzilla i personalitzar les visualitzacions.

Per obtenir més informació, vegeu [Treballar amb etiquetes i columnes](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Activar l'ús compartit de dades amb Dataverse el vostre propi compte d'emmagatzematge

Si el vostre entorn utilitza Azure Data Lake Storage per emmagatzemar dades del Customer Insights, l'ús compartit de dades amb Microsoft Dataverse necessita una configuració addicional.
Anteriorment, només podeu habilitar l'ús compartit de dades quan Dataverse les vostres dades s'han emmagatzemat al nostre llac de dades administrades. 

Per obtenir més informació, vegeu [Habilitar l'ús compartit de dades des Dataverse de la vostra pròpia Azure Data Lake Storage (Visualització prèvia).](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)"

### <a name="new-export-destinations-iterable-and-braze"></a>Noves destinacions d'exportació: Iterable i Braze

Continuem ampliant el nostre ecosistema de destinacions d'exportació amb noves connexions. Ara podeu exportar segments a Iterable i Braze per utilitzar els seus serveis d'activació.

Per obtenir més informació, vegeu [Exportar segments a l'iterable (previsualització)](export-iterable.md) i [Exportar segments a Braze (previsualització)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Millores en l'exportació de Marketo i Google Ads

El canvi d'API en els serveis connectats provoca que les actualitzacions dels connectors s'executin de manera fiable i fluida. Hem publicat algunes actualitzacions de les exportacions als serveis de Marketo i Google Ads:

- Google Ads: la nova versió del connector d'exportació de Google Ads simplifica l'experiència d'autenticació i ara us permet crear públics nous de Google Ads automàticament. 
- Marketo: La nova versió del connector d'exportació Marketo proporciona suport per a l'identificador de Marketo, cosa que us permet evitar duplicitats de dades, actualitzar registres existents i crear registres nous a Marketo. 


## <a name="february-2022-updates"></a>Actualitzacions de febrer del 2022

Les actualitzacions de febrer de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="general-availability-for-prediction-models"></a>Disponibilitat general per a models predicció

Els models de predicció de fora de la caixa, inclosos el **churn** de subscripció, **el churn** transaccional i **el valor de vida del client (CLV)** generalment estan disponibles com a part de Customer Insights. 

Per obtenir més informació, vegeu [Visió general](predictions-overview.md) de les prediccions.

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Font de dades nou: integració amb Azure Synapse Analytics (visualització prèvia)

Azure Synapse Analytics És un servei d'anàlisi empresarial que accelera el temps per obtenir estadístiques a través de magatzems de dades i sistemes de big data.

Les organitzacions que ja utilitzen Azure Synapse Analytics poden ingerir aquestes dades al Customer Insights. 

Per obtenir més informació, vegeu [Connectar una Azure Synapse font de dades (Previsualització)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Enriquiment liveRamp (Preview)

LiveRamp proporciona resolució d'identitat i consolidació de dades de clients. Podeu assignar identificadors personals a les vostres dades de client al gràfic d'identitat d'AbiliTec i rebre identificadors d'AbiliTec. A continuació, podeu utilitzar aquests identificadors per a una millor unificació de les dades dels clients.

Per obtenir més informació, vegeu [Enriqueix els perfils de clients amb dades d'identitat de LiveRamp (Previsualització)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Enriquiment per a fonts de dades (Vista prèvia)

Utilitzeu dades d'orígens com Microsoft i altres socis per enriquir les dades dels clients abans de la unificació de dades. Font de dades enriquiments ajuden a produir una major integritat i qualitat de les dades que poden ajudar a aconseguir millors resultats una vegada que unifiqueu les vostres dades.

Per obtenir més informació, vegeu [Enriquiment per a fonts de dades (Previsualització)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Canvia el propietari de l'entorn

Tot i que diversos usuaris poden tenir permisos d'administració a Customer Insights, només un usuari és el propietari d'un entorn. Una experiència millorada us permet canviar els propietaris d'un entorn i reclamar la propietat si un antic propietari va abandonar l'organització. 

Per obtenir més informació, consulta [Canviar el propietari d'un entorn](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>El procés de preparació de dades llista la raó de corrupció dels registres malmesos

La preparació de dades ara mostra la raó de la corrupció de tots els camps amb dades malmeses. La informació es proporciona a nivell de registre individual per facilitar la identificació. 

Per obtenir més informació, vegeu [Orígens](entities.md#corrupted-data-sources) de dades malmesos.

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Final de la visualització prèvia per a les funcions d'informes a la capacitat d'informació d'interacció

La Dynamics 365 Customer Insights vista prèvia de la capacitat d'informació de compromís va finalitzar el 15 de febrer de 2022.  
Aquest canvi significa que l'experiència de prova del Customer Insights ja no inclou la possibilitat de crear embuts de conversió ni altres funcionalitats d'informes.

Us convidem a explorar i avaluar les moltes altres característiques del Customer Insights [, la plataforma de dades de](https://dynamics.microsoft.com/ai/customer-insights/) clients de Microsoft (CDP).    
 
Durant un període de transició, els participants de previsualització existents encara tenen accés a algunes capacitats i funcionalitats de visualització prèvia:

- Obtén el codi per instrumentar un lloc web o una aplicació mòbil 
- Veure esdeveniments i propietats de l'esdeveniment 
- Millorar els perfils unificats amb esdeveniments ingerits i refinats per beneficiar-se del valor total de les seves dades de clients
  
Durant el període de transició, els esdeveniments capturats encara es transmeten al data lake connectat. Un cop desactivada aquesta funcionalitat, l'intercanvi de dades entre les estadístiques d'interacció i les estadístiques del públic s'aturarà i no s'enviaran esdeveniments nous a l'emmagatzematge connectat.
Poseu-vos en contacte directament amb l'equip del compte Microsoft si teniu preguntes sobre el final de la visualització prèvia de capacitat. L'equip del compte us mantindrà actualitzats en els propers llançaments. 

## <a name="january-2022-updates"></a>Actualitzacions de gener de 2022

Les actualitzacions de gener de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Anàlisi del sentiment dels comentaris dels teus clients

Customer Insights proporciona una nova funció amb IA per sintetitzar el sentiment del client i identificar aspectes empresarials específics com a oportunitats de millores específiques. Mitjançant l'anàlisi dels comentaris escrits dels vostres clients, podeu obtenir estadístiques precises a baix cost. Anàlisi de sentiments impulsat per models de processament del llenguatge natural (PNL) que generen dues estadístiques derivades per a cada identificador de client. Una puntuació de sentiment (de –5 a 5) i una llista dels aspectes empresarials aplicables. 

Per obtenir més informació, vegeu [Analitzar el sentiment a la retroalimentació dels clients (Previsualització)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]