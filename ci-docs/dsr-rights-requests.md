---
title: Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD | MicrosoftDocs
description: Responeu a les sol·licituds de drets de subjecte de dades per al Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c71305ab835b0f4f75adcce716e795959f898e47
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947356"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD

El Reglament general de protecció de dades (RGPD) de la Unió Europea està en vigència des del 25 de maig de 2018. Dona drets importants a les persones pel que fa a les seves dades. El RGPD tracta de protegir i habilitar els drets de privadesa de les persones. Podeu llegir més informació sobre el compromís de Microsoft amb la seguretat i el compliment al [Centre de confiança de Microsoft](https://www.microsoft.com/trust-center).

Ens comprometem a ajudar els nostres clients a complir les seves necessitats del RGPD. Inclou el dret a suprimir i exportar dades que incloguin informació personal, com ara identificadors d'usuari, números de telèfon i adreces electròniques. Els administradors poden implementar sol·licituds d'usuari per suprimir o exportar dades personals.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Respondre a sol·licituds de supressió de subjecte de dades de l'RGPD per al Dynamics 365 Customer Insights

El "dret a suprimir" les dades personals de les dades del client d'una organització és una protecció clau del Reglament general de protecció de dades (RGPD). L'eliminació de dades personals inclou l'eliminació de totes les dades personals i registres generats pel sistema, tret de la informació del registre d'auditoria.

#### <a name="manage-data-subject-delete-requests"></a>Administrar les sol·licituds de supressió de subjectes de dades

El Customer Insights ofereix les experiències següents al producte per suprimir dades personals d'un client o usuari concret:

- **Administrar les sol·licituds de supressió de dades de clients**: les dades dels clients del Customer Insights s'ingereixen des de les fonts de dades originals externes al Customer Insights. Totes les sol·licituds de supressió de l'RGPD s'han de dur a terme a la font de dades original.
- **Administrar les sol·licituds de supressió de dades d'usuari del Customer Insights**: el Customer Insights crea les dades per als usuaris. Totes les sol·licituds de supressió de l'RGPD s'han de dur a terme al Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Administrar les sol·licituds de supressió de dades de clients

Un administrador del Customer Insights pot seguir aquests passos per suprimir les dades del client que s'havien suprimit a la font de dades:

1. Inicieu la sessió a Dynamics 365 Customer Insights.
2. Vés a **Orígens** > **de dades**
3. Per a cada font de dades de la llista que conté dades dels clients suprimides:
   1. Seleccioneu l'el·lipsi vertical (&vellip;) i, a continuació, seleccioneu **Actualitza**.
   2. Consulteu l'estat de la font de dades a **Estat**. Una marca de selecció significa que l'actualització s'ha realitzat correctament. Un triangle d'advertiment significa que alguna cosa ha anat malament. Si es mostra un triangle d'advertiment, poseu-vos en contacte amb D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Gestionar les sol·licituds de l'RGPD de supressió de dades de clients.](media/gdpr-data-sources.png "Gestionar les sol·licituds de l'RGPD de supressió de dades de clients")

##### <a name="manage-delete-requests-for-user-data"></a>Administrar les sol·licituds de supressió de dades d'usuaris

Un administrador del Customer Insights pot seguir aquests passos per suprimir les dades d'usuari del Customer Insights:

1. Inicieu la sessió a Dynamics 365 Customer Insights.
2. Aneu a **Permisos** > **de seguretat de** > **l'administrador**.
3. Activeu la casella de selecció de l'usuari que voleu suprimir.
4. Seleccioneu **Suprimeix**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Respondre a sol·licituds de l'RGPD d'exportació de subjecte de dades

Com a part del nostre compromís d'associar-nos amb vostè en el seu viatge al Reglament General de Protecció de Dades (RGPD), hem desenvolupat documentació per ajudar-vos a respondre a les sol·licituds dels interessats.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]