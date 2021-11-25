---
title: Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD | MicrosoftDocs
description: Respondre a les sol·licituds d'interessats per a la capacitat d'informació de l'audiència Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732668"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD

El Reglament general de protecció de dades (RGPD) de la Unió Europea està en vigència des del 25 de maig de 2018. Dona drets importants a les persones pel que fa a les seves dades. El RGPD tracta de protegir i habilitar els drets de privadesa de les persones. Podeu llegir més informació sobre el compromís de Microsoft amb la seguretat i el compliment al [Centre de confiança de Microsoft](https://www.microsoft.com/trust-center).

Ens comprometem a ajudar els nostres clients a complir les seves necessitats del RGPD. Inclou el dret a suprimir i exportar dades que incloguin informació personal, com ara identificadors d'usuari, números de telèfon i adreces electròniques. Els administradors poden implementar sol·licituds d'usuari per suprimir o exportar dades personals.

## <a name="audience-insights"></a>Conclusions sobre el públic

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>En resposta a l'interessat GDPR suprimeix les sol·licituds de capacitat d'informació de l'audiència Dynamics 365 Customer Insights

El "dret a suprimir" les dades personals de les dades del client d'una organització és una protecció clau del Reglament general de protecció de dades (RGPD). L'eliminació de dades personals inclou l'eliminació de totes les dades personals i registres generats pel sistema, tret de la informació del registre d'auditoria.

#### <a name="manage-data-subject-delete-requests"></a>Administrar les sol·licituds de supressió de subjectes de dades

Les conclusions del públic ofereixen la següent experiència dins del producte per suprimir les dades personals d'un client o usuari específic del Customer Insights:

- **Administrar les sol·licituds de supressió de dades de clients**: les dades dels clients del Customer Insights s'ingereixen des de les fonts de dades originals externes al Customer Insights. Totes les sol·licituds de supressió de l'RGPD s'han de dur a terme a la font de dades original.
- **Administrar les sol·licituds de supressió de dades d'usuari del Customer Insights**: el Customer Insights crea les dades per als usuaris. Totes les sol·licituds de supressió de l'RGPD s'han de dur a terme al Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Administrar les sol·licituds de supressió de dades de clients

Un administrador del Customer Insights pot seguir aquests passos per suprimir les dades del client que s'havien suprimit a la font de dades:

1. Inicieu sessió a Dynamics 365 Customer Insights.
2. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.
3. Per a cada font de dades de la llista que conté dades dels clients suprimides:
   1. Seleccioneu (...) i després trieu **Actualitza**.
   2. Consulteu l'estat de la font de dades a **Estat**. Una marca de selecció significa que l'actualització s'ha realitzat correctament. Un triangle d'advertiment significa que alguna cosa ha anat malament. Si es mostra un triangle d'advertiment, poseu-vos en contacte amb D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Gestionar les sol·licituds de l'RGPD de supressió de dades de clients.](audience-insights/media/gdpr-data-sources.png "Gestionar les sol·licituds de l'RGPD de supressió de dades de clients")

##### <a name="manage-delete-requests-for-user-data"></a>Administrar les sol·licituds de supressió de dades d'usuaris

Un administrador del Customer Insights pot seguir aquests passos per suprimir les dades d'usuari del Customer Insights:

1. Inicieu sessió a Dynamics 365 Customer Insights.
2. A les conclusions del públic, aneu a **Administració** > **Permisos**.
3. Activeu la casella de selecció de l'usuari que voleu suprimir.
4. Seleccioneu **Suprimeix**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Respondre a sol·licituds de l'RGPD d'exportació de subjecte de dades

Com a part del nostre compromís d'associar-nos en el vostre viatge cap a l'RGPD (Reglament general de protecció de dades), hem desenvolupat documentació per ajudar-vos a preparar-vos. En aquesta documentació es descriuen els passos que podeu dur a terme actualment per garantir la conformitat amb el RGPD en utilitzar les conclusions del públic.

#### <a name="manage-export-and-view-requests"></a>Administrar les sol·licituds d'exportació i visualització

