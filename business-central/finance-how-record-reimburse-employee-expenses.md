---
title: Enregistrer et rembourser les dépenses professionnelles des employés | Microsoft Docs
description: Reportez les dépenses des employés avec le journal général sur le compte de l'employé et reportez par la suite un paiement sur le compte bancaire de l'employé pour rembourser les frais professionnels.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reimbursement
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: edef774738233890af240b20622cc40585d79116
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5783832"
---
# <a name="record-and-reimburse-employees-expenses"></a>Enregistrer et rembourser les frais des employés

[!INCLUDE[prod_short](includes/prod_short.md)] prend en charge les transactions des employés de la même manière que pour les fournisseurs. Par conséquent, les groupes de report employé existent pour s'assurer que les écritures d'un employé sont reportées dans les comptes correspondants du grand livre.

> [!NOTE]  
> Les transactions des employés ne peuvent être reportées que dans la devise locale. Les paiements de remboursement aux employés ne prennent pas en charge les escomptes et les tolérances de règlement.

Si les employés dépensent leur propre argent pendant les activités professionnelles, vous pouvez reporter les frais sur le compte de l'employé. Vous pouvez ensuite rembourser l'employé en faisant un paiement sur son compte bancaire, de la même façon que vous payez des fournisseurs.  

> [!TIP]
> Cet article explique comment enregistrer les frais dans les livres et comment rembourser l'employé. Votre organisation peut avoir un portail ou une application où les employés peuvent soumettre leurs notes de frais.

## <a name="to-record-an-employees-expense"></a>Pour enregistrer les dépenses des employés
Reportez les frais employé sur la page **Journal général**.
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux généraux**, puis sélectionnez le lien associé.
2. Ouvrez le lot journal général approprié. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).
3. Sur une nouvelle ligne journal, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]    

    > [!NOTE]
    > [!INCLUDE[journal-showhide-columns-inline-tip](includes/journal-showhide-columns-inline-tip.md)]
4. Répétez l'étape 3 pour tous les frais que l'employé a supportés.

    > [!TIP]  
    > Si vous souhaitez saisir plusieurs lignes de dépenses au-dessus d'une ligne compte contrepartie du compte bancaire de l'employé, activez la case à cocher **Suggérer le montant contrepartie** de la ligne pour votre lot sur la page **Lots journal général**. Puis le champ **Montant** de la ligne compte contrepartie est automatiquement prérempli avec la valeur requise pour équilibrer les dépenses.
5. Choisissez l'action **Reporter** pour enregistrer les frais sur le compte de l'employé.

## <a name="to-reimburse-an-employee"></a>Pour rembourser un employé
Vous remboursez des employés en reportant les paiements sur leur compte bancaire sur la page **Journal paiement**.
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journaux paiement**, puis sélectionnez le lien associé.
2. Ouvrez le lot journal paiement approprié. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).
3. Renseignez les champs selon vos besoins. Pour plus d'informations, reportez-vous à [Effectuer des paiements](payables-make-payments.md).
4. Sinon, choisissez l'action **Proposer paiements aux employés** pour insérer automatiquement des lignes journal pour les remboursements employé en attente.
5. Sélectionnez l'action **Reporter** pour enregistrer le remboursement.  

## <a name="to-reconcile-reimbursements-with-employee-ledger-entries"></a>Pour rapprocher les remboursements avec les écritures de l'employé
Affectez les paiements des employés à leurs écritures employés ouvertes de la même façon que vous le faites pour les paiements des fournisseurs, par exemple sur la page **Journal rapprochement paiement**, en fonction des écritures de relevé bancaire connexes. Pour plus d'informations, reportez-vous à [Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md). Sinon, vous pouvez effectuer une affectation manuelle sur la page **Écritures employés**. Pou plus d'informations, voir [Rapprocher des paiements fournisseur avec le journal paiement ou à partir des écritures fournisseur](payables-how-apply-purchase-transactions-manually.md).  

## <a name="see-also"></a>Voir aussi
[Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md)  
[Utilisation de journaux généraux](ui-work-general-journals.md)  
[Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]