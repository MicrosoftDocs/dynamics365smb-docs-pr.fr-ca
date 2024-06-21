---
title: Enregistrer et rembourser les frais des employés
description: Reportez les dépenses des employés avec le journal général sur le compte de l’employé et reportez par la suite un paiement sur le compte bancaire de l’employé pour rembourser les frais liés à l’entreprise.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: reimbursement
ms.search.form: '63, 234, 625, 5224, 5237, 5238, 5239, 5240'
ms.date: 03/13/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="record-and-reimburse-employees-expenses"></a>Enregistrer et rembourser les frais des employés

[!INCLUDE[prod_short](includes/prod_short.md)] prend en charge les transactions des employés de la même manière que pour les fournisseurs. Par conséquent, les groupes de report employé existent pour s'assurer que les écritures d'un employé sont reportées dans les comptes correspondants du grand livre.

> [!NOTE]  
> Les paiements de remboursement aux employés ne prennent pas en charge les escomptes et les tolérances de règlement.

Si les employés dépensent leur propre argent pendant les activités professionnelles, vous pouvez reporter les frais sur le compte de l'employé. Vous pouvez ensuite rembourser l'employé en faisant un paiement sur son compte bancaire, de la même façon que vous payez des fournisseurs.  

Cet article explique comment enregistrer les frais dans les livres et comment rembourser l'employé. Votre organisation peut avoir un portail ou une application où les employés peuvent soumettre leurs notes de frais.

[!INCLUDE [prod_short](includes/prod_short.md)] est suffisamment flexible pour s’adapter à de nombreuses pratiques différentes. Les numéros de compte exacts à utiliser dépendent de la configuration et des processus de votre organisation.  

Vous pouvez utiliser les journaux généraux des comptes des employés pour enregistrer les dépenses des employés et les transactions de remboursement en devises étrangères, puis suivre facilement les montants et les comparer aux reçus. Laissez votre calculatrice dans le tiroir de votre bureau : Business Central peut ajuster le taux de change pour vous. Lorsque vous utilisez les journaux généraux pour reporter des transactions pour les comptes d’employés, par exemple lorsque vous remboursez des dépenses, vous pouvez utiliser le champ **Code devise** pour spécifier la devise des transactions. La spécification d’une devise vous permet d’utiliser les mêmes fonctionnalités que lorsque vous enregistrez des transactions dans les livres comptables clients et fournisseurs. Par exemple, les employés peuvent enregistrer une dépense en euros mais être payés en dollars.

Pour garantir que le taux de change des montants est à jour, vous pouvez ajuster les soldes des employés lorsque vous exécutez le traitement en lot du taux de change des devises. Si vous souhaitez utiliser la table des taux de change, mais régler les soldes des employés dans votre devise locale, vous pouvez exclure les comptes des employés lorsque vous ajustez les taux de change.

## <a name="to-record-an-employees-expense"></a>Pour enregistrer les dépenses des employés

Reportez les frais employé sur la page **Journal général**.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux généraux**, puis choisissez le lien associé.  
2. Ouvrez le lot journal général approprié. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).
3. Sur une nouvelle ligne journal, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    > [!NOTE]
    > [!INCLUDE[journal-showhide-columns-inline-tip](includes/journal-showhide-columns-inline-tip.md)]
4. Répétez l'étape 3 pour tous les frais que l'employé a supportés.

    > [!TIP]  
    > Si vous souhaitez saisir plusieurs lignes de dépenses au-dessus d'une ligne compte contrepartie du compte bancaire de l'employé, activez la case à cocher **Suggérer le montant contrepartie** de la ligne pour votre lot sur la page **Lots journal général**. Puis le champ **Montant** de la ligne compte contrepartie est automatiquement prérempli avec la valeur requise pour équilibrer les dépenses.
5. Choisissez l'action **Reporter** pour enregistrer les frais sur le compte de l'employé.

## <a name="to-reimburse-an-employee"></a>Pour rembourser un employé

Vous remboursez des employés en reportant les paiements sur leur compte bancaire sur la page **Journal paiement**.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux paiement**, puis choisissez le lien associé.
2. Ouvrez le lot journal paiement approprié. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).
3. Renseignez les champs selon vos besoins. Pour plus d'informations, reportez-vous à [Effectuer des paiements](payables-make-payments.md).
4. Sinon, choisissez l'action **Proposer paiements aux employés** pour insérer automatiquement des lignes journal pour les remboursements employé en attente.
5. Sélectionnez l'action **Reporter** pour enregistrer le remboursement.  

## <a name="to-reconcile-reimbursements-with-employee-ledger-entries"></a>Pour rapprocher les remboursements avec les écritures de l'employé

Affectez les paiements des employés à leurs écritures employés ouvertes de la même façon que vous le faites pour les paiements des fournisseurs, par exemple sur la page **Journal rapprochement paiement**, en fonction des écritures de relevé bancaire connexes. Pour plus d'informations, reportez-vous à [Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md). Sinon, vous pouvez effectuer une affectation manuelle sur la page **Écritures employés**. Pou plus d'informations, voir [Rapprocher des paiements fournisseur avec le journal paiement ou à partir des écritures fournisseur](payables-how-apply-purchase-transactions-manually.md).  

## <a name="see-also"></a>Voir aussi

[Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
