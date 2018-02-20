---
title: "Affecter des écritures dans des devises différentes| Microsoft Docs"
description: "Vous pouvez affecter des écritures du grand livre dans différentes devises, par exemple si vous vendez à un client dans une devise et recevez le paiement dans une autre devise."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies, payment, reconcile
ms.date: 01/25/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: d98fdf358e387be1d53b188cc05c57108e8592b8
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="enable-application-of-ledger-entries-in-different-currencies"></a>Activer l'affectation des écritures en devises différentes
Si vous achetez des produits auprès d'un fournisseur dans une devise et que vous payez ces produits dans une autre devise, vous pouvez affecter le paiement à l'achat.

De même, si vous effectuez une vente à un client dans une devise et recevez le règlement dans une autre devise, vous pouvez affecter le règlement à la facture vente.

La procédure suivante indique comment configurer cela pour les écritures comptables fournisseur dans la fenêtre **Paramètres achats**. La configuration est semblable à celle des écritures comptables client dans la fenêtre **Paramètres ventes**.

## <a name="to-enable-application-of-vendor-ledger-entries-in-different-currencies"></a>Pour activer l'affectation des écritures fournisseur en devises différentes
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres achats**, puis sélectionnez le lien connexe.
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

1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Groupes de report du client**, puis sélectionnez le lien associé.  
2. Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.  
3. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Groupes de report du fournisseur**, puis sélectionnez le lien associé.  
4. Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.  

## <a name="see-also"></a>Voir aussi
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

