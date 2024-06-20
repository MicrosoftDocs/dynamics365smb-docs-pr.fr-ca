---
title: Réévaluer des soldes de compte du grand livre
description: Apprenez à réévaluer les soldes des comptes GL avant de produire vos états financiers.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 03/14/2024
ms.custom: bap-template
ms.search.form: null
ms.service: dynamics-365-business-central
---

# <a name="revalue-general-ledger-account-balances"></a>Réévaluer des soldes de compte du grand livre

Si vous utilisez des comptes du grand livre (GL) pour enregistrer des postes de bilan en devises étrangères, vous devez réévaluer les soldes des comptes avant de produire des états financiers. Les taux de change changent souvent et la réévaluation contribue à rendre vos états financiers plus précis.

## <a name="set-up-revaluations"></a>Configurer réévaluation

Vous configurez chaque compte que vous souhaitez inclure dans les réévaluations sur la page **Fiche de compte du grand livre** . Vous pouvez choisir de reporter les ajustements de réévaluation dans les comptes de gains/pertes réalisés ou non réalisés. La report des gains et des pertes lors d’un ajustement du taux de change suit la routine de report normale. Par exemple, vous le faites pour chaque configuration sur la page **Devises** . Pour en savoir plus sur les ajustements des taux de change, accédez à [Mettre à jour les taux de change](finance-how-update-currencies.md).

Pour minimiser les erreurs, dans le champ **Report devise origine**, vous pouvez configurer une validation pour les devises dont vous souhaitez autoriser le report sur des comptes GL individuels :

* Toutes les devises (vide)
* Plusieurs devises
* Même devise
* Devise locale

## <a name="run-a-revaluation"></a>Exécuter Réévaluation

Pour réévaluer les montants en devise étrangère dans la devise locale pour les soldes des comptes du grand livre, sur la page **Plan comptable** , utilisez l’action **Réévaluation de la devise par compte** pour démarrer un travail en lot. Le travail en lot crée des écritures d’ajustement dans le journal que vous sélectionnez. Lorsque vous reportez les écritures, vous ajustez le solde en devise locale ($) du compte. Les soldes des comptes du grand livre qui s’affichent toujours en $ reflètent désormais les modifications apportées aux devises dans lesquelles les écritures ont été reportées. Cette réévaluation vous permet de produire un état financier plus précis avec moins d’effort.

Si vous utilisez une devise de report additionnelle (dev. add.), les écritures de réévaluation du grand livre ont un montant dev. add.. Montant correspondant uniquement au montant en $ sur ces écritures, et non au solde en dev. add. sur le compte du grand livre. Si vous ajustez les taux de dev. add. après avoir reporté les ajustements, exécutez une nouvelle fois l’ajustement du taux de change de devise pour ajuster toutes les écritures du grand livre.

> [!IMPORTANT]
> La réévaluation du compte du grand livre peut ne pas répondre à toutes les exigences en matière d’enregistrement des transactions et des actifs nécessitant une réévaluation. Par exemple, pour les instruments financiers, les titres, les actifs loués, ou si vous les utilisez pour des volumes spécifiques ou importants de transactions ou d’actifs. Nous vous recommandons de discuter avec votre auditeur si vous pouvez utiliser cette fonctionnalité et, si oui, comment vous devez l’utiliser. Par exemple, si vous autorisez le mélange des devises pour un compte, ou si vous devez conserver un compte séparé pour chaque actif que vous souhaitez suivre.

> [!NOTE]
> La réévaluation ne permet pas d’affecter des écritures ou d’annuler leur affectation, comme c’est le cas avec les écritures clients et fournisseurs. Les ajustements se produisent sur une base de solde par devise.

## <a name="revaluate-accounts-vs-customer-and-vendor-exchange-rate-adjustments"></a>Réévaluer les comptes par rapport aux ajustements de taux de change des clients et des fournisseurs

La réévaluation simplifie la tâche d’ajustement des soldes des comptes du grand livre. La fonctionnalité réévalue le solde par devise et par compte du grand livre, tout comme vous le faites pour les ajustements des comptes du grand livre liés aux comptes bancaires. Si vous utilisez un compte du grand livre pour suivre plusieurs actifs, envisagez plutôt d’utiliser un compte fournisseur ou client.

> [!NOTE]
> La réévaluation du compte du grand livre peut ne pas répondre à toutes les exigences en matière d’enregistrement des transactions et des actifs nécessitant une réévaluation. Par exemple, pour les instruments financiers, les titres, les actifs loués, ou si vous les utilisez pour des volumes spécifiques ou importants de transactions ou d’actifs. Nous vous recommandons de discuter avec votre auditeur si vous pouvez utiliser cette fonctionnalité et, si oui, comment vous devez l’utiliser. Par exemple, si vous autorisez le mélange des devises pour un compte, ou si vous devez conserver un compte séparé pour chaque actif que vous souhaitez suivre.

Les exemples suivants illustrent la différence entre l’utilisation d’un compte du grand livre et l’utilisation d’un compte fournisseur pour suivre le solde de deux actifs monétaires qui utilisent une devise étrangère.

**Utilisez un compte du grand livre** Si vous utilisez un compte du grand livre pour suivre soit plusieurs actifs (par exemple, des prêts ou des immobilisations) dans la même devise, soit des transactions partielles individuelles pour le même actif mais toujours dans la même devise, la réévaluation du GL crée une écriture par réévaluation pour la devise. Cela signifie que vous ne pouvez pas suivre les ajustements liés aux actifs individuels ou aux transactions individuelles pour le même actif.

**Utiliser un compte fournisseur** Si vous configurez plusieurs actifs en tant que fournisseurs et que vous y reportez des transactions, dans la même devise ou dans des devises différentes, vous obtiendrez un ajustement par devise et par fournisseur. Ou, si vous activez le bouton à bascule **Report par écriture** sur l’écriture file d’attente des projets **Ajuster le taux de change devise**, vous obtiendrez une écriture d’ajustement pour chaque écriture fournisseur distincte.

Cette différence est importante lorsque vous évaluez si la réévaluation du grand livre est la fonctionnalité adaptée à vos besoins de rapport.

> [!TIP]
> Nous vous recommandons de demander à votre comptable ou auditeur quel type de compte convient le mieux à votre entreprise. Il pourrait également y avoir une application pour [!INCLUDE [prod_short](includes/prod_short.md)] sur [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=dynamics-365-business-central) c’est parfait pour vos scénarios commerciaux.

## <a name="see-also"></a>Voir aussi .

[Examiner les montants des comptes GL](finance-review-accounts.md)  
[Comprendre le grand livre et le plan comptable](finance-general-ledger.md)  
