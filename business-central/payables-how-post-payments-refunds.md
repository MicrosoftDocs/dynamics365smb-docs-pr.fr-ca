---
title: Enregistrer les paiements et remboursements dans les journaux paiement
description: Découvrez comment enregistrer les paiements effectués aux fournisseurs et les remboursements effectués aux clients sur la page Journal paiement.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'payment journal, print check, vendor payment, customer refund, refund check, creditor, debt, balance due, AP'
ms.search.form: '256, 233, 624, 1228'
ms.date: 07/17/2024
ms.service: dynamics-365-business-central
---
# <a name="record-payments-and-refunds-in-the-payment-journal"></a>Enregistrer les paiements et remboursements dans le journal paiement

Sur la page **Journaux de paiement**, vous enregistrez les paiements que vous effectuez aux fournisseurs et les remboursements que vous effectuez aux clients. Lorsque vous reportez une ligne journal paiement, le montant payé est enregistré sur le compte bancaire spécifié. Vous devez ensuite effectuer des actions pour procéder au transfert d'argent réel à partir du compte bancaire associé.  

Les journaux paiement sont les journaux généraux qui sont optimisés pour effectuer les paiements. Vous pouvez rapidement ajouter des lignes manuellement, vous pouvez laisser [!INCLUDE[prod_short](includes/prod_short.md)] proposer des paiements fournisseur, et vous pouvez affecter le paiement à des documents reportés. Bien que vous effectuez des paiements, vous entrez un montant positif dans le champ **Montant du document**. Selon le type de document de la ligne journal, ce montant est ensuite converti en montant négatif dans les transactions sous-jacentes. Ainsi, il est plus rapide pour vous d'ajouter des lignes journal manuellement. Si vous préférez saisir des montants négatifs, vous pouvez personnaliser le journal paiement pour afficher le champ **Montant** à la place. Pour en savoir plus sur les pages de personnalisation, accédez à [Commencer à personnaliser en utilisant le mode de personnalisation](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).  

- Affecter des paiements à des factures ou des notes de crédit

    Si vous renseignez le champ **N° doc. référence** avec la facture ou la note de crédit qui doit être payée ou remboursée, le document en question est défini sur **Payé** lorsque vous reportez le journal. Ce paramètre s'appelle « affecté. » Outre l'affectation lors du report d'un paiement, vous pouvez utiliser les pages **Affecter écritures fournisseur** et **Affecter écritures client** après avoir reporté le paiement. Pou plus d’informations, voir par exemple [Rapprocher des paiements fournisseur avec le journal paiement ou à partir des écritures fournisseur](payables-how-apply-purchase-transactions-manually.md).  

- Obtenir des suggestions de paiements aux fournisseurs ou aux employés

    Les actions **Proposer paiements fournisseur** et **Proposer paiements employé** peuvent vous aider à renseigner automatiquement les lignes journal paiement en fonction de la priorité des fournisseurs et des dates d’échéance. Pour en savoir plus, rendez-vous sur [Suggérer des paiements au fournisseur](payables-how-suggest-vendor-payments.md). Avec cette fonction, le champ **N° doc. référence** est toujours renseigné.  

- Imprimer des chèques et envoyer des paiements électroniques à votre banque

    Outre l'enregistrement du paiement, vous pouvez également utiliser la page **Journal paiement** pour générer le paiement à des fins de traitement par votre banque. Pour plus d’informations, allez [Effectuer des paiements par chèque](payables-how-work-checks.md) et [Effectuer des paiements électroniques](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).  

## <a name="to-make-payments-in-the-payment-journal"></a>Pour effectuer des paiements dans le journal paiement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux paiement**, puis choisissez le lien associé.
2. Ouvrez le lot journal que vous utilisez pour les paiements.
3. Si vous savez qui payer, renseignez les champs manuellement. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Pour appliquer également le paiement à la facture ou à la note de crédit associée, sélectionnez le champ  **N° de document applicable**, sur la page  **Appliquer les entrées du fournisseur**, sélectionnez la facture ou la note de crédit concernée, puis sélectionnez le bouton **OK** .

    De nombreux champs, tels que **Montant du document** et **Date d’échéance**, contiennent désormais les informations du document sélectionné.
5. Sinon, utilisez la action **Proposer paiements fournisseur**. Tous les montants et informations de référence sont également saisis sur les lignes journal. Pour en savoir plus, rendez-vous sur [Suggérer des paiements au fournisseur](payables-how-suggest-vendor-payments.md).
6. Lorsque toutes les lignes journal paiement sont renseignées, choisissez l'action**Reporter**.

## <a name="to-issue-a-refund-check"></a>Pour émettre un chèque de remboursement

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journaux paiement**, puis sélectionnez le lien associé.
2. Dans le champ **Type document**, sélectionnez **Remboursement**.  
3. Dans le champ **N° de document externe**, entrez référence pour le chèque de remboursement (par exemple, numéro de commande de retour).  
4. Dans le champ **Type compte**, sélectionnez **Client**.  
5. Dans le champ **N° de compte**, sélectionnez le numéro de compte du client auquel le chèque de remboursement est émis.  
6. Dans le champ **Montant**, entrez le total à rembourser.  
7. Dans le champ **Type compte contrepartie**, sélectionnez **Compte bancaire**.  
8. Dans le champ  **N° de compte solde**, Sélectionner indique le compte bancaire d’où provient le chèque.  
9. Dans le champ **N° doc. lettrage**, sélectionnez les documents nécessitant un remboursement.  
10. Lorsque vous avez rempli toutes les lignes journal paiement, choisissez l’action **Reporter/Imprimer**, puis l’action **Reporter et imprimer**, puis **Oui**.  
  
## <a name="see-also"></a>Voir aussi .

[Exécution des paiements par chèque](payables-how-work-checks.md)  
[Désignation des paiements électroniques](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Paramétrage des opérations bancaires](bank-setup-banking.md)  
[Exporter un fichier Positive Pay](finance-how-positive-pay.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Personnaliser votre espace de travail](ui-personalization-user.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
