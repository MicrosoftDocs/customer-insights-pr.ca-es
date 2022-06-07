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
ms.openlocfilehash: d4f2d5ebc828053c40e22065f4915c4d0f84153f
ms.sourcegitcommit: 6ec4626a185892dfb781d3c7af4384f9c13f3723
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 05/17/2022
ms.locfileid: "8763567"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Porteu el vostre propi magatzem de claus de l'Azure (versió preliminar)

Enllaçar un dipòsit de claus [dedicat](/azure/key-vault/general/basic-concepts) de l'Azure a un entorn del Customer Insights ajuda les organitzacions a complir els requisits de compliment.
El magatzem de claus dedicat es pot utilitzar per escenificar i utilitzar els secrets en el límit de compliment de l'organització. El Customer Insights pot utilitzar els secrets de l'Azure Key Vault per [configurar connexions](connections.md) a sistemes de tercers.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Enllaça el dipòsit de claus a l'entorn del Customer Insights

### <a name="prerequisites"></a>Requisits previs

Per configurar el dipòsit de claus al Customer Insights, s'han de complir els requisits previs següents:

- Heu de tenir una subscripció activa de l'Azure.

- Teniu una funció d'administrador [a](permissions.md#admin) Customer Insights. Obteniu més informació sobre els [permisos d'usuari a l'Insights del client](permissions.md#assign-roles-and-permissions).

- Teniu les funcions [Col·laborador](/azure/role-based-access-control/built-in-roles#contributor) i [Administrador d'accés d'usuari](/azure/role-based-access-control/built-in-roles#user-access-administrator) al magatzem de claus o al grup de recursos al qual pertany el magatzem de claus. Per obtenir més informació, aneu a [Afegir o eliminar assignacions de funcions de l'Azure utilitzant el portal de l'Azure](/azure/role-based-access-control/role-assignments-portal). Si no teniu la funció Administrador d'accés d'usuari al magatzem de claus, heu de configurar els permisos de control d'accés basats en funcions per a l'entitat de servei de l'Azure per al Dynamics 365 Customer Insights per separat. Seguiu els passos per [utilitzar l'entitat de servei de l'Azure](connect-service-principal.md) per al magatzem de claus que s'ha d'enllaçar.

- El magatzem de claus ha de tenir el tallafoc del Key Vault **inhabilitat**.

- El dipòsit de claus es troba a la mateixa [ubicació](https://azure.microsoft.com/global-infrastructure/geographies/#overview) de l'Azure que l'entorn Customer Insights. La regió de l'entorn de Customer Insights es mostra a Regió **Quant** > **a regió** > **del sistema** > **d'administració**.

### <a name="link-a-key-vault-to-the-environment"></a>Enllaçar un magatzem de claus amb l'entorn

1. Aneu a **Seguretat** > **de l'administrador** i, a continuació, seleccioneu la **pestanya Dipòsit de claus**.
1. A la peça **Key Vault**, seleccioneu **Configuració**.
1. Trieu una **Subscripció**.
1. Trieu un magatzem de claus de la llista desplegable **Key Vault**. Si es mostren massa magatzems de claus, seleccioneu un grup de recursos per limitar els resultats de la cerca.
1. Accepteu la declaració de **Privadesa de les dades i compliment**.
1. Seleccioneu **Desa**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Passos per configurar un dipòsit de claus enllaçat a Customer Insights.":::

La peça **Key Vault** mostra ara el nom del magatzem de claus enllaçat, el grup de recursos i la subscripció. Està a punt per utilitzar-se en la configuració de connexió.
Per obtenir més informació sobre quins permisos del dipòsit de claus es concedeixen al Customer Insights, aneu a [Permisos concedits al dipòsit de claus](#permissions-granted-on-the-key-vault), més endavant en aquest article.

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

## <a name="permissions-granted-on-the-key-vault"></a>Permisos concedits al dipòsit de claus

Els permisos següents es concedeixen al Customer Insights en un dipòsit de claus enllaçat si [la política](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) d'accés key vault o [el control](/azure/key-vault/general/rbac-guide?tabs=azure-cli) d'accés basat en funcions de l'Azure estan habilitades.

### <a name="key-vault-access-policy"></a>Norma d'accés del Key Vault

| Type        | Permisos          |
| ----------- | -------------------- |
| Tecla         | [Obtén les claus](/rest/api/keyvault/keys/get-keys/get-keys), [Obtén la clau](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Secret      | [Obtén els secrets](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Obtén el secret](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certificat | [Obtén els certificats](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Obtén el certificat](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Els valors anteriors són el mínim per llistar i llegir durant l'execució.

### <a name="azure-role-based-access-control"></a>Control d'accés basat en funcions de l'Azure

Les funcions d'usuari Key Vault Reader i Key Vault Secrets s'afegiran per a les estadístiques del client. Per obtenir detalls sobre aquestes funcions, aneu a [Funcions incorporades de l'Azure per a les operacions de pla de dades del Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Recomanacions

- Utilitzeu un dipòsit de claus separat o dedicat que contingui només els secrets necessaris per al Customer Insights. Llegiu més informació sobre la raó per la qual [es recomana utilitzar magatzems de claus diferents](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Seguiu les [pràctiques recomanades per utilitzar el Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) per controlar l'accés, la còpia de seguretat, l'auditoria i les opcions de recuperació.

## <a name="frequently-asked-questions"></a>Preguntes freqüents

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Pot Customer Insights escriure secrets o sobreescriure secrets a la volta de claus?

No. Només els permisos de lectura i llista descrits a la [secció de permisos concedits](#permissions-granted-on-the-key-vault) anteriorment en aquest article es concedeixen al Customer Insights. El sistema no pot afegir, suprimir o sobreescriure secrets al magatzem de claus. Aquesta és la raó per la qual no podeu introduir credencials quan una connexió utilitza Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Puc canviar una connexió perquè en lloc d'utilitzar els secrets del Key Vault utilitzi l'autenticació per defecte?

No. No podeu tornar a una connexió per defecte després de configurar-la mitjançant un secret d'un magatzem de claus enllaçat. Creeu una connexió independent i suprimiu l'antiga si no la necessiteu.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Com puc revocar l'accés a un dipòsit de claus per al Customer Insights?

Segons si la [norma d'accés del Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o el [control d'accés basat en funcions de l'Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) està habilitat, heu de suprimir els permisos de l'entitat de servei `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` amb el nom `Dynamics 365 AI for Customer Insights`. Totes les connexions que utilitzin el magatzem de claus deixaran de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un secret utilitzat en una connexió s'ha eliminat del magatzem de claus. Què puc fer?

Una notificació apareix a Customer Insights quan ja no es pot accedir a un secret configurat des del dipòsit de claus. Habiliteu la funció de [supressió temporal](/azure/key-vault/general/soft-delete-overview) al magatzem de claus per restaurar els secrets si accidentalment se suprimeixen.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Una connexió no funciona, però el meu secret és al magatzem de claus. Quina podria ser la causa?

Apareix una notificació a Customer Insights quan no pot accedir al dipòsit de claus. La causa podria ser:

- S'han suprimit els permisos del principal del servei del Customer Insights. S'han de restaurar manualment.

- El tallafoc del magatzem de claus està habilitat. Cal inhabilitar el tallafoc per tornar a fer que el dipòsit de claus sigui accessible per al Customer Insights.
