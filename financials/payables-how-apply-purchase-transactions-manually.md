---
title: Rapprocher les paiements fournisseur manuellement| Microsoft Docs
description: "Pour traiter, mettre en correspondance ou rapprocher des paiements ou des remboursements fournisseur manuellement, vous affectez le montant à une ou plusieurs écritures fournisseur ouvertes."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment application, payment processing, match payments
ms.date: 06/06/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 6f0f3e1c14e21fff736b54b4c5f7423e1e909e72
ms.contentlocale: fr-ca
ms.lasthandoff: 07/07/2017


---
# <a name="how-to-reconcile-vendor-payments-manually"></a>Procédure : rapprocher les paiements fournisseur manuellement
Lorsque vous envoyez un règlement à un fournisseur ou recevez un remboursement de sa part, vous devez décider si vous souhaitez affecter le paiement ou le rembourser à une ou plusieurs écritures ouvertes. Vous pouvez indiquer le montant exact que vous souhaitez affecter à la réception paiement ou au remboursement, puis n'affecter que partiellement les écritures fournisseur. Vous devez affecter toutes les écritures fournisseur pour obtenir des rapports et statistiques fournisseur corrects des relevés de compte et des frais financiers.

> [!NOTE]  
>   Les fournisseurs préfèrent parfois procéder à un remboursement plutôt que de créer une note de crédit déductible des prochaines factures, notamment si vous renvoyez des articles que vous avez déjà payés ou si vous avez versé un montant trop élevé pour une facture.

Vous pouvez affecter les écritures fournisseur de trois manières différentes :

* En entrant des informations dans les fenêtres dédiées, telles que la fenêtre **Feuille paiement** et la fenêtre **Feuille rapprochement bancaire**.
* À partir des documents note de crédit achat.
* À partir des écritures fournisseur une fois que les documents achat sont reportés mais non affectés.

> [!NOTE]  
>   Si le champ **Mode de lettrage** de la fiche fournisseur contient **Au plus ancien**, les paiements sont automatiquement lettrés avec l'écriture de crédit ouverte la plus ancienne si vous ne spécifiez pas avec quelle écriture lettrer. Si le mode de lettrage pour un client est **Manuel**, vous devez lettrer les écritures manuellement.

Vous pouvez lettrer les paiements fournisseur manuellement à leurs documents achat associés lorsque vous validez les paiements dans la fenêtre **Feuille paiement**. Pour plus d'informations sur comment renseigner la feuille paiement, reportez-vous à [Procédure : exécuter les paiements](payables-make-payments.md).

Vous pouvez également affecter des paiements fournisseur et des paiements client après que les paiements apparaissent en tant que transactions bancaires négatives au niveau de votre banque. Dans la fenêtre **Feuille rapprochement bancaire**, vous pouvez utiliser les fonctions pour l'importation de relevés bancaires, le lettrage automatique, et le rapprochement bancaire. Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md).

## <a name="to-apply-a-payment-to-a-single-or-multiple-vendor-ledger-entries"></a>Pour affecter un paiement à une seule ou à plusieurs écritures fournisseur
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille paiement**, puis sélectionnez le lien connexe.
2. Dans la fenêtre **Feuille paiement**, dans la première ligne feuille, saisissez les informations appropriées sur l'écriture règlement.
3. Pour affecter une seule écriture fournisseur :
   1. Dans le champ **N° doc. lettrage**, sélectionnez le champ permettant d'ouvrir la fenêtre **Lettrer écritures fournisseur**.
   2. Dans la fenêtre **Lettrer écritures fournisseur**, sélectionnez l'écriture à laquelle lettrer le paiement.
   3. Sur la ligne du champ **Montant à lettrer**, entrez le montant à lettrer à l'écriture.
4. Ou, pour affecter plusieurs écritures fournisseur :

   1. Sélectionnez l'action **Lettrer écritures**.
   2. Dans la fenêtre **Lettrer écritures fournisseur**, sélectionnez les lignes contenant les écritures auxquelles lettrer le paiement.
   3. Sélectionnez l'action **Lettrer**.  
   4. Sur chaque ligne du champ **Montant à lettrer**, entrez le montant à lettrer à l'écriture.

      Si vous n'entrez aucun montant, le programme affecte automatiquement le montant maximal. Au bas de la fenêtre **Lettrer écritures fournisseur**, vous voyez le montant dans le champ Montant lettré et vous constatez si le lettrage est équilibré.
5. Cliquez sur le bouton **OK**.
6. Sélectionnez l'action **Valider** pour valider la feuille paiement.

## <a name="to-apply-a-credit-memo-to-a-single-or-multiple-vendor-ledger-entries"></a>Pour affecter une note de crédit à une seule ou à plusieurs écritures fournisseur
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille paiement**, puis sélectionnez le lien connexe.
2. Ouvrez la note de crédit à affecter.
3. Entrez les informations nécessaires dans l'en-tête.
4. Pour lettrer une seule écriture comptable fournisseur, sur le raccourci **Application**, dans le champ **N° doc. lettrage** sélectionnez l'écriture à laquelle appliquer le crédit, puis, dans le champ **Montant à lettrer**, entrez le montant à lettrer avec l'écriture.
5. Ou, pour affecter plusieurs écritures fournisseur :

   1. Sélectionnez l'action **Lettrer écritures**.
   2. Sélectionnez les lignes contenant les écritures auxquelles affecter la note de crédit.
   3. Sélectionnez l'action **Lettrer**.  
   4. Sur chaque ligne du champ **Montant à lettrer**, entrez le montant à lettrer à l'écriture.

       Si vous n'entrez aucun montant, le programme affecte automatiquement le montant maximal. Au bas de la fenêtre **Lettrer écritures fournisseur**, vous voyez le montant dans le champ **Montant lettré** et vous constatez si le lettrage est équilibré.
