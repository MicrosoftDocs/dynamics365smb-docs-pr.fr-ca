---
title: Aperçu des tâches permettant de gérer les paiements aux fournisseurs
description: 'Décrit les tâches permettant de gérer les paiements aux fournisseurs ou aux créditeurs, y compris le report de lignes paiement et l''obtention d''un aperçu du solde échu.'
author: edupont04
ms.topic: overview
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'print check, vendor payment, creditor, debt, balance due, AP'
ms.search.form: '254, 256, 1190, 1191, 1227, 1228, 1229'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="making-payments" />Effectuer des paiements

Lorsque vous effectuez des paiements aux fournisseurs ou aux clients, ou des remboursements aux employés, vous reportez les lignes paiement associées sur la page **Journal paiement**. Le journal paiement est un journal général qui est optimisé pour effectuer des paiements et inclut un certain nombre de fonctionnalités puissantes telles que la fonction **Proposer paiements fournisseur** qui rassemble les paiements fournisseur échus, et le rapport **Fournisseur - chronologie sommaire** qui affiche un aperçu des paiements fournisseur échus.  

Vous pouvez lancer le processus de paiement depuis des listes, des fiches et des écritures pour les fournisseurs, les clients, ainsi que les employés. Chacune de ces pages a un bouton démarrant le flux de paiement et vous permettant de renseigner le journal paiement.  

À partir du journal paiement, vous pouvez imprimer des chèques informatisés ou effectuer un enregistrement lorsque les chèques sont rédigés. Si vous sélectionnez **Informatique** dans le champ **Mode émission paiement**, toutes les lignes représentant des chèques doivent être imprimées avant que les lignes feuille puissent être validées.

Lorsque les paiements sont reportés, vous pouvez les exporter vers un fichier bancaire à télécharger vers votre banque pour traitement.

Une fois les paiements effectués au niveau de votre banque, vous devez les affecter à leurs écritures fournisseur ou employé ouvertes correspondantes. Vous pouvez le faire manuellement ou en important un fichier de relevé de compte bancaire et en affectant les paiements automatiquement. Pour plus d'informations, reportez-vous à [Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.

| À | Voir |
| --- | --- |
|Comprendre les fonctions de base de la page **Journal des paiements**, qui est basée sur le journal général, pour préparer le report des paiements aux fournisseurs ou employés.|[Utiliser des journaux généraux](ui-work-general-journals.md)|
|Reporter les paiements aux fournisseurs ou aux employés, et les remboursements aux clients et affecter éventuellement les paiements aux factures/notes de crédit impayées pour les fermer comme payées.|[Enregistrer des paiements et des remboursements](payables-how-post-payments-refunds.md)|
| Utilisez une fonction sur la page **Journal paiement** pour proposer des paiements fournisseur en fonction de critères sélectionnés, tels que la date d'échéance, la possibilité d'escompte et vos liquidités. |[Proposer paiements fournisseur](payables-how-suggest-vendor-payments.md) |
| Émettre des chèques pour les paiements fournisseur ou les remboursements client, sous forme de documents imprimés ou de chèques informatiques. Annuler des chèques avant ou après le report. |[Effectuer des paiements par chèque](payables-how-work-checks.md) |
|Effectuer des paiements électroniques conformément à la norme de virement SEPA de l'UE.|[Réalisation de paiements avec l'extension AMC Banking 365 Fundamentals ou le virement SEPA](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)|
| Payez un fournisseur en liquide ou par chèque et reportez le paiement lorsque vous reportez la facture. |[Établir rapidement des factures achat](finance-how-to-settle-purchase-invoices-promptly.md) |
| Assurez-vous que la banque efface uniquement les chèques et les montants validés en envoyant un fichier contenant des informations de paiement, du chèque et du fournisseur. |[Exporter un fichier Positive Pay](finance-how-positive-pay.md) |

## <a name="see-related-microsoft-training" />Voir la [formation Microsoft](/training/paths/process-customer-vendor-payments-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
