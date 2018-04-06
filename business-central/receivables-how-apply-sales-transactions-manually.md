---
title: "Affecter des écritures client pour rapprocher les paiements | Microsoft Docs"
description: "Décrit comment affecter des règlements ou des remboursements client dans une ou plusieurs écritures client ouvertes et rapprocher des paiements client."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, cash receipt
ms.date: 09/08/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: f514f05f5333bc8f2b473c50324e267d19c70d6f
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="reconcile-customer-payments-manually"></a>Rapprocher les paiements client manuellement
Lorsque vous recevez un paiement en liquide d'un client ou que vous effectuez un remboursement en liquide, vous devez décider si vous souhaitez affecter le paiement ou le remboursement pour fermer une ou plusieurs écritures débit ou crédit ouvertes. Vous pouvez indiquer le montant que vous souhaitez affecter. Par exemple, vous pouvez affecter des paiements partiels à des écritures client. La fermeture des écritures client permet de garantir que des informations telles que les statistiques clients, les relevés de compte bancaire et les frais financiers sont corrects.

> [!NOTE]  
>   Dans la fenêtre **Écritures comptables client**, le rouge signifie que le paiement associé a dépassé sa date d'échéance.

Vous pouvez affecter les écritures client de plusieurs manières :

* En entrant des informations dans les fenêtres dédiées, telles que la fenêtre **Feuille règlement** et la fenêtre **Feuille rapprochement bancaire**.
* À partir des documents note de crédit vente.
* À partir des écritures client une fois que les documents vente sont reportés mais non affectés.

> [!NOTE]  
>   Si le champ **Mode de lettrage** de la fiche client contient **Au plus ancien**, les paiements sont automatiquement lettrés avec l'écriture de crédit ouverte la plus ancienne sauf si vous spécifiez une écriture manuellement. Si le mode de lettrage pour un fournisseur est **Manuel**, vous devez toujours lettrer les écritures manuellement.

Vous pouvez lettrer les paiements des clients manuellement dans la fenêtre **Feuille règlement**. Un journal des encaissements est un type de journal général, de sorte que vous pouvez l'utiliser pour reporter des transactions sur des comptes GL, bancaires, client, fournisseur et immobilisations. Vous pouvez affecter le paiement à une ou plusieurs écritures débit lorsque vous reportez le paiement ou vous pouvez l'affecter à partir des écritures reportées ultérieurement.

Vous pouvez également lettrer les paiements client et fournisseur dans la fenêtre **Feuille rapprochement bancaire** à l'aide des fonctions dédiées à l'importation de relevés bancaires, le lettrage automatique et le rapprochement bancaire. Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md). Sinon, vous pouvez rapprocher les paiements client en fonction de la liste des documents vente échus dans la fenêtre **Enregistrement de paiement**. Pour plus d'informations, voir [Rapprocher les paiements client dans une liste des documents vente échus](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md)

## <a name="to-fill-and-post-a-cash-receipt-journal"></a>Pour renseigner et reporter un journal des encaissements
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille règlement**, puis sélectionnez le lien connexe.
2. Sélectionnez **Modifier journal**.
3. Sélectionnez le nom de traitement par lots souhaité dans le champ **Nom de la feuille**.
4. Renseignez le champ **Date comptabilisation**.  
5. Dans le champ **Type document**, sélectionnez **Paiement**.

    Le champ **N° document** contient les séries de numéros affectées au lot.  
6. Utilisez le champ **N° doc. externe** pour stocker un identificateur, tel que le numéro de chèque du client.
7. Dans le champ **Type compte**, sélectionnez **Client**.
8. Dans le champ **N° compte**, sélectionnez le compte du grand livre approprié.
9. Si vous souhaitez reporter l'affectation en même temps que le journal, suivez l'un des exemples ci-dessous.
10. Dans le champ **Type compte contrepartie**, sélectionnez **Compte général** pour les règlements et **Compte bancaire** pour les autres paiements.
11. Dans le champ **N° compte de contrepartie**, sélectionnez le compte caisse pour les paiements en espèces ou le compte bancaire approprié pour d'autres paiements.
12. Reportez le journal.

## <a name="to-apply-a-payment-to-a-single-customer-ledger-entry"></a>Pour affecter un paiement à une seule écriture client
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille règlement**, puis sélectionnez le lien connexe.
2. Sélectionnez **Modifier journal**.
3. Dans la première ligne journal, saisissez les informations appropriées sur l'écriture à affecter.
4. Dans le champ **Type document**, entrez **Paiement**.
5. Dans le champ **Type compte**, entrez **Client**.
6. Dans le champ **Type compte contrepartie**, entrez **Compte bancaire.**
7. Dans le champ **N° doc. affecté à**, sélectionnez le champ permettant d'ouvrir la fenêtre **Affecter écritures clients**.
8. Dans la fenêtre **Lettrer écritures client**, sélectionnez l'écriture à laquelle lettrer le paiement.
9. Dans le champ **Montant à lettrer**, entrez le montant à lettrer à l'écriture. Si vous n'entrez aucun montant, le montant maximal est affecté.

    Au bas de la fenêtre **Lettrer écritures client**, vous voyez le montant spécifique dans le champ **Montant lettré** et constatez si le lettrage est équilibré.  
