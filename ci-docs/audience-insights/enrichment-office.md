---
title: Enriquir els perfils dels clients amb dades de Microsoft Office 365
description: Utilitzeu dades propietàries per enriquir els vostres perfils de Microsoft Office clients amb dades d'interacció.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 938a9de83fd8f5ff0c9ae815d626cdfa35228aba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228462"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Enriquir els perfils dels clients amb dades d'interacció (previsualització)

Utilitzeu dades de per enriquir els perfils del compte de client amb estadístiques sobre les interaccions a través d'aplicacions Microsoft Office 365 Office 365. Les dades d'interacció consisteixen en l'activitat de correu electrònic i reunió, que s'agrega al nivell de compte. Per exemple, el nombre de correus electrònics d'un compte d'empresa o el nombre de reunions amb el compte. No hi ha dades sobre usuaris individuals disponibles. 

Aquest enriquiment està disponible a les següents regions: Regne Unit, Europa, Amèrica del Nord.

## <a name="prerequisites"></a>Requisits previs

Per configurar l'enriquiment s'han de complir els requisits previs següents:

- Teniu una llicència de núvol activa Office 365.
- Teniu [perfils](customer-profiles.md) de clients unificats basats en [comptes d'empresa](work-with-business-accounts.md).
- L'entorn del Customer Insights ha de tenir una [Microsoft Dataverse organització adjunta](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Teniu [permisos d'administrador](permissions.md#administrator).
- Teniu o podeu obtenir el consentiment de l'administrador de l'inquilí Office 365 per utilitzar Office 365 les dades per proporcionar **estadístiques per a l'organització** dins de les aplicacions del Dynamics 365.

## <a name="configure-the-enrichment"></a>Configurar l'enriquiment

1. A les conclusions del públic, aneu a **Dades** > **Enriquiment**.

1. Aneu a la **pestanya Descobreix** i seleccioneu **Enriqueix les meves dades** a la peça Interacció amb **el** compte.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Peça d'interacció amb el compte.":::
   
1. Seleccioneu **Següent** al **pas Visió general** i introduïu adreces electròniques de l'organització per a les quals s'afegiran les dades de l'Office. Només es processen les dades de les adreces de correu electrònic llistades per a la comunicació pertinent. Una pràctica recomanada és utilitzar grups de correu electrònic, per exemple, *l'equip* de vendes dels EUA, que es gestionen fàcilment a Office 365. Es resol i es mostra el nombre d'adreces electròniques dels grups. El nombre total d'adreces electròniques ha de ser com a mínim 2 i no pot superar les 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Adreces electròniques d'interacció amb el compte.":::

1. Reviseu la declaració de consentiment, activeu la **casella de selecció Estic d'acord** i seleccioneu **Endavant**.

1. Seleccioneu el conjunt de dades del client i seleccioneu **Següent**.

1. Assigneu el camp d'adreça electrònica de contacte i seleccioneu **Endavant**.

1. Reviseu la configuració d'enriquiment, doneu un nom a l'enriquiment i seleccioneu **Estalvia enriquiment** per estalviar l'enriquiment.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 consentiment de l'administrador de l'inquilí

Es requereix el consentiment d'un Office 365 administrador d'inquilins per activar l'enriquiment. S'envia un correu electrònic als administradors de l'inquilí Office 365 quan es desa l'enriquiment, cosa que els demana que revisin i consentin permetre que les aplicacions del Dynamics 365 utilitzin les dades de Office 365 les vostres empreses per proporcionar **estadístiques per a l'organització**. L'administrador de l'inquilí Office 365 també pot donar el seu consentiment directament a la seva Office 365 consola d'administració, seleccionant **Estadístiques per a l'organització**.

## <a name="running-the-enrichment-for-the-first-time"></a>Executar l'enriquiment per primera vegada

Quan l'enriquiment s'inicia per primera vegada, després que l'administrador de l'inquilí Office 365 hagi donat el seu consentiment, comença la descàrrega de dades.Office 365 Aquest procés requereix un temps. La primera cursa d'enriquiment es durà a terme amb un retard de sis hores. Podeu veure el nombre de dies que cobreixen les dades a la pàgina visió general de la interacció del compte un cop finalitzi l'enriquiment. Amb un gran volum de dades, torneu a executar l'enriquiment al cap d'uns dies. Assegura que les dades estan completes durant tota la finestra de temps, que és d'un any.

Per iniciar el procés, seleccioneu **Executa** a la pàgina de configuració d'interacció amb el compte. A més, podeu permetre que el sistema executi l'enriquiment automàticament com a part d'una [actualització](system.md#schedule-tab) programada. Per defecte, l'enriquiment s'executa un cop per setmana.

Depenent de la mida de les dades de l'Office, pot trigar diverses hores a completar-se.

Quan executeu un enriquiment, Microsoft processarà les dades dins del límit de Office 365 compliment per crear estadístiques agregades, que després s'afegeixen a l'entorn del Customer Insights. No hi ha dades a nivell individual (per exemple, el cos de qualsevol invitació de correu electrònic o calendari) està disponible per als usuaris del Customer Insights. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultats de l'enriquiment

Després d'executar el procés d'enriquiment, aneu a **Els meus enriquiments** per revisar els resultats de l'enriquiment. Trobareu el nombre total de clients enriquits i una visió general dels resultats d'enriquiment. Inclou el nombre de correus electrònics i reunions processats, el nombre de dies dels quals s'han agregat dades i molt més.

També trobareu un gràfic amb el nombre de clients enriquits al llarg del temps i una visualització prèvia de les dades d'enriquiment.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Visualització prèvia dels resultats després d'executar el procés d'enriquiment.":::

Totes les dades s'agreguen al nivell de compte. El sistema calcula una puntuació d'interacció, que oscil·la entre 0 i 100, per a cada compte. La puntuació d'interacció proporciona una mesura composta de la interacció del compte entre correus electrònics i reunions en relació amb els altres comptes. La llista següent conté les dades agregades que proporciona l'enriquiment de la interacció amb el compte:



| Dades                                                                              | Nom de la columna                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Puntuació d'interacció                                                                  |  EngagementScore                         |
| Nombre de correus electrònics a compte                                                       |  NoOfEmails_ToAccount                    |
| Nombre de correus electrònics del compte                                                     |  NoOfEmails_FromAccount                  | 
| Nombre de reunions iniciades per compte                                           |  NoOfMeetings_FromAccount                | 
| Nombre de reunions iniciades per la vostra organització                                 |  NoOfMeetings_ToAccount                  | 
| Nombre de persones de la vostra organització en reunions amb el compte                  |  NoOfContactsInvolved_Meetings           | 
| Nombre de persones de la vostra organització en converses per correu electrònic amb el compte       |  NoOfContactsInvolved_Emails             | 
| Nombre de persones del compte en reunions amb la vostra organització                  |  NoOfAccountContactsInvolved_Meetings    | 
| Nombre de persones del compte en converses per correu electrònic amb la vostra organització       |  NoOfAccountContactsInvolved_Emails      | 
| Data d'inici de la interacció (primer correu electrònic o reunió a les dades)                        |  EngagementStartDate                     | 
| Dies des de l'últim correu electrònic                                                             |  DaysSinceLastemail                      | 
| Dies des de l'última reunió                                                           |  DaysSinceLastMeeting                    | 
| Durada mitjana de les reunions                                                      |  AverageDuration_Of_Meetings             | 
| Durada mitjana de les respostes de correu electrònic del compte                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Data d'inici de l'agregació                                                            |  AgregacióStartDate                    | 
| Nivell d'agregació (any, mes o setmana)                                          |  Nivell d'agregació                        | 


Reviseu les dades enriquides seleccionant **Mostra'n més** a la secció de visualització prèvia. Obre l'entitat de l'Office *·*. També podeu trobar l'entitat llistada al grup d'enriquiment a **DataEntities**.**·** > **·** També trobareu el *Office_UserEntity*, que conté els identificadors de l'Active Directory per a les adreces de correu electrònic que s'han triat durant la configuració d'enriquiment 

## <a name="see-enrichment-data-on-the-customer-card"></a>Veure dades d'enriquiment a la targeta del client

La interacció amb el compte també es pot veure a les targetes de client individuals. Aneu a **Clients** i seleccioneu un perfil de client. A la targeta de client, trobareu la puntuació d'interacció del compte, el nombre total de correus electrònics i el nombre total de reunions agregades durant l'últim any. També trobareu gràfics que mostren el correu electrònic i l'historial de reunions.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Targeta del client amb dades enriquides.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Crear segments i mesures a partir de les dades enriquides

Les dades enriquides es poden utilitzar per crear segments i mesures tal com es detalla a continuació. Per exemple, un segment que conté tots els clients que tenen un valor de més de 60 durant *dies des de l'últim correu electrònic* i *dies des de l'última reunió*. Aquest segment conté comptes obsolets que podeu provar de reactivar. 

## <a name="next-steps"></a>Passos següents

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