6. Cliquez sur le bouton **OK**.  
   La fenêtre **Avoir achat** affiche l'écriture que vous avez sélectionnée dans les champs **Type doc. lettrage** et **N° doc. lettrage** . La fenêtre affiche également le montant de la note de crédit à reporter, escomptes de paiement éventuels déduits.
7. Cliquez sur le bouton **Valider** pour valider l'avoir achat.

## <a name="to-apply-posted-vendor-ledger-entries"></a>Pour affecter des écritures fournisseur reportées
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Comptes bancaires**, puis sélectionnez le lien connexe.
2. Ouvrez le fournisseur approprié possédant des écritures déjà reportées.
3. Sélectionnez l'action **Écritures comptables**, puis sélectionnez l'action **Lettrer écritures**.
4. Dans la fenêtre **Lettrer écritures fournisseur**, les écritures ouvertes de ce fournisseur s'affichent.
5. Sélectionnez la ligne où figure l'écriture qui sera affectée.
6. Sélectionnez l'action **Lettrer**.

    Le champ **ID lettrage** affiche trois astérisques si vous travaillez dans un système mono-utilisateur ou votre code utilisateur si vous travaillez dans un système multi-utilisateur.  
7. Pour chaque ligne du champ **Montant à lettrer**, entrez le montant à lettrer à l'écriture.

    Si vous n'entrez aucun montant, le programme affecte automatiquement le montant maximal. Vous pouvez voir le montant dans le champ **Montant lettré** au bas de la fenêtre **Lettrer écritures fournisseur**.
8. Sélectionnez l'action **Valider le lettrage**.  

    La fenêtre **Valider le lettrage** s'ouvre et affiche le numéro de document de l'écriture lettrage et la date comptabilisation de l'écriture ayant la date comptabilisation la plus récente.
9. Cliquez sur **OK** pour valider le lettrage.

## <a name="to-apply-vendor-ledger-entries-in-different-currencies-to-one-another"></a>Pour affecter des écritures fournisseur en devises différentes à une autre
Si vous achetez des produits auprès d'un fournisseur dans une devise et que vous effectuez le paiement dans une autre devise, vous pouvez tout de même affecter la facture au paiement.

Si vous affectez une écriture (Écriture 1) dans une devise à une autre écriture (Écriture 2) dont la devise est différente, la date de report de l'Écriture 1 est utilisée pour trouver le taux de change adéquat et convertir les montants de l'Écriture 2. Le taux de change approprié se trouve dans la fenêtre **Taux de change devise**. Dans ce cas, vous devez activer l'affectation des écritures fournisseur en devises différentes. Pour plus d'informations, reportez-vous à [Procédure : activer le lettrage d'écritures comptables client en devises différentes](finance-how-enable-application-ledger-entries-different-currencies.md)

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille paiement**, puis sélectionnez le lien connexe.
2. Ouvrez le journal que vous souhaitez, puis renseignez la première ligne vide du journal à l'aide d'un code devise.
3. Sélectionnez l'action **Lettrer écritures**.
4. Sélectionnez la ligne comportant l'écriture à lettrer avec l'écriture de la feuille paiement. Sélectionnez ensuite l'action **Lettrer**, puis sélectionnez l'écriture sur laquelle le lettrage doit être effectué.
5. Cliquez sur le bouton **OK** pour revenir à la feuille de paiement.
6. Reportez le journal des paiements.

> [!IMPORTANT]  
>   Lorsque vous affectez des écritures les unes aux autres dans des devises différentes, les écritures sont converties en USD. Bien que le taux de change des deux devises concernées soit fixe, comme entre le USD et l'EUR, la conversion de ces montants en devise en une somme en USD peut donner un petit montant résiduel. Le programme valide ces petits montants résiduels en tant que gains et pertes dans le compte défini dans le champ **Cpte gains constatés report** ou **Cpte pertes constatées report** de la fenêtre **Devises**. La valeur du champ **Montant (USD)** est également ajustée sur les écritures comptables fournisseur concernées.

## <a name="to-unapply-an-application-of-vendor-entries"></a>Pour annuler l'affectation des écritures fournisseur
Lorsque vous annulez une affectation erronée, des écritures de correction (écritures identiques à l'écriture originale mais avec le signe opposé dans le champ du montant) sont créées et reportées pour toutes les écritures comportant des reports comptables issus de l'affectation, comme les escomptes de paiement et les pertes et gains en devise. Les écritures qui sont fermées par l'affectation sont rouvertes.

1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Comptes bancaires**, puis sélectionnez le lien connexe.
2. Ouvrez la fiche fournisseur appropriée.
3. Sélectionnez l'action **Écritures comptables**.
4. Sélectionnez l'écriture comptable appropriée, puis sélectionnez l'action **Délettrer les écritures**.
5. Sinon, sélectionnez l'action **Écritures comptables détaillées**.
6. Sélectionnez l'écriture de lettrage appropriée, puis sélectionnez l'action **Délettrer les écritures**.
7. Renseignez les champs de l'en-tête, puis sélectionnez l'action **Délettrer**.

> [!IMPORTANT]  
>   Si une écriture a été affectée par plusieurs écritures d'affectation, vous devez commencer par annuler l'affectation de la dernière écriture.

## <a name="see-also"></a>Voir aussi
[Fournisseurs](payables-manage-payables.md)  
[Achats](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

