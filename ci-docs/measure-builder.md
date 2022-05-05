---
title: Crea noves mesures amb el constructor de mesures
description: Creeu mesures des de zero per analitzar les mètriques clau de la vostra empresa.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 6370df0287362a5512a837cdb588f5d20ef03d3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642402"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Utilitzeu el constructor de mesures per crear mesures des de zero

En aquest article s'explica com crear una nova [mesura](measures.md) des de zero. El constructor de mesures us permet definir càlculs utilitzant operadors matemàtics, funcions d'agregació i filtres. Podeu crear un compàs amb atributs d'entitats relacionades amb l'entitat Client *unificada*.

La creació de mesures en entorns B-a-C i B-to-B funciona de la mateixa manera. Tanmateix, si sou un entorn [B-to-B que utilitza comptes amb jerarquies](relationships.md#set-up-account-hierarchies), podeu afegir el compàs entre sub-comptes relacionats.

També podeu crear ràpidament un compàs escollint entre un conjunt de mesures d'ús comú i predefinides. Per obtenir més informació, vegeu [Utilitzar una plantilla per crear un compàs](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

Podeu crear mesures al nivell de clients individuals (atribut de client, mesura del client) o al nivell de l'empresa o organització (mesura empresarial). L'atribut de client i la mesura del client són dos tipus que us permeten fer un seguiment del rendiment per client. Per exemple, la despesa total de cada client. Les mesures empresarials us permeten fer un seguiment del rendiment per empresa. Per exemple, els ingressos totals de l'empresa.

- Atribut client: genera la sortida com un atribut nou, que es desa com una columna nova a l'entitat generada pel sistema anomenada *Customer_Measure*. En actualitzar un atribut de client, tots els altres atributs del client de l'entitat *Customer_Measure* s'actualitzen simultàniament. A més, els atributs del client es mostren a la targeta de perfil del client. Un cop executat o desat, l'atribut client no el podeu canviar a un compàs de client.

- Mesura del client: genera la sortida com a entitat pròpia i no podeu canviar-la a un atribut de client un cop executada o desada. Les mesures del client no es mostren a la targeta de perfil del client.

- Mesura de negoci: genera la sortida com a entitat pròpia i es mostra a la pàgina d'inici de l'entorn del Customer Insights.

1. Aneu a **Mesures**.

1. Seleccioneu **Crea** i trieu **Crea'n una de pròpia**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Pantalla de configuració buida per a un compàs B-to-C." lightbox="media/measure-b2c.png":::

1. Per fer un seguiment del rendiment a nivell empresarial, commuta **el tipus** de mesura al nivell **d'empresa**. **El nivell** de client està seleccionat per defecte. **El nivell** de client afegeix automàticament l'atribut CustomerId *a Dimensions mentre* que el **nivell** d'empresa l'elimina automàticament.

1. A l'àrea de configuració, trieu la funció d'agregació al menú desplegable Selecciona la **funció**. Les funcions d'agregació inclouen:
   - **Suma**
   - **Mitjana**
   - **Recompte**
   - **Compta únics**
   - **Màx**
   - **Min**
   - **Primer**: pren el primer valor del registre de dades
   - **Últim**: pren l'últim valor que s'ha afegit al registre de dades
   - **ArgMax**: troba el registre de dades que dóna el valor màxim d'una funció de destinació
   - **ArgMin**: troba el registre de dades que dóna el valor mínim d'una funció de destinació

1. Seleccioneu **Afegeix un atribut** per seleccionar les dades que necessiteu per crear aquesta mesura.

   1. Seleccioneu la pestanya **Atributs**.
   1. Entitat de dades: trieu l'entitat que inclou l'atribut que voleu mesurar.
   1. Atribut de dades: trieu l'atribut que voleu utilitzar a la funció d'agregació per calcular la mesura. Només podeu seleccionar un atribut cada vegada.
   1. Per seleccionar un atribut de dades d'una mesura existent, seleccioneu la pestanya **Mesures** o bé cerqueu una entitat o un nom de mesura.
   1. Seleccioneu **Afegeix** per afegir l'atribut seleccionat a la mesura.

1. Per crear mesures més complexes, podeu afegir més atributs o utilitzar operadors matemàtics a la funció de mesura.

1. Per afegir filtres, seleccioneu el **Filtre** a l'àrea de configuració. L'aplicació de filtres només utilitzarà els registres que coincideixin amb els filtres per calcular la mesura.
  
   1. A la secció **Afegeix un atribut** de la subfinestra **Filtres**, seleccioneu l'atribut que voleu utilitzar per crear filtres.
   1. Definiu els operadors de filtre per definir el filtre per a cada atribut seleccionat.
   1. Seleccioneu **Aplica** per afegir els filtres a la mesura.

1. Seleccioneu **Dimensió** per triar més camps que s'afegeixin com a columnes a l'entitat de sortida de compàs.

   1. Seleccioneu **Edita les dimensions** per afegir atributs de dades pels quals voleu agrupar els valors de mesura. Per exemple, ciutat o gènere.
   > [!TIP]
   > Si heu seleccionat **el nivell** de client com a **tipus** de mesura, l'atribut CustomerId *ja s'ha* afegit. Si suprimiu l'atribut, **el tipus** De compàs commuta al nivell **d'empresa**.
   1. Seleccioneu **Fet** per afegir les dimensions a la mesura.

1. Si hi ha valors a les dades que heu de substituir per un enter, seleccioneu **Regles**. Configureu la regla i assegureu-vos que trieu només els nombres enters com a substituts. Per exemple, substituïu *nul* per *0*.

1. Si hi ha diversos rutes entre l'entitat de dades assignada i l'entitat *Client*, heu de triar un dels [camins de relació d'entitat](relationships.md) identificats. Els resultats de la mesura poden variar en funció del camí seleccionat.

   1. Seleccioneu el **Camí de la relació** i trieu el camí d'entitat que s'ha d'utilitzar per identificar la mesura. Si només hi ha un camí a l'entitat *Client*, aquest control no es mostrarà.
   1. Seleccioneu **Fet** per aplicar la vostra selecció.

1. Per afegir més càlculs per a la mesura, seleccioneu **Càlcul nou**. Només podeu utilitzar les entitats al mateix camí d'entitat per als càlculs nous. Més càlculs es mostraran com a columnes noves a l'entitat de sortida de mesura.

1. Seleccioneu **...** en el càlcul per **duplicar**, **canviar el nom** o **suprimir** un càlcul d'una mesura.

1. A l'àrea **Visualització prèvia**, veureu l'esquema de dades de l'entitat de sortida de mesura, incloent-hi els filtres i dimensions. La visualització prèvia reacciona dinàmicament als canvis a la configuració.

1. Seleccioneu **Edita els detalls** que hi ha al costat del compàs sense títol. Donar un nom per a la mesura. Opcionalment, afegiu [etiquetes](work-with-tags-columns.md#manage-tags) al compàs.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Quadre de diàleg Edita els detalls.":::

1. Seleccioneu **Executa** per calcular els resultats de la mesura configurada. Seleccioneu **Desa i tanca** si voleu mantenir la configuració actual i executar la mesura més endavant.

1. Aneu a **Mesures** per veure la mesura que s'ha creat recentment a la llista.

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

Podeu crear mesures al nivell de comptes individuals (mesura del client) o al nivell de tots els comptes (mesura de negoci).

- Mesura del client: genera la sortida com a entitat pròpia. Les mesures del client no es mostren a la targeta de perfil del client.

- Mesura de negoci: genera la sortida com a entitat pròpia i es mostra a la pàgina d'inici de l'entorn del Customer Insights.

1. Aneu a **Mesures**.

1. Seleccioneu **Crea**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Pantalla de configuració buida per a un compàs B-to-B.":::

1. A l'àrea de configuració, trieu la funció d'agregació al menú desplegable Selecciona la **funció**. Les funcions d'agregació inclouen:
   - **Suma**
   - **Mitjana**
   - **Recompte**
   - **Compta únics**
   - **Màx**
   - **Min**
   - **Primer**: pren el primer valor del registre de dades
   - **Últim**: pren l'últim valor que s'ha afegit al registre de dades

1. Seleccioneu **Afegeix un atribut** per seleccionar les dades que necessiteu per crear aquesta mesura.

   1. Seleccioneu la pestanya **Atributs**.
   1. Entitat de dades: trieu l'entitat que inclou l'atribut que voleu mesurar.
   1. Atribut de dades: trieu l'atribut que voleu utilitzar a la funció d'agregació per calcular la mesura. Només podeu seleccionar un atribut cada vegada.
   1. Per seleccionar un atribut de dades d'una mesura existent, seleccioneu la pestanya **Mesures** o bé cerqueu una entitat o un nom de mesura.
   1. Seleccioneu **Afegeix** per afegir l'atribut seleccionat a la mesura.

1. Per crear mesures més complexes, podeu afegir més atributs o utilitzar operadors matemàtics a la funció de mesura.

1. Per afegir filtres, seleccioneu el **Filtre** a l'àrea de configuració. L'aplicació de filtres només utilitzarà els registres que coincideixin amb els filtres per calcular la mesura.
  
   1. A la secció **Afegeix un atribut** de la subfinestra **Filtres**, seleccioneu l'atribut que voleu utilitzar per crear filtres.
   1. Definiu els operadors de filtre per definir el filtre per a cada atribut seleccionat.
   1. Seleccioneu **Aplica** per afegir els filtres a la mesura.

1. Seleccioneu **Dimensió** per triar més camps que s'afegeixin com a columnes a l'entitat de sortida de compàs.

   1. Seleccioneu **Edita les dimensions** per afegir atributs de dades pels quals voleu agrupar els valors de mesura. Per exemple, ciutat o gènere.
      > [!TIP]
      > Si heu seleccionat **el nivell** de client com a **tipus** de mesura, l'atribut CustomerId *ja s'ha* afegit. Si suprimiu l'atribut, **el tipus** De compàs canvia al nivell **d'empresa**.
   1. Seleccioneu **Fet** per afegir les dimensions a la mesura.

1. Si hi ha valors a les dades que heu de substituir per un enter, seleccioneu **Regles**. Configureu la regla i assegureu-vos que trieu només els nombres enters com a substituts. Per exemple, substituïu *nul* per *0*.

1. Podeu utilitzar la **Genera un informe dels subcomptes** si [utilitzeu comptes amb jerarquies](relationships.md#set-up-account-hierarchies).
   - Si està definit com a **Desactivat**, la mesura es calcula per a cada compte. Cada compte té el seu propi resultat.
   - Si està definit com a **Activat**, seleccioneu **Edita** per triar la jerarquia de comptes segons les jerarquies ingerides. La mesura només produirà un resultat, perquè s'agrega amb subcomptes.

1. Si hi ha diversos rutes entre l'entitat de dades assignada i l'entitat *Client*, heu de triar un dels [camins de relació d'entitat](relationships.md) identificats. Els resultats de la mesura poden variar en funció del camí seleccionat.

   1. Seleccioneu el **Camí de la relació** i trieu el camí d'entitat que s'ha d'utilitzar per identificar la mesura. Si només hi ha un camí a l'entitat *Client*, aquest control no es mostrarà.
   1. Seleccioneu **Fet** per aplicar la vostra selecció.

1. Seleccioneu **...** en el càlcul per **duplicar**, **canviar el nom** o **suprimir** un càlcul d'una mesura.

1. A l'àrea **Visualització prèvia**, veureu l'esquema de dades de l'entitat de sortida de mesura, incloent-hi els filtres i dimensions. La visualització prèvia reacciona dinàmicament als canvis a la configuració.

1. Seleccioneu **Edita els detalls** que hi ha al costat del compàs sense títol. Donar un nom per a la mesura. Opcionalment, afegiu [etiquetes](work-with-tags-columns.md#manage-tags) al compàs.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Quadre de diàleg Edita els detalls.":::

1. Seleccioneu **Executa** per calcular els resultats de la mesura configurada. Seleccioneu **Desa i tanca** si voleu mantenir la configuració actual i executar la mesura més endavant.

1. Aneu a **Mesures** per veure la mesura que s'ha creat recentment a la llista.
