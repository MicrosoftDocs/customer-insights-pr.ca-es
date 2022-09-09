---
title: Treballar amb dades del Customer Insights al Microsoft Dataverse
description: Obteniu informació sobre com connectar el Customer Insights i Microsoft Dataverse entendre les entitats de sortida a les quals s'exporta Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424297"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Treballar amb dades del Customer Insights al Microsoft Dataverse

El Customer Insights ofereix l'opció de fer que les entitats de sortida estiguin disponibles al [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Aquesta integració permet compartir dades fàcilment i desenvolupar-les a mida mitjançant un enfocament de codi baix / sense codi. Les [entitats](#output-entities) de sortida estan disponibles com a taules en un Dataverse entorn. Podeu utilitzar les dades per a qualsevol altra aplicació basada Dataverse en taules. Aquestes taules permeten escenaris com ara fluxos de treball automatitzats a través Power Automate o creació d'aplicacions amb Power Apps.

La connexió al vostre Dataverse entorn també us permet ingerir [dades de fonts de dades local mitjançant Power Platform fluxos de dades i passarel·les](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Requisits previs

- El Customer Insights i Dataverse els entorns han d'estar allotjats a la mateixa regió.
- Una funció d'administrador global configurada a l'entorn Dataverse. Verifiqueu si aquest [Dataverse entorn està associat](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinats grups de seguretat i assegureu-vos que hàgiu afegit a aquests grups de seguretat.
- Cap altre entorn del Customer Insights ja està associat amb l'entorn Dataverse que voleu connectar. Obteniu informació sobre com [podeu suprimir una connexió existent a un Dataverse entorn](#remove-an-existing-connection-to-a-dataverse-environment).
- Un Microsoft Dataverse entorn connectat a un únic compte d'emmagatzematge si configureu l'entorn per [utilitzar el vostre Azure Data Lake Storage](own-data-lake-storage.md) fitxer.

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse dret a la capacitat d'emmagatzematge

Una subscripció del Customer Insights us dóna dret a una capacitat addicional per a la capacitat [Dataverse d'emmagatzematge existent](/power-platform/admin/capacity-storage) de la vostra organització. La capacitat afegida depèn del nombre de perfils que utilitzi la subscripció.

**Exemple:**

Suposant que obteniu 15 GB d'emmagatzematge de bases de dades i 20 GB d'emmagatzematge de fitxers per cada 100,000 perfils de clients. Si la teva subscripció inclou perfils de clients de 300.000, la teva capacitat total d'emmagatzematge és de 45 GB (3 x 15 GB) d'emmagatzematge de bases de dades i 60 GB d'emmagatzematge de fitxers (3 x 20 GB). De la mateixa manera, si teniu una subscripció B a B amb comptes de 30K, la vostra capacitat total d'emmagatzematge és de 45 GB (3 x 15 GB) d'emmagatzematge de bases de dades i 60 GB d'emmagatzematge de fitxers (3 x 20 GB).

La capacitat de registre no és incremental ni fixa per a la vostra organització.

Per obtenir més informació sobre els drets detallats de capacitat, vegeu [Guia](https://go.microsoft.com/fwlink/?LinkId=866544) de llicències del Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Connectar un Dataverse entorn al Customer Insights

El **Microsoft Dataverse** pas us permet connectar el Customer Insights amb el vostre Dataverse entorn mentre [creeu un entorn](create-environment.md) del Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="compartició de dades amb Microsoft Dataverse habilitat automàticament per a entorns nous.":::

1. Proporcioneu l'adreça URL al vostre Dataverse entorn o deixeu-la en blanc per crear-ne una.

   > [!NOTE]
   > Després d'establir la connexió entre el Customer Insights i Dataverse, no canvieu el nom de l'organització per a l'entorn Dataverse. El nom de l'organització s'utilitza a l'adreça Dataverse URL i un nom canviat trenca la connexió amb el Customer Insights.

   [Power Platform els administradors poden controlar qui pot crear un entorn Dataverse nou](/power-platform/admin/control-environment-creation). Si esteu intentant configurar un entorn nou del Customer Insights i no podeu, és possible que l'administrador hagi desactivat la creació d'entorns Dataverse per a tothom, excepte per als administradors.

1. Si utilitzeu el vostre propi compte del Data Lake Storage:
   1. Seleccioneu **Habilita l'ús compartit de** dades amb Dataverse.
   1. Introduïu l'identificador **de permisos**. Per obtenir l'identificador de permisos, [habiliteu l'ús compartit de dades amb Dataverse el vostre propi fitxer Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Habiliteu l'ús compartit de dades amb Dataverse els vostres propis Azure Data Lake Storage (visualització prèvia)

Al [vostre compte Azure Data Lake Storage](own-data-lake-storage.md), verifiqueu que l'usuari que configura l'entorn del Customer Insights tingui com a mínim **permisos de lector** de dades Blob d'emmagatzematge al `customerinsights` contenidor del compte d'emmagatzematge.

### <a name="limitations"></a>Limitacions

- Només s'assigna un a un entre una Dataverse organització i un Azure Data Lake Storage compte. Una vegada que una Dataverse organització està connectada a un compte d'emmagatzematge, no es pot connectar a un altre compte d'emmagatzematge. Aquesta limitació impedeix Dataverse omplir diversos comptes d'emmagatzematge.
- L'ús compartit de dades no funcionarà si es necessita una configuració de l'Azure Private Link per accedir al vostre Azure Data Lake Storage compte perquè es troba darrere d'un tallafoc. Dataverse actualment no admet la connexió a punts finals privats a través de Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Configureu grups de seguretat pel vostre compte Azure Data Lake Storage

1. Creeu dos grups de seguretat a la subscripció de l'Azure: un **grup de seguretat del lector** i un **grup de seguretat del Col·laborador** i definiu el Microsoft Dataverse servei com a propietari dels dos grups de seguretat.

1. Gestioneu la llista de control d'accés (ACL) del contenidor del `customerinsights` vostre compte d'emmagatzematge mitjançant aquests grups de seguretat.
   1. Afegiu el Microsoft Dataverse servei i qualsevol Dataverse aplicació empresarial basada, com ara el Dynamics 365 Marketing, al **grup de seguretat del lector** amb **permisos de només** lectura.
   1. Afegiu *només* l'aplicació Coneixements del client al grup de **seguretat de Contributor** per concedir permisos de **lectura i d'escriptura** per escriure perfils i estadístiques.

### <a name="set-up-powershell"></a>Configuració del PowerShell

Configureu el PowerShell per executar scripts del PowerShell.

1. Instal·leu la versió més recent del [Azure Active Directory PowerShell per al Graph](/powershell/azure/active-directory/install-adv2).
   1. A l'ordinador, seleccioneu la tecla del Windows al teclat, cerqueu el **Windows PowerShell** i seleccioneu **Executa com a administrador**.
   1. A la finestra del PowerShell que s'obre, introduïu `Install-Module AzureAD`.

1. Importar tres mòduls.
   1. A la finestra del PowerShell, introduïu `Install-Module -Name Az.Accounts` i seguiu els passos.
   1. Repetiu per `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Executeu scripts del PowerShell i obteniu l'identificador de permisos

1. Baixeu els dos scripts de PowerShell que necessiteu per executar-los des del repositori [GitHub del](https://github.com/trin-msft/byol) nostre enginyer.
   - `CreateSecurityGroups.ps1`: requereix permisos d'administració d'inquilins.
   - `ByolSetup.ps1`: requereix permisos de propietari de dades blob d'emmagatzematge al nivell de compte d'emmagatzematge/contenidor. Aquest script us crearà el permís. L'assignació de funcions es pot eliminar manualment després d'executar correctament l'script.

1. Executeu `CreateSecurityGroups.ps1` al Windows PowerShell proporcionant l'identificador de subscripció de l'Azure que conté el vostre Azure Data Lake Storage fitxer. Obriu l'script del PowerShell en un editor per revisar la informació addicional i la lògica implementada.

   Aquest script crea dos grups de seguretat a la subscripció de l'Azure: un per al grup de lectors i un altre per al grup de col·laboradors. Microsoft Dataverse el servei és el propietari d'aquests dos grups de seguretat.

1. Deseu els dos valors d'ID del grup de seguretat generats per aquest script per utilitzar-los a l'script `ByolSetup.ps1`.

   > [!NOTE]
   > La creació de grups de seguretat es pot desactivar a l'inquilí. En aquest cas, es necessitaria una configuració manual i el vostre Azure AD administrador hauria d'habilitar la [creació](/azure/active-directory/enterprise-users/groups-self-service-management) de grups de seguretat.

1. Executeu-lo `ByolSetup.ps1` al Windows PowerShell proporcionant l'identificador de subscripció de l'Azure que conté el Azure Data Lake Storage vostre nom de compte d'emmagatzematge, el nom del grup de recursos i els valors de l'identificador de grup de seguretat del Lector i del Col·laborador. Obriu l'script del PowerShell en un editor per revisar la informació addicional i la lògica implementada.

   Aquest script afegeix el control d'accés basat en funcions necessari per al Microsoft Dataverse servei i qualsevol Dataverse aplicació empresarial basada en funcions. També actualitza la Llista de control d'accés (ACL) al `customerinsights` contenidor per als grups de seguretat creats amb l'script `CreateSecurityGroups.ps1`. El grup de col·laboradors té *permís rwx* i el grup de lectors només té *permís r-x*.

1. Copieu la cadena de sortida que té l'aspecte següent: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Introduïu la cadena de sortida copiada al **camp Identificador de permisos** del pas de configuració de l'entorn per a Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcions de configuració per habilitar l'ús compartit de dades des del vostre compte Azure Data Lake Storage amb Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Suprimir una connexió existent a un Dataverse entorn

Quan us connecteu a un Dataverse entorn, el missatge **d'error Aquesta organització de CDS ja està connectada a una altra instància** del Customer Insights significa que l'entorn Dataverse ja s'utilitza en un entorn del Customer Insights. Podeu suprimir la connexió existent com a administrador global a l'entorn Dataverse. Els canvis poden trigar un parell d'hores a omplir-se.

1. Aneu al [Power Apps](https://make.powerapps.com).
1. Seleccioneu l'entorn del selector d'entorns.
1. Aneu a **Solucions**.
1. Desinstal·leu o suprimiu la solució anomenada **Dynamics 365 Customer Insights Complement de targeta de client (visualització prèvia).**

O

1. Obriu el vostre Dataverse entorn.
1. Aneu a **Solucions** > **de configuració** avançada.
1. Desinstal·leu la **solució CustomerInsightsCustomerCard**.

Si l'eliminació de la connexió falla a causa de dependències, també heu d'eliminar les dependències. Per obtenir més informació, vegeu [Supressió de dependències](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entitats de sortida

Algunes entitats de sortida del Customer Insights estan disponibles com a taules a Dataverse. Les seccions següents descriuen l'esquema esperat d'aquestes taules.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquiment](#enrichment)
- [Predicció](#prediction)
- [Pertinença al segment](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Aquesta taula conté el perfil de client unificat del Customer Insights. L'esquema d'un perfil de client unificat depèn de les entitats i atributs utilitzats en el procés d'unificació de dades. Un esquema de perfil de client sol contenir un subconjunt dels atributs de la [definició del model de dades comú del CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Per a l'escenari B a B, el perfil de client conté comptes unificats i l'esquema sol contenir un subconjunt dels atributs de la [definició de compte del Common Data Model de dades](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

Un ContactProfile conté informació unificada sobre un contacte. Els contactes són [individus que s'assignen a un compte](data-unification-contacts.md) en un escenari de B a B.

| Column                       | Type                | Descripció     |
| ---------------------------- | ------------------- | --------------- |
|  Data de naixement            | Data/hora       |  Data de naixement del contacte               |
|  Ciutat                 | SMS |  Ciutat de l'adreça de contacte               |
|  ContactId            | SMS |  Identificació del perfil de contacte               |
|  ContacteProfileId     | Identificador únic   |  GUID per al contacte               |
|  CountryOrRegion      | SMS |  País o regió de l'adreça de contacte               |
|  CustomerId           | SMS |  Identificador del compte al qual està mapejat el contacte               |
|  EntityName           | SMS |  Entitat de la qual provenen les dades                |
|  FirstName            | SMS |  Nom del contacte               |
|  Gènere               | SMS |  Gènere del contacte               |
|  Id.                   | SMS |  GUID determinista basat en`Identifier`               |
|  Identificador           | SMS |  Identificació interna del perfil de contacte: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | SMS |  Títol del treball del contacte               |
|  LastName             | SMS |  Cognom del contacte               |
|  PostalCode           | SMS |  Codi postal de l'adreça de contacte               |
|  Correu primari         | SMS |  Adreça de correu electrònic del contacte               |
|  Telèfon principal         | SMS |  Telèfon del contacte               |
|  StateOrProvince      | SMS |  Estat o província de l'adreça de contacte               |
|  StreetAddress        | SMS |  Carrer de l'adreça de contacte               |

### <a name="alternatekey"></a>AlternateKey

La taula AlternativeKey conté les claus de les entitats que han participat en el procés d'unificació.

|Column  |Type  |Descripció  |
|---------|---------|---------|
|DataSourceName    |SMS         | Nom de la font de dades. Per exemple: `datasource5`        |
|EntityName        | SMS        | Nom de l'entitat al Customer Insights. Per exemple: `contact1`        |
|AlternateValue    |SMS         |Identificador alternatiu assignat a l'identificador de client. Exemple: `cntid_1078`         |
|KeyRing           | SMS        | Valor JSON  </br> Exemple: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | SMS        | Identificador del perfil de client unificat.         |
|AlternateKeyId     | Identificador únic        |  GUID determinista d'AlternateKey basat en`Identifier`      |
|Identificador |   SMS      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemple: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Aquesta taula conté activitats dels usuaris que estan disponibles al Customer Insights.

| Column            | Type        | Descripció                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | SMS      | Identificador del perfil del client                                                                      |
| ActivityId        | SMS      | Identificador intern de l'activitat de client (clau principal)                                       |
| SourceEntityName  | SMS      | Nom de l'entitat d'origen                                                                |
| SourceActivityId  | SMS      | Clau principal de l'entitat d'origen                                                       |
| ActivityType      | SMS      | Tipus d'activitat administrada o nom de l'activitat personalitzada                                        |
| ActivityTimeStamp | Data/hora    | Segell de temps de l'activitat                                                                      |
| Càrrec             | SMS      | Títol o nom de l'activitat                                                               |
| Descripció       | SMS      | Descripció d'activitat                                                                     |
| Adreça URL               | SMS      | Enllaçar amb una adreça URL externa específica de l'activitat                                         |
| SemanticData      | SMS | Inclou una llista de parelles de valors clau per als camps d'assignació semàntica específics del tipus d'activitat |
| RangeIndex        | SMS      | Marca de temps unix utilitzada per ordenar la cronologia de l'activitat i les consultes d'interval eficaces |
| UnifiedActivityId   | Identificador únic | Identificador intern de l'activitat de client (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Aquesta taula conté les dades de sortida de les mesures basades en atributs del client.

| Column             | Type             | Descripció                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | SMS           | Identificador del perfil del client        |
| Mesures           | SMS      | Inclou una llista de parelles de valors clau per al nom de mesura i els valors del client determinat |
| Identificador | SMS           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Identificador únic     | Identificador del perfil del client |

### <a name="enrichment"></a>Enriquiment

Aquesta taula conté la sortida del procés d'enriquiment.

| Column               | Type             |  Descripció                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | SMS           | Identificador del perfil del client                                 |
| EnrichmentProvider   | SMS           | Nom del proveïdor de l'enriquiment                                  |
| EnrichmentType       | SMS           | Tipus d'enriquiment                                      |
| Valors               | SMS      | Llista d'atributs produïts pel procés d'enriquiment |
| EnriquimentId | Identificador únic            | GUID determinista generat a partir de`Identifier` |
| Identificador   | SMS           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predicció

Aquesta taula conté la sortida de les prediccions de models.

| Column               | Type        | Descripció                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | SMS      | Identificador del perfil del client                                  |
| ModelProvider        | SMS      | Nom del proveïdor del model                                      |
| Model                | SMS      | Nom del model                                                |
| Valors               | SMS | Llista d'atributs produïts pel model |
| PredictionId | Identificador únic       | GUID determinista generat a partir de`Identifier` |
| Identificador   | SMS      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Pertinença al segment

Aquesta taula conté informació de pertinença per segments dels perfils de clients.

| Column        | Type | Descripció                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | SMS       | Identificador del perfil del client        |
| SegmentProvider      | SMS       | Aplicació que publica els segments.      |
| SegmentMembershipType | SMS       | Tipus de client per al registre de pertinença a aquest segment. Admet diversos tipus, com ara Client, Contacte o Compte. Per defecte: client  |
| Segments       | SMS  | Llista de segments únics dels quals el perfil de client és membre      |
| Identificador  | SMS   | Identificador únic del registre de pertinença al segment. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Identificador únic      | GUID determinista generat a partir de`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
