---
title: Affecter des paiements à des documents connexes et les reporter | Microsoft Docs
description: Décrit comment enregistrer les paiements effectués aux fournisseurs et les remboursements effectués aux clients.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment journal, print check, vendor payment, customer refund, creditor, debt, balance due, AP
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: b45b4c109d33773ead4e920d5692a615faa7a366
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4759602"
---
# <a name="record-payments-and-refunds-in-the-payment-journal"></a>Enregistrer les paiements et remboursements dans le journal paiement

Sur la page **Journal paiement**, vous enregistrez les paiements effectués aux fournisseurs et les remboursements effectués aux clients. Lorsque vous reportez une ligne journal des paiements, le montant payé est enregistré sur le compte bancaire système spécifié. Vous devez ensuite effectuer des actions pour procéder au transfert d'argent réel à partir du compte bancaire associé.  

Le journal paiement est un journal général qui est optimisé pour effectuer des paiements. Vous pouvez rapidement ajouter des lignes manuellement, vous pouvez laisser [!INCLUDE[prod_short](includes/prod_short.md)] proposer des paiements fournisseur, et vous pouvez affecter le paiement à des documents reportés. Bien que vous effectuiez des paiements, vous entrez un montant positif dans le champ **Montant du document**. Selon le type de document de la ligne journal, ce montant est ensuite converti en montant négatif dans les transactions sous-jacentes. Ainsi, il est plus rapide pour vous d'ajouter des lignes journal manuellement. Si vous préférez saisir des montants négatifs, vous pouvez personnaliser le journal paiement pour afficher le champ **Montant** à la place.  

- Affecter des paiements à des factures ou des notes de crédit

    Si vous renseignez le champ **N° doc. référence** avec la facture ou la note de crédit qui doit être payée ou remboursée, le document en question est défini sur Payé lorsque vous reportez le journal. C'est ce qu'on appelle « affecté ». Outre l'affectation lors du report du paiement, vous pouvez utiliser la page **Affecter écritures fournisseur** et **Affecter écritures client** après avoir reporté le paiement. Pou plus d'informations, voir par exemple [Rapprocher des paiements fournisseur avec le journal paiement ou à partir des écritures fournisseur](payables-how-apply-purchase-transactions-manually.md).  

- Obtenir des suggestions de paiements aux fournisseurs ou aux employés

    Les fonctions **Proposer paiements fournisseur** et **Proposer paiements employé** peuvent vous aider à renseigner automatiquement les lignes journal paiement en fonction de la priorité des fournisseurs et des dates d'échéance. Pour plus d'informations, reportez vous à [Proposer des paiements fournisseur](payables-how-suggest-vendor-payments.md). Avec cette fonction, le champ **N° doc. référence** est toujours renseigné.  

- Imprimer des chèques et envoyer des paiements électroniques à votre banque

    Outre l'enregistrement du paiement, vous pouvez également utiliser la page **Journal paiement** pour générer le paiement à des fins de traitement par votre banque. Pour plus d'informations, voir [Effectuer des paiements par chèque](payables-how-work-checks.md) et [Effectuer des paiements électroniques](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).  

## <a name="to-make-payments-in-the-payment-journal"></a>Pour effectuer des paiements dans le journal paiement

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journaux paiement**, puis sélectionnez le lien associé.
2. Ouvrez le lot journal dédié aux paiements.
3. Si vous savez qui payer ou rembourser, renseignez les champs manuellement. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Pour affecter également le paiement à la facture ou la note de crédit associée, sélectionnez le champ **N° doc. référence**, sur la page **Affecter écritures fournisseur**, sélectionnez la facture ou la note de crédit appropriée, puis cliquez sur le bouton **OK**.

    De nombreux champs, tels que **Montant du document** et **Date d'échéance**, sont maintenant renseignés avec les informations du document sélectionné.
5. Sinon, utilisez la fonction **Proposer paiements fournisseur**. Tous les montants et informations de référence sont également saisis sur les lignes journal. Pour plus d'informations, reportez vous à [Proposer des paiements fournisseur](payables-how-suggest-vendor-payments.md).

    Les messages vous aident à renseigner correctement les champs obligatoires.
6.  Lorsque toutes les lignes journal des paiements sont renseignées, cliquez sur **Reporter**.

## <a name="see-also"></a>Voir aussi
[Effectuer des paiements par chèque](payables-how-work-checks.md)  
[Effectuer des paiements électroniques](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Paramétrage des opérations bancaires](bank-setup-banking.md)  
[Exporter un fichier Positive Pay](finance-how-positive-pay.md)  
[Utilisation de journaux généraux](ui-work-general-journals.md)  
[Personnaliser votre espace de travail](ui-personalization-user.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]