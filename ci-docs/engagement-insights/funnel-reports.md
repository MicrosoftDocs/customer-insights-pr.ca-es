---
title: Informes de l'embut
description: Com s'utilitzen els informes d'embut per comprendre com el públic pren les decisions.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: efb10f2664630a5851d9582ff09c378c01777b96
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558801"
---
# <a name="create-and-manage-funnel-reports"></a>Crear i administrar informes d'embut

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un informe d'embut recopila informació sobre els passos que s'han produït durant un recorregut del client al lloc web o a l'aplicació mòbil. Us ajuda a entendre el progrés d'un públic a través d'un procés i identifica punts d'entrega. Per exemple, podeu utilitzar un informe d'embut per identificar les rutes que prenen els clients abans de fer una compra. Un informe d'embut proporciona dades per informar de les decisions i identificar àrees per a optimitzar i millorar processos.

## <a name="create-a-funnel-report"></a>Crear un informe d'embut

Per crear l'informe d'embut, especifiqueu els passos que voleu incloure-hi i l'activitat de cada pas. Una activitat és una [incidència](glossary.md) que representa el comportament de l'usuari. A l'informe d'embut es visualitza el nombre d'usuaris que han completat cada pas definit. 

1. Aneu a **Embuts** i seleccioneu **Embut nou** per iniciar un informe d'embut.

1. A l'**Editor d'embut**, a **Passos**, seleccioneu **+Afegeix un pas**. 

1. Introduïu un nom a **Títol del pas**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Informe d'embut nou.":::

