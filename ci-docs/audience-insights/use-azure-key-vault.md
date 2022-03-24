---
title: Porteu el vostre propi magatzem de claus de l'Azure per administrar els secrets
description: Més informació sobre com configurar el Customer Insights per utilitzar el vostre propi magatzem de claus de l'Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 418575f724090628da8bd01e2569a4cb9e646337
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376496"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Porteu el vostre propi magatzem de claus de l'Azure (versió preliminar)

Enllaçar un [magatzem de claus de l'Azure](/azure/key-vault/general/basic-concepts) dedicat a un entorn de conclusions del públic ajuda les organitzacions a complir els requisits de compliment.
El magatzem de claus dedicat es pot utilitzar per escenificar i utilitzar els secrets en el límit de compliment de l'organització. Les conclusions del públic poden utilitzar els secrets de l'Azure Key Vault per [configurar connexions](connections.md) amb sistemes de tercers.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Enllaçar el magatzem de claus a l'entorn de conclusions del públic

### <a name="prerequisites"></a>Requisits previs

Per configurar el magatzem de claus a les conclusions del públic, cal complir els requisits previs següents:

- Heu de tenir una subscripció activa de l'Azure.

- Teniu una funció d'[Administrador](permissions.md#admin) als coneixements del públic. Obteniu més informació sobre els [permisos d'usuari a les conclusions del públic](permissions.md#assign-roles-and-permissions).

- Teniu les funcions [Col·laborador](/azure/role-based-access-control/built-in-roles#contributor) i [Administrador d'accés d'usuari](/azure/role-based-access-control/built-in-roles#user-access-administrator) al magatzem de claus o al grup de recursos al qual pertany el magatzem de claus. Per obtenir més informació, aneu a [Afegir o eliminar assignacions de funcions de l'Azure utilitzant el portal de l'Azure](/azure/role-based-access-control/role-assignments-portal). Si no teniu la funció Administrador d'accés d'usuari al magatzem de claus, heu de configurar els permisos de control d'accés basats en funcions per a l'entitat de servei de l'Azure per al Dynamics 365 Customer Insights per separat. Seguiu els passos per [utilitzar l'entitat de servei de l'Azure](connect-service-principal.md) per al magatzem de claus que s'ha d'enllaçar.

- El magatzem de claus ha de tenir el tallafoc del Key Vault **inhabilitat**.

- El magatzem de claus es troba a la mateixa [ubicació de l'Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) que l'entorn de les conclusions del públic. La regió de l'entorn de les conclusions del públic es mostra **Administració** > **Sistema** > **Quant a** > **Regió**.

### <a name="link-a-key-vault-to-the-environment"></a>Enllaçar un magatzem de claus amb l'entorn

1. Aneu al **Administració** > **Sistema** i seleccioneu la pestanya **Seguretat**.
1. A la peça **Key Vault**, seleccioneu **Configuració**.
1. Trieu una **Subscripció**.
1. Trieu un magatzem de claus de la llista desplegable **Key Vault**. Si es mostren massa magatzems de claus, seleccioneu un grup de recursos per limitar els resultats de la cerca.
1. Accepteu la declaració de **Privadesa de les dades i compliment**.
1. Seleccioneu **Desa**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Passos per configurar un magatzem de claus enllaçat a les conclusions del públic.":::

La peça **Key Vault** mostra ara el nom del magatzem de claus enllaçat, el grup de recursos i la subscripció. Està a punt per utilitzar-se en la configuració de connexió.
Per obtenir detalls sobre els permisos que s'atorguen al magatzem de claus a les conclusions del públic, aneu a [Permisos atorgats al magatzem de claus a les conclusions del públic](#permissions-granted-on-the-key-vault-to-audience-insights), més endavant en aquest article.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilitzar el magatzem de claus de la configuració de connexió

Quan [configureu connexions](connections.md) a sistemes de tercers, els secrets del Key Vault enllaçat es poden utilitzar per configurar les connexions.

1. Aneu a **Administració** > **Connexions**.
1. Seleccioneu **Afegeix una connexió**.
1. Per als tipus de connexió compatibles, hi ha disponible una commutació **Utilitza el Key Vault** si heu enllaçat un magatzem de claus.
1. En lloc d'introduir el secret manualment, podeu triar el nom del secret que assenyala al valor del secret del magatzem de claus.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Subfinestra de connexió amb una connexió SFTP que utilitza un secret del Key Vault.":::

## <a name="supported-connection-types"></a>Tipus de connexió admesos

S'admeten les connexions d'[exportació](export-destinations.md) següents:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Permisos atorgats al magatzem de claus a les conclusions del públic

Si s'habilita la [norma d'accés de Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o el [control d'accés basat en funcions de l'Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), s'atorguen els permisos següents a les conclusions del públic en un magatzem de claus enllaçat.

### <a name="key-vault-access-policy"></a>Norma d'accés del Key Vault

| Type        | Permisos          |
| ----------- | -------------------- |
| Tecla         | [Obtén les claus](/rest/api/keyvault/get-keys), [Obtén la clau](/rest/api/keyvault/get-key)                                 |
| Secret      | [Obtén els secrets](/rest/api/keyvault/get-secrets), [Obtén el secret](/rest/api/keyvault/get-secret)                     |
| Certificat | [Obtén els certificats](/rest/api/keyvault/get-certificates), [Obtén el certificat](/rest/api/keyvault/get-certificate) |

Els valors anteriors són el mínim per llistar i llegir durant l'execució.

### <a name="azure-role-based-access-control"></a>Control d'accés basat en funcions de l'Azure

Les funcions de lector del Key Vault i usuari de secrets del Key Vault s'afegiran per a les conclusions del públic. Per obtenir detalls sobre aquestes funcions, aneu a [Funcions incorporades de l'Azure per a les operacions de pla de dades del Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Recomanacions

- Utilitzeu una clau independent o dedicada que només contingui els secrets necessaris per a les conclusions del públic. Llegiu més informació sobre la raó per la qual [es recomana utilitzar magatzems de claus diferents](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Seguiu les [pràctiques recomanades per utilitzar el Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) per controlar l'accés, la còpia de seguretat, l'auditoria i les opcions de recuperació.

## <a name="frequently-asked-questions"></a>Preguntes freqüents

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Les conclusions del públic poden escriure secrets o sobreescriure'n al magatzem de claus?

No. Només s'atorga a les conclusions del públic els permisos de lectura i llista que s'han detallat a la secció de [permisos concedits](#permissions-granted-on-the-key-vault-to-audience-insights) més amunt en aquest article. El sistema no pot afegir, suprimir o sobreescriure secrets al magatzem de claus. Aquesta és la raó per la qual no podeu introduir credencials quan una connexió utilitza Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Puc canviar una connexió perquè en lloc d'utilitzar els secrets del Key Vault utilitzi l'autenticació per defecte?

No. No podeu tornar a una connexió per defecte després de configurar-la mitjançant un secret d'un magatzem de claus enllaçat. Creeu una connexió independent i suprimiu l'antiga si no la necessiteu.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Com puc revocar l'accés a un magatzem de claus per a les conclusions del públic?

Segons si la [norma d'accés del Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o el [control d'accés basat en funcions de l'Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) està habilitat, heu de suprimir els permisos de l'entitat de servei `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` amb el nom `Dynamics 365 AI for Customer Insights`. Totes les connexions que utilitzin el magatzem de claus deixaran de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un secret utilitzat en una connexió s'ha eliminat del magatzem de claus. Què puc fer?

Es mostra una notificació a les conclusions del públic quan un secret configurat del magatzem de claus ja no està accessible. Habiliteu la funció de [supressió temporal](/azure/key-vault/general/soft-delete-overview) al magatzem de claus per restaurar els secrets si accidentalment se suprimeixen.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Una connexió no funciona, però el meu secret és al magatzem de claus. Quina podria ser la causa?

Es mostra una notificació a les conclusions del públic quan no pot accedir al magatzem de claus. La causa podria ser:

- Els permisos per a l'entitat de servei de les conclusions del públic s'han eliminat. S'han de restaurar manualment.

- El tallafoc del magatzem de claus està habilitat. Cal que el tallafoc estigui inhabilitat perquè el magatzem de claus torni a estar accessible per a les conclusions del públic.
