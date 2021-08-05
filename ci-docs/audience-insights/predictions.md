---
title: Emplenar dades parcials mitjançant prediccions
description: Utilitzeu prediccions per emplenar les dades incompletes dels clients.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 31b9b1b709540896c1dbc19f974df4ab056a7b8d
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692515"
---
# <a name="complete-your-partial-data-with-predictions"></a>Completar les dades parcials amb prediccions

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Les prediccions us permeten crear fàcilment valors previstos que poden millorar la comprensió d'un client. A la pàgina **Intel·ligència** > **Prediccions**, seleccioneu **Les meves prediccions** per veure les prediccions que heu configurat en altres parts de les conclusions del públic i seguir personalitzant-les.

> [!NOTE]
> No podeu utilitzar aquesta característica si l'entorn utilitza l'emmagatzematge de l'Azure Data Lake Gen 2.
>
> La característica de prediccions utilitza mitjans automatitzats per avaluar dades i fer prediccions a partir d'aquestes dades i, per tant, té la capacitat de ser utilitzada com a mètode de perfilació, com es defineix el terme al Reglament general de protecció de dades ("RGPD"). L'ús del client d'aquesta característica per processar les dades pot estar subjecte a l'RGPD o altres lleis o regulacions. Us responsabilitzeu de garantir que l'ús del Dynamics 365 Customer Insights, incloent-hi prediccions, compleixi totes les lleis i normatives aplicables, incloent-hi la legislació relacionada amb la privadesa, les dades personals, les dades biomètriques, la protecció de dades i la confidencialitat de comunicació.

## <a name="prerequisites"></a>Requisits previs

Per tal que la vostra organització pugui utilitzar la característica de prediccions, heu de complir els requisits previs següents:

