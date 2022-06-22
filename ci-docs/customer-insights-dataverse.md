---
title: Treballar amb dades del Customer Insights al Microsoft Dataverse
description: Obteniu informació sobre com podeu connectar el Customer Insights i Microsoft Dataverse entendre les entitats de sortida a les que s'exporten a Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011508"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Treballar amb dades del Customer Insights al Microsoft Dataverse

Customer Insights proporciona l'opció de fer que les entitats de sortida estiguin disponibles com a [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Aquesta integració permet compartir dades fàcil i el desenvolupament personalitzat a través d'un enfocament de codi baix / sense codi. Les [entitats](#output-entities) de sortida estan disponibles com a taules en un Dataverse entorn. Podeu utilitzar les dades per a qualsevol altra aplicació basada en Dataverse taules. Aquestes taules permeten escenaris com ara fluxos de treball automatitzats o Power Automate la creació d'aplicacions amb Power Apps.

La connexió amb el vostre Dataverse entorn també us [permet ingerir dades de local orígens de dades mitjançant Power Platform fluxos de dades i passarel·les](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Requisits previs

- Les estadístiques del client i Dataverse els entorns s'han d'allotjar a la mateixa regió.
- Heu de tenir una funció d'administrador global a l'entorn Dataverse. Comproveu si aquest [Dataverse entorn està associat](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinats grups de seguretat i assegureu-vos que esteu afegit a aquests grups de seguretat.
- Cap altre entorn del Customer Insights ja està associat amb l'entorn Dataverse en què us voleu connectar. Obteniu informació sobre com [podeu suprimir una connexió existent amb un Dataverse entorn](#remove-an-existing-connection-to-a-dataverse-environment).
- Un Microsoft Dataverse entorn només es pot connectar a un únic compte d'emmagatzematge. Només s'aplica si configureu l'entorn per [utilitzar el vostre Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Connectar un Dataverse entorn a Customer Insights

El **Microsoft Dataverse** pas us permet connectar el Customer Insights amb el vostre Dataverse entorn mentre [creeu un entorn](create-environment.md) d'estadístiques del client.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="l'ús compartit de dades amb Microsoft Dataverse l'habilitació automàtica per a entorns nous de xarxa.":::

Els administradors poden configurar el Customer Insights per connectar un entorn existent Dataverse. En proporcionar l'URL a l'entorn Dataverse, s'adjunta al seu nou entorn d'estadístiques del client.

Si no voleu utilitzar un entorn existent Dataverse, el sistema crea un entorn nou per a les dades del Customer Insights a l'inquilí. [Power Platform els administradors poden controlar qui pot crear entorns](/power-platform/admin/control-environment-creation). Quan esteu configurant un entorn nou del Customer Insights i l'administrador ha inhabilitat la creació d'entorns Dataverse per a tothom, excepte per als administradors, és possible que no pugueu crear un entorn nou.

**Activa l'ús compartit de** dades amb Dataverse el que activeu la casella de selecció Compartició de dades.

Si utilitzeu el vostre propi compte d'emmagatzematge del llac de dades, també necessiteu l'identificador **Permisos**. Per obtenir més informació sobre com obtenir l'identificador de permisos, reviseu la secció següent.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Habilita l'ús compartit de dades amb Dataverse el vostre (Azure Data Lake Storage visualització prèvia)

Habilitar l'ús compartit de dades quan Microsoft Dataverse el vostre entorn [utilitza el vostre propi Azure Data Lake Storage compte](own-data-lake-storage.md) necessita una configuració addicional. L'usuari que configura l'entorn del Customer Insights ha de tenir com a mínim **permisos del lector** de dades blob d'emmagatzematge al *contenidor CustomerInsights* del Azure Data Lake Storage compte.

1. Creeu dos grups de seguretat a la vostra subscripció a l'Azure: un **grup de seguretat Lector** i un **grup de seguretat col·laborador** i definiu el Microsoft Dataverse servei com a propietari per a ambdós grups de seguretat.
2. Gestioneu la llista de control d'accés (ACL) al contenidor CustomerInsights del compte d'emmagatzematge a través d'aquests grups de seguretat. Afegiu el Microsoft Dataverse servei i qualsevol Dataverse aplicació empresarial basada en el Dynamics 365 Marketing al **grup de seguretat Lector** amb **permisos de només** lectura. Afegiu *només* l'aplicació Customers Insights al **grup de seguretat Col·laborador** per concedir permisos de **lectura i escriptura** per escriure perfils i estadístiques.

### <a name="limitations"></a>Limitacions

Hi ha dues limitacions a l'hora d'utilitzar Dataverse amb el vostre propi Azure Data Lake Storage compte:

- Hi ha una assignació un a un entre una Dataverse organització i un Azure Data Lake Storage compte. Una vegada que una Dataverse organització està connectada a un compte d'emmagatzematge, no es pot connectar a un altre compte d'emmagatzematge. Aquesta limitació impedeix que un Dataverse no empleni diversos comptes d'emmagatzematge.
- L'ús compartit de dades no funcionarà si es necessita una configuració de l'Azure Private Link per accedir al compte Azure Data Lake Storage perquè està darrere d'un tallafoc. Dataverse actualment no admet la connexió als extrems privats a través de Private Link.

### <a name="set-up-powershell"></a>Configura el PowerShell

Per executar els scripts del PowerShell, primer heu de configurar el PowerShell en conseqüència.

1. Instal·leu la versió més recent del [Azure Active Directory PowerShell per al Graph](/powershell/azure/active-directory/install-adv2).
   1. A l'ordinador, seleccioneu la tecla del Windows al teclat, cerqueu el **Windows PowerShell** i seleccioneu **Executa com a administrador**.
   1. A la finestra del PowerShell que s'obre, introduïu `Install-Module AzureAD`.
2. Importa tres mòduls.
    1. A la finestra powerShell, introduïu `Install-Module -Name Az.Accounts` i seguiu els passos.
    1. Repetiu per `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Passos de configuració

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
        - Executeu aquest script del PowerShell al Windows PowerShell proporcionant l'identificador de subscripció de l'Azure que conté el vostre Azure Data Lake Storage, nom del compte d'emmagatzematge, nom del grup de recursos i els valors d'identificador del grup de seguretat lector i col·laborador. Obriu l'script del PowerShell en un editor per revisar la informació addicional i la lògica implementada.
        - Copia la cadena de sortida després d'executar correctament l'script. La cadena de sortida té aquest aspecte: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Introduïu la cadena de sortida copiada des de dalt al **camp Identificador** de permisos del pas de configuració de l'entorn per a Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcions de configuració per habilitar l'ús compartit de dades des del vostre compte Azure Data Lake Storage amb Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Suprimir una connexió existent a un Dataverse entorn

En connectar-se a un Dataverse entorn, el missatge **d'error Aquesta organització del CDS ja està connectada a una altra instància** del Customer Insights significa que l'entorn ja s'utilitza Dataverse en un entorn del Customer Insights. Podeu suprimir la connexió existent com a administrador global a l'entorn Dataverse. Pot trigar un parell d'hores a omplir els canvis.

1. Aneu al [Power Apps](https://make.powerapps.com).
1. Seleccioneu l'entorn del selectador d'entorns.
1. Anar a **solucions**
1. Desinstal·leu o suprimiu la solució anomenada **Dynamics 365 Customer Insights complement de targeta de client (visualització prèvia).**

O

1. Obre el teu Dataverse entorn.
1. Aneu a **Solucions** > **avançades** de configuració.
1. Desinstal·leu la **solució CustomerInsightsCustomerCard**.

Si la supressió de la connexió falla a causa de dependències, també heu de suprimir les dependències. Per obtenir més informació, vegeu [Eliminar dependències](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entitats de sortida

Algunes entitats de sortida del Customer Insights estan disponibles com a taules al Dataverse. Les seccions següents descriuen l'esquema esperat d'aquestes taules.

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
|EntityName        | String        | Nom de l'entitat a Customer Insights. Per exemple: `contact1`        |
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

Aquesta taula conté informació de pertinença al segment dels perfils de clients.

| Column        | Type | Descripció                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Identificador del perfil del client        |
| SegmentProvider      | String       | Aplicació que publica els segments.      |
| SegmentMembershipType | String       | Tipus de client d'aquest registre de pertinença al segment. Admet diversos tipus, com ara client, contacte o compte. Per defecte: client  |
| Segments       | Cadena JSON  | Llista de segments únics dels que el perfil de client és membre      |
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
