---
title: Creeu mesures amb el creador de mesures
description: Creeu mesures des de zero per analitzar les mètriques clau sobre la vostra empresa.
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
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170837"
---
# <a name="create-measures-with-measure-builder"></a>Creeu mesures amb el creador de mesures

El creador de mesures us permet definir càlculs mitjançant operadors matemàtics, funcions d'agregació i filtres. Definiu mesures mitjançant atributs d'entitats relacionades amb l'entitat client *unificada*.

La creació de mesures en entorns B-to-C i B-to-B funciona de la mateixa manera. Tanmateix, si l'entorn [B-to-B utilitza comptes amb jerarquies](relationships.md#set-up-account-hierarchies), trieu si voleu agregar la mesura entre subcomptes relacionats.

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

Crear mesures a nivell de clients individuals (atribut de client, mesura de client) o a nivell d'empresa/organització (mesura empresarial). L'atribut del client i la mesura del client us permeten fer un seguiment del rendiment per client. Per exemple, la despesa total de cada client. Les mesures empresarials fan un seguiment del rendiment per empresa. Per exemple, els ingressos totals de l'empresa.

- Atribut de client: genera la sortida com un atribut nou, que es desa com una columna nova a l'entitat generada pel sistema anomenada *Customer_Measure*. En actualitzar un atribut de client, tots els altres atributs del client de l'entitat *Customer_Measure* s'actualitzen simultàniament. A més, els atributs de client es mostren a la targeta de perfil de client. Un cop executat o desat, no podeu canviar un atribut de client a una mesura de client.

- Mesura del client: genera la sortida com a entitat pròpia i no la podeu canviar a un atribut de client un cop executada o desada. Les mesures del client no es mostren a la targeta de perfil de client.

- Mesura de negoci: genera la sortida com a entitat pròpia i es mostra a la pàgina d'inici de l'entorn del Customer Insights.

1. Anar a **Mesures**.

1. Seleccioneu **Crea** > **Crea'n un de propi**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Pantalla de configuració buida per a una mesura de B a C." lightbox="media/measure-b2c.png":::

