---
title: Característiques noves i previstes
description: Informació sobre les noves característiques, millores i correccions d'errors.
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: e501df8701493a1c5b83c4d06da3a73fd226165f
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673803"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novetats de la capacitat de conclusions del públic del Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Estem molt contents d'anunciar les nostres actualitzacions més recents. En aquest article es resumeixen les característiques de versió preliminar pública, millores de disponibilitat general i actualitzacions de característiques. Per veure els plans de característiques a llarg termini, doneu una ullada als [plans de llançament del Dynamics 365 i el Power Platform](/dynamics365/release-plans/).

Implementarem les actualitzacions per regió. Per tant, algunes regions poden veure les característiques abans que altres. Si no s'especifica de manera diferent, no cal que feu cap acció i actualitzarem l'aplicació automàticament sense temps d'inactivitat.

> [!TIP]
> Per enviar i votar peticions de característiques i suggeriments de productes, aneu al [Portal d'idees de l'aplicació del Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="september-2021-updates"></a>Actualitzacions de setembre de 2021

Les actualitzacions de setembre del 2021 inclouen noves característiques, actualitzacions de rendiment i correccions d'errors.

### <a name="activities"></a>Activitats

- **Millores de la cronologia de l'activitat** Hem ampliat els filtres de la cronologia d'activitats als perfils de client. A més, podeu utilitzar la nova subfinestra de filtre per filtrar per tipus d'activitat i per data. Les dates es poden filtrar amb diferents condicions. Per obtenir més informació, vegeu [Visualitzar les cronologies d'activitats als perfils de client](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relacions

- **Compatibilitat amb les relacions de diversos salts** Utilitzeu relacions de diversos salts quan configureu activitats i definiu relacions entre entitats. Les relacions de diversos salts utilitzen una entitat intermèdia per connectar dues entitats. Quan configureu una activitat, podeu utilitzar una relació de diversos salts per connectar l'entitat d'activitat a una entitat intermèdia i després a una entitat de client. Podeu combinar relacions de diversos salts amb relacions de diversos camins. Per obtenir més informació, vegeu [Relació de diversos salts](relationships.md#multi-hop-relationship).

- **Compatibilitat amb les relacions de diversos camins** Utilitzeu relacions de diversos camins quan configureu activitats i definiu relacions entre entitats. Les relacions de diversos camins relacionen una entitat d'origen amb més d'una entitat. Quan configureu una activitat, podeu utilitzar una relació de diversos camins per connectar l'entitat d'activitat a més d'una entitat de client. Podeu combinar relacions de diversos camins amb relacions de diversos salts. Per obtenir més informació, vegeu [Relació de diversos camins](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Actualitzacions d'agost de 2021

Les actualitzacions del juliol i l'agost del 2021 inclouen una nova característica, actualitzacions de rendiment i correccions d'errors.

### <a name="extensibility"></a>Extensibilitat

- **Exportar segments a Klaviyo** Hem ampliat les nostres [destinacions d'exportació per incloure Klaviyo](export-klaviyo.md). Ara podeu exportar segments per crear campanyes, fer contingut de màrqueting per correu electrònic i utilitzar grups específics de clients amb el Klaviyo. 


## <a name="june-2021-updates"></a>Actualitzacions de juny del 2021

Les actualitzacions de juny del 2021 inclouen diverses característiques, actualitzacions de rendiment i correccions d'errors.

### <a name="data-ingestion"></a>Ingestió de dades

- **Actualitzacions del progrés millorat d'unificació de dades** Ara podeu veure actualitzacions d'estat dinàmic més granulars i millorades als passos del [procés d'unificació de dades](data-unification.md). Aquesta característica us permet fer un seguiment del progrés detallat per entendre el flux del procés i actuar si algun pas necessita atenció.

### <a name="extensibility"></a>Extensibilitat

- **Exportar segments i altres dades a Salesforce Marketing Cloud** Hem ampliat les nostres destinacions d'exportació per incloure [Salesforce Marketing Cloud](export-salesforce.md). Ara podeu exportar segments i altres tipus de dades a Salesforce Marketing Cloud a través d'una exportació SFTP de marca. La importació de dades es pot automatitzar completament al Salesforce i es pot utilitzar per crear campanyes de màrqueting més efectives.  
 
- **Exportar segments a ActiveCampaign** Hem ampliat les nostres destinacions d'exportació per incloure [Active Campaign](export-active-campaign.md). Ara podeu exportar segments per generar campanyes, dirigir contingut de màrqueting per correu electrònic i treballar amb grups específics de l'ActiveCampaign.
 
- **Exportar segments a Sendinblue** Hem ampliat les nostres destinacions d'exportació per incloure [Sendinblue](export-sendinblue.md). Ara podeu exportar segments per generar campanyes, dirigir contingut de màrqueting per correu electrònic i treballar amb grups específics amb el Sendinblue.
 
### <a name="ux-updates"></a>Actualitzacions de l'experiència d'usuari 

- **Pàgina Clients nova i millorada i pàgina de detalls del perfil** Hem redissenyat la pàgina Clients i les pàgines de detalls del perfil per millorar l'experiència de l'usuari i un millor rendiment. Aquests canvis us permeten veure, ordenar, cercar i filtrar clients. Els filtres ara es representen a l'adreça URL per compartir els resultats de la cerca amb altres usuaris sense problemes. Els resultats de la cerca també es poden desar com a segments.    
  La pàgina de detalls dels perfils de client ara agrupa les dades en diverses subseccions, com ara dades demogràfiques, identificadors i altres atributs de perfil per millorar la llegibilitat. Altres seccions de la pàgina de detalls del perfil ara són més interactives. Per exemple, la secció d'activitats ara permet filtrar i ordenar.


## <a name="may-2021-updates"></a>Actualitzacions de maig de 2021

Les actualitzacions del maig de 2021 inclouen diverses característiques, actualitzacions de rendiment i correccions d'errors.

### <a name="data-ingestion"></a>Ingestió de dades

- **Visualitzeu o modifiqueu les metadades o la definició d'entitat quan adjunteu dades de l'Azure Data Lake Storage** Ara podeu visualitzar i editar les metadades o la definició d'entitat a l'auditori quan adjunteu dades d'una carpeta del Model de dades comú al vostre Azure Data Lake Storage. Aquesta capacitat proporciona comentaris en temps real, validació del model i comprovació d'errors. Permet editar tant model.json com manifest.json sense problemes.

### <a name="extensibility"></a>Extensibilitat

- **Exportacions de segments millorades, planificació personalitzada i duplicació** Ara podeu [veure totes les exportacions d'un segment concret](export-destinations.md#view-exports-and-export-details) en una llista. Aquesta nova visualització ajuda a administrar com s'utilitza un segment concret i adaptar o crear exportacions noves.    
  Podeu [definir planificacions d'actualització personalitzades](export-destinations.md#schedule-and-run-exports) per a exportacions individuals o diverses exportacions alhora. Fins ara, totes les exportacions s'executaven amb cada actualització del sistema.    
  En comptes de crear una exportació nova des de zero, podeu començar basant-vos en una d'existent per estalviar temps.

- **Exporteu segments al Microsoft Advertising** Hem ampliat les nostres destinacions d'exportació per incloure-hi el Microsoft Advertising. Creeu públics del Customer Match al Microsoft Advertising amb les dades del perfil del client unificat i utilitzeu-los per a les campanyes de publicitat. Per obtenir-ne més informació, vegeu [Exportar segments al Microsoft Advertising](export-microsoft-advertising.md).

- **Exporteu segments a LinkedIn Ads** Hem ampliat les nostres destinacions d'exportació per incloure LinkedIn Ads i permetre-us desbloquejar la segmentació de contactes i d'empreses mitjançant LinkedIn i exportant les dades de perfil de client unificat. Per obtenir-ne més informació, vegeu [Exportar segments al LinkedIn Ads](export-linkedin-ads.md).


- **Exporteu segments a Omnisend** Hem ampliat les nostres destinacions d'exportació per incloure-hi Omnisend. Utilitzeu els segments creats als coneixements del públic per generar campanyes, proporcionar contingut de màrqueting per correu electrònic i utilitzar grups específics de clients amb Omnisend. Per obtenir-ne més informació, vegeu [Exportar segments a Omnisend](export-omnisend.md)

### <a name="predictions"></a>Prediccions

- **Informe d'ús de dades d'entrada** L'informe d'ús de dades d'entrada proporciona una visualització consolidada dels errors i advertiments que poden generar les previsions de sèrie. També recomana com millorar el rendiment del model.    
  L'informe està disponible quan un model ha finalitzat el procés d'entrenament. Es crea per a cada model per separat, independentment de si s'ha completat correctament o no.
  Actualment, aquesta característica només està disponible per al model de cancel·lació de la transacció. Per obtenir-ne més informació, vegeu [informe d'ús de dades d'entrada](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relacions

- **Visualitzador de relacions** El visualitzador de relacions us permet veure totes les relacions existents entre les entitats i la seva cardinalitat. Les relacions s'organitzen ara en grups: usuari creat, sistema i relacions heretades. També podeu exportar una visualització com a imatge. Per obtenir-ne més informació, consulteu [Visualitzar relacions](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Actualitzacions d'abril de 2021

Les actualitzacions de l'abril de 2021 inclouen diverses característiques, actualitzacions de rendiment i correccions d'errors.

### <a name="data-unification"></a>Unificació de dades
 
- **Experiència de combinació millorada per a la unificació de dades**    
  
   Ara tenim una experiència d'usuari millorada en la configuració de la combinació del procés d'unificació de dades. Els canvis inclouen l'ordenació intuïtiva dels camps combinats i les estadístiques detallades sobre camps combinats i únics.

- **Reordenament d'entitat i configuració de tots els registres de l'entitat Client**  
      
   Ara podeu reordenar i suprimir entitats d'un pla de combinació existent al procés d'unificació de dades. Dona flexibilitat per reordenar les entitats en el procés de partit segons les necessitats empresarials. A més, habilitem la inclusió de tots els registres no coincidents a l'entitat *Client* final, que els permet definir la definició del conjunt de dades del perfil de client.

### <a name="enrichments"></a>Enriquiments

 - **Enriquiment nou: adreces millorades**    
  
   Ens fa il·lusió introduir un nou enriquiment per millorar les adreces de les dades dels clients. Les adreces de les dades poden ser desestructurades, incompletes o incorrectes. Aquesta característica utilitza els models de Microsoft per normalitzar i enriquir les adreces en el format del model de dades comú per obtenir una millor precisió i informació.
 
   Per obtenir més informació, vegeu [Enriquiment dels perfils de client amb adreces millorades](enrichment-enhanced-addresses.md).

- **Experiència de configuració guiada per a enriquiments**    
  
   Hem revisat l'experiència de configuració per a enriquiments amb una experiència guiada simple. Ara teniu un procés pas a pas clar per crear i editar enriquiments.
 
   A més, hem separat la configuració de les connexions per a enriquiments de tercers per permetre que s'utilitzi la mateixa connexió per diversos enriquiments. Només els administradors poden configurar noves connexions, però les connexions creades estan disponibles per als administradors i per als col·laboradors.    

   Per obtenir més informació, consulteu [Informació general de les connexions](connections.md).

- **Múltiples enriquiments del mateix tipus**    
  
   Ara permetem als usuaris crear i administrar diversos enriquiments del mateix tipus d'enriquiment. Per exemple, ara podeu crear dos enriquiments d'adreces independents per enriquir dos segments de clients diferents. Els límits s'apliquen sobre el nombre d'enriquiments del mateix tipus que es poden crear i varien segons el tipus d'enriquiment.
  
   Per obtenir més informació, vegeu [Enriquiment per a perfils de client](enrichment-hub.md).

## <a name="march-2021-updates"></a>Actualitzacions de març del 2021

Les actualitzacions del març de 2021 inclouen diverses característiques, actualitzacions de rendiment i correccions d'errors.

### <a name="activities"></a>Activitats

- **Auxiliar d'activitat i tipus semàntics**

   Hem millorat i actualitzat la nostra experiència d'assignació d'activitats per guiar i simplificar la creació d'assignacions d'activitats. En aquesta nova experiència, els usuaris poden tenir una experiència guiada per ajudar a completar cada pas del procés. Al pas d'assignació de l'activitat, a més de triar entre molts tipus d'activitats, l'usuari pot triar d'assignar semànticament dades per a *Subscription* i/o *SalesOrderLine* als esquemes estàndard del sector, que es poden utilitzar per al consum descendent.   

   Per obtenir més informació, vegeu [Activitats del client](activities.md).

### <a name="data-ingestion"></a>Ingestió de dades

- **Connecteu-vos a fonts de dades locals mitjançant fluxos de dades i passarel·les del Power Platform** Ens complau anunciar la versió preliminar dels fluxos de dades del Power Platform i la connectivitat local mitjançant l'ús de passarel·les al Customer Insights amb un entorn associat del Power Platform o del Dataverse. Totes les fonts de dades noves creades en un entorn del Customer Insights amb un entorn del Dataverse enllaçat seran per defecte fluxos de dades del Power Platform que aportaran connectivitat de dades locals i un conjunt enriquit de connectors i capacitats de transformació.

### <a name="extensibility"></a>Extensibilitat

- **Exportacions organitzades en connexions i exportacions** Hem canviat el nom de la pàgina **Destinacions d'exportació** per **Connexions** i hem afegit una pàgina independent per a les **Exportacions**. Com a part d'aquesta actualització, farem la transició de les exportacions existents a parells d'una connexió i una exportació que utilitzen aquesta connexió. Els administradors poden veure més clarament les dades sortints a la pàgina **Connexions**. Totes les funcions d'usuari tenen accés a la pàgina **Exportacions**, però només els administradors poden optar per permetre als col·laboradors d'editar exportacions específiques amb connexions compartides.     
  Per obtenir més informació, vegeu [Informació general sobre les connexions](connections.md) i [Informació general sobre les exportacions](export-destinations.md).

- **Exporteu segments a Campaign Monitor** Hem ampliat les nostres destinacions d'exportació per incloure-hi Campaign Monitor. Ara podeu exportar segments des del Customer Insights a les llistes de Campaign Monitor i utilitzar-los com a base per a les campanyes de màrqueting.    
   Per obtenir més informació, vegeu [Exportació a Campaign Monitor](export-campaign-monitor.md).

- **Exporteu segments a Constant Contact** Hem ampliat les nostres destinacions d'exportació per incloure-hi Constant Contact. Ara podeu exportar segments des del Customer Insights a les llistes de Constant Contact i utilitzar-los com a base per a les campanyes de màrqueting.   
   Per obtenir més informació, vegeu [Exportació a Constant Contact](export-constant-contact.md).

- **Exporteu segments a RollWorks** Hem ampliat les nostres destinacions d'exportació per incloure-hi RollWorks. Ara podeu exportar segments del Customer Insights als públics del RollWorks i utilitzar-los com a base per a la publicitat d'empresa a empresa.    
   Per obtenir més informació, vegeu [Exportació a RollWorks](export-rollworks.md).

- **Exporteu segments a Snapchat** Hem ampliat les nostres destinacions d'exportació per incloure-hi Snapchat. Ara podeu exportar segments des del Customer Insights als públics de Snapchat i utilitzar-los com a base per a la publicitat.     
   Per obtenir més informació, vegeu [Exportació a Snapchat](export-snapchat.md).

### <a name="predictions"></a>Prediccions

- **Utilitzeu filtres de producte a les recomanacions de producte predictives** Hem afegit la capacitat d'utilitzar filtres de producte al nostre model de recomanació de productes. Ara podeu crear una predicció que només utilitzi un subconjunt dels vostres productes.    
   Per obtenir més informació, vegeu [Configurar filtres de producte](predict-product-recommendation.md#configure-product-filters).

- **Crear segments a partir de predictions de model** Hem afegit una manera ràpida de crear segments utilitzant els resultats d'un model de predicció. Des de la pàgina de resultats del model, podeu crear fàcilment un segment nou seleccionant l'opció **Crea un segment**.    
  Per obtenir més informació, vegeu [Crear un segment basat en un model de predicció](prediction-based-segment.md).

- **Explicacions de les recomanacions de producte** Hem afegit informació sobre els factors clau que aprèn el model d'IA per generar recomanacions de producte i el grau amb què aquests factors contribueixen a les recomanacions de producte. Aquesta informació s'afegeix a la pantalla de resultats del model.    
   Per obtenir més informació, vegeu [Revisar un estat de predicció i els resultats](predict-product-recommendation.md#review-a-prediction-status-and-results).

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

  Els administradors poden copiar configuracions d'entorn a un entorn nou de la mateixa organització. Aquesta característica amplia la funcionalitat de còpia de l'entorn per als casos en què s'utilitzen fonts de dades basades en un llac de dades administrat pel Microsoft Dataverse o una carpeta del model de dades comú.

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




[!INCLUDE[footer-include](../includes/footer-banner.md)]