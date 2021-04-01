---
title: Característiques noves i previstes
description: Informació sobre les noves característiques, millores i correccions d'errors.
ms.date: 03/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 96c0b871eeaaf0976e5c718f37f883f4410977dc
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598419"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novetats de la capacitat de conclusions del públic del Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Estem molt contents d'anunciar les nostres actualitzacions més recents. En aquest article es resumeixen les característiques de versió preliminar pública, millores de disponibilitat general i actualitzacions de característiques. Per veure els plans de característiques a llarg termini, doneu una ullada als [plans de llançament del Dynamics 365 i el Power Platform](/dynamics365/release-plans/).

També podeu veure el següent vídeo per obtenir més informació sobre les capacitats planificades durant els darrers sis mesos.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Implementarem les actualitzacions per regió. Per tant, algunes regions poden veure les característiques abans que altres. Si no s'especifica de manera diferent, no cal que feu cap acció i actualitzarem l'aplicació automàticament sense temps d'inactivitat.

> [!TIP]
> Per enviar i votar peticions de característiques i suggeriments de productes, aneu al [Portal d'idees de l'aplicació del Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="february-2021-updates"></a>Actualitzacions de febrer del 2021

Les actualitzacions de febrer del 2021 inclouen diverses característiques, actualitzacions de rendiment i correccions d'errors.

#### <a name="extensibility"></a>Extensibilitat

- **Exporta segments a AdRoll**

  Hem ampliat les nostres destinacions d'exportació per incloure-hi AdRoll. Ara podeu exportar segments del Customer Insights als públics d'AdRoll i utilitzar-los com a base per a la publicitat. Per obtenir més informació, vegeu [Connector per a AdRoll](export-adroll.md).

#### <a name="segments"></a>Segments
 
- **Duplicar un segment**
  
  Per crear un segment nou basat en un d'existent, ara podeu duplicar un segment i editar el segment duplicat per refinar-lo encara més. 

- **Afegir atributs addicionals a un segment**

  Ara podeu incloure atributs a la sortida del segment, encara que aquests atributs no formin part del perfil de client. Per exemple, podeu incloure els identificadors de subscripció en un segment tot i que formi part de l'entitat de subscripció que té una relació M:1 amb l'entitat de client. Sempre que l'atribut pertanyi a una entitat relacionada amb l'entitat de client, podreu incloure-hi aquests atributs.  

#### <a name="predictions"></a>Prediccions

- **Crear recomanacions de productes predictives**

  Comprendre què estan interessats a comprar els clients és un dels primers passos que calen per millorar els ingressos de l'empresa i aconseguir fidelitzar els clients mitjançant la personalització i la interacció. Proporcionar recomanacions per a productes que no s'ajusten als interessos del client pot crear una sensació de desconnexió entre el client i la vostra empresa i, finalment, limitar els ingressos potencials globals i l'experiència d'un client. 

  Amb les vostres pròpies dades, ara podeu crear prediccions per als productes que els vostres clients podrien comprar més endavant. Per obtenir més informació, vegeu [Predicció de recomanacions de productes](predict-product-recommendation.md).

#### <a name="system-administration"></a>Administració del sistema

- **La còpia d'entorn admet més tipus de fonts de dades**

  Els administradors poden copiar configuracions d'entorn a un entorn nou de la mateixa organització. Aquesta característica amplia la funcionalitat de l'entorn de còpia per als casos en què s'utilitzen fonts de dades basades en un llac de dades del Common Data Service o una carpeta del Model de dades comú.

## <a name="january-2021-updates"></a>Actualitzacions de gener de 2021

Les actualitzacions de gener del 2021 inclouen diverses característiques, actualitzacions de rendiment i correccions d'errors.

#### <a name="extensibility"></a>Extensibilitat

- **Funcionalitat ampliada i rendiment millorat per a l'exportació de SFTP** Ara podeu exportar totes les entitats de sortida del Customer Insights a un amfitrió SFTP. Anteriorment, l'exportació es limitava a les entitats de segment. A més, el rendiment de l'exportació SFTP permet més volum de dades en menys temps, en funció del rendiment de l'amfitrió SFTP.    
  Per obtenir més informació, vegeu [Connector per a SFTP (versió preliminar)](export-sftp.md).  

#### <a name="segments"></a>Segments

- **Segments suggerits basats en aprenentatge automàtic per millorar les mètriques** Hi ha una nova manera de descobrir i crear segments. El sistema utilitza un model d'IA per suggerir segments que poden ajudar a millorar un KPI (mesura) que ja seguiu. Es mostra l'extensió de la influència dels atributs que seleccioneu en una mesura o en un altre atribut principal. Aquesta informació ajuda a trobar segments potencials que presenten oportunitats.    
  Per obtenir més informació, vegeu [Segments suggerits (versió preliminar)](suggested-segments.md).

#### <a name="data-unification"></a>Unificació de dades

- **Experiència de coincidència millorada** A l'àrea d'unificació de dades, l'experiència de coincidència s'ha actualitzat. Permet configurar i visualitzar les regles de coincidència, incloent-hi estadístiques detallades per explicar encara més el funcionament de la coincidència. Hi ha opcions per inhabilitar una regla de coincidència per tal que ja no estigui activa conservant la configuració, arrossegar i deixar anar regles de coincidència, etc.
  Per obtenir-ne més informació, consulteu [Coincidència d'entitats](match-entities.md).

- **La sortida de deduplicació del procés de coincidència està disponible com a entitat** La sortida del procés de desduplicació del procés de coincidència s'escriu ara en una entitat independent per analitzar-la encara més. Aquesta entitat consta dels camps utilitzats en el procés de deduplicació i el registre guanyador i els registres alternatius corresponents que es fusionen amb el registre guanyador.
  Per obtenir més informació, vegeu [Sortida de la desduplicació com a entitat](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administració del sistema

- **Compartiu fàcilment dades amb el Microsoft Dataverse** Ara podeu compartir la sortida del Customer Insights amb les aplicacions del Microsoft Dataverse que utilitzen el Microsoft Dataverse Managed Data Lake. Quan associeu un entorn del Dataverse amb el Customer Insights, teniu l'opció d'habilitar l'ús compartit de dades.
  Per obtenir més informació, vegeu [Administrar entorns](manage-environments.md).


## <a name="december-2020-updates"></a>Actualitzacions de desembre de 2020

Les actualitzacions de desembre de 2020 inclouen diverses característiques, millores del rendiment i correccions d'errors.

### <a name="new-and-updated-features-in-december-2020"></a>Característiques noves i actualitzades de desembre de 2020

#### <a name="data-enrichment"></a>Enriquiment de dades

- **Millores en l'enriquiment d'afinitat de marca i interès**
  
  Hem simplificat les nostres puntuacions d'afinitat per fer-les més fàcils d'entendre i utilitzar. Ara podeu identificar ràpidament els clients en funció de l'afinitat que tenen per a una marca o un interès determinats.

  A més, hem afegit noves opcions de configuració per controlar millor com voleu que els vostres perfils de client s'enriqueixin. 

  Per obtenir més informació, vegeu [Enriquir els perfils de clients amb afinitats de marca i interès](enrichment-microsoft-graph.md).

- **Controleu quins perfils s'han d'enriquir**

  Ara podeu enriquir només un subconjunt dels perfils de client amb l'opció de seleccionar una entitat de segment en comptes de l'entitat de client per defecte. Creeu un segment amb els perfils de client que voleu enriquir i seleccioneu-lo a la configuració d'enriquiment del conjunt de dades de clients.
  Aquesta característica només està disponible per als enriquiments proporcionats per Experian i HERE Technologies. Habilitarem aquesta característica per a més enriquiments aviat.

  Per obtenir més informació, vegeu [Enriquir els perfils de clients amb dades demogràfiques d'Experian](enrichment-experian.md) o [Enriquiment de perfils de clients amb HERE Technologies](enrichment-here.md).

#### <a name="extensibility"></a>Extensibilitat

- **Activar els segments mitjançant Autopilot**

  Exporteu segments a Autopilot i utilitzeu-los per a finalitats de màrqueting. Per obtenir més informació, vegeu [Connector per a Autopilot (versió preliminar)](export-autopilot.md).

- **Activar els segments mitjançant SendGrid**

  Exporteu segments a SendGrid i utilitzeu-los per a finalitats de màrqueting. Per obtenir més informació, vegeu [Connector per a SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Administració del sistema

- **Experiència d'administració d'entorns actualitzada**
  
  Ara podeu crear, editar, suprimir i restablir entorns directament des del selector d'entorn a la capçalera de l'aplicació. 
  
  A més, l'entorn que utilitzeu s'ancorarà a la part superior de la finestra de l'entorn per tal que no hàgiu de cercar-lo més.

  Per obtenir més informació, vegeu [Administrar entorns](manage-environments.md).

## <a name="november-2020-updates"></a>Actualitzacions de novembre de 2020

Les actualitzacions de novembre de 2020 inclouen diverses característiques, millores del rendiment i correccions d'errors.

### <a name="new-and-updated-features-in-november-2020"></a>Característiques noves i actualitzades de novembre de 2020

#### <a name="data-enrichment"></a>Enriquiment de dades

- **Incorporeu les vostres pròpies dades d'enriquiment mitjançant la importació personalitzada del protocol de transferència segura de fitxers (SFTP)**
  
  La importació personalitzada d'SFTP us permet importar dades d'enriquiment que no han de passar pel procés d'unificació de dades. Més informació sobre la importació personalitzada d'SFTP.

  Per obtenir més informació, vegeu [Enriquir els perfils de client amb dades personalitzades (versió preliminar)](enrichment-SFTP-custom-import.md).
 
- **Enriquir les dades dels vostres clients amb dades d'ubicació de HERE Technologies**

  Amb els serveis d'enriquiment de dades de HERE Technologies, podeu crear una localització més precisa dels clients amb la normalització d'adreces o l'extracció de la latitud i la longitud, entre d'altres. Apreneu sobre l'enriquiment amb HERE Technologies.

  Per obtenir més informació, vegeu [Enriquiment de perfils de client amb HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Unificació de dades

- **Flexibilitat per habilitar la perfilació de dades en entitats i camps seleccionats del compte d'emmagatzematge**

  Podeu indicar quines entitats i camps de dades d'una carpeta del Common Data Model del compte d'emmagatzematge de l'Azure Data Lake voleu habilitar per a la perfilació de dades com a part del procés d'ingestió de dades.

  Per obtenir més informació, vegeu [Connectar-se a una carpeta del Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Extensibilitat

- **Activar els segments mitjançant el Google Ads**

  Exporteu els segments a llistes de públics de Google Ads i utilitzeu aquestes llistes per anunciar-vos a la Cerca de Google, la Xarxa de Display de Google, YouTube i Gmail. Més informació sobre l'activació dels segments a través de Google Ads.

  Per obtenir més informació, vegeu [Connector per a Google Ads](export-google-ads.md).

- **Activar els segments mitjançant Marketo**

  Exporteu segments als públics de Marketo i utilitzeu aquests públics per a l'automatització del màrqueting. Més informació sobre l'activació dels segments a través de Marketo. 

  Per obtenir més informació, vegeu [Connector per a Marketo](export-marketo.md).

- **Activar els segments mitjançant DotDigital**

  Exporteu segments a DotDigital i utilitzeu-los per a finalitats de màrqueting. Més informació sobre l'activació dels segments a través de DotDigital. 

  Per obtenir més informació, vegeu [Connector per a DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Prediccions

- **Predir la rotació de transaccions**

  La característica de predicció de rotació de transaccions us permet, sense l'ajuda d'un científic de dades, predir la probabilitat que un client deixi d'adquirir els vostres productes o serveis.  Amb la puntuació de la predicció, podeu combinar altres dades sobre els clients, com ara el valor del client, per crear segments d'alt risc de rotació o clients d'alt valor. Utilitzeu aquest segment per adreçar-vos directament als clients mitjançant activitats de màrqueting, servei d'atenció al client i altres escenaris per reduir el risc de rotació.
 
  Configureu la definició de rotació com una finestra basada en el temps específica de la vostra empresa i definiu quan es consideraran els clients en rotació. Per exemple, una botiga de queviures pot considerar un client en rotació si no ha comprat res en els darrers 30 dies.
 
  A mesura que continueu creant la predicció, se us guiarà pel que fa a les dades necessàries i podreu assignar dades sobre el vostre negoci als camps necessaris per predir la rotació dels vostres clients. També podeu definir una planificació per tornar a entrenar el model a partir de la nova informació del sistema per adaptar-lo a les circumstàncies canviants del negoci.
 
  Per obtenir més informació, vegeu [Predicció de rotació de transaccions (versió preliminar)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administració del sistema

- **Restablir l’entorn**

  Restabliu-ho tot en un entorn d'una instància seleccionada per començar des de zero.

  Per obtenir més informació, vegeu [Restablir un entorn existent](manage-environments.md#reset-an-existing-environment).


- **Connectar-vos al compte d'emmagatzematge de l'Azure Data Lake mitjançant una entitat de servei**

  Escriviu la sortida de les dades en el vostre compte d'emmagatzematge i llegiu-ne les dades mitjançant una entitat de servei de l'Azure. Les connexions del compte d'emmagatzematge existents poden continuar utilitzant la clau del compte. També ofereixen una opció d'actualització per utilitzar l'entitat de servei en endavant. Les connexions noves es basaran en el mètode d'autenticació de l'entitat de servei corresponent al vostre compte d'emmagatzematge.

  Per obtenir més informació, vegeu [Connectar-se a un compte Gen2 de l'Azure Data Lake Storage amb una entitat de servei de l'Azure per a les conclusions del públic](connect-service-principal.md).

## <a name="october-2020-updates"></a>Actualitzacions d'octubre de 2020

Les actualitzacions d'octubre de 2020 inclouen diverses característiques, millores del rendiment i correccions d'errors.

### <a name="new-and-updated-features-in-october-2020"></a>Característiques noves i actualitzades d'octubre de 2020

#### <a name="extensibility"></a>Extensibilitat

- **Exportar al Mailchimp**

Exporteu segments a les llistes de públics existents del Mailchimp per proporcionar una experiència de correu electrònic personalitzada als vostres clients.

Per obtenir més informació, vegeu [Connector per a Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Enriquiment de dades

- **Desduplicar els registres d'origen d'una entitat de coincidència**

Especifiqueu les regles de desduplicació d'entitats que s'utilitzaran al procés de coincidència per tal d'identificar registres duplicats. Combineu-los en un únic registre i enllaceu tots els registres d'origen amb aquest registre combinat. Tot seguit, el registre desduplicat s'utilitzarà al procés de coincidència entre entitats.

Per obtenir més informació, vegeu [Definir la desduplicació en una entitat de coincidència](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Administració del sistema

- **Orquestració: nova opció d'actualització a la combinació**

Fins avui, quan executàveu el procés de combinació, el sistema executava tots els processos derivats que depenen de la combinació i els processos posteriors. Ara podeu comprovar el resultat del procés de combinació (l'entitat del client unificada) abans d'utilitzar-lo en el processament derivat, com ara segments o mesures.
A la pàgina de combinació, ara podeu triar entre executar només el pas de combinació i executar només aquest procés. Per actualitzar també tots els processos derivats, podeu triar executar els processos de combinació i derivats. 

## <a name="september-2020-updates"></a>Actualitzacions de setembre de 2020

Les actualitzacions de setembre de 2020 inclouen diverses característiques, millores de rendiment i correccions d'errors.

### <a name="new-and-updated-features-in-september-2020"></a>Característiques noves i actualitzades al setembre de 2020

#### <a name="activities"></a>Activitats

- **Predicció intel·ligent de la semàntica d'atributs**

Aquesta nova característica prediu els tipus semàntics dels atributs d'entrada que s'envien al procés d'unificació de dades. Utilitza models d'aprenentatge automàtic que milloren la precisió i estalvien temps.

#### <a name="enrichments"></a>Enriquiments

- **Enriquiment amb dades demogràfiques d'Experian**

L'enriquiment demogràfic d'Experian està ara disponible en versió preliminar. Experian és un líder mundial en informes de consum i cedit empresarial i serveis de màrqueting. Amb els [serveis d'enriquiment de dades d'Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), podeu obtenir una comprensió més profunda dels clients enriquint els perfils dels clients amb dades demogràfiques com la mida de la llar, els ingressos i més.

Per utilitzar aquesta funció, heu de tenir una subscripció d'Experian activa.

Per a més informació, vegeu [Enriquir perfils de clients amb dades demogràfiques d'Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Administració del sistema

- **Subfinestra Detalls de la tasca**

La subfinestra de detalls de la tasca us permet veure els detalls sobre les tasques que executa el sistema. És una manera pràctica d'identificar problemes amb la configuració i trobar solucions.
Reviseu els missatges d'error per veure com abordar problemes potencials.
 
- **Informació de processament afegida a més pàgines**

Aquesta millora afegeix informació sobre l'estat de les vostres entitats a la pàgina **Entitats** i **Clients**.
 
A més, podeu trobar detalls sobre el progrés dels processos, juntament amb els detalls de la tasca, en ambdues pàgines.

- **Millores a la pàgina d'estat del sistema**

Hem millorat l'estructura de la taula de detalls d'estat a **Sistema** > **Estat** en revisar les exportacions de dades.
 
A més, els errors de la columna **Detalls** són ara més detallats i fàcils d'aplicar. 
 
- **La cancel·lació retorna la tasca a l'estat anterior**

Quan cancel·leu una tasca, per exemple, en el procés de coincidència, tornarà al seu últim estat. Per exemple, si el procés de coincidència es va completar ahir i el cancel·leu avui, tornarà a l'estat correcte d'ahir.


## <a name="august-2020-updates"></a>Actualitzacions d'agost de 2020

Les actualitzacions d'agost de 2020 inclouen diverses característiques, millores de rendiment i correccions d'errors.

### <a name="new-and-updated-features-in-august-2020"></a>Característiques noves i actualitzades a l'agost de 2020

#### <a name="data-unification"></a>Unificació de dades

- **Experiència millorada per a la fase d'assignació durant la unificació de dades**

  L'experiència a la fase d'assignació en el procés d'unificació de dades permet seleccionar entitats, atributs i definir la semàntica d'una manera més eficient.

  Els canvis inclouen:
  
  - menys interaccions necessàries per afegir entitats i camps
  - funcionalitats de cerca millorades a la pàgina d'assignació
  - identificació visual i fàcil del tipus de camp suggerit

#### <a name="enrichment"></a>Enriquiment

- **Enriquiment d'afinitats d'interessos disponible a més mercats**

  Ampliem la disponibilitat de l'enriquiment d'afinitats d'interès més enllà dels Estats Units a cinc mercats més: Canadà, Austràlia, Regne Unit, França i Alemanya. Amb aquesta extensió, podeu enriquir les dades dels clients amb més interessos aplicables a aquests mercats. També enriquim els perfils de client que es troben en aquests mercats mitjançant les dades de propietaris locals del Microsoft Graph.
  Per obtenir més informació, vegeu [Enriquir els perfils de clients amb afinitats de marca i interès](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Actualitzacions de juliol del 2020

Les actualitzacions de juliol del 2020 inclouen diverses característiques, actualitzacions de rendiment i correccions d'errors.

### <a name="new-and-updated-features-in-july-2020"></a>Característiques noves i actualitzades de juliol del 2020

#### <a name="extensibility"></a>Capacitat d'ampliació

- **Disparador del Power Automate per al procés d'unificació finalitzat**

  Hem ampliat els nostres disparadors per al Power Automate i us permetem crear una notificació o una acció quan s'hagi completat l'actualització del procés d'unificació (assignació, coincidència i combinació).    
  Per obtenir més informació, vegeu [Connector del Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Enriquiment

- **Enriquiment d'afinitats de marques disponible a més mercats**

  Ampliem la disponibilitat de l'enriquiment d'afinitats de marca més enllà dels Estats Units a cinc mercats més: Canadà, Austràlia, Regne Unit, França i Alemanya. Amb aquesta ampliació, podeu enriquir les dades dels clients amb marques locals en aquests mercats. També enriquim els perfils de client que es troben en aquests mercats mitjançant les dades de propietaris locals del Microsoft Graph.
  Per obtenir més informació, vegeu [Enriquir els perfils de clients amb afinitats de marca i interès](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Actualitzacions de juny del 2020

Les actualitzacions de juny del 2020 inclouen diverses característiques, actualitzacions de rendiment i correccions d'errors.

### <a name="new-and-updated-features-in-june-2020"></a>Característiques noves i actualitzades de juny del 2020

#### <a name="enrichment"></a>Enriquiment

- **Enriquiment amb dades de l'empresa del Leadspace**
  
  Definiu els camps de perfils de client unificats que s'utilitzen per cercar dades d'empreses relacionades des del Leadspace. Després d'executar el procés d'enriquiment, els perfils de B2B s'enriqueixen amb més atributs, com ara la mida de l'empresa, la ubicació, el sector, etc.    
  Aquesta col·laboració us permet millorar la qualitat de les dades amb l'entrada de serveis de tercers. Per utilitzar aquest enriquiment, necessitareu una llicència del Leadspace per accedir a les dades de l'empresa B2B. El sistema utilitzarà aquesta llicència per mantenir les dades constantment enriquides.    
  Per obtenir més informació, vegeu [Enriquiment de perfils d'empresa amb el Leadspace](enrichment-leadspace.md).

- **Pàgina del centre d'enriquiment**

  Tots els enriquiments de dades disponibles de proveïdors d'enriquiment propis o de tercers es configuren al mateix lloc. Configurar l'enriquiment de dades és una experiència sense problemes que es gestiona des d'un lloc comú.    
  Per obtenir més informació, vegeu [Enriquiment per a perfils de client](enrichment-hub.md).

- **Enriquiment d'afinitat de marca i interès independents**

  Les afinitats de marca i interès estan disponibles actualment com a dos enriquiments independents. Els enriquiment independents us donen la flexibilitat de configurar-los i administrar-los individualment, en funció dels requisits o les necessitats de l'empresa.    
  Per obtenir més informació, vegeu [Enriquir els perfils de clients amb afinitats de marca i interès](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Capacitat d'ampliació

- **URL on es pot fer clic per a activitats unificades al complement de la targeta del client del Dynamics 365**

  Les activitats unificades del complement de targeta de client mostren ara adreces URL on es pot fer clic si aquestes s'han definit durant la configuració de les activitats.    
  Per obtenir més informació, vegeu [Complement de targeta del client](customer-card-add-in.md).

- **Afinitats de marca i interès disponibles al complement de la targeta del client del Dynamics 365**

  Un control nou del complement de la targeta del client del Dynamics 365 us permet mostrar els enriquiments de marca i interès dels vostres contactes a les aplicacions d'interacció amb els clients al Dynamics 365.    
  Per obtenir més informació, vegeu [Complement de targeta del client](customer-card-add-in.md).

- **Més disparadors del Power Automate**

  Hem ampliat els nostres disparadors per al Power Automate i hem afegit els següents:
  - Rebre una notificació o dur a terme una acció quan es completa una actualització completa automatitzada (fonts de dades, unificació, segments, mesures, exportacions)
  - Definiu un llindar per a una mesura empresarial. Per exemple, podeu crear una notificació que s'enviï quan es passi el llindar definit. A més, el disparador porta informació que us permet crear fluxos de treball més complexos al Power Automate.    
  Per obtenir més informació, vegeu [Connector del Power Automate](export-power-automate.md)

- **Exporta al Facebook Ads Manager**
  
  Aquesta capacitat us permet exportar segments a l'Administrador d'anuncis del Facebook. Els segments s'exporten com a públics personalitzats per a l'ús de perfils de client unificats a les campanyes i anuncis de màrqueting del Facebook. Les audiències personalitzades també es poden utilitzar per crear campanyes a Instagram amb el Facebook Ads Manager.    
  Per obtenir més informació, vegeu [Connector per al Facebook Ads Manager](export-facebook.md).

#### <a name="predictions"></a>Prediccions

- **Predicció de rotació de la subscripció**

  Seguiu una experiència guiada per crear una predicció de rotació en àrees de subscripció com ara serveis al núvol, subscripcions de clients i altres sectors. 

  La característica de predicció de rotació de la subscripció us permet predir la probabilitat que un client deixi d'utilitzar els productes o serveis basats en subscripcions sense interactuar amb un científic de dades. Amb la puntuació de predicció, podeu combinar més informació sobre els clients per crear segments d'alt risc de rotació. Amb l'ajuda d'aquest segment, podreu adreçar-vos directament als clients en el màrqueting, el servei d'atenció al client i altres escenaris per tal de reduir el risc de rotació de determinats clients i millorar així els ingressos i reduir els costos.

  Dins de l'experiència, podeu configurar la definició de rotació com un període de temps específic per a l'empresa. Per exemple, un negoci de transmissió de vídeos que té un procés de subscripció mensual pot plantejar-se la rotació d'un client 15 dies després del venciment de la subscripció.

  A mesura que continueu per la predicció, us guiarem per les dades que es necessiten i podreu assignar dades sobre la vostra empresa als camps necessaris per predir la rotació per als vostres clients. A mesura que canvia la informació de l'empresa, també podeu definir una planificació per tornar a entrenar la predicció quan hi hagi informació nova al sistema per adaptar-la a les circumstàncies empresarials canviants.    
  Per obtenir més informació, vegeu [Predicció de rotació de la subscripció (versió preliminar)](predict-subscription-churn.md).

#### <a name="segments"></a>Segments

- **Cerca clients similars**
  
  Cerqueu clients semblants a la base de clients mitjançant la intel·ligència artificial. Un model d'aprenentatge automàtic de classificació binària assigna una puntuació de similitud als clients del segment ampliat. La puntuació es basa en la similitud amb els clients del segment d'origen. Segons la puntuació de similitud, els perfils dels clients s'afegeixen a un segment acabat de crear.

  De vegades conegut com a modelatge de similitud al màrqueting digital, utilitza un model d'iA per ajudar a trobar clients que siguin semblants a un altre segment dels clients prenent més atributs. No només us permet triar els atributs, sinó que també us permet especificar el nombre màxim de clients que haurien d'estar en aquest nou segment. A continuació, el model d'IA calcula les puntuacions de similitud per a cada client en funció dels atributs seleccionats i trobarà els clients amb la puntuació de similitud mitjana més alta. El segment resultant inclourà els clients que tenen un aspecte semblant al client del segment original.    
  Per obtenir més informació, vegeu [Clients semblants](find-similar-customer-segments.md).

- **Superposició de segments i diferenciadors**

  La superposició de segments us permet veure quants i quins són comuns entre dos o més segments. Per exemple, la superposició d'un segment de clients que gasten molts diners amb un segment de clients amb nivells alts de satisfacció o la superposició d'un segment de clients de rotació amb un segment de clients amb nivells baixos de satisfacció. A més, podeu analitzar com canvia la superposició segons un atribut addicional que vulgueu.

  Els diferenciadors de segments revelen què diferencia un segment de la resta de clients o d'un altre segment. Tot el que heu de fer és identificar un segment i el sistema identificarà les mesures i els atributs del perfil que distingeixen el segment al formulari d'una llista de diferenciadors classificada: des dels diferenciadors més importants als menys importants.    
  Per obtenir més informació, vegeu [Informació detallada de segments (versió preliminar)](segment-insights.md).

- **Cicle de vida d'un segment**
  
  Definiu una planificació per activar o desactivar un segment.    
  Per obtenir més informació, vegeu [Habilitar segments existents](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Actualitzacions de maig de 2020

Les actualitzacions de maig de 2020 inclouen diverses característiques, actualitzacions de rendiment i correccions d'errors.

### <a name="new-and-updated-features-in-may-2020"></a>Característiques noves i actualitzades al maig de 2020

#### <a name="data-ingestion"></a>Ingestió de dades

- **Ingestió de dades en temps real: visualitzacions d'historial**

  Quan s'utilitza la nostra API per ingerir actualitzacions en temps real, podeu veure fins a 30 dies d'historial agregat per a aquestes actualitzacions. Teniu accés a agregacions de totes les trucades de l'API correctes o no, incloent-hi el seu resultat, el sistema d'origen i altres metadades útils.    
  Per obtenir més informació, vegeu [Ingestió de dades en temps real](real-time-data-ingestion.md).

- **Ingestió de dades en temps real: actualitzacions de perfil**

  Aquesta extensió de l'ingestió de dades en temps real us permet veure, en qüestió de segons, els canvis en els camps específics d'un perfil d'usuari.    
  A banda de la funcionalitat en temps real per a les activitats, el sistema admet actualitzacions de latència baixa per als camps de perfil. Les actualitzacions en temps real per als camps de perfil tenen una hora de venciment i, per tant, no són un substitut de les actualitzacions planificades.    
  Per obtenir més informació, vegeu [Ingestió de dades en temps real](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Capacitat d'ampliació

- **Cronologia actualitzada i paginació sobre el complement de la targeta del client**

  La cronologia de la solució de complement de targeta de client coincideix amb la cronologia de l'activitat. La paginació de la cronologia ha millorat, que mostra fins a 50 activitats alhora. També permet carregar més activitats a la cronologia.    
  Per obtenir més informació, vegeu [Complement de targeta del client](customer-card-add-in.md).

- **Disparador del Power Automate de canvis de segment**

  Els disparadors del Power Automate defineixen des de què podeu generar un flux. El disparador acabat d'afegir us permet definir un llindar per a un segment. Per exemple, podeu crear una notificació que s'enviï quan es passi el llindar definit.    
  Per obtenir més informació, vegeu [Connector del Power Automate](export-power-automate.md).

- **Comptabilitat amb diversos inquilins per a models personalitzats**

  Configureu fluxos de treball per a models personalitzats amb un servei web d'un inquilí de l'aprenentatge automàtic de l'Azure diferent. Podreu iniciar la sessió a l'inquilí de l'aprenentatge automàtic de l'Azure quan creeu un flux de treball nou per a models personalitzats. Aquesta capacitat és una addició a la capacitat existent d'integrar el vostre propi servei web personalitzat de l'aprenentatge automàtic de l'Azure.    
  Per obtenir més informació, vegeu [Models d'aprenentatge automàtic personalitzats](custom-models.md).

#### <a name="segments"></a>Segments

- **Automatització de camins d'entitat**

  En crear un segment, els usuaris han de definir el camí de l'entitat. Aquesta capacitat fa un primer pas per automatitzar la definició de camí d'entitat per tal que pugueu centrar-vos en els criteris de segmentació que tingueu pensats.    
  Si l'entitat per la qual voleu segmentar els clients està directament relacionada amb l'entitat del client unificada, ja no haureu de definir el camí d'entitat. No obstant, si hi ha més d'un camí d'entitat possible, encara l'heu de definir manualment.

- **Accions en diversos segments**
  
  Els usuaris poden seleccionar diversos segments i dur-hi a terme accions, com ara actualitzar els segments, amb un sol clic.    

- **Actualitzar els segments**

  Els usuaris poden actualitzar un sol segment o seleccionar només els segments que volen actualitzar.    

  
- **Millores per a segments compostos**

  Els usuaris poden crear, editar i suprimir segments que es basen en altres segments. Per exemple, un segment basat en un altre segment que es basava en un tercer segment.    

- **Pàgina de llista de segments**

  El nou disseny de la pàgina segments utilitza un format de llista que us permet veure més segments a la vegada. S'afegeix un camp de cerca per cercar segments ràpidament. Ara, els usuaris poden aplicar accions com la baixada o la supressió de diversos segments a la vegada. S'ha presentat una experiència de tendència nova per identificar ràpidament els canvis significatius als segments.    
  Per a més informació, vegeu [Crear i administrar segments](segments.md).

#### <a name="system-administration"></a>Administració del sistema

- **Customer Insights disponible al Microsoft Dynamics 365 Online Government**

  Amb més i més canals d'interaccions, les dades de ciutadans s'escampen per diversos sistemes, la qual cosa resulta en dades aïllades i una visió fragmentada de la informació sobre les interaccions dels ciutadans. Sense una visualització completa de les interaccions d'un ciutadà entre canals, és impossible que els governs es modernitzin a escala. Microsoft s'ha compromès a donar suport a les necessitats de tecnologia del govern per mantenir-se al dia amb les expectatives dels ciutadans per a una experiència coherent i sensible.    
  Amb la fase 1 de llançament de 2020, el Dynamics 365 Customer Insights estarà disponible per al núvol comunitari de l'administració pública (GCC), un entorn creat per satisfer les necessitats de major compliment dels organismes governamentals dels Estats Units. Els organismes adquireixen una visió unificada dels ciutadans i utilitzen IA preconstruïda per obtenir informació que millori les interaccions, capaciti els empleats i transformi les comunitats, alhora que redueixi la complexitat de TI i compleixi els estàndards de compliment i de seguretat dels Estats Units. El Dynamics 365 Government compleix els exigents requisits del Programa d'administració de risc i autorització federal dels EUA (FedRAMP), que permet als organismes federals dels Estats Units beneficiar-se de l'estalvi de costos i de la seguretat rigorosa del núvol de Microsoft.

## <a name="april-2020-updates"></a>Actualitzacions d'abril de 2020

Les actualitzacions d'abril de 2020 inclouen diverses característiques, actualitzacions de rendiment i correccions d'errors.

### <a name="new-and-updated-features-in-april-2020"></a>Característiques noves i actualitzades a l'abril de 2020

#### <a name="activities"></a>Activitats

- **Assignar l'entitat d'activitat al tipus d'activitat estàndard**
  
  La configuració i l'emmagatzematge de l'activitat es basen actualment en un disseny estàtic per visualitzar-los en una cronologia. El significat semàntic de les activitats, que té el potencial per a diversos casos d'ús de models d'IA, no s'utilitza del tot en aquest moment. Planegem fer més dinàmica la cronologia de l'activitat segons el tipus d'activitat i millorar la comprensió semàntica de les activitats. Aquesta característica té com a objectiu identificar el tipus d'activitat que s'ha definit en el Common Data Model per a qualsevol activitat ingerida.
  Per obtenir més informació, vegeu [Activitats del client](activities.md).

#### <a name="data-ingestion"></a>Ingestió de dades

- **Ingestió de dades en temps real: activitats**
  
  La ingestió de dades en temps real proporciona dades de manera immediata per al consum fins que la següent actualització planificada extreu aquestes dades de la font de dades.    
  Per obtenir més informació, vegeu [Ingestió de dades en temps real](real-time-data-ingestion.md).

- **Millores en la preparació de dades**
  
  Més informació sobre les dades ingerides en una entitat. Amb el resum de dades, podeu comprendre les característiques de qualitat de les dades que poden ajudar a emprendre l'acció adient.    
  Per obtenir més informació, vegeu [Explorar les dades d'entitat](entities.md#exploring-a-specific-entitys-data).

- **Ingerir dades analítiques del Dynamics 365 amb el Common Data Service**
  
  El Common Data Service està disponible com a mètode per crear fonts de dades. Els clients del Dynamics 365 existents poden ingerir entitats analítiques del Common Data Service al Customer Insights. Una sola font de dades pot utilitzar simultàniament el mateix llac administrat pel Common Data Service en un entorn del Customer Insights.    
  Per obtenir més informació, vegeu [Connectar-se a les dades d'un llac de dades administrat del Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Capacitat d'ampliació

- **Exportar a LiveRamp**

  Activeu les dades a LiveRamp® per connectar-vos amb més de 500 plataformes en ecosistemes digitals, socials i de TV. Utilitzeu les dades a LiveRamp per a dirigir, suprimir i personalitzar campanyes publicitàries.    
  Per obtenir més informació, vegeu [Connector de LiveRamp&reg;](export-liveramp.md).

- **Complement del Teams del Customer Insights**
  
  El bot proporciona la capacitat de cerca de perfils unificats de client. Es mostrarà una targeta amb fins a 15 camps del perfil de client resultant. Les coincidències múltiples retornen una llista de resultats on podeu seleccionar un perfil.    
  Per obtenir més informació, vegeu [Bot del Teams per al Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Mesures

- **Pàgina de llista de mesures**
  
  Le millores de la pàgina de mesures inclouen el suport de les accions en una única mesura i en diverses mesures a la vegada. A més, trobareu un camp de cerca per trobar i fer un seguiment de les mesures ràpidament.    
  Per a més informació, vegeu [Crear i administrar segments](segments.md).

- **Millores per a mesures compostes**
  
  Els usuaris poden crear, editar i suprimir mesures que es basen en altres mesures. Per exemple, una mesura basada en una altra mesura que es basava en una tercera mesura.

#### <a name="segments"></a>Segments

- **Un altre operador**
  
  L'operador In-set permet la segmentació per als clients mitjançant diversos valors de cadena possibles. Abans d'afegir-se a aquest operador, havíeu de construir aquests segments amb diverses condicions OR. L'operador In-set us permet fer-ho amb una única condició.    
  Per a més informació, vegeu [Crear i administrar segments](segments.md).

#### <a name="system-administration"></a>Administració del sistema

- **Copiar la configuració a un entorn nou**
  
  Copieu la configuració d'un entorn a un altre. Mentre creeu un entorn nou, podeu seleccionar un entorn existent del qual vulgueu copiar la configuració. Actualment admetem fonts de dades, unificació de dades, relacions, mesures i segments per copiar-los. No es copien les credencials ni les dades reals de la font de dades.    
  Per obtenir més informació, vegeu [Administrar entorns](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]