1. Seleccioneu **Edita els detalls** al costat de Mesura sense títol. Proporcioneu un nom per a la mesura. Opcionalment, afegiu [etiquetes](work-with-tags-columns.md#manage-tags) a la mesura.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Edita els detalls del quadre de diàleg.":::

1. Seleccioneu **Fet**.

1. Per fer un seguiment del rendiment a nivell empresarial, commuta **El tipus** de mesura al **nivell** d'empresa. **El nivell** de client està seleccionat per defecte. **El nivell** de client afegeix automàticament l'atribut *CustomerId* a Dimensions mentre que **el nivell** d'empresa l'elimina automàticament.

1. A l'àrea de configuració, trieu la funció d'agregació al menú desplegable Selecciona la **funció**. Les funcions d'agregació inclouen:
   - **Suma**
   - **Mitjana**
   - **Recompte**
   - **Compta únics**
   - **Màx**
   - **Min**
   - **Primer**: pren el primer valor del registre de dades
   - **Últim**: pren l'últim valor que s'ha afegit al registre de dades
   - **ArgMax**: troba el registre de dades donant el màxim valor d'una funció objectiu
   - **ArgMin**: troba el registre de dades donant el valor mínim d'una funció de destinació

1. Seleccioneu **Afegeix un atribut** per seleccionar les dades per crear aquesta mesura.

   1. Seleccioneu la pestanya **Atributs**.
   1. Entitat de dades: trieu l'entitat que inclou l'atribut que voleu mesurar.
   1. Atribut de dades: trieu l'atribut que voleu utilitzar a la funció d'agregació per calcular la mesura. Només podeu seleccionar un atribut cada vegada.
   1. Opcionalment, trieu un atribut de dades d'una mesura existent seleccionant la **pestanya Mesures** o cerqueu un nom d'entitat o mesura.
   1. Seleccioneu **Afegeix**.

1. Per crear mesures més complexes, afegiu més atributs o utilitzeu operadors matemàtics a la funció de mesura.

1. Per afegir filtres, seleccioneu el **Filtre** a l'àrea de configuració. En l'aplicació de filtres només s'utilitzaran els registres que coincideixin amb els filtres per calcular la mesura.
  
   1. A la secció **Afegeix un atribut** de la subfinestra **Filtres**, seleccioneu l'atribut que voleu utilitzar per crear filtres.
   1. Definiu els operadors de filtre per definir el filtre per a cada atribut seleccionat.
   1. Seleccioneu **Aplica**.

1. Seleccioneu **Dimensió** per triar més camps per afegir com a columnes a l'entitat de sortida de la mesura.

   1. Seleccioneu **Edita les dimensions** per afegir atributs de dades pels quals voleu agrupar els valors de mesura. Per exemple, ciutat o gènere.
      > [!TIP]
      > Si heu seleccionat **el nivell** de client com a mesura, **l'atribut** *CustomerId* ja està afegit. Si suprimiu l'atribut, **Tipus de mesura** canvia a **Nivell d'empresa**.
   1. Seleccioneu **Fet**.

1. Si hi ha valors a les dades que s'han de substituir per un nombre enter, seleccioneu **Regles**. Configureu la regla i assegureu-vos que trieu només els nombres enters com a substituts. Per exemple, substituïu *nul* per *0*.

1. Si hi ha diversos camins entre l'entitat de dades que heu mapejat i l'entitat *Client*, trieu un dels camins de relació d'entitat [identificats](relationships.md). Els resultats de la mesura poden variar en funció del camí seleccionat.

   1. Seleccioneu el **Camí de la relació** i trieu el camí d'entitat que s'ha d'utilitzar per identificar la mesura. Si només hi ha un camí a l'entitat *Client*, aquest control no es mostrarà.
   1. Seleccioneu **Fet**.

1. Per afegir més càlculs per a la mesura, seleccioneu **Càlcul nou**. Utilitzeu només entitats del mateix camí d'entitat per a càlculs nous. Més càlculs es mostraran com a columnes noves a l'entitat de sortida de mesura. Opcionalment, seleccioneu **Edita el nom** per crear un nom per al càlcul.

1. Seleccioneu l'el·lipsi vertical (&vellip;) del càlcul a **Duplicar** o **Treure** un càlcul d'una mesura.

1. A l'àrea **Visualització prèvia**, veureu l'esquema de dades de l'entitat de sortida de mesura, incloent-hi els filtres i dimensions. La visualització prèvia reacciona dinàmicament als canvis a la configuració.

1. Seleccioneu **Executa** per calcular els resultats de la mesura configurada. Seleccioneu **Desa i tanca** si voleu mantenir la configuració actual i executar la mesura més endavant. Es **mostra la pàgina Mesures**.

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

Creeu mesures a nivell de comptes individuals (mesura del client) o al nivell de tots els comptes (mesura empresarial).

- Mesura del client: Genera la sortida com a entitat pròpia. Les mesures del client no es mostren a la targeta de perfil de client.

- Mesura de negoci: genera la sortida com a entitat pròpia i es mostra a la pàgina d'inici de l'entorn del Customer Insights.

1. Anar a **Mesures**.

1. Seleccioneu **Crea**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Pantalla de configuració buida per a una mesura de B a B.":::

1. Seleccioneu **Edita els detalls** al costat de Mesura sense títol. Proporcioneu un nom per a la mesura. Opcionalment, afegiu [etiquetes](work-with-tags-columns.md#manage-tags) a la mesura. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Edita els detalls del quadre de diàleg.":::

1. Seleccioneu **Fet**.

1. A l'àrea de configuració, trieu la funció d'agregació al menú desplegable Selecciona la **funció**. Les funcions d'agregació inclouen:
   - **Suma**
   - **Mitjana**
   - **Recompte**
   - **Compta únics**
   - **Màx**
   - **Min**
   - **Primer**: pren el primer valor del registre de dades
   - **Últim**: pren l'últim valor que s'ha afegit al registre de dades

1. Seleccioneu **Afegeix un atribut** per seleccionar les dades per crear aquesta mesura.

   1. Seleccioneu la pestanya **Atributs**.
   1. Entitat de dades: trieu l'entitat que inclou l'atribut que voleu mesurar.
   1. Atribut de dades: trieu l'atribut que voleu utilitzar a la funció d'agregació per calcular la mesura. Només podeu seleccionar un atribut cada vegada.
   1. Opcionalment, trieu un atribut de dades d'una mesura existent seleccionant la **pestanya Mesures** o cerqueu un nom d'entitat o mesura.
   1. Seleccioneu **Afegeix** per afegir l'atribut seleccionat a la mesura.

1. Per crear mesures més complexes, afegiu més atributs o utilitzeu operadors matemàtics a la funció de mesura.

1. Per afegir filtres, seleccioneu el **Filtre** a l'àrea de configuració. En l'aplicació de filtres només s'utilitzaran els registres que coincideixin amb els filtres per calcular la mesura.
  
   1. A la secció **Afegeix un atribut** de la subfinestra **Filtres**, seleccioneu l'atribut que voleu utilitzar per crear filtres.
   1. Definiu els operadors de filtre per definir el filtre per a cada atribut seleccionat.
   1. Seleccioneu **Aplica** per afegir els filtres a la mesura.

1. Seleccioneu **Dimensió** per triar més camps per afegir com a columnes a l'entitat de sortida de la mesura.

   1. Seleccioneu **Edita les dimensions** per afegir atributs de dades pels quals voleu agrupar els valors de mesura. Per exemple, ciutat o gènere.
      > [!TIP]
      > L'atribut *CustomerId* ja s'ha afegit indicant que es tracta d'un tipus de mesura a nivell de client. Si suprimeixes l'atribut, el tipus de mesura canviarà al nivell d'empresa.
   1. Seleccioneu **Fet** per afegir les dimensions a la mesura.

1. Si hi ha valors a les dades que s'han de substituir per un nombre enter, seleccioneu **Regles**. Configureu la regla i assegureu-vos que trieu només els nombres enters com a substituts. Per exemple, substituïu *nul* per *0*.

1. Si utilitzeu [comptes amb jerarquies](relationships.md#set-up-account-hierarchies), reviseu **Acumula els subcomptes**.
   - Si està definit com a **Desactivat**, la mesura es calcula per a cada compte. Cada compte obté el seu propi resultat.
   - Si està definit com a **Activat**, seleccioneu **Edita** per triar la jerarquia de comptes segons les jerarquies ingerides. La mesura només donarà un resultat perquè està agregat amb subcomptes.

1. Si hi ha diversos camins entre l'entitat de dades que heu mapejat i l'entitat *Client*, trieu un dels camins de relació d'entitat [identificats](relationships.md). Els resultats de la mesura poden variar en funció del camí seleccionat.

   1. Seleccioneu el **Camí de la relació** i trieu el camí d'entitat que s'ha d'utilitzar per identificar la mesura. Si només hi ha un camí a l'entitat *Client*, aquest control no es mostrarà.
   1. Seleccioneu **Fet** per aplicar la vostra selecció.

1. Seleccioneu l'el·lipsi vertical (&vellip;) del càlcul a **Duplicar** o **Treure** un càlcul d'una mesura.

1. A l'àrea **Visualització prèvia**, veureu l'esquema de dades de l'entitat de sortida de mesura, incloent-hi els filtres i dimensions. La visualització prèvia reacciona dinàmicament als canvis a la configuració.

1. Seleccioneu **Executa** per calcular els resultats de la mesura configurada. Seleccioneu **Desa i tanca** si voleu mantenir la configuració actual i executar la mesura més endavant. Es **mostra la pàgina Mesures**.

---

## <a name="next-step"></a>Pas següent

Utilitzeu les mesures existents per crear [un segment](segments.md) de clients.

[!INCLUDE [footer-include](includes/footer-banner.md)]
