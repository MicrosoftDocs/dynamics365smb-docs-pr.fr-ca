---
title: "Annuler un report en reportant une écriture de contrepassation | Microsoft Docs"
description: "Si vous avez effectué une erreur de report dans le journal général, vous pouvez utiliser la fonction Inverser la transaction pour annuler le report avec une piste d'audit correcte."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reimbursement
ms.date: 08/03/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 802171d4f421270cb7e9b4f9dfedec9b9fe5ddc6
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-reverse-postings"></a>Procédure : inverser des reports
Pour annuler un report journal erroné, sélectionnez l'écriture et créez une écriture inverse (écritures identiques aux écritures originales mais avec le signe opposé dans le champ de montant) portant les mêmes numéro de document et date de report que l'écriture d'origine. Une fois l'écriture inversée, créez l'écriture correcte.

Vous pouvez uniquement inverser les écritures reportées à partir d'une ligne journal général. Une écriture ne peut être inversée qu'une seule fois.

Pour plus d'informations sur la validation d'une feuille comptabilité, voir [Procédure : Valider les transactions directement vers la comptabilité](finance-how-post-transactions-directly.md).

Si vous avez effectué un report de quantité négatif incorrect, comme un bon de commande avec, par exemple, un nombre d'articles incorrect et que vous l'avez reporté comme étant reçu (mais non facturé), vous pouvez annuler ce report.

Si vous avez effectué un report de quantité positif incorrect, comme un retour commande achat avec, par exemple, un nombre d'articles incorrect et que vous l'avez reporté comme étant livré (mais non facturé), vous pouvez annuler ce report.   

## <a name="to-reverse-the-journal-posting-of-a-general-ledger-entry"></a>Pour inverser le report journal d'une écriture grand livre
Vous pouvez inverser des écritures dans toutes les fenêtres **Écritures comptables**. La procédure suivante se base sur la fenêtre **Écritures comptables**.
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ecritures comptables**, puis sélectionnez le lien connexe.
2. Sélectionnez l'écriture à contrepasser, puis cliquez sur l'action **Contrepasser la transaction**. Notez qu'elle doit provenir d'un report journal.
3. Dans la fenêtre **Contrepasser les écritures de transaction**, sélectionnez l'écriture voulue, puis sélectionnez l'action **Contrepasser**.
4. Choisissez le bouton **Oui** dans le message de confirmation.

## <a name="to-undo-a-quantity-posting-on-a-posted-purchase-receipt"></a>Pour annuler un report de quantité sur une réception d'achat reportée  

1.  Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Réceptions achat reportées**, puis sélectionnez le lien associé.  
2.  Ouvrez la réception reportée à annuler.  
3.  Sélectionnez la ligne ou les lignes à annuler.  
4.  Choisissez l'action **Annuler réception**.

    Une ligne de correction est insérée sous la ligne de la réception sélectionnée.  

    Si la quantité a été reçue dans une réception entrepôt, une ligne de correction est insérée dans la réception entrepôt reportée.  

    Les champs **Quantité reçue** et **Qté reçue non facturée** de la commande achat associée sont remis à zéro.

## <a name="to-undo-and-then-redo-a-quantity-posting-on-a-posted-return-shipment"></a>Pour annuler, puis effectuer à nouveau le report de quantité sur une livraison retour reportée

1.  Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Livraisons de retour reportées**, puis sélectionnez le lien associé.  
2.  Ouvrez la livraison de retour reportée à annuler.
3. Sélectionnez la ligne ou les lignes à annuler.  

4.  Choisissez l'action **Annuler livraison retour**.  

    Une ligne de correction est insérée dans le document reporté et les champs **Qté retour livrée** et **Livraison retour non facturée** du retour sont remis à zéro.  

    Retournez à présent au retour achat pour un nouveau report.  

5.  Dans la fenêtre **Livraison retour reportée**, notez le numéro situé dans le champ **N° retour** .  
6.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Retours achat**, puis sélectionnez le lien associé.  
7.  Ouvrez la commande retour concernée, puis sélectionnez l'action **Rouvrir**.  
8.  Corrigez l'écriture dans le champ **Quantité** et reportez à nouveau le retour achat.  

## <a name="see-also"></a>Voir aussi
[Procédure : Valider les transactions directement vers la comptabilité](finance-how-post-transactions-directly.md)  
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)  
[Finances](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

