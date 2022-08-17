---
title: Informació general sobre les connexions (versió preliminar)
description: Connexions amb altres serveis des del Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245499"
---
# <a name="connections-preview-overview"></a>Informació general sobre les connexions (versió preliminar)

Les connexions són la clau per permetre l'ús compartit de dades al i des del Customer Insights. Cada connexió estableix l'ús compartit de dades amb un servei específic. Utilitzeu connexions per [configurar enriquiments](enrichment-hub.md) de tercers i [configurar les exportacions](export-destinations.md). La mateixa connexió es pot utilitzar diverses vegades. Per exemple, una connexió al Dynamics 365 Marketing funciona per a diverses exportacions i es pot utilitzar una connexió de Leadspace per a diverses millores.

## <a name="export-connections"></a>Exportar connexions

Només els administradors poden configurar connexions noves, però poden [concedir accés als col·laboradors](#allow-contributors-to-use-a-connection-for-exports) per utilitzar connexions existents. Els administradors controlen on poden anar les dades, els col·laboradors defineixen la càrrega i la freqüència que s'ajusten a les seves necessitats.

## <a name="enrichment-connections"></a>Connexions d'enriquiment

Només els administradors poden configurar noves connexions, però les connexions creades sempre estan disponibles tant per als administradors com per als col·laboradors. Els administradors administren les credencials i donen el consentiment per a les transferències de dades. A continuació, les connexions es poden utilitzar per a enriquiments dels administradors i els col·laboradors.

## <a name="add-a-new-connection"></a>Afegir una connexió nova

### <a name="prerequisites"></a>Requisits previs

- [Permisos d'administrador](permissions.md)
- Altres serveis de Microsoft, si n'hi ha, es troben a la mateixa organització

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu **Afegeix connexió** i trieu el tipus de connexió que voleu crear. O bé, aneu a la **pestanya Descobreix** i seleccioneu **Configura** en una peça de connexió.

1. Doneu a la connexió un nom reconeixible al camp **Nom de visualització**. El nom i el tipus de connexió descriuen aquesta connexió. Us recomanem que trieu un nom que expliqui la finalitat i l'objectiu de la connexió.

1. Introduïu els detalls necessaris. Els camps exactes depenen del servei al qual us connecteu. Per obtenir més informació sobre un tipus de connexió específic, consulteu l'article sobre el servei de destinació.

1. Si [utilitzeu el vostre propi magatzem de claus](use-azure-key-vault.md) per emmagatzemar secrets, activeu **Utilitza Key Vault** i trieu el secret de la llista.

1. Reviseu la privadesa i el compliment de les dades i seleccioneu **Accepto**.

1. Seleccioneu **Desa** per crear la connexió.

### <a name="data-privacy-and-compliance"></a>Compliment i privadesa de les dades

Quan habiliteu Dynamics 365 Customer Insights per transmetre dades a tercers o altres productes de Microsoft, permeteu la transferència de dades fora del límit de compliment, Dynamics 365 Customer Insights incloses les dades potencialment sensibles, com ara les dades personals. Microsoft transferirà aquestes dades segons les vostres instruccions, però sou responsable d'assegurar-vos que el tercer compleixi qualsevol obligació de privadesa o seguretat que pugueu tenir. Per obtenir més informació, vegeu la [Declaració de privadesa de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

L'administrador Dynamics 365 Customer Insights pot suprimir la connexió en qualsevol moment per interrompre l'ús de la funcionalitat.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permetre que els col·laboradors utilitzin una connexió per a les exportacions

Quan configureu o editeu una connexió d'exportació, trieu quins usuaris poden utilitzar aquesta connexió específica per definir [les exportacions](export-destinations.md). Per defecte, una connexió està disponible per als usuaris amb una funció d'administrador. Canvieu l'opció **Tria qui pot utilitzar aquesta configuració de connexió** per permetre que els usuaris amb rol de col·laborador utilitzin aquesta connexió.

- Els col·laboradors no podran visualitzar ni editar la connexió. Només veuran el nom de visualització i el seu tipus quan creïn una exportació.
- Mitjançant l'ús compartit d'una connexió, permeteu que els col·laboradors utilitzin una connexió. Els col·laboradors veuran les connexions compartides quan configurin exportacions. Poden administrar totes les exportacions que utilitzin aquesta connexió específica.
- Podeu canviar aquesta configuració mantenint les exportacions que ja han estat definides pels col·laboradors.

## <a name="manage-existing-connections"></a>Administrar les connexions existents

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu la **pestanya Enriquiment** o **Exportacions** per veure una llista de connexions d'enriquiment o exportació, el tipus de connexió, quan es va crear i qui hi té accés. Podeu ordenar la llista de connexions per qualsevol columna.

1. Seleccioneu la connexió per visualitzar les accions disponibles.

   - **Editeu** la connexió.
   - [**Suprimiu**](#remove-a-connection) una connexió.

### <a name="remove-a-connection"></a>Suprimir una connexió

Si la connexió que suprimiu s'utilitza per enriquiments o exportacions, primer desprengueu-los o traieu-los. El diàleg d'eliminació us guia cap als enriquiments o exportacions pertinents.

> [!TIP]
> Els enriquiments desactivats i les exportacions desvinculades queden inactives. Els reactiveu afegint-hi una altra connexió a la pàgina [Enriquiments](enrichment-hub.md) o [Exportacions](export-destinations.md).

1. Aneu a **Administració** > **Connexions**.

1. Seleccioneu la **pestanya Enriquiment** o **Exportacions**.

1. Seleccioneu la connexió que voleu suprimir.

1. Seleccioneu **Suprimeix** al menú desplegable. Apareix un quadre de diàleg de confirmació.

   1. Si hi ha enriquiments o exportacions que utilitzen aquesta connexió, seleccioneu el botó per veure què utilitza la connexió.
      - **Exportacions: selecciona** aquesta opció per **eliminar** l'exportació o **"Desprendre la connexió**". La separació de la connexió manté la configuració d'exportació, però no s'executarà fins que s'hi afegeixi una altra connexió.
      - **Enriquiments:** trieu **eliminar** o **desactivar** els enriquiments.
   1. Quan la connexió no té més dependències, torneu a **Administració** > **Connexions** i torneu a provar de suprimir la connexió.

1. Per confirmar la supressió, seleccioneu **Suprimeix**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurar les connexions amb els secrets administrats pel vostre propi Key Vault

Algunes connexions necessiten secrets com ara les claus de l'API o les contrasenyes. Algunes connexions admeten secrets emmagatzemats al vostre propi Key Vault. Obteniu més informació sobre les connexions admeses i sobre com podeu configurar-les al [vostre propi Key Vault for Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
