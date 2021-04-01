---
title: Experiments amb Machine Learning Studio (clàssic)
description: Utilitzeu models basats en el Machine Learning Studio (clàssic) al Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 71881f7e1f9448fe0a7d6d92b8102b8b42de7c2a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598327"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Utilitzar models basats en el Machine Learning Studio (clàssic) de l'Azure

Les dades unificades del Dynamics 365 Customer Insights constitueixen un origen per a la creació de models d'aprenentatge automàtic que puguin generar informació addicional de negoci. El Customer Insights s'integra amb el Machine Learning Studio (clàssic) per utilitzar els vostres propis models personalitzats. Per veure com els models desenvolupats a l'aprenentatge automàtic de l'Azure s'integren amb el Customer Insights, vegeu els [experiments amb l'aprenentatge automàtic de l'Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Requisits previs

- Accés al Customer Insights
- Subscripció a l'Azure Enterprise activa
- [Perfils de client unificats](data-unification.md)
- [Exportació d'entitats a l'Azure Blob Storage](export-azure-blob-storage.md) configurada

## <a name="set-up-machine-learning-studio-classic"></a>Configurar el Machine Learning Studio (clàssic)

En un primer pas, necessitem crear una àrea de treball i obrir el Machine Learning Studio (clàssic).

1. Aneu a[https://www.portal.azure.com](https://www.portal.azure.com/) i inicieu la sessió.

1. Seleccioneu **Crea un recurs**.

1. Cerqueu **Àrea de treball del Machine Learning Studio** i seleccioneu **Crea**.

1. Introduïu els detalls necessaris per [crear l'àrea de treball](/azure/machine-learning/studio/create-workspace). Trieu el **nivell de preus del pla del servei web** segons la quantitat de dades que vulgueu importar. Per obtenir un millor rendiment, seleccioneu la **Ubicació** que us sigui geogràficament més propera.

1. Després de crear el recurs, es mostrarà l'escriptori digital de l'àrea de treball del Machine Learning Studio. Seleccioneu **Inicia el Machine Learning Studio**.

   ![Interfície de l'usuari de l'Azure Machine Learning Studio](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Treballar amb l'Azure Machine Learning Studio

Ara podeu crear un experiment nou o importar una plantilla d'experiments existent des de la galeria d'exemple. Hi ha experiments d'exemple corresponents a tres escenaris estàndard:

- [Predicció de rotació](#churn-analysis)

- [Valor del cicle de vida del client](#customer-lifetime-value-prediction)

- [Recomanació de productes o següent acció recomanada](#productrecommendation-or-next-best-action)

1. Si creeu un experiment nou o utilitzeu una plantilla d'experiments de la galeria, heu de configurar les propietats de les **Dades d'importació**. Utilitzeu l'experiència guiada o proporcioneu directament els detalls per accedir a l'emmagatzematge blob de l'Azure que conté les dades.  

   ![Experiment de l'Azure Machine Learning Studio](media/azure-machine-learning-studio-experiment.png)

1. Ara podeu crear un pipeline de processament personalitzat per netejar i preprocessar les dades, extreure'n característiques i entrenar un model adient.

1. Proveu i optimitzeu el rendiment del model.

1. Quan us satisfaci la qualitat d'un model, seleccioneu **Configura el servei web** > **Servei web predictiu**. Aquesta opció importa el model entrenat i el pipeline de caracterització de l'experiment d'entrenament a un servei predictiu. El servei predictiu pot utilitzar un altre conjunt de dades d'entrada amb l'esquema utilitzat a l'experiment d'entrenament per fer prediccions.

   ![Configurar un servei web predictiu](media/predictive-webservice-control.png)

1. Quan l'experiment del servei web predictiu tingueu èxit, podreu implementar-lo per a la planificació automàtica. Per fer que el servei web funcioni amb el Customer Insights, seleccioneu **Implementa el servei web** > **Implementa el servei web [Nou] Versió preliminar**. [Més informació sobre implementar un servei web](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Implementar un servei web predictiu](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Models d'exemple de la galeria

Farem servir un escenari fictici de l'Hotel Contoso per als models d'aquest article. L'Hotel Contoso recull les dades següents:

- Dades del CRM que consisteixen en l'activitat d'estades de l'hotel. El conjunt de dades inclou informació sobre les dates d'estada de cada client registrat. També conté informació sobre la reserva, els tipus d'habitacions, els detalls de les despeses, etc. Les dades abasten quatre anys, de gener del 2014 a gener del 2018.
- Perfils de client dels hostes de l'hotel. Aquests perfils contenen informació sobre cada client, com ara el nom, la data de naixement, l'adreça postal, el sexe i el número de telèfon.
- Ús dels serveis oferts per l'hotel, com ara spa, servei de bugaderia, Wi-Fi o missatgeria. Aquesta informació es registra per a cada client registrat. Normalment, l'ús dels serveis està enllaçat amb l'estada. En alguns casos, els clients poden utilitzar els serveis sense estar-se a l'hotel.

## <a name="churn-analysis"></a>Anàlisi de rotació

L'anàlisi de rotació s'aplica a diferents àrees de negoci. En aquest exemple, veurem el servei de rotació, concretament en el context dels serveis de l'hotel com es descriu més amunt. Proporciona un exemple d'un pipeline de model d'extrem a extrem que es pot utilitzar com a punt de partida per a qualsevol altre tipus de model de rotació.

### <a name="definition-of-churn"></a>Definició de rotació

La definició de rotació pot ser diferent en funció de l'escenari. En aquest exemple, un hoste que no ha visitat l'hotel durant l'últim any s'hauria d'etiquetar com a Rotació.  

La plantilla de l'experiment es pot importar des de la galeria. En primer lloc, assegureu-vos que importeu les dades corresponents a **Activitat d'estades de l'hotel**, **Dades dels clients** i **Dades d'ús del servei** des de l'emmagatzematge blob de l'Azure.

   ![Importar dades per al model de rotació](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Caracterització

En funció de la definició de rotació, primer identifiquem les característiques sense processar que influiran en l'etiqueta. A continuació, processem aquestes característiques i les convertim en característiques numèriques que es poden utilitzar amb models d'aprenentatge automàtic. Les dades s'integren al Customer Insights per tal que puguem unir aquestes taules mitjançant l'*ID de client*.

   ![Unir dades importades](media/join-imported-data.png)

La caracterització per a la creació del model per a l'anàlisi de rotació pot ser una mica complicada. Les dades són una funció de temps amb l'activitat de l'hotel nova registrada diàriament. Durant la caracterització, volem generar característiques estàtiques a partir de dades dinàmiques. En aquest cas, generem diverses característiques de l'activitat de l'hotel amb una finestra lliscant d'un any. També ampliem les característiques de categories, com ara el tipus d'habitació o el tipus de reserva, i les convertim en característiques separades mitjançant la codificació one-hot.  

Llista final de característiques:

| **Número**  | **Original_Column**          | **Característiques derivades**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Tipus d'habitació                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Tipus de reserva                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Categoria de viatge              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Dòlars gastats                | TotalDollarSpent                                                                                                                          |
| 5           | Dates d'entrada i sortida  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Ús de serveis                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Selecció del model

Ara hem de triar l'algoritme òptim que voleu utilitzar. En aquest cas, la majoria de les característiques es basen en característiques de categoria. Normalment, els models basats en arbres de decisions funcionen bé. Si només hi ha característiques numèriques, les xarxes neuronals serien una millor opció. Una màquina vectorial de suport (SVM) també és un bon candidat en aquestes situacions; tanmateix, necessita més ajustaments per obtenir-ne el millor rendiment. Escollim **Arbre de decisions potenciat per dues classes** com a primer model d'elecció seguit per **SVM de dues classes** com a segon model. L'Azure Machine Learning Studio us permet fer proves A/B, per la qual cosa és beneficiós començar amb dos models en comptes d'un.

A la imatge següent es mostra el pipeline d'entrenament i avaluació del model de l'Azure Machine Learning Studio:

![Model de rotació de l'Azure Machine Learning Studio](media/azure-machine-learning-model.png)

També apliquem una tècnica anomenada **Importància de característica de permutació**, un aspecte important de l'optimització de models. Els models integrats no tenen pràcticament cap impacte en qualsevol característica específica de la predicció final. La calculadora d'importància de característica utilitza un algoritme personalitzat per calcular la influència de les característiques individuals en el resultat d'un model específic. La importància de característica es normalitza entre +1 i -1. Una influència negativa significa que la característica corresponent té una influència poc intuïtiva en el resultat i s'hauria de suprimir del model. Una influència positiva indica que la característica contribueix en gran mesura a la predicció. Aquests valors no són coeficients de correlació perquè són mètriques diferents. Per obtenir més informació, vegeu [Importància de característica de permutació](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Trobareu [l'experiment de rotació sencer a la Galeria d'IA de l'Azure](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Predicció del valor del cicle de vida del client

El càlcul del valor del cicle de vida del client (CLTV) és una de les mètriques clau que una empresa pot utilitzar per avaluar i segmentar els seus clients. Per al negoci hoteler, és fonamental conèixer els clients. Per exemple, entendre els factors que defineixen els bons clients és informació crucial. Ajuda l'administració de l'hotel a avaluar les característiques en què necessita centrar-se i que necessita millorar per satisfer els clients d'alt potencial econòmic. Aquestes decisions poden tenir un impacte directe en les vendes i els guanys.  

### <a name="definition-of-cltv"></a>Definició del CLTV

En aquest exemple, definim el CLTV d'un client com l'import total en dòlars que s'espera que el client gasti en els pròxims 365 dies. Utilitzarem els últims tres anys de dades de tots els clients per predir aquest valor.

### <a name="featurization"></a>Caracterització

En aquest cas, la caracterització serà bastant semblant a l'escenari de rotació. No obstant això, les etiquetes i els valors previstos són diferents dels que s'han definit anteriorment.

### <a name="model-selection"></a>Selecció del model

Predir el CLTV és un problema de regressió, ja que el valor de predicció és una variable contínua que es valora positivament. En funció de les propietats de les característiques, seleccionem **Regressió d'arbre de decisions potenciat** com a algoritme i **Regressió de xarxa neuronal** com a algoritme addicional per l'aprenentatge del model.

## <a name="product-recommendation-or-next-best-action"></a>Recomanació de productes o següent acció recomanada

La recomanació de producte en un escenari de l'hotel s'interpreta com a serveis de recomanació oferts per l'hotel als clients. L'objectiu és triar els serveis adients per als clients per tal de maximitzar-ne l'ús. És similar a les recomanacions de pel·lícules per a usuaris de servei de transmissió de vídeos.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definició de recomanació de productes o següent acció recomanada

Definim l'objectiu com a maximitzar la quantitat de dòlars de l'ús del servei oferint els millors serveis als clients de l'hotel segons el seu interès.

### <a name="featurization"></a>Caracterització

Igual que el model de rotació, unim el valor de ServiceCustomerID de l'hotel amb el de CustomerID per crear recomanacions coherents per al valor de CustomerID.

![Caracterització del model de recomanacions](media/azure-machine-learning-model-featurization.png)

Les dades provenen de tres entitats diferents i característiques que se'n deriven. La caracterització del problema de recomanació és diferent en comparació amb els escenaris de rotació o del CLTV. El model de recomanació necessita introduir dades en tres conjunts de característiques.

### <a name="model-selection"></a>Selecció del model

Preveiem els productes o serveis mitjançant l'algoritme anomenat **Entrena el recomanador de Matchbox** per entrenar el model de recomanació.

![Algoritme de recomanació de productes](media/azure-machine-learning-model-recommendation-algorithm.png)

Els tres ports d'entrada per al model **Entrena el recomanador de Matchbox** utilitzen les dades d'ús del servei d'aprenentatge, la descripció del client (opcional) i la descripció del servei. Hi ha tres maneres diferents de puntuar el model. Una és per a l'avaluació de models en què es calcula una puntuació de guanys acumulats descomptats normalitzats (NDCG) per classificar els elements que s'han valorat. En aquest experiment, la puntuació de l'NDCG és 0,97. Les altres dues opcions puntuen el model en relació amb tot el catàleg de serveis recomanables o només els elements que els usuaris no han utilitzat abans.

Si ens fixem més en les distribucions de les recomanacions de tot el catàleg de serveis, veurem que els principals serveis que s'han de recomanar són el telèfon, el Wi-Fi i la missatgeria. Això és coherent amb el que hem trobat a les distribucions de les dades de consum del servei:

![Resultat del model de recomanació](media/azure-machine-learning-model-output.png)

Podeu accedir a [tot l'experiment de recomanació de productes a la Galeria d'IA de l'Azure.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrar models personalitzats

Per utilitzar aquestes prediccions al Customer Insights, heu d'**exportar** les prediccions juntament amb els ID de client. [Exporteu-los a la mateixa ubicació d'emmagatzematge de blob de l'Azure](/azure/storage/common/storage-import-export-data-from-blobs) que la ubicació a la qual exporteu les dades d'origen. El servei web predictiu es pot planificar per executar-se periòdicament i actualitzar les puntuacions.

Les dades generades pel model personalitzat es poden utilitzar per continuar enriquint les dades dels clients. Per obtenir més informació, vegeu [Models d'aprenentatge automàtic personalitzats](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]