El dret de portabilitat de les dades permet als subjectes de dades sol·licitar una còpia de les seves dades personals en un format electrònic (definit com a "format estructurat, d’ús comú, llegible per ordinador i interoperable”) que es pugui transmetre a un altre controlador de dades.

##### <a name="export-customer-data-tenant-admin"></a>Exportar dades del client (administrador d'inquilins)

Un administrador d'inquilins pot seguir aquests passos per exportar dades:

1. Envieu un missatge de correu electrònic a D365CI@microsoft.com especificant l'adreça de correu electrònic del client a la sol·licitud. L'equip del Customer Insights enviarà un missatge de correu electrònic a l'adreça electrònica de l'administrador de l'inquilí registrada demanant la confirmació per exportar les dades.
2. Reconeixeu la confirmació per exportar les dades del client sol·licitat.
3. Rebeu les dades exportades a través de l'adreça electrònica de l'administrador d'inquilins.

##### <a name="export-user-data-tenant-admin"></a>Exportar dades de l'usuari (administrador de l'inquilí)

1. Envieu un missatge de correu electrònic a D365CI@microsoft.com especificant l'adreça de correu electrònic de l'usuari a la sol·licitud. L'equip del Customer Insights enviarà un missatge de correu electrònic a l'adreça electrònica de l'administrador de l'inquilí registrada demanant la confirmació per exportar les dades.
2. Reconeixeu la confirmació per exportar les dades de l'usuari sol·licitat.
3. Rebeu les dades exportades a través de l'adreça electrònica de l'administrador d'inquilins.

## <a name="consent-management-preview"></a>Gestió del consentiment (previsualització)

La capacitat de gestió del consentiment no recull directament les dades de l'usuari. Només importa i processa dades de consentiment que són proporcionades pels usuaris en altres aplicacions.

Per eliminar les dades de consentiment sobre usuaris concrets, suprimiu-les en les fonts de dades ingerides a la capacitat de gestió del consentiment. Després d'actualitzar el font de dades, les dades eliminades també se suprimiran al Centre de consentiment. Les aplicacions que utilitzen l'entitat de consentiment també suprimiran les dades que s'han suprimit a l'origen després d'una [actualització](audience-insights/system.md#refresh-processes). Recomanem actualitzar les fonts de dades ràpidament després de respondre a una sol·licitud de l'interessat per eliminar les dades de l'usuari de tots els altres processos i aplicacions.


## <a name="engagement-insights-preview"></a>Conclusions sobre la interacció (versió preliminar)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Suprimir i exportar dades d'incidències que contenen informació identificable de l'usuari final

Les seccions següents descriuen com se suprimeixen i s'exporten les dades d'incidències que podrien incloure dades personals.

Per a suprimir o exportar dades:

1. Etiqueteu propietats d'incidències que contenen dades amb informació personal.
2. Suprimiu o exporteu dades associades amb valors específics (per exemple, un identificador d'usuari especificat).

#### <a name="tag-and-update-event-properties"></a>Etiqueteu i actualitzeu les propietats d'incidències

Les dades personals s'etiqueten a un nivell de propietat d'incidències. En primer lloc, etiqueteu les propietats que es consideren per a la supressió o l'exportació.

Per etiquetar una propietat d'incidències que contingui informació personal, seguiu aquests passos:

1. Obriu l'espai de treball que conté la incidència.

1. Aneu a **Dades** > **Incidències** per a veure una llista d'incidències a l'àrea de treball seleccionada.
  
1. Seleccioneu la incidència que voleu etiquetar.

1. Seleccioneu **Edita les propietats** per obrir la subfinestra amb una llista de totes les propietats de la incidència seleccionada.
     
1. Seleccioneu **...** i, a continuació, trieu **Edita** per arribar al quadre de diàleg **Actualitza la propietat**.

   ![Edita l'esdeveniment.](engagement-insights/media/edit-event.png "Edita l'esdeveniment")

1. A la finestra **Actualitza la propietat**, trieu **...** a la part superior dreta i, a continuació, trieu el quadre **Conté EUII**. Trieu **Actualitza** per a desar els canvis.

   ![Desa els canvis.](engagement-insights/media/update-property.png "Desa els canvis")

   > [!NOTE]
   > Cada vegada que l'esquema d'incidències canvia o creeu una incidència nova, es recomana que avalueu les propietats de la incidència associada i les etiqueteu o desetiqueteu conforme contenen dades personals, si cal.

#### <a name="delete-or-export-tagged-event-data"></a>Suprimir o exportar dades d'incidències etiquetades

Si totes les propietats d'una incidència s'han etiquetat correctament segons s'indica al pas anterior, un administrador de l'entorn pot emetre una sol·licitud de supressió de les dades de la incidència etiquetades.

Per a administrar sol·licituds de supressió o exportació d'EUII

1. Aneu a **Administrador** > **Entorn** > **Configuració**.

1. A la secció **Administra la informació identificable de l'usuari final (EUII)**, seleccioneu **Administra EUII**.

##### <a name="deletion"></a>Supressió

Per a suprimir, podeu introduir una llista d'identificadors d'usuari separats per comes a la secció **Suprimeix la informació identificable de l'usuari final (EUII)**. A continuació, aquests identificadors es compararan amb totes les propietats d'incidències etiquetades de tots els projects a l'entorn actual per mitjà de la coincidència exacta de les cadenes. 

Si un valor de propietat coincideix amb un dels identificadors proporcionats, la incidència associada se suprimirà definitivament. A causa de la irreversibilitat d'aquesta acció, heu de confirmar la supressió després de seleccionar **Suprimeix**.

##### <a name="export"></a>Export

El procés d'exportació és idèntic al procés de supressió quan es tracta de definir valors de propietat d'incidències a la secció **Exporta la informació identificable de l'usuari final (EUII)**. A més, haureu de proporcionar una **URL d'emmagatzematge blob de l'Azure** per especificar la destinació d'exportació. L'URL blob de l'Azure ha d'incloure una [signatura d'accés compartit (SAS)](/azure/storage/common/storage-sas-overview).

Després de seleccionar **Exporta**, totes les incidències de l'equip actual que continguin propietats etiquetades coincidents s'exportaran en format CSV a la destinació d'exportació.

### <a name="good-practices"></a>Procediments recomanats

* Intenteu evitar l'enviament d'incidències que continguin dades personals.
* Si heu d'enviar incidències que contenen dades EUII, limiteu el nombre d'incidències i propietats d'incidències que contenen dades EUII. Idealment, limiteu-vos a una incidència.
* Assegureu-vos que el mínim de persones possible té accés a les dades personals enviades.
* Per a les incidències que contenen dades personals, assegureu-vos que definiu una propietat que generi un identificador únic que es pugui enllaçar fàcilment a un usuari concret (per exemple, un identificador d'usuari). D'aquesta manera, és més fàcil segregar les dades i exportar o suprimir les dades correctes.
* Etiqueteu només una propietat per incidència conforme conté dades personals. Idealment, una que només contingui un identificador únic.
* No etiqueteu les propietats que contenen valors detallats (per exemple, un cos de sol·licitud sencer). La capacitat dels coneixements d'interacció utilitza una coincidència de cadena exacta a l'hora de decidir quines incidències cal suprimir o exportar.

[!INCLUDE[footer-include](includes/footer-banner.md)]