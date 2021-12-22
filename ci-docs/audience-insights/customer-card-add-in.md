---
title: Complement de targeta de client per a aplicacions del Dynamics 365 (vídeo)
description: Mostra dades dels coneixements del públic a les aplicacions del Dynamics 365 amb aquest complement.
ms.date: 12/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: f3d613d7183fd0af2998cd081d08d4316c7a5628
ms.sourcegitcommit: ae3b92926ea1adfcc50e4bfd000b06ea0ccfc0ee
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 12/15/2021
ms.locfileid: "7921853"
---
# <a name="customer-card-add-in-preview"></a>Complement de targeta del client (versió preliminar)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Obtingueu una visió integral dels clients directament a les aplicacions del Dynamics 365. Amb el complement de targeta de client instal·lat a l'aplicació del Dynamics 365 admesa, podeu triar si voleu que es visualitzin els camps, les conclusions i la cronologia d'activitat del perfil del client. El complement recuperarà les dades del Customer Insights sense que afectin les dades de l'aplicació del Dynamics 365 connectada.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Requisits previs

- El complement només funciona amb les aplicacions controlades per models del Dynamics 365, com ara Vendes o Servei d'atenció al client, versió 9.0 i posteriors.
- Perquè les dades del Dynamics 365 s'assignin als perfils de client dels coneixements del públic, han de ser [ingerides des de l'aplicació del Dynamics 365 utilitzant el connector del Microsoft Dataverse](connect-power-query.md).
- Tots els usuaris del Dynamics 365 del complement de la targeta del client s'han d'[afegir com a usuaris](permissions.md) als coneixements del públic per veure les dades.
- [Les capacitats de cerca i filtre configurades](search-filter-index.md) als coneixements del públic són necessàries per cercar dades per treballar.
- Cada complement es basa en dades específiques dels coneixements del públic. Algunes dades i controls només estan disponibles en entorns de tipus específics. La configuració del complement us informarà si un control no està disponible a causa del tipus d'entorn seleccionat. Més informació sobre [casos d'ús d'entorns](work-with-business-accounts.md).
  - **Control de mesura**: requereix [mesures configurades](measures.md) dels atributs de tipus client.
  - **Control d'intel·ligència:** Requereix dades generades mitjançant [prediccions o models personalitzats](predictions-overview.md).
  - **Control de detalls del client**: tots els camps del perfil estan disponibles al perfil de client unificat.
  - **Control d'enriquiment**: requereix [enriquiments](enrichment-hub.md) actius aplicats als perfils del client. El complement de la targeta admet aquests enriquiments: [marques](enrichment-microsoft.md) proporcionades per Microsoft, [Interessos](enrichment-microsoft.md) proporcionats per Microsoft i dades [d'interacció de l'Office](enrichment-office.md) proporcionades per Microsoft.
  - **Control de contactes**: requereix una definició d'entitat semàntica de contactes de tipus.
  - **Control de la cronologia**: requereix [activitats configurades](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instal·lar el complement de targeta del client

El complement de la targeta del client és una solució per a les aplicacions d'interacció amb els clients al Dynamics 365. Per instal·lar la solució, aneu a AppSource i cerqueu **Targeta del client del Dynamics**. Seleccioneu el [Complement de targeta del client a AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i seleccioneu **Obtén ara**.

Potser heu d'iniciar la sessió amb les credencials d'administrador de l'aplicació Dynamics 365 per instal·lar la solució. Pot ser que la solució tardi una estona en instal·lar-se al vostre entorn.

## <a name="configure-the-customer-card-add-in"></a>Configurar el complement de targeta del client

1. Com a administrador, aneu a la secció **Configuració** al Dynamics 365 i seleccioneu **Solucions**.

1. Seleccioneu l'enllaç **Nom de visualització** per a la solució del **Complement de targeta de client del Dynamics 365 Customer Insights (visualització prèvia)**.

   > [!div class="mx-imgBorder"]
   > ![Seleccionar el nom de visualització.](media/select-display-name.png "Seleccioneu el nom de visualització.")

1. Seleccioneu **Inicia la sessió** i introduïu les credencials del compte d'administrador que utilitzeu per configurar el Customer Insights.

   > [!NOTE]
   > Comproveu que el bloquejador d'elements emergents del navegador no bloquegi la finestra d'autenticació en seleccionar el botó **Inicia la sessió**.

1. Seleccioneu l'entorn del Customer Insights des del qual voleu obtenir dades.

1. Definiu l'assignació de camps als registres de l'aplicació del Dynamics 365. Segons les dades del Customer Insights, podeu triar entre assignar les opcions següents:
   - Per dur a terme l'assignació a un contacte, seleccioneu el camp de l'entitat de client que coincideixi amb l'identificador de l'entitat del contacte.
   - Per dur a terme l'assignació a un compte, seleccioneu el camp de l'entitat de client que coincideixi amb l'identificador de l'entitat del compte.

   > [!div class="mx-imgBorder"]
   > ![Camp Identificador de contacte.](media/contact-id-field.png "Camp Identificador de contacte.")

1. Seleccioneu **Desa la configuració** per desar la configuració.

1. A continuació, heu d'assignar funcions de seguretat al Dynamics 365 per tal que els usuaris puguin personalitzar i veure la targeta del client. Al Dynamics 365, aneu a **Configuració** > **Seguretat** > **Usuaris**. Seleccioneu els usuaris per editar funcions d'usuari i seleccioneu **Administra les funcions**.

1. Assigneu la funció **Personalitzador de targetes del Customer Insights** a usuaris que personalitzaran el contingut que es mostra a la targeta per a tota l'organització.

## <a name="add-customer-card-controls-to-forms"></a>Afegir controls de la targeta de client a formularis

Segons el vostre escenari, podeu triar afegir controls al formulari de **Contacte** o al formulari de **Compte**. Si el vostre entorn de coneixements sobre el públic és per a comptes empresarials, es recomana afegir els controls al formulari de Compte. En aquest cas, substituïu "contacte" als passos següents per "compte".

1. Per afegir els controls de la targeta del client al formulari de contacte, aneu a **Configuració** > **Personalitzacions** al Dynamics 365.

1. Seleccioneu **Personalitza el sistema**.

1. Navegueu a l'entitat **Contacte**, expandiu-la i seleccioneu **Formularis**.

1. Seleccioneu el formulari de contacte al qual voleu afegir els controls de la targeta del client.

    > [!div class="mx-imgBorder"]
    > ![Seleccioneu el formulari de contacte.](media/contact-active-forms.png "Seleccioneu el formulari Contacte.")

1. Per afegir un control, a l'editor de formularis, arrossegueu qualsevol camp de l'**Explorador de camps** a on voleu que aparegui el control.

1. Seleccioneu el camp al formulari que acabeu d'afegir i seleccioneu **Canvia les propietats**.

1. Aneu a la pestanya **Controls** i seleccioneu **Afegeix un control**. Trieu un dels controls personalitzats disponibles i seleccioneu **Afegeix**.

1. Al quadre de diàleg **Propietats del camp**, desactiveu la casella de selecció **Mostra l'etiqueta al formulari**.

1. Seleccioneu l'opció **Web** per al control. Per al control Enriquiment, seleccioneu el tipus d'enriquiment que voleu mostrar configurant el camp **enrichmentType**. Afegiu un control d'enriquiment diferent per a cada tipus d'enriquiment.

1. Seleccioneu **Desa** i **Publica** per publicar el formulari de contacte actualitzat.

1. Aneu al formulari de contacte publicat. Es mostra el control acabat d'afegir. Pot ser que hàgiu d'iniciar la sessió la primera vegada que l'utilitzeu.

1. Per personalitzar el que voleu que es mostri en el control personalitzat, seleccioneu el botó Edita a la cantonada superior dreta.

## <a name="upgrade-customer-card-add-in"></a>Actualitzar el complement de targeta del client

El complement de targeta del client no s'actualitza automàticament. Per actualitzar a l'última versió, seguiu aquests passos a l'aplicació Dynamics 365 que té el complement instal·lat.

1. A l'aplicació Dynamics 365, aneu a **Configuració** > **Personalització** i seleccioneu **Solucions**.

1. A la taula de complements, cerqueu **CustomerInsightsCustomerCard** i seleccioneu la fila.

1. Seleccioneu **Aplica l'actualització de la solució** a la barra d'accions.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualitzar la solució a l'àrea Personalització de les aplicacions del Dynamics 365.":::

1. Després d'iniciar el procés d'actualització, veureu un indicador de càrrega fins que finalitzi l'actualització. Si no hi ha cap versió nova, l'actualització mostrarà un missatge d'error.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
