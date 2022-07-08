---
title: Affecter des écritures dans des devises différentes
description: Vous pouvez affecter des écritures du grand livre dans différentes devises, par exemple si vous vendez à un client dans une devise et recevez le paiement dans une autre devise.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies, payment, reconcile
ms.search.form: 148, 460, 25
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 0ec081740ff45dc018d975f6d84deae4aae907cb
ms.sourcegitcommit: 00a8acc82cdc90e0d0db9d1a4f98a908944fd50a
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9078710"
---
# <a name="enable-application-of-ledger-entries-in-different-currencies"></a>Activer l'affectation des écritures en devises différentes

Si vous achetez des produits auprès d'un fournisseur dans une devise et que vous payez ces produits dans une autre devise, vous pouvez affecter le paiement à l'achat.

De même, si vous effectuez une vente à un client dans une devise et recevez le règlement dans une autre devise, vous pouvez affecter le règlement à la facture vente.

La procédure suivante indique comment configurer cela pour les écritures fournisseur sur la page **Configuration achats et à payer**. La configuration est semblable à celle des écritures client sur la page **Configuration des ventes et des comptes à recevoir**.

## <a name="to-enable-application-of-vendor-ledger-entries-in-different-currencies"></a>Pour activer l'affectation des écritures fournisseur en devises différentes

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration achats et à payer**, puis choisissez le lien associé.
2. Dans le champ **Lettrage entre devises**, sélectionnez l'une des options suivantes.

| Option | Description |
| --- | --- |
| Aucun |L'affectation entre devises n'est pas autorisée. |
| Devises U.M.E. |L'affectation entre devises UME est autorisée. |
| Tout |L'affectation entre toutes les devises est autorisée. |

## <a name="to-set-up-gl-accounts-for-currency-application-rounding-differences"></a>Pour configurer des comptes du grand livre afin d'autoriser les différences d'arrondissement des devises

Si vous affectez des écritures dans différentes devises, vous devez configurer les comptes du grand livre sur lesquels reporter les différences d'arrondissement.  

> [!NOTE]  
> Vous devez configurer les comptes généraux avant de terminer la tâche. Pour plus d'informations, voir [Description du grand livre et du plan comptable](finance-general-ledger.md).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Groupes de report client**, puis choisissez le lien associé.  
2. Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.  
3. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Groupes de report fournisseur**, puis choisissez le lien associé.  
4. Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/process-foreign-currency-payments-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi .

[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]