---
title: Rapprocher des paiements fournisseur avec le journal paiement ou à partir des écritures fournisseur | Microsoft Docs
description: Pour traiter, mettre en correspondance ou rapprocher des paiements ou des remboursements fournisseur manuellement, vous affectez le montant à une ou plusieurs écritures fournisseur ouvertes.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment application, payment processing, match payments
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: b981a0062c628f3ffe3b0de8eaf4c811a13632ec
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3916836"
---
# <a name="reconcile-vendor-payments-with-the-payment-journal-or-from-vendor-ledger-entries"></a>Rapprocher des paiements fournisseur avec le journal paiement ou à partir des écritures fournisseur
Lorsque vous envoyez un règlement à un fournisseur ou recevez un remboursement de sa part, vous devez décider si vous souhaitez affecter le paiement ou le rembourser à une ou plusieurs écritures ouvertes. Vous pouvez indiquer le montant exact que vous souhaitez affecter à la réception paiement ou au remboursement, puis n'affecter que partiellement les écritures fournisseur. Vous devez affecter toutes les écritures fournisseur pour obtenir des rapports et statistiques fournisseur corrects des relevés de compte et des frais financiers.

> [!NOTE]  
>   Les fournisseurs préfèrent parfois procéder à un remboursement plutôt que de créer une note de crédit déductible des prochaines factures, notamment si vous renvoyez des articles que vous avez déjà payés ou si vous avez versé un montant trop élevé pour une facture.

Vous pouvez affecter les écritures fournisseur de trois manières différentes :

* En entrant des informations sur les pages dédiées, telles que la page **Journal paiement** et la page **Journal rapprochement paiement** .
* À partir des documents note de crédit achat.
* À partir des écritures fournisseur une fois que les documents achat sont reportés mais non affectés.

> [!NOTE]  
>   Si le champ **Mode de lettrage** de la fiche fournisseur contient **Au plus ancien** , les paiements sont automatiquement lettrés avec l'écriture de crédit ouverte la plus ancienne si vous ne spécifiez pas avec quelle écriture lettrer. Si le mode de lettrage pour un client est **Manuel** , vous devez lettrer les écritures manuellement.

Vous pouvez affecter les paiements fournisseur manuellement à leurs documents achat associés lorsque vous reportez les paiements sur la page **Journal paiement** . Pour plus d'informations sur la manière de renseigner le journal paiement, reportez-vous à [Effectuer des paiements](payables-make-payments.md).

Vous pouvez également affecter des paiements fournisseur et des paiements client après que les paiements apparaissent en tant que transactions bancaires négatives dans votre banque. Sur la page **Journal rapprochement paiement** , vous pouvez utiliser les fonctions pour l'importation de relevés bancaires, l'affectation automatique et le rapprochement de comptes bancaires. Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md).

## <a name="to-apply-a-payment-to-a-single-or-multiple-vendor-ledger-entries"></a>Pour affecter un paiement à une seule ou à plusieurs écritures fournisseur
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal paiement** , puis sélectionnez le lien associé.
2. Sur la page **Journal paiement** , dans la première ligne journal, saisissez les informations appropriées sur l'écriture paiement.
3. Pour affecter une seule écriture fournisseur :
   1. Dans le champ **N° doc. référence** , sélectionnez le champ permettant d'ouvrir la page **Affecter écritures fournisseur** .
   2. Sur la page **Affecter écritures fournisseur** , sélectionnez l'écriture à laquelle affecter le paiement.
   3. Sur la ligne du champ **Montant à lettrer** , entrez le montant à lettrer à l'écriture.
4. Ou, pour affecter plusieurs écritures fournisseur :

   1. Sélectionnez l'action **Lettrer écritures** .
   2. Sur la page **Affecter écritures fournisseur** , sélectionnez les lignes contenant les écritures auxquelles affecter le paiement.
   3. Sélectionnez l'action **Lettrer** .  
   4. Sur chaque ligne du champ **Montant à lettrer** , entrez le montant à lettrer à l'écriture.

      Si vous n'entrez aucun montant, le programme affecte automatiquement le montant maximal. Au bas de la page **Affecter écritures fournisseur** , vous voyez le montant dans le champ Montant affecté et vous constatez si l'affectation est équilibrés.
5. Cliquez sur le bouton **OK** .
6. Sélectionnez l'action **Valider** pour valider la feuille paiement.

## <a name="to-apply-a-credit-memo-to-a-single-or-multiple-vendor-ledger-entries"></a>Pour affecter une note de crédit à une seule ou à plusieurs écritures fournisseur
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Note de crédit achat** , puis sélectionnez le lien associé.
2. Ouvrez la note de crédit à affecter.
3. Entrez les informations nécessaires dans l'en-tête.
4. Pour affecter une seule écriture fournisseur, dans le raccourci **Affectation** , dans le champ **N° doc. affecté à** , sélectionnez l'écriture à laquelle affecter le crédit puis, dans le champ **Montant à affecter** , entrez le montant à affecter à l'écriture.
5. Ou, pour affecter plusieurs écritures fournisseur :

   1. Sélectionnez l'action **Lettrer écritures** .
   2. Sélectionnez les lignes contenant les écritures auxquelles affecter la note de crédit.
   3. Sélectionnez l'action **Lettrer** .  
   4. Sur chaque ligne du champ **Montant à lettrer** , entrez le montant à lettrer à l'écriture.

       Si vous n'entrez aucun montant, le programme affecte automatiquement le montant maximal. Au bas de la page **Affecter écritures fournisseur** , vous voyez le montant dans le champ **Montant affecté** et vous constatez si l'affectation est équilibrée.
