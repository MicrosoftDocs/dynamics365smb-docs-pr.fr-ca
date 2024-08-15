---
title: Aperçu des tâches permettant de gérer les paiements aux fournisseurs
description: 'Décrit les tâches permettant de gérer les paiements aux fournisseurs ou aux créditeurs, y compris le report de lignes paiement et l''obtention d''un aperçu du solde échu.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.keywords: 'print check, vendor payment, creditor, debt, balance due, AP'
ms.search.form: '254, 256, 1190, 1191, 1227, 1228, 1229'
ms.date: 07/15/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# <a name="make-payments"></a>Exécution des paiements

Vous effectuez des paiements aux fournisseurs ou aux clients, ou des remboursements aux employés, en reportant les lignes paiement sur la page **Journal paiement**. Le journal paiement est un journal général qui est optimisé pour effectuer les paiements et qui offre beaucoup d'actions puissantes. Par exemple, l'action **Suggérer des paiements fournisseur** qui recherche les paiements fournisseur qui sont dus, et le rapport **Fournisseur – Chronologie sommaire** qui montre un aperçu des paiements fournisseur dus.  

Vous pouvez lancer le processus de paiement depuis les listes, les fiches, et les écritures pour les fournisseurs, les clients, ainsi que les employés. Chacune de ces pages a un bouton démarrant le flux de paiement et vous permettant de renseigner le journal paiement.  

À partir du journal paiement, vous pouvez imprimer des chèques informatisés ou effectuer un enregistrement lorsque les chèques sont rédigés. Si vous sélectionnez **Informatique** dans le champ **Mode émission paiement**, vous devez imprimer les lignes représentant des chèques avant de reporter le journal paiement.

Une fois que les paiements sont reportés, vous pouvez les exporter-dans un fichier bancaire que vous pouvez télécharger vers votre banque pour traitement.

Une fois les paiements effectués au niveau de votre banque, vous devez les affecter à leurs écritures fournisseur ou employé ouvertes correspondantes. Vous pouvez les affecter manuellement ou en important un fichier de relevé bancaire et en affectant les paiements automatiquement. Pour plus d'informations, reportez-vous à [Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les articles qui les décrivent.

| À | Voir |
| --- | --- |
|Comprendre les fonctions de base de la page **Journal des paiements**, qui est basée sur le journal général, pour préparer le report des paiements aux fournisseurs ou employés.|[Utiliser des journaux généraux](ui-work-general-journals.md)|
|Reporter les paiements aux fournisseurs ou aux employés, et les remboursements aux clients et affecter éventuellement les paiements aux factures/notes de crédit impayées pour les fermer comme payées.|[Enregistrer des paiements et des remboursements](payables-how-post-payments-refunds.md)|
| Utilisez une fonction sur la page **Journal paiement** pour proposer des paiements fournisseur en fonction de critères sélectionnés, tels que la date d'échéance, la possibilité d'escompte et vos liquidités. |[Proposer paiements fournisseur](payables-how-suggest-vendor-payments.md) |
| Émettre des chèques pour les paiements fournisseur ou les remboursements client, sous forme de documents imprimés ou de chèques informatiques. Annuler des chèques avant ou après le report. |[Effectuer des paiements par chèque](payables-how-work-checks.md) |
|Effectuer des paiements électroniques conformément à la norme de virement SEPA de l'UE.|[Réalisation de paiements avec l'extension AMC Banking 365 Fundamentals ou le virement SEPA](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)|
| Payez un fournisseur en liquide ou par chèque et reportez le paiement lorsque vous reportez la facture. |[Établir rapidement des factures achat](finance-how-to-settle-purchase-invoices-promptly.md) |
| Assurez-vous que la banque efface uniquement les chèques et les montants validés en envoyant un fichier contenant des informations de paiement, du chèque et du fournisseur. |[Exportation du fichier Positive Pay](finance-how-positive-pay.md) |

## <a name="see-also"></a>Voir aussi .

[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
