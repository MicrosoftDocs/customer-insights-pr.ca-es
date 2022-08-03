---
title: Treballar amb dades del Customer Insights al Microsoft Dataverse
description: Obteniu informació sobre com connectar el Customer Insights i Microsoft Dataverse entendre les entitats de sortida a les quals s'exporta Dataverse.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153392"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Treballar amb dades del Customer Insights al Microsoft Dataverse

El Customer Insights proporciona l'opció de fer que les entitats de sortida estiguin disponibles com a [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Aquesta integració permet compartir dades fàcilment i desenvolupar-les a mida mitjançant un enfocament de codi baix / sense codi. Les [entitats](#output-entities) de sortida estan disponibles com a taules en un Dataverse entorn. Podeu utilitzar les dades per a qualsevol altra aplicació basada Dataverse en taules. Aquestes taules permeten escenaris com ara fluxos de treball automatitzats a través Power Automate o creació d'aplicacions amb Power Apps.

La connexió al vostre Dataverse entorn també us permet ingerir [dades de fonts de dades local mitjançant Power Platform fluxos de dades i passarel·les](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Requisits previs

- El Customer Insights i Dataverse els entorns han d'estar allotjats a la mateixa regió.
- Heu de tenir una funció d'administrador global a l'entorn Dataverse. Verifiqueu si aquest [Dataverse entorn està associat](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinats grups de seguretat i assegureu-vos que hàgiu afegit a aquests grups de seguretat.
- Cap altre entorn del Customer Insights ja està associat amb l'entorn Dataverse que voleu connectar. Obteniu informació sobre com [podeu suprimir una connexió existent a un Dataverse entorn](#remove-an-existing-connection-to-a-dataverse-environment).
- Un Microsoft Dataverse entorn només es pot connectar a un únic compte d'emmagatzematge. Només s'aplica si configureu l'entorn per [utilitzar el vostre Azure Data Lake Storage](own-data-lake-storage.md) fitxer.

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse dret a la capacitat d'emmagatzematge

Una subscripció del Customer Insights us dóna dret a una capacitat addicional per a la capacitat [Dataverse d'emmagatzematge existent](/power-platform/admin/capacity-storage) de la vostra organització. La capacitat afegida depèn del nombre de perfils que utilitzi la subscripció.

**Exemple:**

Suposant que obteniu 15 GB d'emmagatzematge de bases de dades i 20 GB d'emmagatzematge de fitxers per cada 100,000 perfils de clients. Si la teva subscripció inclou perfils de clients de 300.000, la teva capacitat total d'emmagatzematge seria de 45 GB (3 x 15 GB) d'emmagatzematge de bases de dades i 60 GB d'emmagatzematge de fitxers (3 x 20 GB). De la mateixa manera, si teniu una subscripció B2B amb comptes de 30K, la vostra capacitat total d'emmagatzematge seria de 45 GB (3 x 15 GB) d'emmagatzematge de bases de dades i emmagatzematge de fitxers de 60 GB (3 x 20 GB).

La capacitat de registre no és incremental ni fixa per a la vostra organització.

Per obtenir més informació sobre els drets detallats de capacitat, vegeu [Guia](https://go.microsoft.com/fwlink/?LinkId=866544) de llicències del Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Connectar un Dataverse entorn al Customer Insights

El **Microsoft Dataverse** pas us permet connectar el Customer Insights amb el vostre Dataverse entorn mentre [creeu un entorn](create-environment.md) del Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="compartició de dades amb Microsoft Dataverse habilitat automàticament per a entorns nets nous.":::

Els administradors poden configurar el Customer Insights per connectar un entorn existent Dataverse. En proporcionar l'URL a l'entorn Dataverse, es connecta al seu nou entorn del Customer Insights. Després d'establir la connexió entre el Customer Insights i Dataverse, no canvieu el nom de l'organització per a l'entorn Dataverse. El nom de l'organització s'utilitza a l'adreça Dataverse URL i un nom canviat trenca la connexió amb el Customer Insights.

Si no voleu utilitzar un entorn existent Dataverse, el sistema crea un entorn nou per a les dades del Customer Insights a l'inquilí. [Power Platform els administradors poden controlar qui pot crear entorns](/power-platform/admin/control-environment-creation). Quan configureu un entorn nou del Customer Insights i l'administrador ha desactivat la creació d'entorns Dataverse per a tothom excepte per als administradors, és possible que no pugueu crear un entorn nou.

**Activeu la casella de** selecció per compartir Dataverse dades.

Si utilitzeu el vostre propi compte del Data Lake Storage, també necessiteu l'identificador **de permisos**. Per obtenir més informació sobre com obtenir l'identificador de permisos, consulteu la secció següent.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Habiliteu l'ús compartit de dades amb Dataverse els vostres propis Azure Data Lake Storage (Visualització prèvia)

Habilitar l'ús compartit de dades quan Microsoft Dataverse l'entorn [utilitza el vostre propi Azure Data Lake Storage compte](own-data-lake-storage.md) necessita una configuració addicional. L'usuari que configuri l'entorn del Customer Insights ha de tenir com a mínim **permisos de lector** de dades Blob d'emmagatzematge al *contenidor CustomerInsights* del Azure Data Lake Storage compte.

1. Creeu dos grups de seguretat a la subscripció de l'Azure: un **grup de seguretat del lector** i un **grup de seguretat del Col·laborador** i definiu el Microsoft Dataverse servei com a propietari dels dos grups de seguretat.
2. Gestioneu la Llista de control d'accés (ACL) al contenidor CustomerInsights del vostre compte d'emmagatzematge mitjançant aquests grups de seguretat. Afegiu el Microsoft Dataverse servei i qualsevol Dataverse aplicació empresarial basada, com ara el Dynamics 365 Marketing, al **grup de seguretat del lector** amb **permisos de només** lectura. Afegiu *només* l'aplicació Coneixements del client al grup de **seguretat de Contributor** per concedir permisos de **lectura i d'escriptura** per escriure perfils i estadístiques.

### <a name="limitations"></a>Limitacions

Hi ha dues limitacions a l'hora d'utilitzar-lo Dataverse amb el vostre propi Azure Data Lake Storage compte:

- Hi ha una assignació individual entre una Dataverse organització i un Azure Data Lake Storage compte. Una vegada que una Dataverse organització està connectada a un compte d'emmagatzematge, no es pot connectar a un altre compte d'emmagatzematge. Aquesta limitació impedeix que no Dataverse s'emplenin diversos comptes d'emmagatzematge.
- L'ús compartit de dades no funcionarà si es necessita una configuració de l'Azure Private Link per accedir al vostre Azure Data Lake Storage compte perquè es troba darrere d'un tallafoc. Dataverse actualment no admet la connexió a punts finals privats a través de Private Link.

### <a name="set-up-powershell"></a>Configuració del PowerShell

Per executar els scripts del PowerShell, primer heu de configurar el PowerShell en conseqüència.

1. Instal·leu la versió més recent del [Azure Active Directory PowerShell per al Graph](/powershell/azure/active-directory/install-adv2).
   1. A l'ordinador, seleccioneu la tecla del Windows al teclat, cerqueu el **Windows PowerShell** i seleccioneu **Executa com a administrador**.
   1. A la finestra del PowerShell que s'obre, introduïu `Install-Module AzureAD`.
2. Importar tres mòduls.
    1. A la finestra del PowerShell, introduïu `Install-Module -Name Az.Accounts` i seguiu els passos.
    1. Repetiu per `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Passos de configuració

1. Baixeu els dos scripts de PowerShell que necessiteu per executar-los des del repositori [GitHub del](https://github.com/trin-msft/byol) nostre enginyer.
    1. `CreateSecurityGroups.ps1`
       - Necessiteu *permisos d'administrador d'inquilins* per executar aquest script del PowerShell.
       - Aquest script del PowerShell crea dos grups de seguretat a la subscripció de l'Azure. Un per al grup lector i un altre per al grup Col·laboradors i farà Microsoft Dataverse servei com a propietari d'aquests dos grups de seguretat.
       - Executeu aquest script del PowerShell al Windows PowerShell proporcionant l'identificador de subscripció de l'Azure que conté el vostre Azure Data Lake Storage fitxer. Obriu l'script del PowerShell en un editor per revisar la informació addicional i la lògica implementada.
       - Deseu els dos valors d'identificador de grup de seguretat generats per aquest script perquè els utilitzarem a l'script `ByolSetup.ps1`.

        > [!NOTE]
        > La creació de grups de seguretat es pot desactivar a l'inquilí. En aquest cas, es necessitaria una configuració manual i el vostre Azure AD administrador hauria d'habilitar la [creació de grups de seguretat](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Necessiteu *permisos storage Blob Data Owner* a nivell de compte d'emmagatzematge/contenidor per executar aquest script o aquest script en crearà un per a vosaltres. L'assignació de funcions es pot eliminar manualment després d'executar correctament l'script.
        - Aquest script del PowerShell afegeix el control d'accés basat en funcions necessari per al Microsoft Dataverse servei i qualsevol Dataverse aplicació empresarial basada en funcions. També actualitza la Llista de control d'accés (ACL) al contenidor CustomerInsights per als grups de seguretat creats amb l'script `CreateSecurityGroups.ps1`. El grup de col·laboradors tindrà *permís rwx* i el grup de lectors només tindrà *permís r-x*.
        - Executeu aquest script del PowerShell al Windows PowerShell proporcionant l'identificador de subscripció de l'Azure que conté el Azure Data Lake Storage vostre nom de compte d'emmagatzematge, el nom del grup de recursos i els valors de l'identificador de grup de seguretat del lector i del col·laborador. Obriu l'script del PowerShell en un editor per revisar la informació addicional i la lògica implementada.
        - Copieu la cadena de sortida després d'executar correctament l'script. La cadena de sortida té aquest aspecte: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Introduïu la cadena de sortida copiada des de dalt al **camp Identificador** de permisos del pas de configuració de l'entorn per a Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcions de configuració per habilitar l'ús compartit de dades des del vostre compte Azure Data Lake Storage amb Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Suprimir una connexió existent a un Dataverse entorn

Quan us connecteu a un Dataverse entorn, el missatge **d'error Aquesta organització de CDS ja està connectada a una altra instància** del Customer Insights significa que l'entorn Dataverse ja s'utilitza en un entorn del Customer Insights. Podeu suprimir la connexió existent com a administrador global a l'entorn Dataverse. Els canvis poden trigar un parell d'hores a omplir-se.

1. Aneu al [Power Apps](https://make.powerapps.com).
1. Seleccioneu l'entorn del selector d'entorns.
1. Anar a **Solucions**
1. Desinstal·leu o suprimiu la solució anomenada **Dynamics 365 Customer Insights Complement de targeta de client (visualització prèvia).**

O

1. Obriu el vostre Dataverse entorn.
1. Aneu a **Solucions** > **de configuració** avançada.
1. Desinstal·leu la **solució CustomerInsightsCustomerCard**.

Si l'eliminació de la connexió falla a causa de dependències, també heu d'eliminar les dependències. Per obtenir més informació, vegeu [Supressió de dependències](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entitats de sortida

Algunes entitats de sortida del Customer Insights estan disponibles com a taules a Dataverse. Les seccions següents descriuen l'esquema esperat d'aquestes taules.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquiment](#enrichment)
- [Predicció](#prediction)
- [Pertinença al segment](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Aquesta taula conté el perfil de client unificat del Customer Insights. L'esquema d'un perfil de client unificat depèn de les entitats i atributs utilitzats en el procés d'unificació de dades. Un esquema de perfil de client sol contenir un subconjunt dels atributs de la [definició del model de dades comú del CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

La taula AlternativeKey conté les claus de les entitats que han participat en el procés d'unificació.

|Column  |Type  |Descripció  |
|---------|---------|---------|
|DataSourceName    |String         | Nom de la font de dades. Per exemple: `datasource5`        |
|EntityName        | String        | Nom de l'entitat al Customer Insights. Per exemple: `contact1`        |
|AlternateValue    |String         |Identificador alternatiu assignat a l'identificador de client. Exemple: `cntid_1078`         |
|KeyRing           | Text de diverses línies        | Valor JSON  </br> Exemple: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Identificador del perfil de client unificat.         |
|AlternateKeyId     | GUID         |  GUID determinista d'AlternateKey basat en msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemple: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Aquesta taula conté activitats dels usuaris que estan disponibles al Customer Insights.

| Column            | Type        | Descripció                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Identificador del perfil del client                                                                      |
| ActivityId        | String      | Identificador intern de l'activitat de client (clau principal)                                       |
| SourceEntityName  | String      | Nom de l'entitat d'origen                                                                |
| SourceActivityId  | String      | Clau principal de l'entitat d'origen                                                       |
| ActivityType      | String      | Tipus d'activitat administrada o nom de l'activitat personalitzada                                        |
| ActivityTimeStamp | DATETIME    | Marca de temps de l'activitat                                                                      |
| Càrrec             | String      | Títol o nom de l'activitat                                                               |
| Descripció       | String      | Descripció d'activitat                                                                     |
| Adreça URL               | String      | Enllaçar amb una adreça URL externa específica de l'activitat                                         |
| SemanticData      | Cadena JSON | Inclou una llista de parelles de valors clau per als camps d'assignació semàntica específics del tipus d'activitat |
| RangeIndex        | String      | Marca de temps unix utilitzada per ordenar la cronologia de l'activitat i les consultes d'interval eficaces |
| mydynci_unifiedactivityid   | GUID | Identificador intern de l'activitat de client (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Aquesta taula conté les dades de sortida de les mesures basades en atributs del client.

| Column             | Type             | Descripció                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Identificador del perfil del client        |
| Mesures           | Cadena JSON      | Inclou una llista de parelles de valors clau per al nom de mesura i els valors del client determinat | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Identificador del perfil del client |


### <a name="enrichment"></a>Enriquiment

Aquesta taula conté la sortida del procés d'enriquiment.

| Column               | Type             |  Descripció                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Identificador del perfil del client                                 |
| EnrichmentProvider   | String           | Nom del proveïdor de l'enriquiment                                  |
| EnrichmentType       | String           | Tipus d'enriquiment                                      |
| Valors               | Cadena JSON      | Llista d'atributs produïts pel procés d'enriquiment |
| msdynci_enrichmentid | GUID             | GUID determinista generat a partir de msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predicció

Aquesta taula conté la sortida de les prediccions de models.

| Column               | Type        | Descripció                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Identificador del perfil del client                                  |
| ModelProvider        | String      | Nom del proveïdor del model                                      |
| Model                | String      | Nom del model                                                |
| Valors               | Cadena JSON | Llista d'atributs produïts pel model |
| msdynci_predictionid | GUID        | GUID determinista generat a partir de msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Pertinença al segment

Aquesta taula conté informació de pertinença per segments dels perfils de clients.

| Column        | Type | Descripció                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Identificador del perfil del client        |
| SegmentProvider      | String       | Aplicació que publica els segments.      |
| SegmentMembershipType | String       | Tipus de client d'aquest registre de pertinença a aquest segment. Admet diversos tipus, com ara Client, Contacte o Compte. Per defecte: client  |
| Segments       | Cadena JSON  | Llista de segments únics dels quals el perfil de client és membre      |
| msdynci_identifier  | String   | Identificador únic del registre de pertinença al segment. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinista generat a partir de`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
