---
title: Preguntes freqüents de la versió de prova - Dynamics 365 Customer Insights
description: Solucions a preguntes freqüents relacionades amb la configuració i l'administració de la versió de prova del Customer Insights. Més informació sobre com resoldre problemes específics de la plataforma i de l'aplicació.
author: m-hartmann
ms.author: mhart
ms.date: 09/30/2021
ms.topic: get-started
ms.service: customer-insights
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 2837ae13b4150310193a2d09d59aed66b4a69c69
ms.sourcegitcommit: e6020c178a61beb0ee31a031c11ded914d10d995
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "7642848"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Preguntes més freqüents sobre la versió de prova del Dynamics 365 Customer Insights

## <a name="sign-up"></a>Inscripció

### <a name="what-are-the-system-requirements-for-the-trial"></a>Quins són els requisits del sistema per a la versió de prova?

Aquesta aplicació és un servei basat en el núvol que no requereix programari especial més enllà d'un navegador web actualitzat, però s'hi apliquen algunes restriccions. Per tenir la millor experiència de prova, eviteu accedir al lloc de prova en mode d'incògnit i trieu la ubicació de prova que tingueu més a prop. [Més informació sobre els requisits de l'aplicació web.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Com em puc subscriure a la versió de prova sense un inquilí del Microsoft 365?

Podeu introduir una adreça electrònica que no sigui laboral i crearem un compte i un inquilí.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Puc registrar-me per obtenir diverses aplicacions del Dynamics 365, com ara el Sales, el Marketing i el Customer Service?

Sí. Per visualitzar totes les proves disponibles, [consulteu la pàgina del centre de prova](https://dynamics.microsoft.com/dynamics-365-free-trial). Per registrar-vos a diferents proves, podeu utilitzar el mateix compte de correu electrònic. Tanmateix, no es poden tenir diverses aplicacions al mateix lloc de prova. Cada versió de prova estarà disponible en una organització i una adreça URL diferents. Les dades de prova no es compartiran entre les aplicacions.

## <a name="trial-app"></a>Aplicació de prova

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>No he rebut el correu electrònic amb els detalls de la versió de prova després d'inscriure-m'hi, què he de fer?

Quan us registreu per obtenir la versió de prova, rebreu un correu electrònic amb els detalls de la versió de prova. Si no veieu el correu electrònic a la safata d'entrada, comproveu la carpeta de correu brossa. O bé, seguiu aquests passos per accedir a l'aplicació:

1. Aneu al lloc de prova i seleccioneu **Proveu-ho de franc**.
1. Introduïu l'ID de correu electrònic que heu utilitzat per registrar-vos a la versió de prova. Se us redirigirà a l'aplicació de prova.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Com afegeixo més usuaris a una versió de prova?

Per afegir usuaris, aneu al [Centre d'administració del Microsoft 365](https://admin.microsoft.com) mitjançant el compte d'administració de prova. Seguiu les [instruccions del Centre d'administració](/microsoft-365/admin/add-users/add-users) per afegir usuaris al límit de llicències de la versió de prova. Si l'usuari que afegiu ja té un compte del Microsoft 365, assigneu-li una funció de seguretat a l'organització de prova. Per obtenir més informació, vegeu [Assignar una funció de seguretat a un usuari](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Quants usuaris puc afegir al meu entorn de prova?

Podeu afegir un nombre il·limitat d'usuaris a l'entorn de prova.

### <a name="how-do-i-reset-the-trial-environment"></a>Com es reinicialitza l'entorn de prova?

No podeu reinicialitzar l'entorn de prova. Tanmateix, podeu esperar que el període de prova acabi i, a continuació, tornar-vos a registrar per crear una versió de prova nova.

## <a name="trial-expiration-and-extension"></a>Caducitat i ampliació de la versió de prova

### <a name="how-do-i-extend-the-trial"></a>Com s'amplia la versió de prova?

Podeu ampliar la versió de prova directament a l'aplicació. Podeu ampliar la versió de prova un cop.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Puc convertir la versió de prova en una llicència de pagament?

En general, us recomanem que comenceu de nou amb les vostres pròpies dades quan actualitzeu a la versió de pagament del Customer Insights. 

O bé, si només utilitzeu les conclusions del públic, podeu copiar les dades d'un entorn de prova si adquiriu el Customer Insights. Heu de ser l'administrador de la versió de prova del Customer Insights i l'administrador global del vostre inquilí del Microsoft 365 o l'administrador del Dynamics 365 a l'organització per migrar la configuració d'un entorn de prova a un entorn de pagament. 

Després d'iniciar la sessió a la instància de pagament del Customer Insights per primera vegada, se us demana que creeu un entorn nou. En aquest procés, podeu triar de copiar la configuració d'un entorn existent i migrar la majoria dels paràmetres. Si teniu els permisos esmentats anteriorment, l'entorn de prova es mostrarà en aquesta llista. Per obtenir més informació, vegeu [Copiar la configuració de l'entorn](audience-insights/manage-environments.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Quins són els límits i les quotes de la versió de prova?

- No podeu utilitzar el vostre propi compte de l'Azure Data Lake Storage per emmagatzemar les dades de sortida durant una versió de prova de conclusions del públic. No obstant això, podeu ingerir dades d'un compte del Data Lake Storage.
- Podeu emmagatzemar fins a 3 GB de dades a l'entorn del Dataverse que es proveeix automàticament quan inicieu una versió de prova del Customer Insights.

## <a name="customer-insights-specific-questions"></a>Preguntes específiques del Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>Com es comença a utilitzar la versió de prova?

Quan us registreu a la versió de prova, veureu la pantalla principal de l'aplicació. La pantalla principal proporciona enllaços a les guies de l'usuari i els tutorials. Per obtenir més informació, consulteu els enllaços de la secció [Recursos addicionals](trial-signup.md#additional-resources) de la pàgina de registre de la versió de prova.

### <a name="what-features-are-available-in-the-trial"></a>Quines característiques estan disponibles a la versió de prova?

La majoria de les característiques de les capacitats del Customer Insights estan disponibles a la versió de prova.

La característica següent no està disponible: 
- No podeu crear entorns nous que utilitzin el vostre propi compte de l'Azure Data Lake Storage.

### <a name="how-long-does-the-trial-last"></a>Quant de temps dura la versió de prova?

La versió de prova del Customer Insights té una durada de 30 dies. Podeu ampliar la versió de prova una vegada passats 23 dies quan inicieu la sessió a l'entorn de prova.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Com se suprimeixen les dades d'exemple de la versió de prova?

No podeu suprimir les dades d'exemple de la versió de prova.
