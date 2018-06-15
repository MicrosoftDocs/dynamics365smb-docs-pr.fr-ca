---
title: "Affecter des paiements à des documents connexes et les reporter | Microsoft Docs"
description: "Décrit comment enregistrer les paiements effectués aux fournisseurs et les remboursements effectués aux clients."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment journal, print check, vendor payment, customer refund, creditor, debt, balance due, AP
ms.date: 04/30/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 75501b9402bb1c14fcfeb2fc6e61f055a2247493
ms.openlocfilehash: 3cad699234d95a849bf48f04c8462afa968789f6
ms.contentlocale: fr-ca
ms.lasthandoff: 05/15/2018

---
# <a name="record-payments-and-refunds"></a>Enregistrer des paiements et des remboursements
Dans la fenêtre **Journal des paiements**, vous enregistrez les paiements effectués aux fournisseurs et les remboursements effectués aux clients. Lorsque vous reportez une ligne journal des paiements, le montant payé est enregistré sur le compte bancaire système spécifié. Vous devez ensuite effectuer des actions pour procéder au transfert d'argent réel à partir du compte bancaire associé.

Si vous renseignez le champ **N° doc. référence** avec la facture ou la note de crédit qui doit être payée ou remboursée, le document en question est défini sur Payé lorsque vous reportez le journal. C'est ce qu'on appelle « affecté ». Outre l'affectation lors du report du paiement, vous pouvez utiliser la fenêtre **Affecter écritures fournisseur** ou **Affecter écritures client** après avoir reporté le paiement. Pour plus d'informations, voir [Rapprocher les paiements fournisseur manuellement](payables-how-apply-purchase-transactions-manually.md), par exemple.

La fonction **Proposer paiements fournisseur** peut vous aider à renseigner automatiquement les lignes journal des paiements en fonction de la priorité des fournisseurs et des dates d'échéance. Pour plus d'informations, reportez vous à [Proposer des paiements fournisseur](payables-how-suggest-vendor-payments.md). Avec cette fonction, le champ **N° doc. référence** est toujours renseigné.

Outre l'enregistrement du paiement, vous pouvez également utiliser la fenêtre **Journal des paiements** pour générer le paiement à des fins de traitement par votre banque. Pour plus d'informations, voir [Effectuer des paiements par chèque](payables-how-work-checks.md) et [Effectuer des paiements électroniques](payables-how-export-payments-bank-file.md).  

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles paiement**, puis sélectionnez le lien connexe.
2. Ouvrez le lot journal dédié aux paiements.
3. Si vous savez qui payer ou rembourser, renseignez les champs manuellement. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Pour affecter également le paiement à la facture ou la note de crédit associée, sélectionnez le champ **N° doc. référence**, dans la fenêtre **Affecter écritures fournisseur**, sélectionnez la facture ou la note de crédit appropriée, puis cliquez sur le bouton **OK**.

    De nombreux champs, tels que **Montant** et **Date d'échéance**, sont maintenant renseignés avec les informations du document sélectionné.
5. Sinon, utilisez la fonction **Proposer paiements fournisseur**. Tous les montants et informations de référence sont également saisis sur les lignes journal. Pour plus d'informations, reportez vous à [Proposer des paiements fournisseur](payables-how-suggest-vendor-payments.md).

    Les messages vous aident à renseigner correctement les champs obligatoires.
6.  Lorsque toutes les lignes journal des paiements sont renseignées, cliquez sur **Reporter**.

## <a name="see-also"></a>Voir aussi
[Effectuer des paiements par chèque](payables-how-work-checks.md)  
[Effectuer des paiements électroniques](payables-how-export-payments-bank-file.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Paramétrage des opérations bancaires](bank-setup-banking.md)  
[Exporter un fichier Positive Pay](finance-how-positive-pay.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