10. Cliquez sur le bouton **OK**. La fenêtre **Journal des encaissements** affiche désormais l'écriture que vous avez saisie dans les champs **Type document affecté à** et **N° doc. affecté à**.
11. Reportez le journal des encaissements.

## <a name="to-apply-a-payment-to-multiple-customer-ledger-entries"></a>Pour affecter un paiement à plusieurs écritures client
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille règlement**, puis sélectionnez le lien connexe.
2. Sélectionnez **Modifier journal**.
3. Dans la première ligne journal, saisissez les informations appropriées sur l'écriture à affecter.
4. Dans le champ **Type document**, entrez **Paiement**.
5. Dans le champ **Type compte**, entrez **Client**.
6. Dans le champ **Type compte contrepartie**, entrez **Compte bancaire.**
7. Dans le champ **Montant**, entrez le paiement complet sous forme de montant négatif.
8. Pour lettrer le paiement avec plusieurs écritures comptables client lors de la validation, sélectionnez l'action **Lettrer écritures**.  
9. Sélectionnez les lignes correspondant aux écritures avec lesquelles l'écriture lettrage doit être lettrée, puis sélectionnez l'action **Lettrer**.  
10. Sur chaque ligne du champ **Montant à lettrer**, entrez le montant que vous souhaitez lettrer à l'écriture. Si vous n'entrez aucun montant, le montant maximal est affecté.

    Au bas de la fenêtre **Lettrer écritures client**, vous voyez le montant spécifique dans le champ **Montant lettré** et constatez si le lettrage est équilibré.  
11. Cliquez sur le bouton **OK**.
12. Reportez le journal des encaissements.

## <a name="to-apply-a-credit-memo-to-a-single-customer-ledger-entry"></a>Pour affecter une note de crédit à une seule écriture client
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille règlement**, puis sélectionnez le lien connexe.
2. Ouvrez la note de crédit vente souhaitée.
3. Pour affecter la note de crédit à une seule écriture client lors du report, dans le champ **N° doc. affecté à**, sélectionnez l'écriture à laquelle affecter le paiement.
4. Sur la ligne du champ **Montant à lettrer**, entrez le montant à lettrer avec l'écriture.  

    Si vous n'entrez aucun montant, le programme affecte automatiquement le montant maximal. Au bas de la fenêtre **Lettrer écritures client**, vous voyez le montant spécifique dans le champ **Montant lettré** et constatez si le lettrage est équilibré.    
5. Cliquez sur le bouton **OK**. La fenêtre **Note de crédit vente** affiche désormais l'écriture que vous avez saisie dans les champs **Type document affecté à** et **N° doc. affecté à**. Et le montant de la note de crédit à reporter, escomptes de paiement éventuels déduits.
6. Reportez la note de crédit.

## <a name="to-apply-a-credit-memo-to-multiple-customer-ledger-entries"></a>Pour affecter une note de crédit à plusieurs écritures client
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille règlement**, puis sélectionnez le lien connexe.
2. Ouvrez la note de crédit vente souhaitée.
3. Pour lettrer l'avoir avec plusieurs écritures comptables client lors de la validation, sélectionnez l'action **Lettrer écritures**.
4. Sélectionnez les lignes correspondant aux écritures avec lesquelles l'écriture lettrage doit être lettrée, puis sélectionnez l'action **Lettrer**.
5. Sur chaque ligne du champ **Montant à lettrer**, entrez le montant que vous souhaitez lettrer à l'écriture. Si vous n'entrez aucun montant, le montant maximal est affecté.  

    Au bas de la fenêtre **Lettrer écritures client**, vous voyez le montant spécifique dans le champ **Montant lettré** et constatez si le lettrage est équilibré.  
6. Cliquez sur le bouton **OK**. La fenêtre **Avoir vente** affiche désormais le montant de l'avoir à valider, escomptes éventuels déduits.
7. Reportez la note de crédit.

## <a name="to-apply-posted-customer-ledger-entries"></a>Pour affecter des écritures client reportées
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Clients**, puis sélectionnez le lien connexe.
2. Ouvrez la fiche du client possédant les écritures que vous souhaitez affecter.
3. Sélectionnez l'action **Écritures comptables**, puis sélectionnez la ligne où figure l'écriture qui sera l'écriture lettrage.
4. Sélectionnez l'action **Lettrer écritures**. La fenêtre **Lettrer écritures client** s'ouvre et affiche les écritures ouvertes de ce client.
5. Sélectionnez les lignes correspondant aux écritures avec lesquelles l'écriture lettrage doit être lettrée, puis sélectionnez l'action **Lettrer**.  
6. Pour chaque ligne du champ **Montant à lettrer**, entrez le montant que vous souhaitez lettrer à l'écriture. Si vous n'entrez aucun montant, le montant maximal est affecté.  

    Au bas de la fenêtre **Lettrer écritures client**, vous voyez le montant spécifique dans le champ **Montant lettré**.  
