---
title: Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD | MicrosoftDocs
description: Responeu a les sol·licituds de subjecte de dades per a la capacitat de conclusions del públic del Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405154"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Respondre a les sol·licituds de supressió del subjecte de dades del RGPD per a la capacitat de conclusions del públic del Dynamics 365 Customer Insights

El "dret a suprimir" les dades personals de les dades del client d'una organització és una protecció clau del Reglament general de protecció de dades (RGPD). L'eliminació de dades personals inclou l'eliminació de totes les dades personals i registres generats pel sistema, tret de la informació del registre d'auditoria.

### <a name="manage-data-subject-delete-requests"></a>Administrar les sol·licituds de supressió de subjectes de dades

Les conclusions del públic ofereixen la següent experiència dins del producte per suprimir les dades personals d'un client o usuari específic del Customer Insights:

- **Administrar les sol·licituds de supressió de dades de clients**: les dades dels clients del Customer Insights s'ingereixen des de les fonts de dades originals externes al Customer Insights. Totes les sol·licituds de supressió de l'RGPD s'han de dur a terme a la font de dades original.
- **Administrar les sol·licituds de supressió de dades d'usuari del Customer Insights**: el Customer Insights crea les dades per als usuaris. Totes les sol·licituds de supressió de l'RGPD s'han de dur a terme al Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Administrar les sol·licituds de supressió de dades de clients

Un administrador del Customer Insights pot seguir aquests passos per suprimir les dades del client que s'havien suprimit a la font de dades:

1. Inicieu la sessió a Dynamics 365 Customer Insights.
2. A les conclusions del públic, aneu a **Dades** > **Fonts de dades**.
3. Per a cada font de dades de la llista que conté dades dels clients suprimides:
   1. Seleccioneu (...) i després trieu **Actualitza**.
   2. Consulteu l'estat de la font de dades a **Estat**. Una marca de selecció significa que l'actualització s'ha realitzat correctament. Un triangle d'advertiment significa que alguna cosa ha anat malament. Si es mostra un triangle d'advertiment, poseu-vos en contacte amb D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Gestionar les sol·licituds de l'RGPD de supressió de dades de clients](media/gdpr-data-sources.png "Gestionar les sol·licituds de l'RGPD de supressió de dades de clients")

#### <a name="manage-delete-requests-for-user-data"></a>Administrar les sol·licituds de supressió de dades d'usuaris

Un administrador del Customer Insights pot seguir aquests passos per suprimir les dades d'usuari del Customer Insights:

1. Inicieu la sessió a Dynamics 365 Customer Insights.
2. A les conclusions del públic, aneu a **Administració** > **Permisos**.
3. Activeu la casella de selecció de l'usuari que voleu suprimir.
4. Seleccioneu **Suprimeix**.

> [!div class="mx-imgBorder"]
> ![Gestionar sol·licituds de l'RGPD de supressió de dades d'usuaris](media/gdpr-permissions.png "Gestionar sol·licituds de l'RGPD de supressió de dades d'usuaris")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Respondre a sol·licituds de l'RGPD d'exportació de subjecte de dades

Com a part del nostre compromís d'associar-nos en el vostre viatge cap a l'RGPD (Reglament general de protecció de dades), hem desenvolupat documentació per ajudar-vos a preparar-vos. En aquesta documentació es descriuen els passos que podeu dur a terme actualment per garantir la conformitat amb el RGPD en utilitzar les conclusions del públic.

### <a name="manage-export-and-view-requests"></a>Administrar les sol·licituds d'exportació i visualització

El dret de portabilitat de les dades permet als subjectes de dades sol·licitar una còpia de les seves dades personals en un format electrònic (definit com a "format estructurat, d’ús comú, llegible per ordinador i interoperable”) que es pugui transmetre a un altre controlador de dades.

#### <a name="export-customer-data-tenant-admin"></a>Exportar dades del client (administrador d'inquilins)

Un administrador d'inquilins pot seguir aquests passos per exportar dades:

1. Envieu un missatge de correu electrònic a D365CI@microsoft.com especificant l'adreça de correu electrònic del client a la sol·licitud. L'equip del Customer Insights enviarà un missatge de correu electrònic a l'adreça electrònica de l'administrador de l'inquilí registrada demanant la confirmació per exportar les dades.
2. Reconeixeu la confirmació per exportar les dades del client sol·licitat.
3. Rebeu les dades exportades a través de l'adreça electrònica de l'administrador d'inquilins.

#### <a name="export-user-data-tenant-admin"></a>Exportar dades de l'usuari (administrador de l'inquilí)

1. Envieu un missatge de correu electrònic a D365CI@microsoft.com especificant l'adreça de correu electrònic de l'usuari a la sol·licitud. L'equip del Customer Insights enviarà un missatge de correu electrònic a l'adreça electrònica de l'administrador de l'inquilí registrada demanant la confirmació per exportar les dades.
2. Reconeixeu la confirmació per exportar les dades de l'usuari sol·licitat.
3. Rebeu les dades exportades a través de l'adreça electrònica de l'administrador d'inquilins.