1. Seleccioneu una **Activitat**. Una activitat registra quan un usuari visualitza una pàgina (activitat de **visualització**) o interactua amb el contingut (activitat d'**acció**).

1. Utilitzeu **Criteris de pas** per especificar les condicions de l'activitat. Les [dimensions](dimensions.md) són atributs que poden descriure, filtrar o agrupar dades.

1. O bé podeu configurar passos d'embut de diverses condicions. Seleccioneu **Afegeix una condició** per especificar més dimensions en un pas. Cal que altres criteris utilitzin el mateix tipus d'activitat. Podeu triar si hi ha diverses condicions connectades amb un operador I o un O.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Editor d'embut que mostra la configuració del pas amb passos de diverses condicions.":::

1. Seleccioneu **Afegeix un pas** fins que completeu tots els passos que voleu a l'informe.

1. Seleccioneu **Desa**, poseu un nom a l'informe i seleccioneu **Desa** una altra vegada. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Exemple: informe d'embut per a l'empresa Fourth Coffee

A l'escenari següent es mostra una manera d'utilitzar un informe d'embut. Un analista de l'empresa Fourth Coffee vol comprendre la influència d'una campanya recent sobre les taxes de subscripció. L'analista crea un informe d'embut per identificar l'activitat del client. Comença quan els clients arriben a la pàgina inicial de l'empresa fins que utilitzen el codi promocional de la subscripció. L'analista crea un informe d'embut amb els passos següents:

Pas 1: clients que entren a la pàgina inicial   
Pas 2: clients que fan una compra   
Pas 3: clients que utilitzen el codi promocional per obtenir un descompte en una subscripció   
Pas 4: inici de sessió de la subscripció   

:::image type="content" source="media/funnel-report-example.png" alt-text="exemple d'informe d'embut.":::
  
Aquest embut us permet veure el nombre d'usuaris que han utilitzat el codi de promocions després d'una compra única per registrar-se al programa de subscripció.

### <a name="configure-advanced-settings"></a>Configurar els paràmetres avançats 

Els informes d'embut permeten definir un límit segons el temps que triga a completar un embut. Per exemple, podeu definir l'hora per completar l'embut en quatre dies. Aquesta configuració només comptarà els registres de subscripció correctes que s'han produït en el termini de quatre dies des que un usuari visita la pàgina inicial.

1. Aneu a **Embuts** per obrir la **Biblioteca d'embuts**.

1. Seleccioneu un nom per obrir l'informe. 

1. A la subfinestra **Editor de l'embut**, seleccioneu **Configuració avançada**. 

1. Definiu el temps de finalització de l'embut límit a **Activat**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editor d'embut que mostra opcions avançades i opcions per limitar el temps per completar un embut.":::

1. Trieu l'hora a la qual s'ha d'haver completat l'embut a la llista desplegable **Defineix el límit a**.

1. Seleccioneu **Desa** per aplicar els canvis.


## <a name="cross-channel-funnel-reports"></a>Informes d'embut entre canals 

Les conclusions d'interacció també poden recopilar dades de clients de comportament a l'aplicació mòbil. Un cop hàgiu instrumentat l'aplicació mòbil amb l'[SDK de l'Android](get-started-android.md) o l'[SDK de l'iOS](get-started-ios.md), podeu crear informes d'embut entre canals. 

### <a name="create-a-cross-channel-funnel-report"></a>Crear un Informe d'embut entre canals 

1. Seguiu els passos per [crear un informe d'embut](#create-a-funnel-report).    

1. Per fer un seguiment de com els clients interactuen amb la vostra marca a tot el lloc web i a l'aplicació mòbil o a diversos llocs web, utilitzeu el commutador d'àrea de treball per crear passos d'embut amb dades d'altres àrees de treball. A l'**Editor d'embut**, a **Passos**, seleccioneu l'àrea de treball de la qual han de provenir les dades del pas d'embut.

## <a name="manage-funnel-reports"></a>Administra els informes d'embut

Podeu revisar els informes d'embut per analitzar dades, fer el seguiment del rendiment i recopilar informació.

> [!NOTE]
> - Actualment, els informes d'embut dels coneixements d'interacció admeten escenaris en què tots els usuaris de l'embut són anònims o tots els usuaris estan autenticats. 
> - L'historial de dades dels informes d'embut està disponible durant els darrers 30 dies.

### <a name="view-funnel-reports"></a>Visualitzar informes d'embut

1. Aneu a **Embuts** per obrir la **Biblioteca d'embuts**.
1. Seleccioneu un nom per obrir l'informe.    

### <a name="see-the-data-collected-for-a-report"></a>Veure les dades recopilades d'un informe   

Per veure informació sobre una fase

- Apuntar un pas de l'informe.

:::image type="content" source="media/funnel-step-data.png" alt-text="dades d'embut.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Canviar l'interval de dates de l'informe d'embut

1. Aneu a **Embuts** per obrir la **Biblioteca d'embuts**.

1. Seleccioneu un nom per obrir l'informe.

1. Obriu l'**interval de temps** i seleccioneu un període de temps nou de la llista o **Interval de dates fix** per especificar un interval de dates.

## <a name="edit-or-delete-funnel-reports"></a>Editar o suprimir informes d'embut

Podeu canviar el nom d'un informe d'embut, suprimir-lo o modificar-ne els passos.

### <a name="rename-or-delete-a-funnel-report"></a>Canviar el nom d'un informe d'embut o suprimir-lo

1. Aneu a **Embuts** per obrir la **Biblioteca d'embuts**. 

1. Seleccioneu **Més** al costat de l'informe que voleu canviar i trieu **Edita el nom** o **Suprimeix**.

### <a name="edit-a-funnel-step"></a>Editar un pas d'embut  

1. Aneu a **Embuts** per obrir la **Biblioteca d'embuts**. 

1. Seleccioneu un nom per obrir l'informe.

1. Seleccioneu el pas que voleu editar.

1. Seleccioneu **Editar**.

1. A l'**Editor d'embut**, actualitzeu la informació que voleu canviar.  

1. Seleccioneu **Desa**.

### <a name="reorder-a-funnel-step"></a>Reordenar un pas d'embut

1. Aneu a **Embuts** per obrir la **Biblioteca d'embuts**. 

1. Seleccioneu un nom per obrir l'informe.

1. Seleccioneu el pas que voleu reordenar.

1. Seleccioneu **Desplaça** i, a continuació, **Amunt**, **Avall**, **A la part superior** o **A la part inferior** per moure el pas.

### <a name="delete-a-funnel-step"></a>Suprimir un pas d'embut

1. Aneu a **Embuts** per obrir la **Biblioteca d'embuts**. 

1. Seleccioneu un nom per obrir l'informe.

1. Seleccioneu el pas que vulgueu eliminar i seleccioneu **Suprimeix**.

## <a name="funnel-insights"></a>Informació sobre l'embut 

Ara, la informació de la interacció ofereix informació sobre l'embut per als clients. Utilitzeu la informació sobre l'embut per obtenir informació més detallada sobre el comportament dels clients sobre els passos de l'informe de l'embut. En crear i desar un informe d'embut nou, la informació sobre l'embut es genera automàticament per a l'informe. 

:::image type="content" source="media/funnel-insights.png" alt-text="Conclusions d'embut.":::

> [!NOTE]
> Les conclusions d'embut només es poden generar per als passos d'embut que **no** inclouen dimensions personalitzades. Per generar conclusions d'embut per a tots els passos de l'embut, utilitzeu les dimensions predefinides de les conclusions d'interacció per crear els passos d'embut. 

Podeu visualitzar la informació sobre l'embut de les categories següents, als nivells principal i de pas: 

 - Taxa de conversió
 -    La taxa de conversió entre Finalització de compra i Compra és del 22%.
 - Temps de transició 
 -    El temps de conversió mitjà entre Carretó i Finalització de compra és de 23 minuts. 
 - Hora de finalització 
 -    La mitjana de temps que triguen els clients a completar l'embut és de 47 minuts. 

Utilitzeu aquesta informació per explorar més el comportament dels clients i comprendre millor els punts d'abandonament i les conversions de l'informe d'embut. 

Per comparar les conclusions de diferents passos, seleccioneu **Mostra el desglossament del pas** o **Compara amb altres passos** a les targetes de conclusions. Es mostrarà un gràfic de barres en què es comparen les mètriques de cada pas de l'embut. 

La informació d'embut es torna a calcular cada 24 hores o quan **deseu** l'informe d'embut. 

> [!NOTE]
> Per poder visualitzar la informació d'embut, heu de desar l'informe cada vegada que feu canvis. 

