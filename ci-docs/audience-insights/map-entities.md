---
title: Assignar entitats i atributs per a la unificació de dades
description: Seleccioneu les entitats, els atributs, les claus principals i els tipus semàntics per assignar les dades al perfil de client unificat.
ms.date: 10/18/2020
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 81f1e97dfbecd9292c50529ca21da8dab9295b5d
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354946"
---
# <a name="map-entities-and-attributes"></a>Assignar entitats i atributs

L'**assignació** és la primera fase del procés d'unificació de dades de les conclusions del públic. L'assignació consta de tres fases:

- *Selecció d'entitats*: identifiqueu les entitats combinables que condueixen a un conjunt de dades amb informació més completa sobre els clients.
- *Selecció d'atributs*: per a cada entitat, identifiqueu les columnes que voleu combinar i conciliar en les fases de *concordança* i *combinació*. Aquestes columnes s'anomenen *Atributs*.
- *Selecció de clau principal i tipus semàntic*: per a cada entitat, identifiqueu un atribut que vulgueu definir com a clau principal per a l'entitat i per a cada atribut, identifiqueu un tipus semàntic que descrigui millor l'atribut.

Per obtenir més informació sobre el flux general d'unificació de dades, vegeu [Unificar](data-unification.md).

## <a name="select-the-first-entities"></a>Seleccionar les primeres entitats

1. A les conclusions del públic, aneu a **Dades** > **Unifica** > **Assignació**.

2. Per iniciar la fase d'assignació, seleccioneu **Selecciona entitats**.

3. Seleccioneu les entitats i els atributs que voleu utilitzar a les fases de *coincidència* i *combinació*. Podeu seleccionar els atributs necessaris individualment d'una entitat o incloure tots els atributs d'una entitat seleccionant la casella de selecció **Inclou tots els camps** del nivell d'entitat. Es recomana seleccionar com a mínim dues entitats per beneficiar-se del procés d'unificació de dades.

   > [!div class="mx-imgBorder"]
   > ![Exemple d'addició d'entitats.](media/data-manager-configure-map-add-entities-example.png "Exemple d'addició d'entitats")

   En aquest exemple, estem afegint les entitats **eCommerceContacts** i **loyCustomers**. En triar aquestes entitats, podeu derivar informació sobre els client de quina empresa en línia són membres del programa de fidelització.
   
   Podeu fer cerques per paraules clau a tots els atributs i les entitats per seleccionar els atributs necessaris que voleu assignar.
   
     > [!div class="mx-imgBorder"]
   > ![Exemple de camps de cerca.](media/data-manager-configure-map-search-fields-example.png "Exemple de camps de cerca")

4. Seleccioneu **Aplica** per confirmar les seleccions.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Seleccioneu la clau principal i el tipus semàntic per als atributs

Després de seleccionar les entitats, la pàgina **Assignació** enumera les entitats seleccionades per a la revisió. Definiu la clau principal per a una entitat i identifiqueu el tipus semàntic per a un atribut a l'entitat.

- **Clau principal**: seleccioneu un atribut com a clau principal per a cadascuna de les entitats. Per tal que un atribut sigui una clau principal vàlida, no hauria d'incloure valors duplicats, valors que faltin o valors nuls. Els atributs del tipus de dades de cadena, enter i GUID s'admeten com a claus principals i es mostraran en un camp perquè els seleccioneu.

- **Tipus semàntic d'atribut**: categories dels atributs, com ara l'adreça electrònica o el nom. Per utilitzar models d'IA per a la predicció intel·ligent de la semàntica, estalviar temps i millorar la precisió, establiu **Assignació intel·ligent** a **Activada**. L'assignació intel·ligent destaca la recomanació semàntica basada en IA en el camp **Tipus**. Si la establiu a **Desactivada**, veureu les nostres recomanacions normals d'assignació. Podeu seleccionar qualsevol tipus semàntic de la llista d'opcions disponibles i substituir la selecció suggerida.

> [!div class="mx-imgBorder"]
> ![Tipus d'atribut i predicció semàntica.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipus d'atribut i predicció semàntica")

L'addició d'un tipus semàntic d'entitat personalitzat també és possible. Seleccioneu el camp de tipus per a un atribut i escriviu el nom del tipus semàntic de l'atribut personalitzat. D'aquesta manera, també podeu canviar els tipus d'atribut que s'han identificat pel sistema.

Tots els atributs per als quals s'identifica automàticament un tipus semàntic es classifiquen a la secció **Revisió dels camps assignats**. Reviseu aquests atributs i els seus tipus semàntics perquè s'utilitzaran per combinar les entitats al pas de combinació d'unificació de dades.

Els atributs que no estan assignats automàticament a un tipus semàntic s'agrupen a la secció **Definiu les dades als camps no assignats**. Seleccioneu el camp tipus semàntic per als atributs no assignats o introduïu el nom del tipus d'atribut personalitzat.

> [!div class="mx-imgBorder"]
> ![Clau principal i tipus d'atribut.](media/data-manager-configure-map-add-attributes.png "Clau principal i tipus d'atribut")

> [!NOTE]
> Un camp hauria d'assignar-se a l'usuari de tipus semàntic Person.FullName per emplenar el nom del client a la targeta del client. Altrament, les targetes del client apareixeran sense nom. 

## <a name="add-and-remove-attributes-and-entities"></a>Afegir i suprimir atributs i entitats

1. A **Unifica** > **Assigna**, seleccioneu **Edita els camps**.

2. A la subfinestra **Edita els camps**, afegiu o suprimiu els atributs i les entitats. Utilitzeu la cerca o desplaçament per cercar i seleccionar els atributs i les entitats d'interès. No podeu suprimir un atribut ni una entitat si ja s'han assignat.

   > [!div class="mx-imgBorder"]
   > ![Afegir o suprimir atributs.](media/configure-data-map-edit.png "Afegir o suprimir atributs")

3. Seleccioneu **Aplica**.

## <a name="add-images-to-profiles"></a>Afegir imatges als perfils

Si una entitat conté URL d'imatges de perfil o logotips disponibles públicament, podeu afegir-los al perfil del client unificat.

Seleccioneu l'entitat i cerqueu el camp que conté l'adreça URL a la imatge de perfil. Al camp d'entrada **Tipus** introduïu manualment el valor següent: 
- Per a una persona: Person.ProfileImage
- Per a una organització: Organization.LogoImage

Continueu amb els passos d'unificació i assegureu-vos que l'atribut que conté l'adreça URL de la imatge també s'afegeixi al pas [Combinació](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Definir els atributs per a organitzacions

Per a les organitzacions (versió preliminar), cal que el tipus d'atribut s'assigni a "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Clau principal i tipus d'atribut d'empresa a empresa.](media/configure-data-map-edit-b2b.png "Clau principal i tipus d'atribut d'empresa a empresa")

## <a name="next-step"></a>Pas següent

Com a part del procés d'unificació de dades, aneu a la pàgina **Coincidència**. Visiteu [**Coincidència**](match-entities.md) per obtenir més informació sobre aquesta fase.

> [!TIP]
> Consulteu el vídeo següent: [Introducció: crear un perfil de client unificat](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]