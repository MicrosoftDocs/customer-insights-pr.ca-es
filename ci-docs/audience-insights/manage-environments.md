---
title: Crear i administrar entorns
description: Apreneu a registrar-vos al servei i a administrar entorns.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491986"
---
# <a name="manage-environments"></a>Gestionar entorns

## <a name="switch-environments"></a>Canvi d'entorn

Seleccioneu el control **Entorn** a la part superior dreta de la pàgina per canviar d'entorns.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de pantalla del control per canviar d'entorn.":::

Els administradors poden [crear](create-environment.md) i administrar entorns.

## <a name="edit-an-existing-environment"></a>Editar un entorn existent

Podeu editar alguns dels detalls dels entorns existents.

1.  Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

2.  Seleccioneu la icona **Edita**.

3. Al quadre **Edita l'entorn** podeu actualitzar la configuració de l'entorn.

Per obtenir més informació sobre la configuració de l'entorn, vegeu [Crear un entorn nou](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Connectar a l’Microsoft Dataverse
   
El pas del **Microsoft Dataverse** us permet connectar el Customer Insights al vostre entorn del Dataverse. 

Proporcioneu el vostre propi Microsoft Dataverse entorn per compartir dades (perfils i estadístiques) amb aplicacions empresarials basades en, com ara Dataverse el Dynamics 365 Marketing o aplicacions basades en models a Power Apps.

