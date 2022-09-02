---
title: Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD | MicrosoftDocs
description: Responeu a les sol·licituds de drets de subjecte de dades per al Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387099"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Sol·licituds de drets de subjecte de dades (DSR) a l'RGPD

El Reglament general de protecció de dades (RGPD) de la Unió Europea està en vigència des del 25 de maig de 2018. Dona drets importants a les persones pel que fa a les seves dades. El RGPD tracta de protegir i habilitar els drets de privadesa de les persones. Obteniu més informació sobre el compromís de Microsoft amb la seguretat i el compliment al [Centre de confiança de Microsoft](https://www.microsoft.com/trust-center).

Ens comprometem a ajudar els nostres clients a complir les seves necessitats del RGPD. Inclou el dret a suprimir o exportar dades que incloguin informació personal, com ara identificadors d'usuari, números de telèfon i adreces de correu electrònic. Els administradors poden implementar sol·licituds d'usuari per suprimir o exportar dades personals.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Respondre a les sol·licituds de supressió de l'interessat de GDPR per al Customer Insights

El "dret a suprimir" les dades personals de les dades del client d'una organització és una protecció clau del Reglament general de protecció de dades (RGPD). L'eliminació de dades personals inclou l'eliminació de totes les dades personals i registres generats pel sistema, tret de la informació del registre d'auditoria.

### <a name="manage-data-subject-delete-requests"></a>Administrar les sol·licituds de supressió de subjectes de dades

El Customer Insights ofereix les experiències de producte següents per suprimir dades personals d'un client o usuari concret:

- **Administrar les sol·licituds de supressió de dades de clients**: les dades dels clients del Customer Insights s'ingereixen des de les fonts de dades originals externes al Customer Insights. Realitzeu primer les sol·licituds de supressió de GDPR al font de dades original.
- **Administrar les sol·licituds de supressió de dades d'usuari del Customer Insights**: el Customer Insights crea les dades per als usuaris. Realitzeu totes les sol·licituds de supressió de GDPR al Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Administrar les sol·licituds de supressió de dades de clients

Com a administrador del Customer Insights, suprimiu les dades de client del Customer Insights que s'han suprimit al font de dades. Verifiqueu que les sol·licituds de supressió de l'RGPD s'hagin realitzat a la font de dades original.

1. Inicieu la sessió a Dynamics 365 Customer Insights.

1. Aneu a **Dades** > **Fonts de dades**.

1. Per a cada font de dades de la llista que conté dades dels clients suprimides:
   1. Seleccioneu el font de dades i, a continuació, seleccioneu **Actualitza**.
   1. Consulteu l'estat de la font de dades a **Estat**. Una marca de selecció significa que l'actualització s'ha realitzat correctament. Un triangle d'advertiment significa que alguna cosa ha anat malament. Si es mostra un triangle d'advertiment, poseu-vos en contacte amb D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Gestionar les sol·licituds de l'RGPD de supressió de dades de clients.":::

1. Després d'actualitzar correctament les fonts de dades, executeu també actualitzacions aigües avall. Especialment, si no teniu programada una actualització completa periòdica del Customer Insights.

   > [!IMPORTANT]
   > Els segments estàtics no s'inclouen en una actualització completa ni s'actualitzen aigües avall després d'una sol·licitud de supressió. Per assegurar-vos que les dades dels clients també s'eliminin dels segments estàtics, torneu a crear els segments estàtics amb les dades d'origen actualitzades.

#### <a name="manage-delete-requests-for-user-data"></a>Administrar les sol·licituds de supressió de dades d'usuaris

Com a administrador del Customer Insights, suprimiu les dades d'usuari del Customer Insights.

1. Inicieu la sessió a Dynamics 365 Customer Insights.

1. Aneu a **Seguretat d'administració** > **·** > i seleccioneu la **pestanya Usuaris**.

1. Activeu la casella de selecció dels usuaris que voleu suprimir.

1. Seleccioneu **Suprimeix**.

1. Confirmar la supressió.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Respondre a sol·licituds de l'RGPD d'exportació de subjecte de dades

El dret de portabilitat de les dades permet als subjectes de dades sol·licitar una còpia de les seves dades personals en un format electrònic (definit com a "format estructurat, d’ús comú, llegible per ordinador i interoperable”) que es pugui transmetre a un altre controlador de dades.

### <a name="manage-export-and-view-requests"></a>Administrar les sol·licituds d'exportació i visualització

Gestionar les sol·licituds d'exportació de dades de clients o usuaris.

#### <a name="export-customer-data-tenant-admin"></a>Exportar dades del client (administrador d'inquilins)

Com a administrador d'inquilins, exporteu les dades dels clients.

1. Envieu un missatge de correu electrònic a D365CI@microsoft.com especificant l'adreça de correu electrònic del client a la sol·licitud. L'equip del Customer Insights enviarà un missatge de correu electrònic a l'adreça electrònica de l'administrador de l'inquilí registrada demanant la confirmació per exportar les dades.
2. Reconeixeu la confirmació per exportar les dades del client sol·licitat.
3. Rebeu les dades exportades a través de l'adreça electrònica de l'administrador d'inquilins.

#### <a name="export-user-data-tenant-admin"></a>Exportar dades de l'usuari (administrador de l'inquilí)

Com a administrador d'inquilins, exporta les dades d'usuari.

1. Envieu un missatge de correu electrònic a D365CI@microsoft.com especificant l'adreça de correu electrònic de l'usuari a la sol·licitud. L'equip del Customer Insights envia un correu electrònic a l'adreça de correu electrònic de l'administrador de l'inquilí registrat, demanant confirmació per exportar dades.
1. Reconeixeu la confirmació per exportar les dades de l'usuari sol·licitat.
1. Rebeu les dades exportades a través de l'adreça electrònica de l'administrador d'inquilins.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Tractament de supressió de dades en Dynamics 365 Customer Insights

Les dades se suprimeixen (particions de dades i instantànies de dades) si les particions de dades i les instantànies de dades estan inactives durant més de 30 dies, és a dir, s'han substituït per una nova partició de dades i una instantània mitjançant una actualització de les fonts de dades.

No se suprimeixen totes les dades i instantànies. La partició de dades i la instantània de dades més recents estan actives perquè s'utilitzen al Customer Insights. Per a les dades més recents, no importa si les fonts de dades no s'han actualitzat en els darrers 30 dies.

[!INCLUDE [footer-include](includes/footer-banner.md)]
