---
title: Novetats del Dynamics 365 Customer Insights
description: Informació sobre les noves característiques, millores i correccions d'errors.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 1e734464cec1f66428c3a2a2e403437a2a9d8500
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387270"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novetats del Dynamics 365 Customer Insights

Estem molt contents d'anunciar les nostres actualitzacions més recents. En aquest article es resumeixen les característiques de versió preliminar pública, millores de disponibilitat general i actualitzacions de característiques. Per veure els plans de característiques a llarg termini, doneu una ullada als [plans de llançament del Dynamics 365 i el Power Platform](/dynamics365/release-plans/).

Implementarem les actualitzacions per regió. Per tant, algunes regions poden veure les característiques abans que altres. Tret que s'especifiqui d'una altra manera, no cal que feu cap acció, actualitzarem l'aplicació automàticament sense temps d'inactivitat.

> [!TIP]
> Per enviar i votar peticions de característiques i suggeriments de productes, aneu al [Portal d'idees de l'aplicació del Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2022-updates"></a>Actualitzacions d'agost de 2022

Les actualitzacions de l'agost de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="contact-unification-in-b-to-b-environments"></a>Unificació de contactes en entorns B-to-B

Els entorns B-to-B del Customer Insights ara admeten una experiència millorada d'unificació de dades.

Ara podeu unificar contactes a més de comptes per obtenir una visualització completa dels contactes de la vostra empresa. Els contactes unificats s'associen a comptes unificats i ara apareixen a les targetes de client. 

Per obtenir més informació, vegeu [Crear un perfil de contacte unificat](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Creació i exportació de segments basats en contactes unificats

Gràcies a la nova unificació de contactes, podeu crear segments de contactes mitjançant criteris de contactes, comptes o tots dos. Aquests segments es poden exportar per activar-los en altres serveis.

Per obtenir més informació, vegeu [Informació general de les exportacions](export-destinations.md).

## <a name="july-2022-updates"></a>Actualitzacions de juliol del 2022

Les actualitzacions del juliol de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="export-to-moengage"></a>Exportació a MoEngage

Exporta segments de perfils de clients unificats a MoEngage i utilitza'ls per a email màrqueting a MoEngage.

Per obtenir més informació, vegeu [Exportació de segments a MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>Suport SSH per a exportacions basades en SFTP

Trieu si voleu autenticar-vos mitjançant SSH o nom d'usuari/contrasenya per a connexions amb destinacions d'exportació SFTP.

Per obtenir més informació, vegeu [Exportació de dades a amfitrions SFTP](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Personalitzar experiències amb dades d'usuaris coneguts i desconeguts

Gestionar les dades dels clients no és un repte nou, però cada vegada és més difícil a mesura que els usuaris naveguen pels diferents canals digitals que ofereixen les marques. Un usuari conegut (autenticat) en un canal es torna desconegut (no autenticat) en un altre si no ha iniciat la sessió. El problema sovint és que els usuaris no autenticats (desconeguts) no tenen un identificador comú. Es podria utilitzar per associar atributs de perfils significatius i generar perfils de clients unificats. El Customer Insights ajuda a resoldre aquest problema ingerint dades dels mètodes de seguiment als vostres sistemes d'origen.

Per obtenir més informació, vegeu [Personalitzar les experiències amb dades sobre usuaris](unknown-to-known.md) coneguts i desconeguts.

## <a name="june-2022-updates"></a>Actualitzacions de juny del 2022

Les actualitzacions del juny de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Experiència d'usuari actualitzada per a fonts de dades i ingestió de dades

Importar dades d'una àmplia gamma de fonts de dades és la base per consolidar les dades dels vostres clients en Dynamics 365 Customer Insights. Hem revisat l'experiència d'usuari per a la importació i la connexió de fonts de dades. L'objectiu d'aquesta actualització és facilitar-vos la introducció de dades al Customer Insights.

Per obtenir més informació, vegeu [Informació general de les fonts de dades](data-sources.md).

### <a name="export-to-inmobi"></a>Exportació a InMobi

InMobi ajuda les marques a entendre, identificar, involucrar i adquirir consumidors. Podeu exportar segments i altres dades al servei InMobi mitjançant comptes d'emmagatzematge blob de l'Azure.

Per obtenir més informació, vegeu [Exporta a InMobi (visualització prèvia)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Assistència de lockbox al Customer Insights

Customer Lockbox proporciona una interfície per revisar i aprovar (o rebutjar) les sol·licituds d'accés a dades. Aquestes sol·licituds es produeixen quan es necessita l'accés a les dades dels clients per resoldre un cas de suport tècnic.

Per obtenir més informació, vegeu [Accés segur a les dades dels clients amb Customer Lockbox (Visualització prèvia).](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview)

### <a name="connect-to-your-data-using-azure-private-link"></a>Connecteu-vos a les vostres dades mitjançant l'Azure Private Link

Azure Private Link permetem que el Customer Insights es connecti al vostre Azure Data Lake Storage compte a través d'un punt final privat de la vostra xarxa virtual. Per a les dades d'un compte d'emmagatzematge, que no estan exposades a Internet pública, Private Link permet la connexió a aquesta xarxa restringida.

Per obtenir més informació, vegeu [Utilitzar l'enllaç privat al Customer Insights](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Actualitzacions de maig de 2022

Les actualitzacions del maig de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="updated-data-unification-experience"></a>Experiència actualitzada d'unificació de dades

 La unificació de dades us permet unificar fonts de dades un cop disparades en un únic conjunt de dades mestre que proporciona una visualització unificada d'aquestes dades. Les dades es poden unificar en una sola entitat o en diverses entitats. En primer lloc, seleccioneu entitats i camps d'origen, [elimineu registres duplicats](map-entities.md), especifiqueu regles per a [les condicions](remove-duplicates.md) de coincidència i definiu [quins](match-entities.md) camps heu d'incloure als perfils de client unificats [.](merge-entities.md)

Per obtenir més informació, vegeu [Informació general](data-unification.md) sobre la unificació de dades.

### <a name="refreshed-home-page-in-customer-insights"></a>Pàgina d'inici actualitzada al Customer Insights

**Home** us guia a través del procés de configuració de les funcions clau i proporciona una visió general dels segments, mesures i dades d'enriquiment. Hem refrescat l'experiència per proporcionar informació més rellevant d'un cop d'ull.

Per obtenir més informació, vegeu [Explora les estadístiques](home.md) del client.

### <a name="track-usage-of-a-segment"></a>Fer un seguiment de l'ús d'un segment

Ara [podeu fer un seguiment de l'ús d'un segment](segments.md#track-usage-of-a-segment) a les aplicacions, que es basen en l'organització Dataverse connectada amb el Customer Insights. Per [als segments del Customer Insights utilitzats en els recorreguts del client del Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), el sistema us informa sobre l'ús d'aquest segment.

### <a name="export-to-criteo"></a>Exportació a Criteo

Criteo és una plataforma en línia que ajuda els usuaris a gestionar la publicitat digital. Ara pots exportar segments de perfils de clients unificats per generar campanyes, proporcionar email màrqueting i utilitzar grups específics de clients amb Criteo.

Per obtenir més informació, vegeu [Exportació de segments a Criteo (visualització prèvia).](export-criteo.md)

### <a name="refined-documentation-structure-for-environment-creation"></a>Estructura de documentació refinada per a la creació d'entorns

Hem revisat els documents d'ajuda relacionats amb la creació i la gestió d'entorns al Customer Insights. Els articles ara s'agrupen sota el node Entorns a la taula de continguts. Els articles reestructurats proporcionen més orientacions per a les diferents maneres de configurar entorns i tenen una estructura més clara. Si teniu comentaris per compartir, feu-nos-ho saber mitjançant els controls cap al final dels articles d'ajuda.

Per obtenir més informació, vegeu [Com: Crear un entorn](create-environment.md) nou.

## <a name="april-2022-updates"></a>Actualitzacions d'abril de 2022

Les actualitzacions de l'abril de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet enriquiment (Vista prèvia)

Dun & Bradstreet proporciona dades comercials, anàlisis i estadístiques per a les empreses. Permet enriquir les dades als clients amb perfils de clients unificats per a les empreses. Els enriquiments inclouen atributs com el número DUNS, la mida de l'empresa, la ubicació, la indústria i molt més.

Per obtenir més informació, vegeu [Enriquiment dels perfils de l'empresa amb Dun & Bradstreet (Preview)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definir el tipus de mesura en crear una nova mesura

Ara pots distingir entre mesures per a perfils individuals i mesures per a tota l'empresa. Tot i que les mesures empresarials es mostren a la pàgina d'inici del Customer Insights, les mesures dels clients s'exposen a les visualitzacions detallades dels clients.

Per obtenir més informació, vegeu [Utilitzar el creador de mesures per crear mesures des de zero](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Consolidació de la documentació del Customer Insights

Hem revisat els nostres articles de documentació i hem suprimit mencions d'estadístiques d'interacció i funcions d'informació del públic. Avançant, ens referirem constantment al nom del producte Customer Insights quan escrivim sobre les característiques bàsiques de l'aplicació. Aquest canvi també comporta una reestructuració significativa de la taula de continguts, l'estructura d'URL i les rutes del fitxer al repositori de documentació subjacent. Totes les adreces d'interès o els enllaços existents continuen funcionant i redirigeixen als URL actualitzats.

Si voleu fer-nos saber com percebeu aquest canvi o detectar alguna cosa que no funciona com s'esperava, digueu-nos [enviant comentaris per a aquesta pàgina](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Actualitzacions de març del 2022

Les actualitzacions del març de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec enriquiment (Preview)

LiveRamp proporciona resolució d'identitat i consolidació de dades de clients. Podeu assignar els identificadors personals de les dades dels vostres clients al gràfic d'identitat d'AbiliTec i rebre els identificadors d'AbiliTec. A continuació, podeu utilitzar aquests identificadors per a una millor unificació de les dades dels vostres clients.

Per obtenir més informació, vegeu [Enriquir perfils de clients amb dades d'identitat del LiveRamp (visualització prèvia)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organitzar segments i mesures amb etiquetes i filtres

Si la vostra organització manté molts segments o mesures, trobar-ne l'adequat de vegades pot semblar un repte. Aquesta nova característica us permet organitzar llistes mitjançant etiquetes i columnes. Ajuda a trobar dades de manera ràpida i senzilla i a personalitzar les visualitzacions.

Per obtenir més informació, vegeu [Treballar amb etiquetes i columnes](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Activar l'ús Dataverse compartit de dades amb el teu propi compte d'emmagatzematge

Si el vostre entorn utilitza Azure Data Lake Storage per emmagatzemar dades del Customer Insights, l'ús compartit de dades necessita Microsoft Dataverse alguna configuració addicional.
Anteriorment, només podies activar l'ús compartit de Dataverse dades quan les teves dades s'emmagatzemaven al nostre llac de dades administrades.

Per obtenir més informació, vegeu [Habilitar l'ús compartit de dades des Dataverse del vostre compte Azure Data Lake Storage (Visualització prèvia)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)

### <a name="new-export-destinations-iterable-and-braze"></a>Noves destinacions d'exportació: Iterable i Braze

Continuem ampliant el nostre ecosistema de destinacions d'exportació amb noves connexions. Ara podeu exportar segments a Iterable i Braze per utilitzar els seus serveis d'activació.

Per obtenir més informació, vegeu [Exporta els segments a Iterable (visualització prèvia)](export-iterable.md) i [Exporta els segments a Braze (visualització prèvia).](export-braze.md)

### <a name="improvements-to-marketo-and-google-ads-export"></a>Millores a l'exportació de Marketo i Google Ads

Canviar les API dels serveis connectats comporta actualitzacions perquè els connectors s'executin de manera fiable i fluida. Hem publicat algunes actualitzacions de les exportacions als serveis de Marketo i de Google Ads:

- Google Ads: la nova versió del connector d'exportació de Google Ads simplifica l'experiència d'autenticació i ara us permet crear públics de Google Ads automàticament. 
- Marketo: La nova versió del connector d'exportació de Marketo proporciona suport per a l'identificador de Marketo, cosa que us permet evitar la duplicació de dades, actualitzar els registres existents i crear nous registres a Marketo. 

## <a name="february-2022-updates"></a>Actualitzacions de febrer del 2022

Les actualitzacions del febrer de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="general-availability-for-prediction-models"></a>Disponibilitat general per a models predicció

Els models de predicció pròpiament dits, com ara **el percentatge** de subscripció, **la quantitat transaccional** i **el valor de la vida útil del client (CLV),** estan generalment disponibles com a part del Customer Insights. 

Per obtenir més informació, vegeu [Informació general](predictions-overview.md) de les prediccions.

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nou font de dades: Integració amb Azure Synapse Analytics (Preview)

Azure Synapse Analytics és un servei d'anàlisi empresarial que accelera el temps per obtenir informació sobre magatzems de dades i sistemes de big data.

Les organitzacions que ja les utilitzen Azure Synapse Analytics poden ingerir aquestes dades al Customer Insights. 

Per obtenir més informació, vegeu [Connectar un Azure Synapse font de dades (Visualització prèvia).](connect-synapse.md)

### <a name="liveramp-enrichment-preview"></a>Enriquiment LiveRamp (Preview)

LiveRamp proporciona resolució d'identitat i consolidació de dades de clients. Podeu assignar els identificadors personals de les dades dels vostres clients al gràfic d'identitat d'AbiliTec i rebre els identificadors d'AbiliTec. A continuació, podeu utilitzar aquests identificadors per a una millor unificació de les dades dels vostres clients.

Per obtenir més informació, vegeu [Enriquir perfils de clients amb dades d'identitat del LiveRamp (visualització prèvia)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Enriquiment per a fonts de dades (Preview)

Utilitzeu dades de fonts com Microsoft i altres socis per enriquir les dades dels vostres clients abans de la unificació de dades. Font de dades enriquiments ajuden a produir una major integritat i qualitat de les dades que poden ajudar a obtenir millors resultats un cop unifiqueu les dades.

Per obtenir més informació, vegeu [Enriquiment per a les fonts de dades (Visualització prèvia).](data-sources-enrichment.md)

### <a name="change-owner-of-environment"></a>Canvia el propietari de l'entorn

Tot i que diversos usuaris poden tenir permisos d'administrador al Customer Insights, només un usuari és el propietari d'un entorn. Una experiència millorada us permet canviar els propietaris d'un entorn i reclamar-ne la propietat si un antic propietari ha abandonat l'organització. 

Per obtenir més informació, vegeu [Canvi del propietari d'un entorn](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>El procés de preparació de dades enumera la raó de corrupció dels registres danyats

La preparació de dades mostra ara el motiu de la corrupció per a tots els camps amb dades danyades. La informació es proporciona a nivell de registre individual per facilitar-ne la identificació. 

Per obtenir més informació, vegeu [Fonts de dades malmeses](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Final de la previsualització per a les característiques dels informes de la capacitat d'estadístiques d'interacció

La Dynamics 365 Customer Insights previsualització de la capacitat d'informació d'interacció va finalitzar el 15 de febrer de 2022.  
Aquest canvi significa que l'experiència de prova del Customer Insights ja no inclou la possibilitat de crear embuts de conversió ni cap altra funcionalitat d'informes.

Us convidem a explorar i avaluar moltes altres característiques del Customer Insights [, la plataforma de](https://dynamics.microsoft.com/ai/customer-insights/) dades de clients de Microsoft (CDP).    
 
Durant un període de transició, els participants de visualització prèvia existents encara tenen accés a algunes capacitats i funcionalitats de visualització prèvia:

- Obtén el codi per instrumentar un lloc web o una aplicació mòbil 
- Consultar esdeveniments i propietats d'esdeveniments 
- Millorar els perfils unificats amb esdeveniments ingerits i refinats per beneficiar-se de tot el valor de les dades dels seus clients
  
Durant el període de transició, els esdeveniments capturats encara es transmeten al llac de dades connectat. Un cop desactivada aquesta funcionalitat, l'ús compartit de dades s'aturarà i no s'enviaran esdeveniments nous a l'emmagatzematge connectat.
Poseu-vos en contacte directament amb l'equip del compte Microsoft si teniu preguntes sobre el final de la visualització prèvia de capacitats. L'equip del compte us mantindrà al dia en els propers llançaments. 

## <a name="january-2022-updates"></a>Actualitzacions de gener de 2022

Les actualitzacions del gener de 2022 inclouen noves funcions, actualitzacions de rendiment i correccions d'errors.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Anàlisi de sentiment dels comentaris dels vostres clients

El Customer Insights proporciona una nova característica basada en IA per sintetitzar el sentiment dels clients i identificar aspectes empresarials específics com a oportunitats de millores específiques. En analitzar els comentaris escrits dels vostres clients, podeu obtenir informació precisa a baix cost. Anàlisi de sentiments impulsada per models de processament del llenguatge natural (PNL) que generen dues estadístiques derivades per a cada identificador de client. Una puntuació de sentiment (de –5 a 5) i una llista d'aspectes empresarials aplicables. 

Per obtenir més informació, vegeu [Analitzar el sentiment als comentaris dels clients (visualització prèvia)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]