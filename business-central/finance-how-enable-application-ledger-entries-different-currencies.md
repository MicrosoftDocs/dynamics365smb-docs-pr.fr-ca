---
title: Affecter des écritures dans des devises différentes| Microsoft Docs
description: Vous pouvez affecter des écritures du grand livre dans différentes devises, par exemple si vous vendez à un client dans une devise et recevez le paiement dans une autre devise.
services: project-madeira
documentationcenter: ''
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies, payment, reconcile
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 564ac8edfb21573e310a3be3eaa22060d84bef22
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4750915"
---
# <a name="enable-application-of-ledger-entries-in-different-currencies"></a>Activer l'affectation des écritures en devises différentes
Si vous achetez des produits auprès d'un fournisseur dans une devise et que vous payez ces produits dans une autre devise, vous pouvez affecter le paiement à l'achat.

De même, si vous effectuez une vente à un client dans une devise et recevez le règlement dans une autre devise, vous pouvez affecter le règlement à la facture vente.

La procédure suivante indique comment configurer cela pour les écritures fournisseur sur la page **Configuration achats et à payer**. La configuration est semblable à celle des écritures client sur la page **Configuration des ventes et des comptes à recevoir**.

## <a name="to-enable-application-of-vendor-ledger-entries-in-different-currencies"></a>Pour activer l'affectation des écritures fournisseur en devises différentes
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration achats et à payer**, puis sélectionnez le lien associé.
2. Dans le champ **Lettrage entre devises**, sélectionnez l'une des options suivantes.

| Option | Description |
| --- | --- |
| Aucun |L'affectation entre devises n'est pas autorisée. |
| Devises U.M.E. |L'affectation entre devises UME est autorisée. |
| Tout |L'affectation entre toutes les devises est autorisée. |

## <a name="to-set-up-gl-accounts-for-currency-application-rounding-differences"></a>Pour configurer des comptes du grand livre afin d'autoriser les différences d'arrondissement des devises  
Si vous affectez des écritures dans différentes devises, vous devez configurer les comptes du grand livre sur lesquels reporter les différences d'arrondissement.  

> [!NOTE]  
>  Vous devez configurer les comptes généraux avant de terminer la tâche. Pour plus d'informations, voir [Description du grand livre et du plan comptable](finance-general-ledger.md).

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Groupes de report client**, puis sélectionnez le lien associé.  
2. Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.  
3. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Groupes de report fournisseur**, puis sélectionnez le lien associé.  
4. Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.  

## <a name="see-also"></a>Voir aussi
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)