Per utilitzar [models de predicció estàndard](predictions-overview.md#out-of-box-models) , configureu l'ús compartit de dades amb el Dataverse. O podeu habilitar la ingesta de dades des de fonts de dades locals, proporcionant l'adreça URL de l'entorn del Microsoft Dataverse que administra l'organització.

Si activeu l'ús compartit Microsoft Dataverse de dades, activeu la casella de selecció Compartició de dades, s'activarà una actualització completa de les fonts de dades i de tots els altres processos.

> [!IMPORTANT]
> 1. Customer Insights i Dataverse han d'estar a la mateixa regió per habilitar l'ús compartit de dades.
> 1. Heu de tenir una funció d'administrador global a l'entorn Dataverse. Comproveu si aquest [Dataverse entorn està associat](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinats grups de seguretat i assegureu-vos que esteu afegit a aquests grups de seguretat.
> 1. No hi ha cap entorn del Customer Insights existent associat amb aquest Dataverse entorn. Obteniu informació sobre com [podeu suprimir una connexió existent amb un Dataverse entorn](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Opcions de configuració per habilitar l'ús compartit de dades amb el Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Habilita l'ús compartit de dades amb Dataverse el vostre (Azure Data Lake Storage visualització prèvia)

Si el vostre entorn està configurat per utilitzar el vostre per Azure Data Lake Storage emmagatzemar dades del Customer Insights, permetre l'ús compartit de dades amb Microsoft Dataverse necessita una configuració addicional.

1. Creeu dos grups de seguretat a la vostra subscripció a l'Azure: un **grup de seguretat Lector** i un **grup de seguretat col·laborador** i definiu el Microsoft Dataverse servei com a propietari per a ambdós grups de seguretat.
2. Gestioneu la llista de control d'accés (ACL) al contenidor CustomerInsights del compte d'emmagatzematge a través d'aquests grups de seguretat. Afegiu el Microsoft Dataverse servei i qualsevol Dataverse aplicació empresarial basada en el Dynamics 365 Marketing al **grup de seguretat Lector** amb **permisos de només** lectura. Afegiu *només* l'aplicació Customers Insights al **grup de seguretat Col·laborador** per concedir permisos de **lectura i escriptura** per escriure perfils i estadístiques.
   
#### <a name="prerequisites"></a>Requisits previs

Per executar els scripts del PowerShell heu de tenir importats els tres mòduls següents. 

1. Instal·leu la versió més recent del [Azure Active Directory PowerShell per al Graph](/powershell/azure/active-directory/install-adv2).
   1. A l'ordinador, seleccioneu la tecla del Windows al teclat, cerqueu el **Windows PowerShell** i seleccioneu **Executa com a administrador**.
   1. A la finestra del PowerShell que s'obre, introduïu `Install-Module AzureAD`.
2. Importa tres mòduls.
    1. A la finestra powerShell, introduïu `Install-Module -Name Az.Accounts` i seguiu els passos. 
    1. Repetiu per `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Passos de configuració

1. Descarregueu els dos scripts de PowerShell que necessiteu executar des del repositori [github del](https://github.com/trin-msft/byol) nostre enginyer.
    1. `CreateSecurityGroups.ps1`
       - Necessiteu *permisos d'administrador d'inquilins* per executar aquest script del PowerShell. 
       - Aquest script del PowerShell crea dos grups de seguretat a la vostra subscripció a l'Azure. Un per al grup Lector i un altre per al grup Col·laborador i es farà Microsoft Dataverse servei com a propietari per a aquests dos grups de seguretat.
       - Executeu aquest script del PowerShell al Windows PowerShell proporcionant l'identificador de subscripció de l'Azure que conté el .Azure Data Lake Storage Obriu l'script del PowerShell en un editor per revisar la informació addicional i la lògica implementada.
       - Deseu els dos valors d'identificador del grup de seguretat generats per aquest script perquè els utilitzarem a l'script `ByolSetup.ps1`.
       
        > [!NOTE]
        > La creació de grups de seguretat es pot inhabilitar a l'inquilí. En aquest cas, es necessitaria una configuració manual i l'administrador hauria Azure AD d'habilitar la [creació](/azure/active-directory/enterprise-users/groups-self-service-management) de grups de seguretat.

    2. `ByolSetup.ps1`
        - Necessiteu *permisos del propietari* de dades del blob d'emmagatzematge al nivell de compte/contenidor d'emmagatzematge per executar aquest script o aquest script en crearà un per a vosaltres. L'assignació de rols es pot suprimir manualment després d'executar correctament l'script.
        - Aquest script del PowerShell afegeix el control d'accés basat en la tole (RBAC) necessari per al Microsoft Dataverse servei i per a qualsevol Dataverse aplicació empresarial basada en el servei. També actualitza la Llista de control d'accés (ACL) al contenidor CustomerInsights per als grups de seguretat creats amb l'script `CreateSecurityGroups.ps1`. El grup Col·laborador tindrà *permís rwx* i el grup Lectors només tindrà *permís r-x*.
        - Executeu aquest script del PowerShell al Windows PowerShell proporcionant l'identificador de subscripció de l'Azure que conté el vostre Azure Data Lake Storage, nom del compte d'emmagatzematge, nom del grup de recursos i els valors de l'identificador del grup de seguretat Lector i Col·laborador. Obriu l'script del PowerShell en un editor per revisar la informació addicional i la lògica implementada.
        - Copia la cadena de sortida després d'executar correctament l'script. La cadena de sortida té aquest aspecte: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Introduïu la cadena de sortida copiada des de dalt al **camp Identificador** de permisos del pas de configuració de l'entorn per a Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcions de configuració per habilitar l'ús compartit de dades des del vostre compte Azure Data Lake Storage amb Microsoft Dataverse.":::

El Customer Insights no admet els escenaris d'ús compartit de dades següents:
- Si habiliteu l'ús compartit de dades amb el Dataverse, no podreu [crear valors previstos o que falten en una entitat](predictions.md).
- Si habiliteu l'ús compartit de dades amb Dataverse, no podreu visualitzar cap informe opcional del PowerBI Embedded al vostre entorn del Customer Insights.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Suprimir una connexió existent a un Dataverse entorn

En connectar-se a un Dataverse entorn, el missatge **d'error Aquesta organització del CDS ja està connectada a una altra instància** del Customer Insights significa que l'entorn ja s'utilitza Dataverse en un entorn del Customer Insights. Podeu suprimir la connexió existent com a administrador global a l'entorn Dataverse. Pot trigar un parell d'hores a omplir els canvis.

1. Aneu al [Power Apps](https://make.powerapps.com).
1. Seleccioneu l'entorn del selectador d'entorns.
1. Anar a **solucions**
1. Desinstal·leu o suprimiu la solució anomenada **Dynamics 365 Customer Insights complement de targeta de client (visualització prèvia).**

O 

1. Obre el teu Dataverse entorn.
1. Aneu a **Configuració** > **avançadaSolutions**.
1. Desinstal·leu la **solució CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Copia la configuració de l'entorn

Com a administrador, podeu triar copiar la configuració des d'un entorn existent quan en creeu un de nou. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla de les opcions de configuració de la configuració de l'entorn.":::

Veureu una llista de tots els entorns disponibles a l'organització des d'on podeu copiar dades.

Es copia la configuració següent:

- Fonts de dades ingerides/importades
- Configuració d'unificació de dades (assignar, coincidir, combinar)
- Segments
- Mesures
- Relacions
- Activitats
- Cerca i filtra l'índex
- Destinacions d'exportació
- Actualització planificada
- Enriquiments
- Administració de models
- Assignacions de funcions

## <a name="set-up-a-copied-environment"></a>Configurar un entorn copiat

Quan copieu la configuració de l'entorn, les dades *següents no* es copien:

- Perfils de client.
- Credencials de la font de dades. Haureu de proporcionar les credencials de cada font de dades i actualitzar manualment les fonts de dades.
- Fonts de dades de la carpeta del Model de dades comú i del llac de dades administrat pel Dataverse. Haureu de crear aquestes fonts de dades manualment amb el mateix nom que a l'entorn d'origen.
- Secrets de connexió que s'utilitzen per a exportacions i enriquiments. Cal reautenticar les connexions i després reactivar els enriquiments i les exportacions. 

Quan copieu un entorn, veureu un missatge de confirmació que s'ha creat l'entorn nou. Seleccioneu **Ves a les fonts de dades** per veure la llista de fonts de dades.

Totes les fonts de dades mostraran l'estat **Credencials obligatòries**. Editeu les fonts de dades i introduïu les credencials per actualitzar-les.

:::image type="content" source="media/data-sources-copied.png" alt-text="Llista de fonts de dades que s'han copiat i que necessiten autenticació.":::

Després d'actualitzar les fonts de dades, aneu a **Dades** > **Unifica**. Aquí trobareu la configuració de l'entorn d'origen. Editeu-les segons calgui o seleccioneu **Executa** per iniciar el procés d'unificació de dades i crear l'entitat de client unificada.

Quan la unificació de dades hagi finalitzat, aneu a **Mesures** i **Segments** per actualitzar-los també.

Abans de reactivar les exportacions i els enriquiments, aneu a **AdminConnections** > **per** reautaticar les connexions al vostre nou entorn.

## <a name="change-the-owner-of-an-environment"></a>Canviar el propietari d'un entorn

Tot i que diversos usuaris poden tenir permisos d'administració a Customer Insights, només un usuari és el propietari d'un entorn. Per defecte, és l'administrador qui crea un entorn inicialment. Com a administrador d'un entorn, podeu assignar la propietat a un altre usuari amb permisos d'administració.

1. Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

1. Seleccioneu la icona **Edita**.

1. Al quadre Edita l'entorn **·**, aneu al **pas Informació** bàsica.

1. Al camp Canvia el **propietari del camp d'entorn**, trieu el nou propietari de l'entorn.  

1. Seleccioneu **Revisa i finalitza** i, a continuació **, Actualitza** per aplicar els canvis. 

## <a name="claim-ownership-of-an-environment"></a>Reclamar la propietat d'un entorn

Si el propietari d'un entorn surt de l'organització o se suprimeix el seu compte d'usuari, l'entorn no tindrà propietari. Un usuari amb permisos d'administrador pot reclamar la propietat i convertir-se en el nou propietari. Poden continuar sent propietaris de l'entorn o [canviar la propietat a un altre administrador](#change-the-owner-of-an-environment). 

Per reclamar la propietat, seleccioneu el botó Pren la **propietat** que es mostra a la part superior de cada pàgina del Customer Insights quan el propietari original va sortir de l'organització.

## <a name="reset-an-existing-environment"></a>Restablir un entorn existent

Com a propietari d'un entorn, podeu restablir un entorn a un estat buit si voleu suprimir totes les configuracions i suprimir les dades ingerides.

1.  Seleccioneu el selector **Entorn** a la capçalera de l'aplicació. 

2.  Seleccioneu l'entorn que voleu restablir i seleccioneu els punts suspensius (**...**). 

3. Trieu l'opció **Reinicialitza**. 

4.  Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Restableix**.

## <a name="delete-an-existing-environment"></a>Suprimir un entorn existent

Com a propietari d'un entorn, podeu suprimir un entorn que administreu.

1.  Seleccioneu el selector **Entorn** a la capçalera de l'aplicació.

2.  Seleccioneu l'entorn que voleu restablir i seleccioneu els punts suspensius (**...**). 

3. Trieu l'opció **Suprimeix**. 

4.  Per confirmar la supressió, introduïu el nom de l'entorn i seleccioneu **Suprimeix**.

> [!NOTE]
> La supressió d'un entorn no elimina l'associació a un Dataverse entorn. Obteniu informació sobre com [podeu suprimir una connexió existent amb un Dataverse entorn](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
