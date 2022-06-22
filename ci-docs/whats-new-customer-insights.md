---
title: Característiques noves i actualitzades
description: Informació sobre les noves característiques, millores i correccions d'errors.
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: d06f8be114f558d7adadf2913107c5fd69686875
ms.sourcegitcommit: 9dd767051014e06d8d9f2f616e248573f24df4cb
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8843335"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novetats del Dynamics 365 Customer Insights

Estem molt contents d'anunciar les nostres actualitzacions més recents. En aquest article es resumeixen les característiques de versió preliminar pública, millores de disponibilitat general i actualitzacions de característiques. Per veure els plans de característiques a llarg termini, doneu una ullada als [plans de llançament del Dynamics 365 i el Power Platform](/dynamics365/release-plans/).

Implementarem les actualitzacions per regió. Per tant, algunes regions poden veure les característiques abans que altres. Si no s'especifica de manera diferent, no cal que feu cap acció i actualitzarem l'aplicació automàticament sense temps d'inactivitat.

> [!TIP]
> Per enviar i votar peticions de característiques i suggeriments de productes, aneu al [Portal d'idees de l'aplicació del Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2022-updates"></a>Actualitzacions de maig de 2022

Les actualitzacions de maig de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="updated-data-unification-experience"></a>Experiència d'unificació de dades actualitzada

 La unificació de dades us permet unificar fonts de dades una vegada dispars en un únic conjunt de dades mestre que proporciona una visualització unificada d'aquestes dades. Les dades es poden unificar en una sola entitat o en diverses entitats. En primer lloc, seleccioneu [entitats i camps](map-entities.md) d'origen, [suprimiu registres](remove-duplicates.md) duplicats, especifiqueu regles per a [les condicions coincidents](match-entities.md) i definiu quins [camps s'han d'incloure als perfils de client unificats](merge-entities.md).

Per obtenir més informació, vegeu Visió [general de la unificació de dades](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Pàgina inicial actualitzada a Customer Insights

**Home** us guia a través del procés de configuració de les funcions clau i proporciona una visió general dels segments, mesures i dades d'enriquiment. Hem refrescat l'experiència per proporcionar informació més rellevant d'un cop d'ull.

Per obtenir més informació, vegeu [Explorar estadístiques](home.md) del client.

### <a name="track-usage-of-a-segment"></a>Seguiment de l'ús d'un segment

Ara [podeu fer un seguiment de l'ús d'un segment](segments.md#track-usage-of-a-segment) a les aplicacions, que es basen en l'organització Dataverse connectada amb el Customer Insights. Per als [segments del Customer Insights utilitzats en els recorreguts del client del Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), el sistema us informa sobre l'ús d'aquest segment.

### <a name="export-to-criteo"></a>Exporta a Criteo

Criteo és una plataforma en línia que ajuda els usuaris a gestionar la publicitat digital. Ara podeu exportar segments de perfils de clients unificats per generar campanyes, proporcionar màrqueting per correu electrònic i utilitzar grups específics de clients amb Criteo.

Per obtenir més informació, vegeu [Exportar segments a Criteo (previsualització)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Estructura de documentació refinada per a la creació d'entorns

Hem revisat els documents d'ajuda relacionats amb la creació i gestió d'entorns al Customer Insights. Els articles ara s'agrupen sota el node Environments de l'índex de continguts. Els articles reestructurats proporcionen més orientació per a les diferents maneres de configurar entorns i tenir una estructura més clara. Si teniu comentaris per compartir, feu-nos-ho saber a través dels controls cap al final dels articles d'ajuda.

Per obtenir més informació, vegeu [Com: Crear un entorn](create-environment.md) nou.

## <a name="april-2022-updates"></a>Actualitzacions d'abril de 2022

Les actualitzacions a l'abril de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="dun--bradstreet-enrichment-preview"></a>Enriquiment Dun & Bradstreet (Vista prèvia)

Dun &Bradstreet proporciona dades comercials, anàlisis i estadístiques per a empreses. Permet enriquir les dades als clients amb perfils de clients unificats per a les empreses. Els enriquiments inclouen atributs com el número DUNS, la mida de l'empresa, la ubicació, la indústria i molt més.

Per obtenir més informació, vegeu [Enriquiment de perfils d'empresa amb Dun &Bradstreet (Preview)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Defineix el tipus de mesura en crear un compàs nou

Ara podeu distingir entre mesures per a perfils individuals i mesures de tot el vostre negoci. Tot i que les mesures de negoci es mostren a la pàgina d'inici de Customer Insights, les mesures dels clients s'exposen a les visualitzacions detallades dels clients.

Per obtenir més informació, vegeu [Utilitzar el constructor de mesures per crear mesures des de zero](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Consolidació de la documentació de Customer Insights

Hem revisat els nostres articles de documentació i hem suprimit mencions d'estadístiques d'interacció i capacitats d'informació del públic. A partir d'ara, ens referirem constantment al nom del producte Customer Insights quan escrivim sobre les característiques bàsiques de l'aplicació. Aquest canvi també condueix a una reestructuració significativa de la taula de continguts, l'estructura de l'URL i les rutes de fitxer al repositori de documentació subjacent. Totes les adreces d'interès o els enllaços existents continuen funcionant i redirigint-se als URL actualitzats.

Si voleu fer-nos saber com percebeu aquest canvi o detecteu alguna cosa que no funciona com s'esperava, digueu-nos [enviant comentaris per a aquesta pàgina](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Actualitzacions de març del 2022

Les actualitzacions de març de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="liveramp-abilitec-enrichment-preview"></a>Enriquiment liveRamp AbiliTec (Preview)

LiveRamp proporciona resolució d'identitat i consolidació de dades de clients. Podeu assignar identificadors personals a les vostres dades de client al gràfic d'identitat d'AbiliTec i rebre identificadors d'AbiliTec. A continuació, podeu utilitzar aquests identificadors per a una millor unificació de les dades dels clients.

Per obtenir més informació, vegeu [Enriquer perfils de clients amb dades d'identitat de LiveRamp (Previsualització)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organitzar segments i mesures amb etiquetes i filtres

Si la vostra organització manté molts segments o mesures, trobar el correcte de vegades pot sentir-se desafiant. Aquesta nova característica us permet organitzar llistes mitjançant etiquetes i columnes. Ajuda a trobar dades de forma ràpida i senzilla i personalitzar les visualitzacions.

Per obtenir més informació, vegeu [Treballar amb etiquetes i columnes](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Activar l'ús compartit de dades amb Dataverse el vostre propi compte d'emmagatzematge

Si el vostre entorn utilitza Azure Data Lake Storage per emmagatzemar dades del Customer Insights, l'ús compartit de dades amb Microsoft Dataverse necessita una configuració addicional.
Anteriorment, només podeu habilitar l'ús compartit de dades quan Dataverse les vostres dades s'han emmagatzemat al nostre llac de dades administrades.

Per obtenir més informació, vegeu [Habilitar l'ús compartit de dades des Dataverse de la vostra pròpia Azure Data Lake Storage (Visualització prèvia).](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)"

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

Per obtenir més informació, vegeu [Enriquer perfils de clients amb dades d'identitat de LiveRamp (Previsualització)](enrichment-liveramp.md).

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
  
Durant el període de transició, els esdeveniments capturats encara es transmeten al data lake connectat. Un cop desactivada aquesta funcionalitat, l'ús compartit de dades s'aturarà i no s'enviaran esdeveniments nous a l'emmagatzematge connectat.
Poseu-vos en contacte directament amb l'equip del compte Microsoft si teniu preguntes sobre el final de la visualització prèvia de capacitat. L'equip del compte us mantindrà actualitzats en els propers llançaments. 

## <a name="january-2022-updates"></a>Actualitzacions de gener de 2022

Les actualitzacions de gener de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Anàlisi del sentiment dels comentaris dels teus clients

Customer Insights proporciona una nova funció amb IA per sintetitzar el sentiment del client i identificar aspectes empresarials específics com a oportunitats de millores específiques. Mitjançant l'anàlisi dels comentaris escrits dels vostres clients, podeu obtenir estadístiques precises a baix cost. Anàlisi de sentiments impulsat per models de processament del llenguatge natural (PNL) que generen dues estadístiques derivades per a cada identificador de client. Una puntuació de sentiment (de –5 a 5) i una llista dels aspectes empresarials aplicables. 

Per obtenir més informació, vegeu [Analitzar el sentiment a la retroalimentació dels clients (Previsualització)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]