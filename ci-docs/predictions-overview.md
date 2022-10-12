---
title: Informació general sobre les prediccions
description: Situacions i opcions de predicció cobertes per l'aplicació del Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610178"
---
# <a name="predictions-overview"></a>Informació general sobre les prediccions

El Dynamics 365 Customer Insights inclou diverses opcions que poden utilitzar l'IA i l'aprenentatge automàtic per predir dades.

## <a name="out-of-box-models"></a>Models de sèrie

La manera més fàcil de començar amb la predicció de dades són els models predefinits, que sovint es coneixen com a models de sèrie. Només necessiten determinades dades i estructura per generar informació ràpidament. Hi ha disponibles els models següents:

# <a name="individual-consumers-b-to-c"></a>[Consumidors individuals (d'empresa a consumidor)](#tab/b2c)

- [Valor de vida dels clients](predict-customer-lifetime-value.md): preveu els ingressos potencials d'un client durant tota la interacció amb una empresa.
- [Recomanació de producte](predict-product-recommendation.md): suggereix conjunts de recomanacions de productes predictives a partir del comportament de compra i dels clients amb patrons de compra similars.
- [Cancel·lació de subscripció](predict-subscription-churn.md): prediu si un client està en risc de deixar d'utilitzar els productes o serveis de subscripció de la vostra empresa.
- [Churn](predict-transactional-churn.md) transaccional: Prediu si un client individual ja no comprarà els vostres productes o serveis en un període de temps determinat.
- [Anàlisi](sentiment-analysis.md) de sentiments: Analitza el sentiment dels comentaris dels clients i identifica els aspectes empresarials que s'esmenten amb freqüència.

# <a name="business-accounts-b-to-b"></a>[Comptes d'empresa (d'empresa a empresa)](#tab/b2b)

- [Churn](predict-transactional-churn.md) transaccional: Prediu si un compte de client deixarà de comprar els vostres productes o serveis en un període de temps determinat.

---

> [!TIP]
> Us recomanem que actualitzeu regularment els models estàndard amb dades actualitzades per assegurar-vos que informin amb precisió el cas d'ús de la vostra empresa. Les dades s'actualitzen ad-hoc quan el sistema ingereix fonts de dades noves o actualitzades. No obstant això, els models només tornaran a aparèixer en aquest cas i continuaran utilitzant les dades d'entrenament existents.
>
> Configureu una planificació **d'actualitzacions** establint la planificació de reciclatge del model durant la configuració. El model es reciclarà i es moderarà en aquest horari, que podeu canviar en qualsevol moment.

## <a name="azure-machine-learning-integration"></a>Integració de l'aprenentatge automàtic de l'Azure

Si una organització ja utilitza escenaris d'aprenentatge automàtic basats en els experiments de d'aprenentatge automàtic de l'Azure, la característica de models personalitzats del Customer Insights ajuda a connectar els punts. Creeu fluxos de treball que us ajudin a triar les dades a partir de les qual voleu generar informació i assigneu els resultats als perfils de client unificats. Per obtenir més informació, vegeu [Models d'aprenentatge automàtic personalitzats](custom-models.md).

## <a name="manage-existing-predictions"></a>Gestionar les prediccions existents

Aneu a la pàgina Prediccions **d'intel** > **·ligència**. A la **pestanya Les meves prediccions**, visualitzeu les prediccions que heu creat, el tipus de predicció, el nom de l'entitat de sortida, l'estat, l'última vegada que es va editar el predicció i l'última vegada que es van actualitzar les dades. Podeu ordenar la llista de prediccions per qualsevol columna.

Seleccioneu un predicció per veure les accions disponibles.

:::image type="content" source="media/predictions.png" alt-text="La meva pàgina de prediccions.":::

- **Editeu** la predicció per canviar-ne les propietats.
- [**Actualitzeu**](#refresh-a-prediction) la predicció per incloure les dades més recents.
- **Consulteu** els detalls de la predicció.
- [**Introduïu l'informe d'usabilitat**](#view-the-input-data-usability-report) de dades per veure errors, advertiments i recomanacions.
- **Suprimiu** el predicció.

### <a name="refresh-a-prediction"></a>Actualitzar una predicció

Les prediccions es poden actualitzar amb una planificació automàtica o actualitzar-les manualment sota demanda. Per actualitzar manualment totes les prediccions, seleccioneu **Actualitza-ho tot**. Per actualitzar manualment un predicció, seleccioneu-lo i seleccioneu **Actualitza**. Per [programar una actualització](schedule-refresh.md) automàtica, aneu a **Planificació del sistema d'administració** > **·** > **·**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Visualitzar l'informe d'ús de dades d'entrada

L'informe d'ús de dades d'entrada proporciona una visualització consolidada dels errors i advertiments que poden generar les previsions de sèrie. També dóna recomanacions sobre com millorar el rendiment del model.

L'informe està disponible quan un model ha finalitzat el procés d'entrenament. Es crea per a cada model per separat, independentment de si va completar la formació amb èxit o no.

A la **pestanya Les meves prediccions**, seleccioneu el predicció i trieu **Informe d'usabilitat de dades d'entrada**. O bé, a la visualització de detalls de l'predicció, seleccioneu **Informe d'usabilitat de dades d'entrada**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemple d'un informe d'ús de dades d'entrada que mostra una taula amb errors, advertiments i recomanacions.":::

L'informe inclou:

- **Nom:** nom descriptiu de l'error, advertiment o recomanació.
- **Pas:** Fase model, tren o puntuació, la informació es refereix.
- **Estat:** Gravetat de la informació (error, advertència, recomanació).
- **Nom de la columna:** columna d'una entitat que cal modificar per millorar el rendiment del model.
- **Nom de l'entitat:** nom de l'entitat que cal modificar per millorar el rendiment del model.
- **Detalls:** detalls sobre l'error, l'advertiment o la recomanació.

[!INCLUDE [footer-include](includes/footer-banner.md)]