6. Cliquez sur le bouton **OK** .  
   La page **Note de crédit achat** affiche l'écriture que vous avez sélectionnée dans les champs **Type doc. référence** et **N° doc. référence** . La page affiche également le montant de la note de crédit à reporter, escomptes de paiement éventuels déduits.
7. Cliquez sur le bouton **Valider** pour valider l'avoir achat.

## <a name="to-apply-posted-vendor-ledger-entries"></a>Pour affecter des écritures fournisseur reportées
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Fournisseurs** , puis sélectionnez le lien associé.
2. Ouvrez le fournisseur approprié possédant des écritures déjà reportées.
3. Sélectionnez l'action **Écritures comptables** , puis sélectionnez l'action **Lettrer écritures** .
4. Sur la page **Affecter écritures fournisseur** , les écritures ouvertes de ce fournisseur s'affichent.
5. Sélectionnez la ligne où figure l'écriture qui sera affectée.
6. Sélectionnez l'action **Lettrer** .

    Le champ **ID lettrage** affiche trois astérisques si vous travaillez dans un système mono-utilisateur ou votre code utilisateur si vous travaillez dans un système multi-utilisateur.  
7. Pour chaque ligne du champ **Montant à lettrer** , entrez le montant à lettrer à l'écriture.

    Si vous n'entrez aucun montant, le programme affecte automatiquement le montant maximal. Vous pouvez voir le montant dans le champ **Montant affecté** au bas de la page **Affecter écritures fournisseur** .
8. Sélectionnez l'action **Valider le lettrage** .  

    La page **Reporter l'affectation** s'ouvre avec le numéro de document de l'écriture affectation et la date de report de l'écriture ayant la date de report la plus récente.
9. Cliquez sur **OK** pour valider le lettrage.

## <a name="to-apply-vendor-ledger-entries-in-different-currencies-to-one-another"></a>Pour affecter des écritures fournisseur en devises différentes à une autre
Si vous achetez des produits auprès d'un fournisseur dans une devise et que vous effectuez le paiement dans une autre devise, vous pouvez tout de même affecter la facture au paiement.

Si vous affectez une écriture (Écriture 1) dans une devise à une autre écriture (Écriture 2) dont la devise est différente, la date de report de l'Écriture 1 est utilisée pour trouver le taux de change adéquat et convertir les montants de l'Écriture 2. Le taux de change approprié se trouve sur la page **Taux de change devise** . Dans ce cas, vous devez activer l'affectation des écritures fournisseur en devises différentes. Pour plus d'informations, voir [Activer l'affectation d'écritures en différentes devises](finance-how-enable-application-ledger-entries-different-currencies.md)

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal paiement** , puis sélectionnez le lien associé.
2. Ouvrez le journal que vous souhaitez, puis renseignez la première ligne vide du journal à l'aide d'un code devise.
3. Sélectionnez l'action **Lettrer écritures** .
4. Sélectionnez la ligne comportant l'écriture à lettrer avec l'écriture de la feuille paiement. Sélectionnez ensuite l'action **Lettrer** , puis sélectionnez l'écriture sur laquelle le lettrage doit être effectué.
5. Cliquez sur le bouton **OK** pour revenir à la feuille de paiement.
6. Reportez le journal des paiements.

> [!IMPORTANT]  
>   Lorsque vous affectez des écritures les unes aux autres dans des devises différentes, les écritures sont converties en USD. Bien que le taux de change des deux devises concernées soit fixe, comme entre le USD et l'EUR, la conversion de ces montants en devise en une somme en USD peut donner un petit montant résiduel. Le programme reporte ces petits montants résiduels en tant que gains et pertes dans le compte défini dans les champs **Cpte gains constatés report** ou **Cpte pertes constatées report** de la page **Devises** . La valeur du champ **Montant (USD)** est également ajustée sur les écritures comptables fournisseur concernées.

## <a name="to-unapply-an-application-of-vendor-entries"></a>Pour annuler l'affectation des écritures fournisseur
Lorsque vous annulez une affectation erronée, des écritures de correction (écritures identiques à l'écriture originale mais avec le signe opposé dans le champ du montant) sont créées et reportées pour toutes les écritures comportant des reports comptables issus de l'affectation, comme les escomptes de paiement et les pertes et gains en devise. Les écritures qui sont fermées par l'affectation sont rouvertes.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Fournisseurs** , puis sélectionnez le lien associé.
2. Ouvrez la fiche fournisseur appropriée.
3. Sélectionnez l'action **Écritures comptables** .
4. Sélectionnez l'écriture comptable appropriée, puis sélectionnez l'action **Délettrer les écritures** .
5. Sinon, sélectionnez l'action **Écritures comptables détaillées** .
6. Sélectionnez l'écriture de lettrage appropriée, puis sélectionnez l'action **Délettrer les écritures** .
7. Renseignez les champs de l'en-tête, puis sélectionnez l'action **Délettrer** .

> [!IMPORTANT]  
>   Si une écriture a été affectée par plusieurs écritures d'affectation, vous devez commencer par annuler l'affectation de la dernière écriture.

## <a name="see-also"></a>Voir aussi
[Fournisseurs](payables-manage-payables.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
