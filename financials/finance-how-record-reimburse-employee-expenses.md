---
title: "Enregistrer et rembourser les dépenses professionnelles des employés | Microsoft Docs"
description: "Reportez les dépenses des employés avec le journal général sur le compte de l'employé et reportez par la suite un paiement sur le compte bancaire de l'employé pour rembourser les frais professionnels."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reimbursement
ms.date: 06/28/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: c12561f4851cd75bdc4098e506c113e50d3bc3be
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="record-and-reimburse-employees-expenses"></a>Enregistrer et rembourser les frais des employés
[!INCLUDE[d365fin](includes/d365fin_md.md)] prend en charge les transactions des employés de la même manière que pour les fournisseurs. Par conséquent, les groupes de report employé existent pour s'assurer que les écritures d'un employé sont reportées dans les comptes correspondants du grand livre.

> [!NOTE]  
> Les transactions des employés ne peuvent être reportées que dans la devise locale. Les paiements de remboursement aux employés ne prennent pas en charge les escomptes et les tolérances de règlement.

Si les employés dépensent leur propre argent pendant les activités professionnelles, vous pouvez reporter les frais sur le compte de l'employé. Vous pouvez ensuite rembourser l'employé en faisant un paiement sur son compte bancaire, de la même façon que vous payez des fournisseurs.

## <a name="to-record-an-employees-expense"></a>Pour enregistrer les dépenses des employés
Reportez les dépenses des employés dans la fenêtre **Journal général**.
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles comptabilité**, puis sélectionnez le lien connexe.
2. Ouvrez le lot journal général approprié. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).
3. Sur une nouvelle ligne journal, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]    
4. Répétez l'étape 3 pour tous les frais que l'employé a supportés.

    > [!TIP]  
    > Si vous souhaitez saisir plusieurs lignes de dépenses au-dessus d'une ligne compte de solde du compte bancaire de l'employé, cochez la case **Suggérer le montant de contrepartie** de la ligne pour votre lot dans la fenêtre **Lots journal général**. Puis le champ **Montant** de la ligne compte contrepartie est automatiquement prérempli avec la valeur requise pour équilibrer les dépenses.
5. Choisissez l'action **Reporter** pour enregistrer les frais sur le compte de l'employé.

## <a name="to-reimburse-an-employee"></a>Pour rembourser un employé
Vous remboursez des employés en reportant les paiements sur leur compte bancaire dans la fenêtre **Journal de paiement**.
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles paiement**, puis sélectionnez le lien connexe.
2. Ouvrez le lot journal paiement approprié. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).
3. Renseignez les champs selon vos besoins. Pour plus d'informations, reportez-vous à [Effectuer des paiements](payables-make-payments.md).
4. Sinon, choisissez l'action **Proposer paiements aux employés** pour insérer automatiquement des lignes journal pour les remboursements employé en attente.
5. Sélectionnez l'action **Reporter** pour enregistrer le remboursement.  

## <a name="to-reconcile-reimbursements-with-employee-ledger-entries"></a>Pour rapprocher les remboursements avec les écritures de l'employé
Affectez les paiements des employés à leurs écritures employés ouvertes correspondantes de la même façon que vous le faites pour les paiements des fournisseurs, par exemple dans la fenêtre **Journal rapprochement paiement**, en fonction des écritures relevé bancaire correspondantes. Pour plus d'informations, reportez-vous à [Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md). Sinon, vous pouvez effectuer une affectation manuelle dans la fenêtre **Écritures employés**. Pour plus d'informations, voir [Rapprocher les paiements fournisseur manuellement](payables-how-apply-purchase-transactions-manually.md).  

## <a name="see-also"></a>Voir aussi
[Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md)  
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)  
[Inverser des reports](finance-how-reverse-journal-posting.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