7. Sélectionnez l'action **Valider le lettrage**. La fenêtre **Valider le lettrage** s'ouvre et affiche le numéro de document de l'écriture lettrage et la date comptabilisation de l'écriture ayant la date comptabilisation la plus récente.  
8. Cliquez sur **OK** pour valider le lettrage.

    Si le lettrage validé génère des écritures comptables client lettrées, ces écritures comptables ne sont plus activées dans le champ **Ouvert**.    
9. Pour afficher les écritures comptables, choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Clients**, puis sélectionnez le lien connexe. Accédez à la fiche du client approprié pour afficher les écritures.  

Dans la liste écritures comptables, sur la ligne contenant l'écriture comptable totalement lettrée vous constatez que la case **Ouvert** n'est pas cochée.  

> [!NOTE]  
>   Une fois que vous avez sélectionné une écriture de la fenêtre **Lettrer écritures client**, ou plusieurs écritures avec l'**ID lettrage**, le champ **Montant lettré** de la ligne feuille contient la somme des montants restants des écritures validées que vous avez sélectionnées, cela à moins que le champ ne soit déjà renseigné. Si vous sélectionnez **Au plus ancien** dans le champ **Mode de lettrage** sur la fiche client, le lettrage intervient automatiquement.

## <a name="to-apply-customer-ledger-entries-in-different-currencies-to-one-another"></a>Pour affecter des écritures client en devises différentes à une autre
Si vous effectuez une vente à un client dans une devise et recevez le règlement dans une autre devise, vous pouvez toujours affecter la facture au paiement.  

Si vous affectez une écriture (Écriture 1) dans une devise à une autre écriture (Écriture 2) dont la devise est différente, la date de report de l'Écriture 1 est utilisée pour trouver le taux de change adéquat et convertir les montants de l'Écriture 2. Le taux de change approprié se trouve dans la fenêtre **Taux de change devise**.  

L'affectation d'écritures client en devises différentes doit être activée. Pour plus d'informations, voir [Activer l'affectation des écritures en devises différentes](finance-how-enable-application-ledger-entries-different-currencies.md).  

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille règlement**, puis sélectionnez le lien connexe.
2. Ouvrez le journal que vous souhaitez, puis renseignez la première ligne vide du journal à l'aide d'un code devise.
3. Sélectionnez l'action **Lettrer écritures**.
4. Sélectionnez la ligne comportant l'écriture à lettrer avec l'écriture de la feuille règlement. Sélectionnez ensuite l'action **Lettrer**, puis sélectionnez l'écriture sur laquelle le lettrage doit être effectué.
5. Cliquez sur le bouton **OK** pour revenir à la feuille règlement.
6. Reportez le journal ventes.  

> [!IMPORTANT]  
>   Lorsque vous affectez des écritures dans des devises différentes, les écritures sont converties en USD. Bien que le taux de change des deux devises concernées soit fixe, comme entre le USD et l'EUR, leur conversion en USD peut donner un petit montant résiduel. Le programme valide ces petits montants résiduels en tant que gains et pertes dans le compte défini dans les champs **Cpte gains constatés report** ou **Cpte pertes constatées report** de la fenêtre **Devises**. La valeur du champ **Montant (USD)** est également ajustée sur les écritures comptables fournisseur.  

## <a name="to-correct-an-application-of-customer-entries"></a>Pour corriger une affectation d'écritures
Lorsque vous corrigez une affectation, des écritures de correction (écritures identiques à l'écriture originale mais avec le signe opposé dans le champ du montant) sont créées et reportées pour toutes les écritures comportant des reports comptables issus de l'affectation, comme les escomptes de paiement et les pertes et gains en devise. Les écritures qui sont fermées par l'affectation sont rouvertes.  

1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Clients**, puis sélectionnez le lien connexe.
2. Ouvrez la fiche client appropriée.
3. Sélectionnez l'action **Écritures comptables**.
4. Sélectionnez l'écriture comptable appropriée, puis sélectionnez l'action **Délettrer les écritures**.
5. Sinon, sélectionnez l'action **Écritures comptables détaillées**.
6. Sélectionnez l'écriture de lettrage appropriée, puis sélectionnez l'action **Délettrer les écritures**.
7. Renseignez les champs de l'en-tête, puis sélectionnez l'action **Délettrer**.  

> [!IMPORTANT]  
>   Si une écriture a été affectée par plusieurs écritures d'affectation, vous devez commencer par annuler l'affectation de la dernière écriture.  

## <a name="see-also"></a>Voir aussi
[Gestion des comptes client](receivables-manage-receivables.md)  
[Ventes](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

