---
title: Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD | MicrosoftDocs
description: Responeu a les sol·licituds de subjecte de dades per a la capacitat de conclusions del públic del Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350257"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD

El Reglament general de protecció de dades (RGPD) de la Unió Europea està en vigència des del 25 de maig de 2018. Dona drets importants a les persones pel que fa a les seves dades. El RGPD tracta de protegir i habilitar els drets de privadesa de les persones. Podeu llegir més informació sobre el compromís de Microsoft amb la seguretat i el compliment al [Centre de confiança de Microsoft](https://www.microsoft.com/trust-center).

Ens comprometem a ajudar els nostres clients a complir les seves necessitats del RGPD. Inclou el dret a suprimir i exportar dades que incloguin informació personal, com ara identificadors d'usuari, números de telèfon i adreces electròniques. Els administradors poden implementar sol·licituds d'usuari per suprimir o exportar dades personals.

## <a name="audience-insights"></a>Conclusions sobre el públic

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Respondre a les sol·licituds de supressió del subjecte de dades del RGPD per a la capacitat de conclusions del públic del Dynamics 365 Customer Insights

El "dret a suprimir" les dades personals de les dades del client d'una organització és una protecció clau del Reglament general de protecció de dades (RGPD). L'eliminació de dades personals inclou l'eliminació de totes les dades personals i registres generats pel sistema, tret de la informació del registre d'auditoria.

#### <a name="manage-data-subject-delete-requests"></a>Administrar les sol·licituds de supressió de subjectes de dades

Les conclusions del públic ofereixen la següent experiència dins del producte per suprimir les dades personals d'un client o usuari específic del Customer Insights:

- **Administrar les sol·licituds de supressió de dades de clients**: les dades dels clients del Customer Insights s'ingereixen des de les fonts de dades originals externes al Customer Insights. Totes les sol·licituds de supressió de l'RGPD s'han de dur a terme a la font de dades original.
- **Administrar les sol·licituds de supressió de dades d'usuari del Customer Insights**: el Customer Insights crea les dades per als usuaris. Totes les sol·licituds de supressió de l'RGPD s'han de dur a terme al Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Administrar les sol·licituds de supressió de dades de clients

Un administrador del Customer Insights pot seguir aquests passos per suprimir les dades del client que s'havien suprimit a la font de dades:

1. Inicieu la sessió a Dynamics 365 Customer Insights.
2. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.
3. Per a cada font de dades de la llista que conté dades dels clients suprimides:
   1. Seleccioneu (...) i després trieu **Actualitza**.
   2. Consulteu l'estat de la font de dades a **Estat**. Una marca de selecció significa que l'actualització s'ha realitzat correctament. Un triangle d'advertiment significa que alguna cosa ha anat malament. Si es mostra un triangle d'advertiment, poseu-vos en contacte amb D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Gestionar les sol·licituds de l'RGPD de supressió de dades de clients.](audience-insights/media/gdpr-data-sources.png "Gestionar les sol·licituds de l'RGPD de supressió de dades de clients")

##### <a name="manage-delete-requests-for-user-data"></a>Administrar les sol·licituds de supressió de dades d'usuaris

Un administrador del Customer Insights pot seguir aquests passos per suprimir les dades d'usuari del Customer Insights:

1. Inicieu la sessió a Dynamics 365 Customer Insights.
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

## <a name="consent-management-preview"></a>Gestió de consentiments (previsualització)

La capacitat de gestió del consentiment no recopila dades de l'usuari directament. Només importa i processa dades de consentiment que els usuaris proporcionen en altres aplicacions.

Per eliminar les dades de consentiment sobre usuaris específics, suprimiu-les a les fonts de dades ingerides a la capacitat de gestió del consentiment. Després d'actualitzar el font de dades, les dades suprimides també se suprimiran al Centre de consentiment. Les aplicacions que utilitzen l'entitat de consentiment també suprimiran les dades que s'han suprimit a l'origen després d'una [actualització](audience-insights/system.md#refresh-processes). Recomanem actualitzar les fonts de dades ràpidament després de respondre a una sol·licitud de l'interessat per eliminar les dades de l'usuari de tots els altres processos i aplicacions.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]