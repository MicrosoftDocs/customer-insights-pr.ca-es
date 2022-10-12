---
title: Prediu la subscripció (conté vídeo)
description: Es prediu si un client està en risc de deixar d'utilitzar els productes o els serveis de la subscripció de l'empresa.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610224"
---
# <a name="predict-subscription-churn"></a>Predir la rotació de subscripcions

Es prediu si un client està en risc de deixar d'utilitzar els productes o els serveis de la subscripció de l'empresa. Les dades de subscripció inclouen subscripcions actives i inactives per a cada client, de manera que hi ha diverses entrades per identificador de client.

Heu de tenir coneixements empresarials per entendre què significa churn per al vostre negoci. Admetem definicions de churn basades en el temps, és a dir, es considera que un client ha batut un període de temps després que hagi finalitzat la seva subscripció.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Proveu el predicció de subscripció amb dades d'exemple: [xuclador de subscripcions predicció guia d'exemple](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Requisits previs

- Com a mínim, [permisos de col·laborador](permissions.md).
- Almenys 10 perfils de clients, preferiblement més de 1.000 clients únics.
- Identificador de client, un identificador únic per fer coincidir les subscripcions amb els vostres clients.
- Dades de subscripció durant almenys el doble de la finestra de temps seleccionada. Preferentment, de dos a tres anys de dades de subscripció. L'historial de subscripcions ha d'incloure:
  - **Identificador de subscripció:** identificador únic d'una subscripció.
  - **Data de finalització de la subscripció:** data en què caduca la subscripció per al client.
  - **Data d'inici de la subscripció:** data d'inici de la subscripció per al client.
  - **Data de transacció:** data en què s'ha produït un canvi de subscripció. Per exemple, un client que compra o cancel·la una subscripció.
  - **Es tracta d'una subscripció recurrent:** camp booleà true/false que determina si la subscripció es renovarà amb el mateix identificador de subscripció sense intervenció del client.
  - **Freqüència de recurrència (en mesos):** per a les subscripcions recurrents, el mes en què es renovarà la subscripció. Per exemple, una subscripció anual que es renova automàticament per a un client cada any durant un altre any té el valor 12.
  - **Import** de la subscripció: quantitat de moneda que un client paga per la renovació de la subscripció. Pot ajudar a identificar patrons per a diferents nivells de subscripcions.
- Almenys dos registres d'activitat per al 50% dels clients que voleu calcular. Les activitats del client han d'incloure:
  - **Clau primària:** identificador únic d'una activitat. Per exemple, una visita a un lloc web o un registre d'ús que mostra que el client ha vist un episodi d'un programa de televisió.
  - **Marca de temps:** data i hora de l'esdeveniment identificat per la clau principal.
  - **Esdeveniment:** nom de l'esdeveniment que voleu utilitzar. Per exemple, un camp anomenat "UserAction" d'un servei de transmissió de vídeos podria tenir el valor "Vist".
  - **Detalls:** informació detallada de la incidència. Per exemple, un camp anomenat "ShowTitle" d'un servei de transmissió de vídeos podria tenir el valor d'un vídeo que el client ha vist.
- Falten menys d'un 20% de valors al camp de dades de l'entitat proporcionada.

## <a name="create-a-subscription-churn-prediction"></a>Crear una predicció de rotació de subscripcions

Seleccioneu **Desa l'esborrany** en qualsevol moment per desar el predicció com a esborrany. L'esborrany predicció es mostra a la **pestanya Les meves prediccions**.

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Crea**, seleccioneu **Utilitza el model** a la **peça Model de churn** del client.

1. Seleccioneu **Subscripció** per al tipus de churn i, a continuació, **Comenceu**.

1. **Anomeneu aquest model** i el **nom de l'entitat de sortida** per distingir-los d'altres models o entitats.

1. Seleccioneu **Següent**.

### <a name="define-customer-churn"></a>Definició de l'abandonament de clients

1. Introduïu el nombre de **Dies des que ha finalitzat la subscripció** que l'empresa considera que un client pot estar en un estat de rotació. Aquest període sol estar vinculat a activitats empresarials, com ara ofertes o altres esforços de màrqueting que intenten evitar perdre el client.

1. Introduïu el nombre de **Dies per investigar el futur per predir el problema**. Per exemple, podeu predir el risc de rotació per als vostres clients en els pròxims 90 dies per alinear-lo amb les vostres estratègies de retenció de màrqueting. Predir el risc de cancel·lació durant períodes de temps més llargs o més curts pot dificultar donar resposta als factors del vostre perfil de risc de cancel·lació, en funció de les necessitats específiques de la vostra empresa.

1. Seleccioneu **Següent**.

### <a name="add-required-data"></a>Addició de les dades necessàries

1. Seleccioneu **Afegeix dades** per a l'historial **de** subscripcions.

1. Seleccioneu el tipus **d'activitat semàntica Subscripció** que conté la informació necessària de l'historial de subscripcions. Si l'activitat no s'ha configurat, seleccioneu **aquí** i creeu-la.

1. A **Activitats**, si els atributs d'activitat es van assignar semànticament quan es va crear l'activitat, trieu els atributs o l'entitat específics en què voleu centrar-vos en el càlcul. Si l'assignació semàntica no s'ha produït, seleccioneu **Edita** i assigna les dades.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Afegir les dades necessàries per al model de subscripció":::

1. Seleccioneu **Següent** i reviseu els atributs necessaris per a aquest model.

1. Seleccioneu **Desa**.

1. Seleccioneu **Afegeix dades** per a **les activitats** del client.

1. Seleccioneu el tipus d'activitat semàntica que proporciona la informació de l'activitat del client. Si l'activitat no s'ha configurat, seleccioneu **aquí** i creeu-la.

1. A **Activitats**, si els atributs d'activitat es van assignar semànticament quan es va crear l'activitat, trieu els atributs o l'entitat específics en què voleu centrar-vos en el càlcul. Si l'assignació semàntica no s'ha produït, seleccioneu **Edita** i assigna les dades.

1. Seleccioneu **Següent** i reviseu els atributs necessaris per a aquest model.

1. Seleccioneu **Desa**.

1. Afegiu més activitats o seleccioneu **Següent**.

### <a name="set-update-schedule"></a>Configurar la planificació d'actualització

1. Trieu la freqüència per reciclar el vostre model. Aquesta configuració és important per actualitzar la precisió de les prediccions a mesura que s'ingereixen dades noves al Customer Insights. La majoria d'empreses poden tornar a entrenar un cop al mes i obtenir una bona precisió de les prediccions.

1. Seleccioneu **Següent**.

### <a name="review-and-run-the-model-configuration"></a>Revisar i executar la configuració del model

El **pas Revisa i executa** mostra un resum de la configuració i proporciona l'oportunitat de fer canvis abans de crear el predicció.

1. Seleccioneu **Edita** en qualsevol dels passos per revisar i fer qualsevol canvi.

1. Si esteu satisfet amb les vostres seleccions, seleccioneu **Desa i executa** per començar a executar el model. Seleccioneu **Fet**. La **pestanya Les meves prediccions** es mostra mentre es crea el predicció. El procés pot tardar unes quantes hores a completar-se en funció de la quantitat de dades que s'han utilitzat a la predicció.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Veure predicció resultats

1. Aneu a Prediccions d'intel **·ligència** > **.**

1. A la **pestanya Les meves prediccions**, seleccioneu la predicció voleu visualitzar.

A la pàgina de resultats hi ha tres seccions principals de dades:

- **Rendiment del model de** formació: Els graus A, B o C indiquen el rendiment de la predicció i us poden ajudar a prendre la decisió d'utilitzar els resultats emmagatzemats a l'entitat de sortida.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Imatge del quadre d'informació de puntuació del model amb la nota A.":::

  Les qualificacions es determinen segons les regles següents:
  - **A** quan el model va predir amb precisió almenys el 50% de les prediccions totals, i quan el percentatge de prediccions precises per als clients que van xutar és superior a la mitjana històrica en almenys un 10%.
  - **B** quan el model va predir amb precisió almenys el 50% de les prediccions totals, i quan el percentatge de prediccions precises per als clients que van batre és fins a un 10% superior a la mitjana històrica.
  - **C** quan el model va predir amb precisió menys del 50% de les prediccions totals, o quan el percentatge de prediccions precises per als clients que van xutar és inferior a la mitjana històrica.
  
- **Probabilitat de rotació (nombre de clients)**: grups de clients segons el risc predit de rotació. Opcionalment, [creeu segments de clients](prediction-based-segment.md) amb alt risc de rebrot. Aquests segments ajuden a entendre on heu de definit la data límit de la subscripció del segment.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Gràfic que mostra la distribució dels resultats de rotació, desglossat en intervals entre 0-100%":::

- **Factors més influents:** hi ha molts factors que s'han de tenir en compte a l'hora de crear la predicció. Cadascun dels factors té la seva importància calculada per a les prediccions agregades que crea un model. Utilitzeu aquests factors per ajudar-vos a validar els resultats predicció. O utilitzeu aquesta informació més endavant per [crear segments](.//prediction-based-segment.md) que puguin ajudar a influir en el risc de rebrot per als clients.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Llista que mostra els factors influents i la seva importància en la predicció del resultat de rotació.":::

> [!NOTE]
> En l'entitat de sortida d'aquest model, *ChurnScore* és la probabilitat predita de churn i *IsChurn* és una etiqueta binària basada *en ChurnScore* amb llindar 0,5. Si aquest llindar predeterminat no funciona per al vostre escenari, [creeu un segment](segments.md) nou amb el llindar preferit. Per visualitzar la puntuació de churn, aneu a **Entitats** > **de dades** i visualitzeu la pestanya dades de l'entitat de sortida que heu definit per a aquest model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
