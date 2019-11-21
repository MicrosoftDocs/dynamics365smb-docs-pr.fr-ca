---
title: Mettre à jour des taux de change devise| Microsoft Docs
description: Suivez des montants dans différentes devises à l'aide de codes devise, et laissez Business Central ajuster les taux de change des écritures reportées avec un service externe.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: multiple currencies, adjust exchange rates
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: c971a3cd11f34db0ff04cd66096d74909cca3651
ms.sourcegitcommit: ab4141739a53ec100d42773f0da863fbeefa384f
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/14/2019
ms.locfileid: "2577265"
---
# <a name="update-currency-exchange-rates"></a>Mettre à jour des taux de change devise
Les compagnies opérant dans un nombre croissant de pays/régions, il est de plus en plus important qu'elles puissent échanger ou générer des rapports financiers dans plusieurs devises. Vous devez définir un code pour chaque devise utilisée si vous achetez ou vendez dans des devises différentes de votre devise locale, si vous disposez de comptes client ou fournisseur dans d'autres devises, ou si vous enregistrez des transactions GL dans des devises différentes.

Votre grand livre est configuré pour utiliser votre devise locale ($), mais vous pouvez le configurer pour utiliser une autre devise avec un taux de change courant. Si vous désignez une deuxième devise comme « devise de report additionnelle », [!INCLUDE[d365fin](includes/d365fin_md.md)] enregistre automatiquement les montants en $ et dans cette devise de report additionnelle pour chaque écriture, ainsi que pour d'autres écritures, telles que les écritures TVA. Pour plus d'informations, voir [Configurer une devise de report additionnelle](finance-how-setup-additional-currencies.md).

## <a name="adjusting-exchange-rates"></a>Ajustement des taux de change
Comme les taux de change ne cessent de fluctuer, il convient d'ajuster périodiquement les équivalents devise supplémentaires de votre système. À défaut d'effectuer ces ajustements, les montants convertis à partir de devises étrangères (ou additionnelles) et reportés dans le grand livre en $ risquent d'être erronés. En outre, les écritures quotidiennes reportées avant la saisie d'un taux de change quotidien dans l'application doivent être mises à jour après la saisie quotidienne des informations de taux de change.

Le traitement en lot **Ajuster taux de change** permet d'ajuster manuellement les taux de change des écritures client, fournisseur et compte bancaire reportées. D'autres montants en devise de report additionnelle peuvent également être mis à jour dans les écritures. Vous pouvez aussi faire ajuster les taux de change automatiquement à l'aide d'un service. Pour plus d'informations, reportez vous à [Configurer un service de taux de change des devises](finance-how-update-currencies.md#to-set-up-a-currency-exchange-rate-service).

### <a name="effect-on-customers-and-vendors"></a>Effet sur les clients et fournisseurs
Pour les comptes client et fournisseur, le traitement en lot ajuste la devise en utilisant le taux de change qui est valide à la date de report spécifiée dans le traitement en lot. Le traitement en lot calcule les différences pour chaque solde en devise et reporte les montants dans le compte GL spécifié dans le champ **Compte gains non réalisés** ou **Compte pertes non réalisées** de la page **Devises**. Les écritures de contrepartie sont automatiquement reportées sur le compte client/fournisseur dans le grand livre.

Ce traitement en lot traite toutes les écritures client et toutes les écritures fournisseur ouvertes. En cas de différence du taux de change d'une écriture, le traitement en lot crée une écriture client ou fournisseur détaillée reflétant le montant ajusté dans l'écriture client ou fournisseur.

#### <a name="dimensions-on-customer-and-vendor-ledger-entries"></a>Dimensions sur des écritures client et fournisseur
Les dimensions des écritures client/fournisseur sont affectées aux écritures ajustement et les ajustements sont reportés par combinaison de valeurs de dimension.

### <a name="effect-on-bank-accounts"></a>Effet sur les comptes bancaires
Pour les comptes bancaires, le traitement en lot ajuste la devise en utilisant le taux de change qui est valide à la date de report spécifiée dans le traitement en lot. Le traitement en lot calcule les différences pour chaque compte bancaire possédant un code devise et reporte les montants dans le compte GL spécifié dans le champ **Compte gains réalisés** ou **Compte pertes réalisées** de la page **Devises**. Les écritures de contrepartie sont automatiquement reportées sur les comptes bancaires du grand livre spécifiés dans les groupes de report compte bancaire. Le traitement en lot calcule une écriture par devise et par groupe de report.

#### <a name="dimensions-on-bank-account-entries"></a>Dimensions sur des écritures compte bancaire
Les dimensions par défaut du compte bancaire sont affectées aux écritures ajustement pour le compte GL du compte bancaire et pour le compte gain/perte.

### <a name="effect-on-gl-accounts"></a>Effet sur les comptes du grand livre
Si vous effectuez le report dans une devise de report additionnelle, vous pouvez demander au traitement en lot de créer de nouvelles écritures pour les ajustements de devise entre devise locale ($) et devise de report additionnelle. Le traitement en lot calcule les différences pour chaque écriture GL et ajuste l'écriture GL en fonction de la valeur du champ **Ajustement taux de change** de chaque compte GL.

##### <a name="dimensions-on-gl-account-entries"></a>Dimensions sur des écritures compte du grand livre
Les dimensions par défaut des comptes dans lesquels elles sont reportées sont affectées aux écritures ajustement.

> [!Important]
> Avant de pouvoir utiliser le traitement en lot, vous devez entrer les taux de change ajustement qui sont utilisés pour ajuster les soldes en devises étrangères. Pour ce faire sur la page **Taux de change devise**.

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE3Q24s]

## <a name="to-set-up-a-currency-exchange-rate-service"></a>Configurer un service de taux de change des devises
Vous pouvez utiliser un service externe pour tenir vos taux de change des devises à jour, par exemple FloatRates.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Services de taux de change devise**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Sur la page **Service de taux de change devise**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Activez la case à cocher **Activé** pour activer le service.

## <a name="to-update-currency-exchange-rates-through-a-service"></a>Pour mettre à jour les taux de change des devises à partir d'un service
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Devises**, puis choisissez le lien associé.
2. Choisissez l'option **Mettre à jour les taux de change**.

La valeur dans le champ **Taux de change** de la page **Devises** est mise à jour avec le dernier taux de change des devises.

## <a name="see-also"></a>Voir aussi
[Configurer une devise de report additionnelle](finance-how-setup-additional-currencies.md)  
[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