1. La vostra organització té una instància [configurada al Microsoft Dataverse](/ai-builder/build-model#prerequisites) i és a la mateixa organització que el Customer Insights.

2. L'entorn de conclusions sobre el públic s'adjunta a la vostra instància del Dataverse.

Si [creeu un nou entorn](get-started-paid.md), configureu-lo al quadre de diàleg **Crea un entorn** i seleccioneu **Avançat**. Si ja heu creat un entorn, aneu a la seva configuració i seleccioneu **Avançat**. De qualsevol manera, a la secció **Utilitza les prediccions**, introduïu l'adreça URL de la instància del Dataverse a la qual voleu adjuntar l'entorn.

## <a name="create-a-prediction-in-the-customer-entity"></a>Crear una predicció a l'entitat Client

1. A les conclusions del públic, aneu a **Dades** > **Entitats**.

2. Seleccioneu l'entitat **Client**.

3. A l'entitat **Client: CustomerInsights**, seleccioneu la pestanya **Camps**.

4. Cerqueu el nom de l'atribut per al qual voleu predir els valors i, a continuació, seleccioneu la icona **Informació general** a la columna **Resum**.
   > [!div class="mx-imgBorder"]
   > ![Icona d'informació general.](media/intelligence-overviewicon.png "Icona d'informació general")

5. Si hi ha un índex elevat de valors que falten per a l'atribut, seleccioneu **Prediu els valors que falten** per continuar amb la vostra predicció.
   > [!div class="mx-imgBorder"]
   > ![Estat d'informació general amb el botó Prediu els valors que falten.](media/intelligence-overviewpredictmissingvalues.png "Estat d'informació general amb el botó Prediu els valors que falten")

6. Proporcioneu un **Nom de visualització** i un **Nom d'entitat de sortida** per als resultats de la predicció.

7. Una llista d'opcions prèviament emplenada es mostrarà, on podeu assignar els valors a una categoria que s'hagi predit. En aquest cas, les úniques opcions de categoria seran 0 o 1, ja que s'assignen a la naturalesa certa/falsa o binària de la predicció. Assigneu els valors de camp que voleu que es classifiquin com a "0" a la predicció final a "0" a la columna Categoria i els elements que voleu que es classifiquin com a "1" a la predicció final a "1".
   > [!div class="mx-imgBorder"]
   > ![Exemple que mostra els valors de camp assignats a categories.](media/intelligence-categorymapping.png "Exemple que mostra els valors de camp assignats a categories")

8. Seleccioneu **Fet** i es processarà la predicció. El processament tardarà una estona, en funció de la mida i la complexitat de les dades. Els resultats estaran disponibles en una entitat nova basada en el **Nom de l'entitat de sortida** de la predicció que heu creat.

## <a name="create-a-prediction-while-creating-a-segment"></a>Crear una predicció durant la creació d'un segment

La predicció dels valors que falten per a un atribut específic determinat també és possible en crear un segment. En concret, quan creeu ràpidament un segment segons la vostra entitat de client unificada o l'entitat Customer_Measure.

Com a part d'aquest flux, trieu un atribut específic en el qual basar el vostre segment com la satisfacció del client o l'import de la compra. Quan es crea un segment, el sistema suggerirà un mètode per predir els valors que falten per a aquest atribut.

1. A les conclusions del públic, aneu a **Segments** i seleccioneu la peça **Perfils**.

2. Trieu un **Camp** del qual crear un segment a i seleccioneu un **Operador** i, a continuació, seleccioneu **Revisa**.

3. Proporcioneu un **Nom** i un **Nom de visualització** per al segment.

4. Seleccioneu **Desa**.

5. Si el segment que heu creat té dades incompletes al camp d'origen, podeu triar predir els valors que falten.
   > [!div class="mx-imgBorder"]
   > ![Botó de predicció.](media/segments-predictoption.png "Botó de predicció")

6. Proporcioneu un **Nom de visualització** i un **Nom d'entitat de sortida** per als resultats de la predicció.

7. Seleccioneu **Fet**. La vostra predicció es generarà en breu en una entitat nova amb el nom que heu indicat per al **Nom de l'entitat de sortida**.

## <a name="view-a-prediction"></a>Visualitzar una predicció

1. A les conclusions del públic, aneu a **Intel·ligència** > **Prediccions** > **Les meves prediccions**.

2. Seleccioneu la predicció que voleu revisar.

3. Seleccioneu els punts suspensius de la columna **Accions** i trieu **Visualitza**.

4. Veureu un nombre de punts de dades a la visualització de la vostra predicció.
   > [!div class="mx-imgBorder"]
   > ![Pàgina Prediccions.](media/intelligence-predictionsviewpage.png "Pàgina Prediccions")

   - **Valors previstos** mostra l'assignació que heu creat durant la fase d'assignació de valor de camp a categoria. Hi ha valors del conjunt de dades que s'han assignat a una categoria concreta.
   -Els **influenciadors principals** són els factors del conjunt de dades que tenen més probabilitats d'influir en la confiança de la predicció del valor del camp assignat a una categoria concreta.
   - El **rendiment** indica la manera com estan les prediccions. Seleccioneu l'enllaç per obtenir més informació.
   - **Visualització prèvia** mostra mostres del conjunt de dades de sortida de la predicció i la probabilitat, o la confiança, del valor previst, on 0 és incert i 1 és segur.

## <a name="update-a-prediction"></a>Actualitzar una predicció

1. A les conclusions del públic, aneu a **Intel·ligència** > **Prediccions** > **Les meves prediccions**.

2. Seleccioneu la predicció que voleu actualitzar i seleccioneu la icona **Actualitza**.

3. La predicció es planificarà per processar-la. Podeu veure l'hora que s'ha actualitzat per última vegada a la columna **Darrera actualització** de la pàgina **Prediccions**.

## <a name="edit-a-prediction"></a>Editar una predicció

Després d'haver creat una predicció, podeu personalitzar el model de l'AI Builder per augmentar l'eficàcia del model.  

1. A les conclusions del públic, aneu a **Intel·ligència** > **Prediccions** > **Les meves prediccions**.

2. Seleccioneu la predicció que voleu editar.

3. Seleccioneu els punts suspensius de la columna **Accions** i trieu **Visualitza**.

4. Seleccioneu **Personalitza a l'AI Builder**.

5. Actualitzeu el model a l'AI Builder. [Més informació sobre la gestió de models a l'AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

A la següent execució de la vostra predicció s'utilitzarà el model actualitzat que hàgiu creat.

> [!NOTE]
> Els models nous creats a l'AI Builder no es mostraran a les conclusions del públic si no s'ha creat el model a partir de les experiències enumerades anteriorment.

## <a name="remove-a-prediction"></a>Suprimir una predicció

1. A les conclusions del públic, aneu a **Intel·ligència** > **Prediccions** > **Les meves prediccions**.

2. Seleccioneu la predicció que voleu suprimir.

3. Seleccioneu els punts suspensius de la columna **Accions** i trieu **Suprimeix**.

4. Confirmar la supressió.

## <a name="troubleshooting"></a>Detecció d'errors

Si no podeu completar el procés d'adjunció del Dataverse a causa d'un error, podeu provar d'acabar el procés manualment. Hi ha dos problemes coneguts que es poden produir en el procés d'adjunció:

- La solució de complement de targeta de client no està instal·lada.
    1. Completeu les instruccions per [instal·lar i configurar la solució](customer-card-add-in.md).

- No s'han concedit permisos de l'aplicació.
    1. Aneu al [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Seleccioneu **Entorns**.
    1. Seleccioneu els punts suspensius que hi ha al costat de l'entorn on voleu afegir el permís i seleccioneu **Configuració**.
    1. Expandiu **Usuaris i permisos** i seleccioneu **Usuaris**.
    1. Seleccioneu **+Nou** i seleccioneu **Usuari**.
    1. Seleccioneu **Usuari de l'aplicació** si ja no està seleccionat i introduïu la següent informació:
        - **Nom d'usuari:** cihelp@microsoft.com
        - **Identificador d'aplicació:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Nom:** Customer
        - **Cognoms:** Insights
        - **Correu electrònic principal:** cihelp@microsoft.com
    1. Seleccioneu **Desa i tanca**.
    1. Seleccioneu l'usuari que acabeu de crear.
    1. Seleccioneu **Administra les funcions** a la barra de menú superior.
    1. Seleccioneu **Administrador del sistema** i, a continuació, seleccioneu **D'acord**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]