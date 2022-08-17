---
title: Porteu el vostre propi magatzem de claus de l'Azure (versió preliminar)
description: Obteniu més informació sobre com configurar el Customer Insights per utilitzar el vostre propi magatzem de claus de l'Azure per gestionar secrets.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ca-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246143"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Porteu el vostre propi magatzem de claus de l'Azure (versió preliminar)

Enllaçar un magatzem de claus dedicat [de](/azure/key-vault/general/basic-concepts) l'Azure a un entorn del Customer Insights ajuda les organitzacions a complir els requisits de compliment.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Enllaçar la clau a l'entorn del Customer Insights

Configureu la volta de claus dedicada a escenificar i utilitzar secrets en el límit de compliment d'una organització.

### <a name="prerequisites"></a>Requisits previs

- Una subscripció activa de l'Azure.

- Una [funció d'administrador](permissions.md#admin)[assignada](permissions.md#add-users) al Customer Insights.

- [Funcions d'administrador](/azure/role-based-access-control/built-in-roles#contributor) de col·laborador [i](/azure/role-based-access-control/built-in-roles#user-access-administrator) d'accés d'usuari a la volta de claus o al grup de recursos al qual pertany la clau. Per obtenir més informació, aneu a [Afegir o eliminar assignacions de funcions de l'Azure utilitzant el portal de l'Azure](/azure/role-based-access-control/role-assignments-portal). Si no teniu la funció d'administrador d'accés d'usuari al dipòsit de claus, configureu els permisos de control d'accés basats en funcions per al principal del servei de l'Azure per Dynamics 365 Customer Insights separat. Seguiu els passos per [utilitzar l'entitat de servei de l'Azure](connect-service-principal.md) per al magatzem de claus que s'ha d'enllaçar.

- Key vault ha de tenir desactivat el **tallafoc** de Key Vault.

- Key vault es troba a la mateixa [ubicació](https://azure.microsoft.com/global-infrastructure/geographies/#overview) de l'Azure que l'entorn del Customer Insights. Al Customer Insights, aneu a **Sistema** > **d'administració** i a la **pestanya Quant** a per veure la regió de l'entorn.

### <a name="recommendations"></a>Recomanacions

- [Utilitzeu una clau independent o dedicada](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) que només contingui els secrets necessaris per al Customer Insights.

- Seguiu les [pràctiques recomanades per utilitzar el Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) per controlar l'accés, la còpia de seguretat, l'auditoria i les opcions de recuperació.

### <a name="link-a-key-vault-to-the-environment"></a>Enllaçar un magatzem de claus amb l'entorn

1. Aneu a Seguretat d'administració i, a **continuació, seleccioneu la** > **pestanya Key Vault**.**·**
1. A la peça **Key Vault**, seleccioneu **Configuració**.
1. Trieu una **Subscripció**.
1. Trieu un magatzem de claus de la llista desplegable **Key Vault**. Si hi ha massa voltes de claus disponibles, seleccioneu un grup de recursos per limitar els resultats de la cerca.
1. Reviseu la [Privadesa de les dades i el compliment](connections.md#data-privacy-and-compliance) i, a continuació, seleccioneu **Accepto**.
1. Seleccioneu **Desa**.

La **peça Key Vault** mostra el nom de la volta de clau enllaçada, la subscripció i el grup de recursos. Està a punt per utilitzar-se en la configuració de connexió.
Per obtenir més informació sobre quins permisos de la clau es concedeixen al Customer Insights, aneu a [Permisos concedits a la clau](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilitzar el magatzem de claus de la configuració de connexió

Quan [configureu connexions a](connections.md) sistemes de tercers [compatibles](#supported-connection-types), utilitzeu els secrets del Key Vault enllaçat per configurar les connexions.

1. Aneu a **Administració** > **Connexions**.
1. Seleccioneu **Afegeix una connexió**.
1. Per als tipus de connexió compatibles, hi ha disponible una commutació **Utilitza el Key Vault** si heu enllaçat un magatzem de claus.
1. En lloc d'introduir el secret manualment, trieu el nom secret que assenyala el valor secret de la volta de la clau.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Subfinestra de connexió amb una connexió SFTP que utilitza un secret del Key Vault.":::

1. Seleccioneu **Desa** per crear la connexió.

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

## <a name="permissions-granted-on-the-key-vault"></a>Permisos concedits a la volta de claus

Els permisos següents es concedeixen al Customer Insights en un magatzem de claus enllaçades si s'habilita [una norma](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) d'accés a Key Vault o [un control](/azure/key-vault/general/rbac-guide?tabs=azure-cli) d'accés basat en funcions de l'Azure.

### <a name="key-vault-access-policy"></a>Norma d'accés del Key Vault

| Type        | Permisos          |
| ----------- | -------------------- |
| Tecla         | [Obtén les claus](/rest/api/keyvault/keys/get-keys/get-keys), [Obtén la clau](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Secret      | [Obtén els secrets](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Obtén el secret](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certificat | [Obtén els certificats](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Obtén el certificat](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Els valors anteriors són el mínim per llistar i llegir durant l'execució.

### <a name="azure-role-based-access-control"></a>Control d'accés basat en funcions de l'Azure

Les [funcions d'usuari de Key Vault Reader i Key Vault Secrets s'afegiran](/azure/key-vault/general/rbac-guide?tabs=azure-cli) per a customer insights.

## <a name="frequently-asked-questions"></a>Preguntes freqüents

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>El Customer Insights pot escriure secrets o sobreescriure secrets a la volta de claus?

No. Només es concedeixen al Customer Insights els permisos de lectura i de llista descrits als [permisos concedits](#permissions-granted-on-the-key-vault). El sistema no pot afegir, suprimir o sobreescriure secrets al magatzem de claus. Aquesta és la raó per la qual no podeu introduir credencials quan una connexió utilitza Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Puc canviar una connexió perquè en lloc d'utilitzar els secrets del Key Vault utilitzi l'autenticació per defecte?

No. No podeu tornar a una connexió per defecte després de configurar-la mitjançant un secret d'un magatzem de claus enllaçat. Creeu una connexió independent i suprimiu l'antiga si no la necessiteu.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Com puc revocar l'accés a un magatzem de claus per al Customer Insights?

Si la norma [d'accés a Key Vault o](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) el [control](/azure/key-vault/general/rbac-guide?tabs=azure-cli) d'accés basat en funcions de l'Azure està habilitat, elimineu els permisos del principal del `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` servei amb el nom `Dynamics 365 AI for Customer Insights`. Totes les connexions que utilitzin el magatzem de claus deixaran de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un secret utilitzat en una connexió s'ha eliminat del magatzem de claus. Què puc fer?

Una notificació apareix al Customer Insights quan ja no es pot accedir a un secret configurat des de la volta de claus. Habiliteu la funció de [supressió temporal](/azure/key-vault/general/soft-delete-overview) al magatzem de claus per restaurar els secrets si accidentalment se suprimeixen.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Una connexió no funciona, però el meu secret és al magatzem de claus. Quina podria ser la causa?

Una notificació apareix al Customer Insights quan no pot accedir a la clau. La causa podria ser:

- S'han suprimit els permisos del director del servei del Customer Insights. S'han de restaurar manualment.

- El tallafoc del magatzem de claus està habilitat. El tallafoc s'ha de desactivar perquè la volta de claus torni a ser accessible per al Customer Insights.
